---
title: Configurare il servizio di segreteria cloud per gli utenti locali
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per l'implementazione della segreteria telefonica basata su cloud per gli utenti ospitati in Skype for Business Server.
ms.openlocfilehash: 4542207beb3ccd090c1215a8832f53b3ab08ed97
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288714"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurare il servizio di segreteria cloud per gli utenti locali

## <a name="overview"></a>Panoramica 
In questo articolo viene descritto come configurare il servizio segreteria telefonica Microsoft Cloud per gli utenti locali di Skype for business.  

In questo articolo si presuppone che sia già stato distribuito Skype for Business Server in una topologia supportata e che siano stati soddisfatti i prerequisiti per la configurazione della connettività ibrida.

Per ulteriori informazioni sui vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio di segreteria cloud, vedere [Plan cloud Voicemail Service](plan-cloud-voicemail.md).




La configurazione del messaggio vocale cloud prevede le attività seguenti:

1.  Assicurarsi di aver soddisfatto i prerequisiti come descritto in [Plan cloud Voicemail Service](plan-cloud-voicemail.md).

2.  Assicurarsi di aver configurato la connettività ibrida, come descritto in [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) e [Configure Hybrid Connectivity](configure-hybrid-connectivity.md). 

3.  Configurare il servizio di [segreteria cloud come provider di hosting nel server perimetrale](#configure-cloud-voicemail-as-the-hosting-provider) , come descritto in questo articolo.

4.  [Configurare un criterio di segreteria telefonica ospitata](#configure-a-hosted-voicemail-policy) come descritto in questo articolo.

5.  [Assegnare un criterio di segreteria telefonica ospitata](#assign-a-hosted-voicemail-policy) come descritto in questo articolo.

6.  [Abilitare un utente per la segreteria telefonica cloud](#enable-a-user-for-cloud-voicemail) , come descritto in questo articolo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurare il messaggio di posta vocale cloud come provider di hosting 

È possibile configurare il messaggio vocale cloud come provider di hosting in un front end server utilizzando il cmdlet New-CsHostingProvider con i seguenti parametri:

- **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. ad esempio, il messaggio vocale cloud. 

- **Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Questo parametro deve essere impostato su true.

- **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Questo parametro deve essere impostato su true.

- **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Skype for Business Server. Questo parametro deve essere impostato su false.

- **ProxyFqdn** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. ad esempio, proxyserver.contoso.com. Per avere tali informazioni, rivolgersi al provider di hosting. Questo valore non può essere modificato. Se il provider di hosting modifica il server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.

- La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server. Questo parametro deve essere impostato su false.

Ad esempio, in Skype for Business Management Shell, il cmdlet seguente configura il messaggio di posta vocale cloud come provider di hosting:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurare un criterio di segreteria telefonica ospitata

Per assicurarsi che la segreteria telefonica dell'organizzazione sia instradata al servizio cloud voicemail, è necessario configurare un criterio di segreteria telefonica ospitata per l'organizzazione. In molti casi, è necessario un solo criterio di segreteria telefonica ospitata ed è possibile modificare i criteri globali per soddisfare tutte le esigenze. Se nell'organizzazione sono necessari più criteri di segreteria telefonica ospitata, è possibile aggiungere criteri utilizzando il cmdlet New-CsHostedVoicemailPolicy.

Per modificare il criterio globale, eseguire il seguente comando in Skype for Business Server Management Shell dopo aver aggiornato l'organizzazione e TenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destinazione** specifica il nome di dominio completo (FQDN) del servizio segreteria telefonica ospitata. Questo valore deve essere impostato su **exap.um.Outlook.com**.

- **Organization** è il dominio predefinito assegnato al tenant. È possibile recuperare queste informazioni facendo in modo che l'amministratore del tenant acceda a office.com, fare clic sull'app dell'interfaccia di amministrazione, passare a **installazione** a sinistra e fare clic su **domini**. Ad esempio: mytenant.onmicrosoft.com.

    Il nome dell'organizzazione è anche il nome di dominio predefinito in Office 365.

Per assicurarsi che un criterio di segreteria telefonica ospitata sia stato creato correttamente, eseguire il seguente comando:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Assegnare un criterio di segreteria telefonica ospitata

Per impostazione predefinita, il criterio segreteria telefonica ospitata Global è assegnato a tutti gli utenti. Se si utilizza un criterio diverso, prima di abilitare gli utenti per la segreteria telefonica ospitata, è necessario innanzitutto concedere agli utenti il criterio segreteria telefonica ospitata desiderata utilizzando il cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Ad esempio, il comando seguente consente di assegnare un criterio di segreteria telefonica ospitata non globale a un utente:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Abilitare un utente per la segreteria telefonica cloud

Per consentire alle chiamate vocali di un utente di essere instradate alla segreteria telefonica cloud, è possibile utilizzare il cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con il parametro HostedVoiceMail. 

Ad esempio, il comando seguente consente di abilitare un account utente per la segreteria telefonica cloud: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

Il cmdlet verifica che un criterio di segreteria telefonica cloud, a livello globale, sito o utente, si applichi a questo utente. Se nessun criterio è applicabile il cmdlet non riesce.  

Nell'esempio seguente viene disabilitato un account utente per la segreteria telefonica cloud:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata, a livello globale, sito o utente, si applichi a questo utente. Se un criterio è applicabile il cmdlet non riesce.

> [!NOTE]
>  Gli utenti devono essere abilitati alla funzionalità VoIP aziendale per l'utilizzo del servizio segreteria telefonica di Microsoft Cloud.
