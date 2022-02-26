---
title: Configurare Cloud Voicemail
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Informazioni su come configurare i Cloud Voicemail per gli utenti.
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974473"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è per Microsoft 365 amministratori che vogliono configurare Cloud Voicemail per gli utenti. 

Cloud Voicemail deposita i messaggi della segreteria telefonica nella cassetta postale Exchange utente. Cloud Voicemail non supporta sistemi di posta elettronica di terze parti. Per Exchange Online di licenza, vedere la descrizione [Exchange Online servizio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Per altre informazioni sui ruoli di amministratore, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Cloud Voicemail provisioning

Per Teams utenti, Cloud Voicemail viene configurato ed eseguito automaticamente il provisioning. *Per Microsoft Teams Telefono Cloud Voicemail non è necessaria una Cloud Voicemail.*

Il provisioning per Teams utenti non è uguale a quello per gli utenti di Skype for Business online. Per gli utenti di Skype for Business Online, Cloud Voicemail è stato automaticamente configurato ed eseguito il provisioning quando agli utenti è stata assegnata una licenza Sistema telefonico e sono VoIP aziendale abilitati dal sistema di provisioning.

Per Skype for Business Server utenti locali, Cloud Voicemail viene configurato ed eseguito automaticamente il provisioning. Tuttavia, è necessario configurare l'ambiente Skype for Business Server per instradare le chiamate a Cloud Voicemail. Per altre informazioni, vedere [Pianificare Cloud Voicemail per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail.md). 

## <a name="cloud-voicemail-storage"></a>Cloud Voicemail archiviazione

I messaggi della segreteria telefonica Cloud Voicemail vengono recapitati e archiviati nella cassetta postale Exchange dell'utente, in Exchange Online o in Exchange Server. Non c'è spazio di archiviazione specifico o aggiuntivo per la segreteria telefonica. I client che accedono alla segreteria telefonica,ad esempio Microsoft Outlook, Microsoft Teams o Skype for Business, lo fanno tramite la cassetta postale di Exchange e le API fornite. 

Un messaggio della segreteria telefonica contiene un file audio allegato con i messaggi vocali e la trascrizione della segreteria telefonica (se abilitata). 

La Exchange cassetta postale di un utente archivia tutti i messaggi di saluto registrati personalizzati. Questi messaggi di saluto vengono recuperati Cloud Voicemail durante una chiamata in arrivo. 

## <a name="cloud-voicemail-processing"></a>Cloud Voicemail elaborazione 

La registrazione e la trascrizione di Cloud Voicemail inizia Microsoft 365 all'origine della chiamata instradata Cloud Voicemail. Il messaggio viene quindi recapitato alla cassetta postale Exchange'utente. 

Ad esempio, se una chiamata viene effettuata a un utente di Routing diretto non disponibile tramite un session border controller (SBC) in Europa, la registrazione e la trascrizione della segreteria telefonica vengono eseguite in Europa. Il messaggio viene quindi recapitato alla cassetta postale Exchange'utente. Per un altro esempio, si supponga che Teams un utente nordamericano chiami un utente Teams non disponibile in Europa. In questo caso, la chiamata inizia in Nord America, l'elaborazione viene eseguita in Nord America e quindi la segreteria telefonica viene recapitata alla cassetta postale Exchange'utente in Europa. 

Il recapito di una segreteria telefonica a Exchange cassetta postale viene eseguito usando smtp (Simple Mail Transport Protocol) come qualsiasi altro messaggio di posta elettronica. 

## <a name="manage-cloud-voicemail-for-users"></a>Gestire Cloud Voicemail per gli utenti 

Per gestire Cloud Voicemail per gli utenti, usare il modulo Teams PowerShell come indicato di seguito. 

Per gestire Cloud Voicemail per gruppi di utenti, usare il cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy). È possibile configurare e assegnare criteri della segreteria telefonica esistenti o nuovi per funzionalità come le regole di risposta alle chiamate, la trascrizione della segreteria telefonica, il mascheramento delle trascrizioni volgari, la traduzione della trascrizione e la lingua richiesta dal sistema. Per altre informazioni, vedere [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Per gestire Cloud Voicemail per singoli utenti, usare il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Cloud Voicemail impostazioni che è possibile applicare ai singoli utenti includono le regole di risposta alle chiamate, la lingua richiesta, l'impostazione predefinita della sintesi vocale e i saluti per le vacanze. Per altre informazioni, vedere [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
Gli utenti finali possono anche configurare queste impostazioni nel client  ->  di Teams selezionando Impostazioni **CallsConfigure** ->  **Voicemail**.

È anche possibile disabilitare Cloud Voicemail per un utente usando il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e impostando il parametro VoicemailEnabled su $false. Questa impostazione garantisce che Cloud Voicemail non possa più registrare una segreteria telefonica per l'utente.



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controllare l'instradamento delle chiamate Cloud Voicemail 

L'impostazione predefinita per tutti gli utenti di cui è stato eseguito il provisioning per Cloud Voicemail è consentire il routing delle chiamate a Cloud Voicemail e consentire agli utenti di inoltrare le chiamate a Cloud Voicemail. 

È possibile controllare se il routing delle chiamate a Cloud Voicemail è consentito agli utenti Teams utenti usando il cmdlet Set-CsTeamsCallingPolicy con il parametro AllowVoicemail. Per altre informazioni, vedere  [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md). 

- Se si imposta AllowVoicemail su AlwaysDisabled, le chiamate non vengono mai instradate alla segreteria telefonica, indipendentemente dalle impostazioni di inoltro di chiamata o senza risposta per un utente. La segreteria telefonica non è disponibile come inoltro di chiamata o come impostazione senza risposta in Teams.  

- Se si imposta AllowVoicemail su AlwaysEnabled, le chiamate vengono sempre inoltrate alla segreteria telefonica dopo aver squillato per trenta secondi, indipendentemente dall'impostazione di inoltro di chiamata senza risposta per un utente.  

- Se si imposta AllowVoicemail su UserOverride, le chiamate vengono inoltrate alla segreteria telefonica in base alle impostazioni di inoltro di chiamata e/o senza risposta per un utente. 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurare le Cloud Voicemail per l'utilizzo con gli utenti locali

È possibile usare Cloud Voicemail per fornire funzionalità di segreteria telefonica per gli utenti che dispongono di cassette postali nei server Exchange o per gli utenti che usano Skype for Business Server. 

In questa sezione viene descritto come configurare le Cloud Voicemail per Exchange Server utenti della cassetta postale. Per informazioni su come configurare i Cloud Voicemail per Skype for Business Server utenti, vedere Pianificare il servizio di Cloud Voicemail [per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare i Cloud Voicemail per Exchange Server utenti della cassetta postale

Le informazioni seguenti riguardano la configurazione Cloud Voicemail per l'utilizzo con Teams utenti che hanno la propria cassetta postale Exchange Server.

1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale Exchange di un utente tramite SMTP instradato tramite Exchange Online Protection. Per abilitare il recapito corretto di questi messaggi, assicurarsi che i connettori Exchange siano configurati correttamente tra i server Exchange e Exchange Online Protection. Per altre informazioni, vedere [Usare i connettori per configurare la posta Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Per abilitare le funzionalità della segreteria telefonica, come la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Teams, è necessario configurare la connettività tra Microsoft 365 e la cassetta postale Exchange Server messaggi. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in Configurare l'autenticazione [OAuth tra organizzazioni di Exchange e Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva. È anche necessario configurare l'integrazione e Oauth tra Teams e Exchange Server descritti in Configurare l'integrazione e [OAuth tra Teams e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).


## <a name="enable-protected-voicemail-in-your-organization"></a>Abilitare la segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. Usando le regole del flusso di posta elettronica per applicare la crittografia dei messaggi, è possibile impedire l'inoltro di tali messaggi della segreteria telefonica ad altri destinatari. Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria cassetta postale della segreteria telefonica o aprendo il messaggio in Outlook, Outlook sul web o in Outlook per Android o iOS. I messaggi della segreteria telefonica protetta non possono essere aperti in Skype for Business o Microsoft Teams.

Per altre informazioni sulla crittografia dei messaggi, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Aiutare gli utenti a conoscere Cloud Voicemail caratteristiche

Per aiutare gli utenti a imparare a usare e gestire le Cloud Voicemail, è possibile consigliare gli articoli seguenti: 

- [Controlla la segreteria telefonica in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gestire le impostazioni della chiamata in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
