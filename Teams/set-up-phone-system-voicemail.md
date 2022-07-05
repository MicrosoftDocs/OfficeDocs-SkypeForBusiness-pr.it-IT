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
ms.openlocfilehash: 9d6752098ff9dee6294d53fb24f6b7df6ee8e21c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616252"
---
# <a name="set-up-cloud-voicemail"></a>Configurare Cloud Voicemail

Questo articolo è rivolto agli amministratori di Microsoft 365 che vogliono configurare Cloud Voicemail per gli utenti.

Cloud Voicemail deposita i messaggi della segreteria telefonica nella cassetta postale di Exchange di un utente. Cloud Voicemail non supporta sistemi di posta elettronica di terze parti. Per Exchange Online requisiti di licenza, vedere [Exchange Online descrizione del servizio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Per altre informazioni sui ruoli di amministratore, vedere [Informazioni sui ruoli di amministratore](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>provisioning Cloud Voicemail

Per gli utenti di Teams, Cloud Voicemail viene configurato e eseguito automaticamente il provisioning. *Non è necessaria una licenza Telefono di Microsoft Teams per Cloud Voicemail.*

Il provisioning per gli utenti di Teams non è uguale a quello per gli utenti di Skype for Business Online. Per Skype for Business utenti online, Cloud Voicemail è stato configurato e eseguito automaticamente il provisioning quando agli utenti è stata assegnata una licenza Sistema telefonico e sono stati VoIP aziendale abilitati dal sistema di provisioning.

Per Skype for Business Server utenti locali, Cloud Voicemail viene configurato e di cui viene eseguito automaticamente il provisioning. È tuttavia necessario configurare l'ambiente di Skype for Business Server per instradare le chiamate a Cloud Voicemail. Per altre informazioni, vedere [Pianificare Cloud Voicemail servizio per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Cloud Voicemail di archiviazione

I messaggi vocali generati da Cloud Voicemail vengono recapitati e archiviati nella cassetta postale di Exchange dell'utente, in Exchange Online o in Exchange Server. Non esiste spazio di archiviazione specifico o aggiuntivo per la segreteria telefonica. I client che accedono alla segreteria telefonica (ad esempio Microsoft Outlook, Microsoft Teams o Skype for Business) lo fanno tramite la cassetta postale di Exchange e le API fornite.

Un messaggio della segreteria telefonica contiene un file audio allegato con i messaggi vocali e la trascrizione della segreteria telefonica (se abilitata).

La cassetta postale di Exchange di un utente archivia tutti i saluti registrati personalizzati. Questi saluti vengono recuperati da Cloud Voicemail in base alle esigenze durante una chiamata in arrivo.

## <a name="cloud-voicemail-processing"></a>elaborazione Cloud Voicemail

La registrazione e la trascrizione di Cloud Voicemail inizia in Microsoft 365 all'origine della chiamata instradata a Cloud Voicemail. Il messaggio viene quindi recapitato alla cassetta postale di Exchange dell'utente.

Ad esempio, se una chiamata arriva a un utente direct routing non disponibile tramite un session border controller (SBC) in Europa, la registrazione e la trascrizione della segreteria telefonica vengono eseguite in Europa. Il messaggio viene quindi recapitato alla cassetta postale di Exchange dell'utente. Per un altro esempio, si supponga che un utente di Teams in America del Nord chiami un utente di Teams non disponibile in Europa. In questo caso, la chiamata inizia in America del Nord, l'elaborazione avviene in America del Nord e quindi la segreteria telefonica viene recapitata nella cassetta postale di Exchange dell'utente in Europa.

Il recapito di un messaggio vocale a una cassetta postale di Exchange viene eseguito tramite SMTP (Simple Mail Transport Protocol) come qualsiasi altro indirizzo di posta elettronica.

## <a name="manage-cloud-voicemail-for-users"></a>Gestire Cloud Voicemail per gli utenti

È possibile gestire Cloud Voicemail per gli utenti specificando i criteri della segreteria telefonica e configurando le impostazioni della segreteria telefonica.  

- **I criteri segreteria telefonica** consentono di gestire le funzionalità per gruppi di utenti. È possibile configurare e assegnare criteri di segreteria telefonica esistenti o nuovi per funzionalità come le regole di risposta alle chiamate, la trascrizione della segreteria telefonica, il mascheramento delle trascrizioni, la traduzione della trascrizione e il linguaggio prompt del sistema. Per informazioni sulla gestione dei criteri della segreteria telefonica, vedere [Gestire i criteri della segreteria telefonica](manage-voicemail-policies.md).

- **Le impostazioni della segreteria** telefonica consentono di configurare le impostazioni per singoli utenti. È possibile configurare impostazioni come le regole di risposta alle chiamate, la lingua richiesta, l'impostazione predefinita per la sintesi vocale e il messaggio di saluto delle vacanze. Per informazioni sulla configurazione delle impostazioni per singoli utenti, vedere [Gestire le impostazioni della segreteria telefonica](manage-voicemail-settings.md). Si noti che gli utenti finali possono anche configurare queste impostazioni nel client di Teams accedendo a **Impostazioni -chiamate > -> Configura segreteria telefonica**.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controllare il routing delle chiamate a Cloud Voicemail

L'impostazione predefinita per tutti gli utenti di cui è stato eseguito il provisioning per Cloud Voicemail è consentire il routing delle chiamate a Cloud Voicemail e consentire agli utenti di inoltrare le chiamate a Cloud Voicemail.

È possibile controllare se il routing delle chiamate a Cloud Voicemail è consentito agli utenti di Teams usando l'interfaccia di amministrazione di Teams o PowerShell. 

- Per usare l'interfaccia di amministrazione di Teams, vai a **Criteri per le chiamate** **vocali** ->  -> aggiungi nuovi o modifica i criteri esistenti -> **La segreteria telefonica è disponibile per il routing delle chiamate in ingresso**.  

- In PowerShell usare il cmdlet Set-CsTeamsCallingPolicy con il parametro AllowVoicemail. Per ulteriori informazioni, vedere [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

  - Se si imposta AllowVoicemail su AlwaysDisabled, le chiamate non vengono mai indirizzate alla segreteria telefonica, indipendentemente dalle impostazioni di inoltro di chiamata o senza risposta per un utente. La segreteria telefonica non è disponibile come impostazione di inoltro di chiamata o senza risposta in Teams.

  - Se si imposta AllowVoicemail su AlwaysEnabled, le chiamate vengono sempre inoltrate alla segreteria telefonica senza risposta dopo aver squillato per trenta secondi, indipendentemente dall'impostazione di inoltro di chiamata senza risposta per un utente.

  - Se si imposta AllowVoicemail su UserOverride, le chiamate vengono inoltrate alla segreteria telefonica in base alle impostazioni di inoltro di chiamata e/o senza risposta per un utente.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurare Cloud Voicemail per l'uso con gli utenti locali

È possibile usare Cloud Voicemail per fornire funzionalità di segreteria telefonica agli utenti che hanno cassette postali nei server Exchange o agli utenti che usano Skype for Business Server.

In questa sezione viene descritto come configurare Cloud Voicemail per Exchange Server utenti di cassette postali. Per informazioni su come configurare Cloud Voicemail per Skype for Business Server utenti, vedere [Pianificare il servizio Cloud Voicemail per gli utenti locali](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurare Cloud Voicemail per Exchange Server utenti di cassette postali

Le informazioni seguenti riguardano la configurazione di Cloud Voicemail per l'uso con gli utenti di Teams che hanno la propria cassetta postale in Exchange Server.

1. I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange di un utente tramite SMTP instradati tramite Exchange Online Protection. Per consentire il recapito corretto di questi messaggi, assicurarsi che i connettori di Exchange siano configurati correttamente tra i server Exchange e Exchange Online Protection. Per altre informazioni, vedere [Usare i connettori per configurare il flusso di posta](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Per abilitare le funzionalità della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e della segreteria telefonica visiva nei client di Teams, è necessario configurare la connettività tra Microsoft 365 e la cassetta postale Exchange Server. Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in [Configurare l'autenticazione OAuth tra Exchange e le organizzazioni Exchange Online](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) oppure eseguire la Procedura guidata per la distribuzione ibrida di Exchange da Exchange 2013 CU5 o versione successiva. È anche necessario configurare l'integrazione e Oauth tra Teams e Exchange Server descritti in [Configurare l'integrazione e OAuth tra Teams e Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Abilitare la segreteria telefonica protetta nell'organizzazione

Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, il messaggio viene recapitato alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica.

Usando Microsoft Purview Information Protection, è possibile crittografare i messaggi della segreteria telefonica lasciati dai chiamanti sia interni che esterni. È anche possibile impedire all'utente di inoltrare questi messaggi. Questa caratteristica è supportata per gli utenti con cassette postali Exchange Online.

Per crittografare il messaggio della segreteria telefonica, è possibile creare un'etichetta di riservatezza. Con la funzionalità di etichettatura automatica, è possibile fare in modo che l'etichetta venga applicata automaticamente ai messaggi della segreteria telefonica in arrivo.

Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti aprendo il messaggio in Outlook, Outlook sul web o Outlook per Android o iOS. I messaggi vocali protetti non possono essere aperti in Microsoft Teams o Skype for Business.

Per creare un'etichetta di riservatezza per la segreteria telefonica, vedere [Usare le etichette di riservatezza](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Nella sezione **Crittografia** scegliere **Consenti agli utenti di assegnare le autorizzazioni quando applicano l'etichetta**. Selezionare **In Outlook applicare una delle limitazioni seguenti** e quindi selezionare l'opzione **Non inoltrare** .

Per creare il criterio di etichettatura automatica per applicare un'etichetta di riservatezza alla segreteria telefonica, vedere [Come configurare i criteri di etichettatura automatica](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) e specificare le impostazioni specifiche seguenti:

- Per **Scegliere le informazioni a cui si vuole applicare l'etichetta**, selezionare **Criteri personalizzati**.

- Per **Scegliere i percorsi in cui applicare l'etichetta**, selezionare **Posizioni: Exchange per tutti gli utenti**.

- In  **Configura regole comuni o avanzate** seleziona **Regole avanzate**.

- Regole di Exchange:
  - Condizioni:
    - **Schema delle corrispondenze dell'intestazione**: Content-Class = Voice-CA
    - **L'indirizzo IP del mittente è**: 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Per **Scegli un'etichetta da applicare automaticamente**, seleziona l'etichetta di riservatezza creata per la segreteria telefonica nel passaggio precedente.

- Per **altre impostazioni per la posta elettronica**, selezionare **Applica crittografia ai messaggi ricevuti dall'esterno dell'organizzazione** e specificare il proprietario di Rights Management.

Gli intervalli IP V4 specificati in Indirizzo IP mittente si basano sull'elenco in ID 12 in [Office 365 URL e intervalli di indirizzi IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Per altre informazioni sulla crittografia dei messaggi, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Aiutare gli utenti a conoscere le funzionalità di Cloud Voicemail

Per aiutare gli utenti a scoprire come usare e gestire le funzionalità di Cloud Voicemail, è possibile consigliare gli articoli seguenti:

- [Controllare la segreteria telefonica in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Gestire le impostazioni delle chiamate in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
