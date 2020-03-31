---
title: Riunioni e conferenze in Microsoft Teams
ms.reviewer: ''
description: Usare queste risorse per la distribuzione per istruzioni su come implementare le riunioni in Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11c3844540288bc94da445e4f13ed90b9a524f46
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053649"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Riunioni e conferenze in Microsoft Teams

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). A questo punto si è pronti per aggiungere il carico di lavoro delle riunioni, inclusi [audioconferenza](deploy-audio-conferencing-teams-landing-page.md), video e condivisione. Questo articolo illustra l'implementazione delle riunioni e dell'audioconferenza. Per iniziare, guardare il video sulle riunioni, le conferenze e i dispositivi di Teams (3:28 minuti):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

*Novità di novembre 2019*: ora si può [usare Advisor per Teams (anteprima) per distribuire Microsoft Teams](use-advisor-teams-roll-out.md). Advisor per Teams (anteprima) guida l'implementazione di Teams, incluse riunioni e conferenze. Valuta l’ambiente di Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente le riunioni e le conferenze in Teams.


## <a name="meetings-and-conferencing-deployment-decisions"></a>Decisioni per la distribuzione di riunioni e conferenze

Teams offre un'esperienza predefinita che la maggior parte delle organizzazioni trova perfetta per le proprie esigenze. Questo articolo è utile per decidere se modificare una o più impostazioni predefinite in base al profilo o ai requisiti dell'organizzazione e illustra la procedura per ogni modifica. Le impostazioni sono state suddivise in due gruppi, a partire dal set di base di [modifiche più probabili](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions) che può essere utile configurare in base alle esigenze dell'organizzazione.

> [!Tip]
> Per altre informazioni sulle riunioni, vedere la sessione seguente: [Introduzione alle riunioni in Microsoft Teams per professionisti IT](https://aka.ms/teams-meetings-intro)


## <a name="meetings-and-conferencing-prerequisites"></a>Prerequisiti per le riunioni e le conferenze 

Prima di estendere la distribuzione delle riunioni all'intera dell'organizzazione, è necessario verificare che l'ambiente sia pronto per offrire agli utenti la migliore esperienza possibile. Rivedere le informazioni seguenti e apportare le modifiche necessarie all'ambiente.

Per ottenere un'esperienza ottimale in Teams, è necessario che l'organizzazione abbia distribuito Exchange Online e SharePoint Online e che disponga di un dominio verificato per Office 365, ad esempio *contoso.com*.

Per estendere le riunioni all'intera organizzazione, occorre verificare che tutte le località degli utenti abbiano accesso a Internet per connettersi ai servizi di Office 365. È necessario verificare che almeno le porte comuni seguenti siano aperte a Internet dalle posizioni degli utenti:

- Porte TCP 80 e 443 in uscita dai client che useranno Teams
- Porte UDP da 3478 a 3481 in uscita dai client che useranno Teams

È possibile usare il [Network Testing Companion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) per verificare che i percorsi di rete siano pronti per il traffico voce e video che supporterà l'esperienza delle riunioni.

| Chiedersi | Azione |
|--------------|--------|
|La rete è pronta per la distribuzione delle riunioni di Teams? | Per verificare che la rete sia pronta, vedere:<ul><li>[Preparare la rete dell'organizzazione per Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.

### <a name="teams-administrators"></a>Amministratori di Teams

Teams include un set di ruoli di amministratore personalizzati che è possibile usare per gestire la soluzione per l'organizzazione. I ruoli forniscono varie funzionalità agli amministratori. 

| Chiedersi | Azione |
|--------------|--------|
|A chi sarà assegnato il ruolo di amministratore delle comunicazioni di Teams?|Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).|
|A chi sarà assegnato il ruolo di tecnico del supporto delle comunicazioni di Teams?|Per assegnare i ruoli amministrativi, vedere [Assegnazione di ruoli di amministratore e senza privilegi di amministratore agli utenti con Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|A chi sarà assegnato il ruolo di specialista del supporto delle comunicazioni di Teams?||
|||

### <a name="meetings-settings"></a>Impostazioni delle riunioni 

Le impostazioni delle riunioni consentono di controllare se gli utenti anonimi possono partecipare alle riunioni di Teams, configurare gli inviti alle riunioni e, se si vuole attivare la Qualità del servizio (QoS), impostare le porte per il traffico in tempo reale. Queste impostazioni verranno usate per tutte le riunioni di Teams che gli utenti pianificano nell'organizzazione. 

| Chiedersi | Azione |
|--------------|--------|
|Le impostazioni iniziali per le riunioni verranno personalizzate? |Per altre informazioni sulle impostazioni delle riunioni, vedere l'[esercitazione sulle riunioni in Teams](tutorial-meetings-in-teams.yml).|
|Si implementerà QoS?|Vedere [Qualità del servizio in Microsoft Teams](qos-in-teams.md) per informazioni sui concetti di QoS, gli scenari e l'implementazione.|
|||

### <a name="meeting-policies"></a>Criteri riunione

I criteri di riunione consentono di controllare quali funzionalità sono disponibili per gli utenti quando partecipano alle riunioni di Teams. È possibile usare il criterio predefinito o creare uno o più criteri di riunione personalizzati per gli utenti dell'organizzazione che ospitano riunioni. Per altre informazioni, vedere l'[esercitazione sulle riunioni in Microsoft Teams](tutorial-meetings-in-teams.yml).

| Chiedersi | Azione |
|--------------|--------|
|<ul><li>I criteri iniziali per le riunioni verranno personalizzati?</li><li>Sono necessari più criteri di riunione?</li><li>Come si determina a quali gruppi di utenti sono applicati i vari criteri di riunione?</li></ul>|<br>Leggere [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md).|
|||

### <a name="audio-conferencing"></a>Audioconferenza

Il servizio di audioconferenza fornisce alle organizzazioni ulteriori punti di accesso a qualsiasi riunione (ad hoc o pianificate), consentendo agli utenti di partecipare tramite la rete PSTN (Public Switched Telephone Network) usando una linea fissa tradizionale, un centralino (PBX, Private Branch Exchange) o un telefono cellulare. 

Quando si sarà pronti per procedere, vedere la guida approfondita sull'[implementazione dell'audioconferenza](deploy-audio-conferencing-teams-landing-page.md).

### <a name="meeting-room-and-personal-devices"></a>Sala riunioni e dispositivi personali

Per un'esperienza di riunione ottimale in Teams è consigliabile usare dispositivi Teams, come sistemi per videoconferenza, telefoni, auricolari e videocamere. Per altre informazioni, vedere [Dispositivi Microsoft Teams per comunicazioni intelligenti](https://products.office.com/microsoft-teams/across-devices).

| Chiedersi | Azione |
|--------------|--------|
|Si acquisteranno dispositivi personali per gli utenti? |Leggere [Gestire i dispositivi in Teams](device-management.md). |
|Si acquisteranno e distribuiranno sistemi per videoconferenza per le sale riunioni?|Vedere [Soluzioni e dispositivi per sala riunioni](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="reporting"></a>Reporting

Usare i report attività per scoprire in che modo gli utenti dell'organizzazione usano Teams. Ad esempio, se alcuni utenti non usano ancora Teams, potrebbero non sapere come iniziare oppure come usare Teams per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per stabilire come assegnare la priorità alle attività di formazione e comunicazione. 


| Chiedersi | Azione |
|--------------|--------|
|Chi sarà responsabile del reporting?|Leggere [Usare i report attività per Teams](teams-activity-reports.md).  |
|Chi sarà responsabile del monitoraggio dell'utilizzo?|Leggere [Monitorare l'utilizzo e il feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).|
|||

## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Può essere utile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="bandwidth-planning"></a>Pianificazione della larghezza di banda 

La pianificazione della larghezza di banda consente alle organizzazioni di stimare la larghezza di banda necessaria per supportare le riunioni nelle WAN e nei collegamenti Internet, così da poter verificare che il provisioning della rete sia adeguato al supporto di un servizio di riunione esteso. 

| Chiedersi | Azione |
|--------------|--------|
| È necessario eseguire la pianificazione della larghezza di banda prima e durante l'implementazione delle riunioni? |Per altre informazioni e collegamenti a strumenti per semplificare il processo di pianificazione, vedere [Preparazione della rete](3-envision-evaluate-my-environment.md#network-readiness).|
|||

### <a name="meeting-recording-and-archiving"></a>Registrazione e archiviazione delle riunioni

Gli utenti possono registrare le riunioni e le chiamate di gruppo per acquisire audio, video e attività di condivisione dello schermo. È anche disponibile un'opzione per la trascrizione automatica delle registrazioni, che consente agli utenti di riprodurre le registrazioni delle riunioni con sottotitoli e cercare gli elementi di discussione importanti nella trascrizione. La registrazione avviene nel cloud e viene salvata in Microsoft Stream, in modo che gli utenti possano condividerla in tutta sicurezza nell'organizzazione. Per trovare la registrazione di una riunione, passare alla conversazione della riunione.

Per altre informazioni, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

| Chiedersi | Azione |
|--------------|--------|
| Si attiverà il servizio di trascrizione riunioni?|Vedere [Attivare o disattivare la trascrizione delle registrazioni](cloud-recording.md#turn-on-or-turn-off-recording-transcription)|
|||


### <a name="live-events-policies"></a>Criteri per gli eventi live

I criteri per gli eventi live di Teams consentono di gestire le impostazioni degli eventi per i gruppi di utenti. È possibile usare il criterio predefinito o creare criteri aggiuntivi da assegnare agli utenti che tengono eventi live all'interno dell'organizzazione. 

| Chiedersi | Azione |
|--------------|--------|
| L'organizzazione userà gli eventi live di Teams?| Per altre informazioni sulla pianificazione, l'impostazione e la configurazione di eventi live, vedere gli [articoli sugli eventi live](teams-live-events/what-are-teams-live-events.md).|
|||

### <a name="conference-room-systems-rollout"></a>Implementazione di sistemi per videoconferenza

Per le organizzazioni con molte sale riunioni può essere utile adottare un approccio strutturato per eseguire l'inventario nelle sale, identificare i dispositivi appropriati e quindi implementarli. 



| Chiedersi | Azione |
|--------------|--------|
| Cosa occorre fare per implementare sistemi per videoconferenza?|Vedere gli articoli sulla [pianificazione di Microsoft Teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="cloud-video-interop"></a>Interoperabilità video sul cloud

L'interoperabilità video sul cloud consente di usare dispositivi per sala riunioni di terze parti per partecipare alle riunioni di Teams. 

La teleconferenza video con collaborazione sui contenuti aiuta a trarre il massimo dalle riunioni. Tuttavia, i sistemi e i dispositivi sistemi per videoconferenza sono costosi da aggiornare. L'interoperabilità video sul cloud per Teams è compatibile con i sistemi di terze parti e offre un'esperienza di riunione nativa per tutti i partecipanti, nelle sale riunioni o all'interno dei clien di Teams. 

| Chiedersi | Azione |
|--------------|--------|
| Si userà una soluzione di interoperabilità video sul cloud come parte della distribuzione dei sistemi per videoconferenza? | Vedere [Interoperabilità video sul cloud per Teams](cloud-video-interop.md).|
|||


### <a name="personal-device-rollout"></a>Implementazione di dispositivi personali

Quando si pianifica una distribuzione più estesa di dispositivi personali per il supporto delle riunioni o delle distribuzioni di servizi voce, è consigliabile usare un processo di implementazione sito-per-sito ripetibile che assicuri una qualità ripetibile.

| Chiedersi | Azione |
|--------------|--------|
|Si userà un approccio sito per sito per implementare le riunioni? |  Il [Playbook sull'abilitazione del sito per Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) offre una buona base da usare per le distribuzioni personalizzate. La guida è incentrata sulle funzionalità vocali, ma i principi generali relativi a consegna dei dispositivi, preparazione degli account, adozione e formazione sono applicabili anche una distribuzione di grandi dimensioni delle riunioni. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Risoluzione dei problemi di qualità per riunioni e chiamate 

Teams offre due modi per monitorare e risolvere i problemi di qualità delle chiamate: Analisi delle chiamate e Dashboard Qualità della chiamata. Analisi delle chiamate mostra informazioni dettagliate sui dispositivi, le reti e la connettività relativamente alle specifiche chiamate e riunioni di ciascun utente. Analisi delle chiamate è progettato per aiutare amministratori e agenti dell'help desk a risolvere i problemi di qualità per specifiche chiamate, mentre Dashboard Qualità della chiamata è progettato per aiutare gli amministratori e i tecnici di rete a ottimizzare una rete. Dashboard Qualità della chiamata non è focalizzato sui singoli utenti, bensì sulle informazioni aggregate di un'intera organizzazione di Teams. 

|Chiedersi|Azione |
|------------|-------|
| Chi sarà responsabile per il monitoraggio e la risoluzione dei problemi di qualità delle chiamate? | Per informazioni sui livelli di autorizzazione necessari per risolvere i problemi di qualità delle chiamate, leggere [Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).|
|||

### <a name="operate-your-meetings-service"></a>Gestire il servizio riunioni

È importante comprendere l'integrità generale del servizio Teams, in modo da poter avvisare in modo proattivo gli altri utenti dell'organizzazione di qualsiasi evento che influisce sul servizio. Gli articoli [Gestire il servizio](1-drive-value-operate-my-service.md) forniscono indicazioni dettagliate per la gestione dei servizi.

|Chiedersi|Azione |
|------------|-------|
|Chi nell'organizzazione sarà responsabile della gestione del servizio riunioni? | Assicurarsi che questa persona abbia le autorizzazioni di amministratore di Teams necessarie per gestire il servizio riunioni. Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Microsoft Teams per gestire Teams](using-admin-roles.md).|
|||


## <a name="next-steps"></a>Passaggi successivi
- [Favorire l'adozione](adopt-microsoft-teams-landing-page.md) di riunioni e conferenze in tutta l'organizzazione.
- [Aggiungere l'audioconferenza](deploy-audio-conferencing-teams-landing-page.md)
- [Implementare Cloud Voice](cloud-voice-landing-page.md)
- Includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungere ulteriori [app, bot e connettori](deploy-apps-microsoft-teams-landing-page.md) per incentivare l'adozione di Teams.
