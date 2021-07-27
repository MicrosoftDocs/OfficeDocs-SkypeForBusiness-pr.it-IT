---
title: Configurare Cloud Voicemail per gli utenti locali
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
description: Istruzioni per l'implementazione della segreteria telefonica basata su cloud per gli utenti ospitati Skype for Business Server.
ms.openlocfilehash: 76d65efcc0df59396942c8a38ebc22006427a0f0
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510577"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurare Cloud Voicemail per gli utenti locali

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>Panoramica 
In questo articolo viene descritto come configurare Microsoft Cloud Voicemail servizio per gli Skype for Business utenti locali.  

In questo articolo si presuppone che Skype for Business Server sia già stata distribuita in una topologia supportata e che siano stati soddisfatti i prerequisiti per la configurazione della connettività ibrida.

Per ulteriori informazioni sui vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione di Cloud Voicemail, vedere [Plan Cloud Voicemail service](plan-cloud-voicemail.md).




La configurazione Cloud Voicemail comporta le attività seguenti:

1.  Verificare di aver soddisfatto i prerequisiti come descritto in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).

2.  Assicurarsi di aver configurato la connettività ibrida come descritto in [Plan hybrid connectivity](plan-hybrid-connectivity.md) e Configure hybrid [connectivity](configure-hybrid-connectivity.md). 

3.  [Configurare Cloud Voicemail come provider di hosting nel Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) come descritto in questo articolo.

4.  [Configurare un criterio segreteria telefonica ospitata](#configure-a-hosted-voicemail-policy) come descritto in questo articolo.

5.  [Assegnare un criterio segreteria telefonica ospitata](#assign-a-hosted-voicemail-policy) come descritto in questo articolo.

6.  [Abilitare un utente per Cloud Voicemail](#enable-a-user-for-cloud-voicemail) come descritto in questo articolo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurare Cloud Voicemail come provider di hosting 

È possibile configurare Cloud Voicemail come provider di hosting in un Front End Server utilizzando il cmdlet New-CsHostingProvider con i parametri seguenti:

- **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. ad esempio, Cloud Voicemail. 

- **Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Questo parametro deve essere impostato su True.

- **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Questo parametro deve essere impostato su True.

- **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare Skype for Business Server account. Questo parametro deve essere impostato su False.

- **ProxyFQDN** specifica il nome di dominio completo (FQDN) per il server proxy utilizzato dal provider di hosting. ad esempio, proxyserver.contoso.com. Per avere tali informazioni, rivolgersi al provider di hosting. Questo valore non può essere modificato. Se il provider di hosting modifica il server proxy, sarà necessario eliminare e quindi creare di nuovo la voce per tale provider.

- **IsLocal** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia Skype for Business Server locale. Questo parametro deve essere impostato su False.

Ad esempio, in Skype for Business Management Shell, il cmdlet seguente configura Cloud Voicemail come provider di hosting:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurare un criterio segreteria telefonica ospitata

Per assicurarsi che la segreteria telefonica dell'organizzazione sia instradata al servizio Cloud Voicemail, è necessario configurare un criterio segreteria telefonica ospitata per l'organizzazione. In molti casi, è necessario un solo criterio di segreteria telefonica ospitata ed è possibile modificare il criterio globale per soddisfare tutte le esigenze. Se l'organizzazione richiede più criteri di segreteria telefonica ospitata, è possibile aggiungere criteri utilizzando il cmdlet new-cshostedvoicemailpolicy.

Per modificare il criterio globale, eseguire il comando seguente in Skype for Business Server management shell dopo aver aggiornato Organization e TenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** specifica il nome di dominio completo (FQDN) del servizio Cloud Voicemail host. Questo valore deve essere impostato su **exap.um.outlook.com**.

- **L'organizzazione** è il dominio predefinito assegnato al tenant. Per recuperare queste informazioni, l'amministratore tenant accede a office.com, fai clic sull'app Interfaccia di amministrazione, passa a **Installazione** a sinistra e fai clic su **Domini.** Ad esempio: mytenant.onmicrosoft.com.

    Il nome dell'organizzazione è anche il nome di dominio predefinito in Microsoft 365 o Office 365.

Per assicurarsi che un criterio segreteria telefonica ospitato sia stato creato correttamente, eseguire il comando seguente:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Assegnare un criterio segreteria telefonica ospitata

Per impostazione predefinita, il criterio di segreteria telefonica ospitata globale viene assegnato a tutti gli utenti. Se si utilizza un criterio diverso, prima di abilitare gli utenti per la segreteria telefonica ospitata, è necessario innanzitutto concedere agli utenti il criterio di segreteria telefonica ospitata desiderato utilizzando il cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)

Ad esempio, il comando seguente assegna un criterio di segreteria telefonica ospitata non globale a un utente:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Abilitare un utente per Cloud Voicemail

Per abilitare le chiamate di segreteria telefonica di un utente da instradare a Cloud Voicemail, utilizzare il cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) con il parametro HostedVoiceMail. 

Ad esempio, il comando seguente abilita un account utente per Cloud Voicemail: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

Il cmdlet verifica che un criterio Cloud Voicemail, a livello globale, di sito o utente, si applichi a questo utente. Se nessun criterio è applicabile il cmdlet non riesce.  

Nell'esempio seguente viene disabilitato un account utente per Cloud Voicemail:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata, a livello globale, di sito o utente, si applichi a questo utente. Se un criterio è applicabile il cmdlet non riesce.

> [!NOTE]
>  Gli utenti devono essere abilitati per voIP aziendale per utilizzare il servizio Microsoft Cloud Voicemail aziendale.