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
description: Informazioni su come configurare Cloud Voicemail per gli utenti.
ms.openlocfilehash: 96c96f85625d0cda7e6d7a28a59d6c9415f2bb79
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922627"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è rivolto agli amministratori Microsoft 365 che vogliono configurare Cloud Voicemail per gli utenti.

Cloud Voicemail deposita i messaggi della segreteria telefonica nella cassetta postale Exchange di un utente. Cloud Voicemail non supporta sistemi di posta elettronica di terze parti. Per Exchange Online requisiti di licenza, vedere [Exchange Online descrizione del servizio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Per altre informazioni sui ruoli di amministratore, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>provisioning Cloud Voicemail

Per Teams utenti, Cloud Voicemail viene configurato e di cui viene eseguito automaticamente il provisioning. *Non è necessaria una licenza Telefono di Microsoft Teams per Cloud Voicemail.*

Il provisioning per Teams utenti non è uguale a quello per gli utenti di Skype for Business Online. Per Skype for Business utenti online, Cloud Voicemail è stato configurato e eseguito automaticamente il provisioning quando agli utenti è stata assegnata una licenza di Sistema telefonico e sono stati VoIP aziendale abilitati dal sistema di provisioning.

Per Skype for Business Server utenti locali, Cloud Voicemail viene configurato e di cui viene eseguito automaticamente il provisioning. È tuttavia necessario configurare l'ambiente di Skype for Business Server per instradare le chiamate a Cloud Voicemail. Per altre informazioni, vedere [Pianificare Cloud Voicemail servizio per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Cloud Voicemail di archiviazione

I messaggi vocali generati da Cloud Voicemail vengono recapitati e archiviati nella cassetta postale Exchange dell'utente, in Exchange Online o in Exchange Server. Non esiste spazio di archiviazione specifico o aggiuntivo per la segreteria telefonica. I client che accedono alla segreteria telefonica (ad esempio Microsoft Outlook, Microsoft Teams o Skype for Business) lo fanno tramite la cassetta postale di Exchange e le API fornite.

Un messaggio della segreteria telefonica contiene un file audio allegato con i messaggi vocali e la trascrizione della segreteria telefonica (se abilitata).

La Exchange cassetta postale di un utente archivia i messaggi di saluto registrati personalizzati. Questi saluti vengono recuperati da Cloud Voicemail in base alle esigenze durante una chiamata in arrivo.

## <a name="cloud-voicemail-processing"></a>elaborazione Cloud Voicemail

La registrazione e la trascrizione di Cloud Voicemail inizia in Microsoft 365 all'origine della chiamata instradata a Cloud Voicemail. Il messaggio viene quindi recapitato alla cassetta postale di Exchange dell'utente.

Ad esempio, se una chiamata arriva a un utente direct routing non disponibile tramite un session border controller (SBC) in Europa, la registrazione e la trascrizione della segreteria telefonica vengono eseguite in Europa. Il messaggio viene quindi recapitato alla cassetta postale di Exchange dell'utente. Per un altro esempio, si supponga che un utente Teams in America del Nord chiami un utente Teams non disponibile in Europa. In questo caso, la chiamata inizia in America del Nord, l'elaborazione avviene in America del Nord e quindi la segreteria telefonica viene recapitata alla cassetta postale Exchange dell'utente in Europa.

Il recapito di un messaggio vocale a una cassetta postale di Exchange viene eseguito tramite SMTP (Simple Mail Transport Protocol) come qualsiasi altro indirizzo di posta elettronica.

## <a name="manage-cloud-voicemail-for-users"></a>Gestire Cloud Voicemail per gli utenti

Per gestire le funzionalità di Cloud Voicemail per gli utenti, usare il modulo Teams PowerShell come indicato di seguito.

Per gestire le funzionalità di Cloud Voicemail per gruppi di utenti, utilizzare il cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).
È possibile configurare e assegnare criteri di segreteria telefonica esistenti o nuovi per funzionalità come le regole di risposta alle chiamate, la trascrizione della segreteria telefonica, il mascheramento delle trascrizioni, la traduzione della trascrizione e il linguaggio prompt del sistema. Per ulteriori informazioni, vedi [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Per gestire le impostazioni di Cloud Voicemail per singoli utenti, utilizza il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Cloud Voicemail impostazioni che è possibile applicare ai singoli utenti includono le regole di risposta alle chiamate, la lingua prompt, l'impostazione predefinita per il testo in sintesi vocale e il messaggio di saluto delle vacanze. Per ulteriori informazioni, vedi [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
Si noti che gli utenti finali possono anche configurare queste impostazioni nel client Teams passando a **Impostazioni** ->  **CallsConfigure** ->  **Voicemail**.

Puoi anche disabilitare Cloud Voicemail per un utente utilizzando il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e impostando il parametro VoicemailEnabled su $false. Questa impostazione garantisce che Cloud Voicemail non possa più registrare un messaggio vocale per l'utente.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controllare il routing delle chiamate a Cloud Voicemail

L'impostazione predefinita per tutti gli utenti di cui è stato eseguito il provisioning per Cloud Voicemail è consentire il routing delle chiamate a Cloud Voicemail e consentire agli utenti di inoltrare le chiamate a Cloud Voicemail.

È possibile controllare se il routing delle chiamate a Cloud Voicemail è consentito agli utenti Teams usando il cmdlet Set-CsTeamsCallingPolicy con il parametro AllowVoicemail. Per ulteriori informazioni,  [vedereSet-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

- Se si imposta AllowVoicemail su AlwaysDisabled, le chiamate non vengono mai indirizzate alla segreteria telefonica, indipendentemente dalle impostazioni di inoltro di chiamata o senza risposta per un utente. La segreteria telefonica non è disponibile come impostazione di inoltro di chiamata o senza risposta in Teams.

- Se si imposta AllowVoicemail su AlwaysEnabled, le chiamate vengono sempre inoltrate alla segreteria telefonica senza risposta dopo aver squillato per trenta secondi, indipendentemente dall'impostazione di inoltro di chiamata senza risposta per un utente.

- Se si imposta AllowVoicemail su UserOverride, le chiamate vengono inoltrate alla segreteria telefonica in base alle impostazioni di inoltro di chiamata e/o senza risposta per un utente.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurare Cloud Voicemail per l'uso con gli utenti locali

È possibile usare Cloud Voicemail per fornire funzionalità di segreteria telefonica agli utenti che hanno cassette postali nei server Exchange o agli utenti che usano Skype for Business Server.

In questa sezione viene descritto come configurare Cloud Voicemail per Exchange Server utenti di cassette postali. Per informazioni su come configurare Cloud Voicemail per Skype for Business Server utenti, vedere [Pianificare il servizio Cloud Voicemail per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare Cloud Voicemail per Exchange Server utenti di cassette postali

Le informazioni seguenti riguardano la configurazione di Cloud Voicemail per l'uso con Teams utenti che hanno la propria cassetta postale in Exchange Server.

1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale Exchange di un utente tramite SMTP instradati tramite Exchange Online Protection. Per consentire il recapito corretto di questi messaggi, assicurarsi che Exchange Connectors siano configurati correttamente tra i server Exchange e Exchange Online Protection. Per altre informazioni, vedere [Usare i connettori per configurare la posta Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Per abilitare le funzionalità della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e della segreteria telefonica visiva nei client Teams, è necessario configurare la connettività tra Microsoft 365 e la cassetta postale Exchange Server. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth Exchange descritto in [Configurare l'autenticazione OAuth tra organizzazioni Exchange e Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) oppure eseguire Exchange Hybrid Wizard da Exchange 2013 CU5 o versione successiva. È anche necessario configurare l'integrazione e Oauth tra Teams e Exchange Server descritti in [Configurare l'integrazione e OAuth tra Teams e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Abilitare la segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, il messaggio viene recapitato alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica. 

Usando Microsoft Purview Information Protection, è possibile crittografare i messaggi vocali lasciati dai chiamanti interni ed esterni. È anche possibile impedire all'utente di inoltrare questi messaggi. Questa caratteristica è supportata per gli utenti con cassette postali Exchange Online.

Per crittografare il messaggio della segreteria telefonica, è possibile creare un'etichetta di riservatezza. Con la funzionalità di etichettatura automatica, è possibile fare in modo che l'etichetta venga applicata automaticamente ai messaggi della segreteria telefonica in arrivo. 

Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria cassetta postale della segreteria telefonica o aprendo il messaggio in Outlook, Outlook sul web o Outlook per Android o iOS. I messaggi della segreteria telefonica protetti non possono essere aperti in Microsoft Teams o Skype for Business.

Per creare un'etichetta di riservatezza per la segreteria telefonica, vedere [Usare le etichette di riservatezza](/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions). Nella sezione **Crittografia** scegliere **Consenti agli utenti di assegnare le autorizzazioni quando applicano l'etichetta**. Selezionare **In Outlook applicare una delle limitazioni seguenti** e quindi selezionare l'opzione **Non inoltrare**.

Per creare il criterio di etichettatura automatica per applicare un'etichetta di riservatezza alla segreteria telefonica, vedere [Come configurare i criteri di etichettatura automatica](/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) e specificare le impostazioni specifiche seguenti:

-   Per **Scegliere le informazioni a cui si vuole applicare l'etichetta**, selezionare **Criteri personalizzati**.

-   Per **Scegliere i percorsi in cui applicare l'etichetta**, selezionare **Posizioni: Exchange per tutti gli utenti**.

-   In  **Configura regole comuni o avanzate** seleziona **Regole avanzate**.

- Exchange regole:
    - Condizioni:<br>
        - **Intestazione corrisponde a schema:**<br>
              Content-Class = Voice-CA
       -  **L'indirizzo IP del mittente è:**<br>
               13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Per **Scegli un'etichetta da applicare automaticamente**, seleziona l'etichetta di riservatezza creata per la segreteria telefonica nel passaggio precedente.

- Per **altre impostazioni per la posta elettronica**, selezionare **Applica crittografia ai messaggi ricevuti dall'esterno dell'organizzazione** e specificare il proprietario di Rights Management.

Gli intervalli IP V4 specificati in Indirizzo IP mittente si basano sull'elenco in ID 12 in [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams).

Per altre informazioni sulla crittografia dei messaggi, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Aiutare gli utenti a conoscere le funzionalità di Cloud Voicemail

Per aiutare gli utenti a scoprire come usare e gestire le funzionalità di Cloud Voicemail, è possibile consigliare gli articoli seguenti:

- [Controllare la segreteria telefonica in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
