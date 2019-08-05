---
title: Configurare il servizio cloud Voicemail per gli utenti locali
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per l'implementazione della segreteria telefonica basata su cloud per gli utenti residenti in Skype for Business Server.
ms.openlocfilehash: 99fc250ff4c01a0b51e784c165edb99cbb867b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185468"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurare il servizio cloud Voicemail per gli utenti locali

## <a name="overview"></a>Panoramica 
Questo articolo descrive come configurare il servizio Microsoft Cloud Voicemail per gli utenti locali di Skype for business.  

Questo articolo presuppone che si disponga già di Skype for Business Server distribuito in una topologia supportata e che siano stati soddisfatti i prerequisiti per la configurazione della connettività ibrida.

Per altre informazioni sui vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione della segreteria telefonica cloud, vedere [pianificare il servizio di segreteria telefonica cloud](plan-cloud-voicemail.md).




La configurazione della segreteria telefonica Cloud include le attività seguenti:

1.  Verificare di avere soddisfatto i prerequisiti come descritto in [servizio cloud Voicemail](plan-cloud-voicemail.md).

2.  Verificare di aver configurato la connettività ibrida come descritto in [pianificare](plan-hybrid-connectivity.md) la connettività ibrida e [configurare la connettività ibrida](configure-hybrid-connectivity.md). 

3.  [Configurare la segreteria telefonica cloud come provider di hosting nell'Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) come descritto in questo articolo.

4.  [Configurare un criterio per la segreteria telefonica ospitata](#configure-a-hosted-voicemail-policy) come descritto in questo articolo.

5.  [Assegnare un criterio per la segreteria telefonica ospitata](#assign-a-hosted-voicemail-policy) come descritto in questo articolo.

6.  [Abilitare un utente per la segreteria telefonica cloud](#enable-a-user-for-cloud-voicemail) come descritto in questo articolo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configurare la segreteria telefonica cloud come provider di hosting nell'Edge Server 

È possibile configurare la segreteria telefonica cloud come provider di hosting in un server front-end usando il cmdlet New-CsHostingProvider con i parametri seguenti:

- **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare. ad esempio, cloud Voicemail. 

- **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Questo parametro deve essere impostato su true.

- **EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso. Questo parametro deve essere impostato su true.

- **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di Skype for Business Server. Questo parametro deve essere impostato su false.

- **ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting. ad esempio, proxyserver.contoso.com. Contattare il provider di hosting per queste informazioni. Questo valore non può essere modificato. Se il provider di hosting modifica il proprio server proxy, sarà necessario eliminarlo e ricrearlo.

- La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Skype for Business Server. Questo parametro deve essere impostato su false.

Ad esempio, in Skype for Business Management Shell, il cmdlet seguente configura il cloud Voicemail come provider di hosting:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurare un criterio per la segreteria telefonica ospitata

Per assicurarsi che la segreteria telefonica per l'organizzazione venga instradata al servizio cloud voicemail, è necessario configurare un criterio per la segreteria telefonica ospitata per l'organizzazione. In molti casi è necessario un solo criterio per la segreteria telefonica ospitata ed è possibile modificare il criterio globale in base a tutte le esigenze. Se l'organizzazione richiede più criteri per la segreteria telefonica ospitata, è possibile aggiungere criteri usando il cmdlet New-CsHostedVoicemailPolicy.

Per modificare il criterio globale, eseguire il comando seguente in Skype for Business Server Management Shell dopo l'aggiornamento dell'organizzazione e ID tenant:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Destinazione** specifica il nome di dominio completo (FQDN) del servizio di segreteria telefonica ospitata. Questo valore deve essere impostato su **exap.um.Outlook.com**.

- **Organizzazione** è il dominio predefinito assegnato al tenant. Per recuperare queste informazioni, è possibile che l'amministratore del tenant acceda a office.com, fare clic sull'app dell'interfaccia di amministrazione, passare a **configurazione** a sinistra e fare clic su **domini**. Ad esempio: mytenant.onmicrosoft.com.

    Il nome dell'organizzazione è anche il nome di dominio predefinito in Office 365.

- **ID tenant** viene usato per identificare il tenant in Office 365. Per altre informazioni, vedere [trovare l'ID tenant di Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Per assicurarsi che sia stato creato correttamente un criterio di segreteria telefonica ospitata, eseguire il comando seguente:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Assegnare un criterio per la segreteria telefonica ospitata

Per impostazione predefinita, il criterio della segreteria telefonica ospitata globale viene assegnato a tutti gli utenti. Se usi un criterio diverso, prima di abilitare gli utenti per la segreteria telefonica ospitata, devi prima concedere agli utenti i criteri desiderati per la segreteria telefonica ospitata usando il cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Ad esempio, con il comando seguente viene assegnato un criterio di segreteria telefonica ospitata non globale a un utente:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Abilitare un utente per la segreteria telefonica cloud

Per consentire alle chiamate vocali dell'utente di essere instradate alla segreteria telefonica cloud, puoi usare il cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con il parametro HostedVoiceMail. 

Ad esempio, il comando seguente abilita un account utente per la segreteria telefonica cloud: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

Il cmdlet verifica che un criterio per la segreteria telefonica cloud, a livello globale, del sito o dell'utente, si applichi a questo utente. Se non viene applicato alcun criterio, il cmdlet non riesce.  

Nell'esempio seguente viene disabilitato un account utente per la segreteria telefonica cloud:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

Il cmdlet verifica che nessun criterio per la segreteria telefonica ospitata, a livello globale, del sito o dell'utente, si applichi a questo utente. Se un criterio si applica, il cmdlet non riesce.

> [!NOTE]
>  Gli utenti devono essere abilitati a Enterprise-Voice per usare il servizio Microsoft Cloud Voicemail.
