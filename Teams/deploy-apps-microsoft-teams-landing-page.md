---
title: App, bot e connettori in Microsoft Teams
ms.reviewer: ''
description: Informazioni sulle app, i bot e i connettori e su come decidere quale distribuire in Microsoft Teams in base al profilo e ai requisiti di business dell'organizzazione.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d1a6462d0cb1581142eb2f5076e6b2ebad2b9003
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196520"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>App, bot e connettori in Microsoft Teams

Le app aiutano a trovarei  contenuti dai servizi preferiti e a condividerli in Teams. Consentono di eseguire operazioni come aggiungere servizi nella parte superiore di un canale, chattare con bot o condividere e assegnare attività. Per altre informazioni, vedere [Panoramica delle app in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0). 

È possibile aggiungere app alla distribuzione di Teams usando le app fornite con Microsoft Teams, app e modelli di terze parti certificati e creando app personalizzate.

## <a name="use-microsoft-provided-apps"></a>Usare le app fornite da Microsoft

Teams include un set di app predefinite, tra cui Elenchi, Tasks, Complimento, Approvazioni e altro ancora. È consigliabile includere nell'implementazione iniziale di Teams le app in primo piano, ad esempio Planner. Aggiungere ulteriori app, bot e connettori per incentivare l'adozione di Teams.

## <a name="use-third-party-apps"></a>Usare app di terze parti

Oltre alle app fornite da Microsoft, è possibile usare app di terze parti certificate Microsoft. Microsoft collabora con i partner sviluppatori di Microsoft 365 per fornire le informazioni necessarie al fine di accelerare le decisioni sull'uso di app e componenti aggiuntivi di Teams. Per altre informazioni, vedere [Sicurezza e conformità delle app di Microsoft Teams](https://docs.microsoft.com/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-teams-templates"></a>Usare i modelli di Teams

È anche possibile usare i [modelli di Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json), app pronte per la produzione per Microsoft Teams che sono guidate dalla community, open source e disponibili su GitHub.

## <a name="create-custom-apps"></a>Creare app personalizzate

È possibile creare rapidamente soluzioni personalizzat con basso impiego di codice usando l'integrazione di Teams con [Microsoft Power Platform](teams-power-platfom-integration.md). È anche possibile creare un'app personalizzata in base alle esigenze dell'organizzazione. Per altre informazioni, vedere [Creare app per Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/overview).  


## <a name="apps-deployment-decisions"></a>Decisioni per la distribuzione delle app

Teams offre un'esperienza di collaborazione predefinita che la maggior parte delle organizzazioni trova perfetta per le proprie esigenze. Questo articolo è utile per decidere se modificare una o più impostazioni predefinite in base al profilo o ai requisiti dell'organizzazione e illustra la procedura per ogni modifica. Le impostazioni sono state suddivise in due gruppi, a partire dal set di base di [modifiche più probabili](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions)che si vuole configurare in base alle esigenze dell’organizzazione.

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni delle app che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.

### <a name="app-availability-settings"></a>Impostazioni di disponibilità app 

Teams offre diverse app pubblicate da Microsoft e di terze parti per coinvolgere gli utenti, supportare la produttività e integrare i servizi commerciali di uso comune in Teams. Si possono scaricare le app dallo Store di Teams. Per impostazione predefinita tutte le app, incluse le app personalizzate inviate tramite il [processo di approvazione dello store di Teams](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), sono attivate per tutti gli utenti. Ad esempio, gli utenti possono usare l'app Planner per creare e gestire le attività del team in Teams.

Per impostazione predefinita, tutte le app fornite da Microsoft, da terze parti e personalizzate sono disponibili ed è possibile attivare o disattivare le singole app. Sono disponibili impostazioni a livello di organizzazione che consente di attivare o disattivare tutte le app di terze parti e/o personalizzate per l'intera organizzazione.

| Chiedersi | Azione |
|--------------|--------|
|Le impostazioni delle app di Team predefinite verranno modificate? | Per altre informazioni sui criteri e le impostazioni che è possibile usare per gestire le app nell'organizzazione, vedere [Impostazioni di amministrazione per le app in Microsoft Teams](admin-settings.md).|
|||

### <a name="app-permissions-and-other-considerations"></a>Autorizzazioni delle app e altre considerazioni

Le app sono autorizzate dagli utenti e gestite dall'amministratore o dal professionista IT tramite criteri. Nella maggior parte dei casi, tuttavia, le autorizzazioni e il profilo di rischio di un'app sono definiti nell'app stessa. 

| Chiedersi | Azione |
|--------------|--------|
|<br>A quali app si vuole consentire l'accesso? A quali non si vuole consentire l'accesso?  | <ul><li>Per un elenco degli elementi che è necessario prendere in considerazione quando si consente l'accesso a un'app, un bot, una scheda o un connettore, vedere [Autorizzazioni e considerazioni sulle app di Microsoft Teams](app-permissions.md).</li><li>Per informazioni su come rendere disponibile un'app agli utenti dell'organizzazione, vedere [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md).</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>Bot per chat e canali privati

I bot sono programmi automatizzati che rispondono alle domande o forniscono aggiornamenti e notifiche su dettagli che gli utenti trovano interessanti o su cui vogliono mantenersi informati. I bot consentono agli utenti di interagire con servizi cloud come la gestione delle attività, la pianificazione e il polling in una chat di Teams. Teams supporta i bot all'interno di chat e canali privati. Gli amministratori possono controllare se in un’organizzazione di Microsoft 365 o Office 365 è consentito l'uso di bot.

| Chiedersi | Azione |
|--------------|--------|
|Si vuole consentire l'uso di bot personalizzati nell’organizzazione?|Per altre informazioni sull'aggiunta di bot, vedere [Aggiungere bot per chat e canali privati in Microsoft Teams](add-bots.md). Per informazioni su come attivare o disattivare i bot personalizzati, vedere [Impostazioni di amministrazione per le app in Microsoft Teams](admin-settings.md).|
|||

### <a name="built-in-and-custom-tabs"></a>Schede predefinite e personalizzate

I proprietari e i membri del team possono aggiungere schede a un canale, una chat privata e una chat di gruppo per integrare i propri servizi cloud. Aggiungere schede per aiutare gli utenti ad accedere ai dati di cui hanno bisogno o che usano di più e a gestirli. Nei canali, le schede Conversazioni e File vengono create per impostazione predefinita. In ogni chat privata, le schede Conversazioni, File, Organizzazione e Attività vengono create per impostazione predefinita. Oltre alle schede predefinite, è possibile progettare e aggiungere schede personalizzate. Per informazioni su come attivare o disattivare app di Teams per l'organizzazione, vedere [Impostazioni di amministrazione per le app in Teams](admin-settings.md).

| Chiedersi | Azione |
|--------------|--------|
|Si vuole consentire l'uso di schede personalizzate nell'organizzazione?|Per altre informazioni, vedere [Usare schede predefinite e personalizzate in Teams](built-in-custom-tabs.md).|
|||

### <a name="custom-connectors"></a>Connettori personalizzati

I connettori mantengono il team aggiornato, fornendo contenuto e aggiornamenti provenienti dai servizi usati di frequente direttamente in un canale. Con i connettori, gli utenti di Teams possono ricevere aggiornamenti dai servizi più diffusi, come Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services, nelle proprie chat di Teams.

| Chiedersi | Azione |
|--------------|--------|
|Si vuole consentire agli utenti di creare connettori personalizzati?|Per altre informazioni, vedere [Usare connettori personalizzati in Teams](office-365-custom-connectors.md).|
|||

## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

Può essere utile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="activity-reports"></a>Report attività

È possibile usare i report attività per scoprire in che modo gli utenti dell'organizzazione usano Teams. Ad esempio, se alcuni utenti non usano ancora Teams, potrebbero non sapere come iniziare oppure come usare Teams per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per stabilire come assegnare la priorità alle attività di formazione e comunicazione. Per visualizzare i report attività è necessario essere un amministratore globale in Office 365 o Microsoft 365, un amministratore del servizio Teams o un amministratore di Skype for Business.

| Chiedersi | Azione |
|--------------|--------|
| <br>Chi ha bisogno di vedere i report attività? L'utente dispone dell'autorizzazione necessaria per farlo? |<ul><li>Se non si vuole assegnare un ruolo di amministratore a un utente, è possibile [assegnare il ruolo Lettore di report](teams-activity-reports.md#reports-reader-role).</li><li>Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Ruoli e autorizzazioni](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Visualizzare e assegnare i ruoli](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</li></ul> |
|||

### <a name="app-templates"></a>Modelli di app

I modelli di app sono app pronte per la produzione per Microsoft Teams, gestite dalla community, open source e disponibili su GitHub. Ognuno contiene istruzioni dettagliate per la distribuzione e l'installazione dell'app per l'organizzazione, fornendo un'app pronta all'uso che è possibile installare e iniziare a usare immediatamente. È disponibile anche il codice sorgente completo, quindi è possibile esaminarlo in dettaglio oppure creare una copia tramite fork del codice e modificarlo per soddisfare esigenze specifiche.

| Chiedersi | Azione |
|--------------|--------|
| Si vogliono installare modelli di app di Teams, ad esempio Icebreaker? |Per altre informazioni, vedere [Modelli di app per Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||





