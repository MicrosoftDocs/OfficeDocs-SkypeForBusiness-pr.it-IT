---
title: Informazioni sulle app in Microsoft Teams
ms.reviewer: ''
description: Scoprire le app e decidere quali app consentire in Teams in base al profilo dell’organizzazione e ai requisiti aziendali.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556527"
---
# <a name="about-apps-in-microsoft-teams"></a>Informazioni sulle app in Microsoft Teams

Le app consentono agli utenti di ottenere contenuti dai servizi preferiti e di condividerli in Teams. Consentono di eseguire attività come aggiungere servizi nella parte superiore di un canale, automatizzare le notifiche usando i bot o condividere e assegnare le attività. Per altre informazioni sull'uso delle app, vedere [Panoramica delle app per gli utenti finali](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

I diversi tipi di app che gli utenti finali possono usare in Teams sono app create da Microsoft, app di terze parti certificate e app personalizzate create dalla propria organizzazione.

## <a name="use-microsoft-provided-apps"></a>Usare le app fornite da Microsoft

Teams include un set di app predefinite, tra cui Elenchi, Tasks, Complimento, Approvazioni e altro ancora. È consigliabile includere le app in primo piano di Teams, come ad esempio Planner, nell'implementazione iniziale di Teams. Aggiungere altre app man mano che si adotta Teams. Alcune funzionalità predefinite come il flusso di attività, la chat, il calendario e le chiamate sono disponibili per impostazione predefinita e aggiunte per facilitare l'accesso agli utenti finali.

## <a name="use-third-party-apps"></a>Usare app di terze parti

Oltre alle app fornite da Microsoft, è possibile usare app di terze parti convalidate da Microsoft. Microsoft collabora con Microsoft 365 partner per sviluppatori per fornire le informazioni necessarie per accelerare le decisioni relative all'uso delle app di Teams. Per altre informazioni, vedere [sicurezza e conformità delle app di Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Usare le app di esempio open source fornite da Microsoft

È anche possibile usare i [modelli di Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), app pronte per la produzione per Microsoft Teams che sono guidate dalla community, open source e disponibili su GitHub.

## <a name="create-custom-apps"></a>Creare app personalizzate

È possibile creare rapidamente soluzioni personalizzat con basso impiego di codice usando l'integrazione di Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions). È anche possibile creare un'app personalizzata in base alle esigenze dell'organizzazione. Per altre informazioni, vedere [Creare app per Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Decisioni per la distribuzione delle app

Teams offre un'esperienza di collaborazione predefinita che la maggior parte delle organizzazioni trova perfetta per le proprie esigenze. Questo articolo è utile per decidere se modificare una o più impostazioni predefinite in base al profilo o ai requisiti dell'organizzazione e illustra la procedura per ogni modifica. Le impostazioni sono state suddivise in due gruppi, a partire dal set di base di [modifiche più probabili](#core-deployment-decisions). Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions)che si vuole configurare in base alle esigenze dell’organizzazione.

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Di seguito sono illustrate le impostazioni delle app che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.

### <a name="app-availability-settings"></a>Impostazioni di disponibilità app

Teams offre diverse app pubblicate da Microsoft e di terze parti per coinvolgere gli utenti, supportare la produttività e integrare i servizi commerciali di uso comune in Teams.
Si possono scaricare le app dallo Store di Teams. Per impostazione predefinita tutte le app, incluse le app personalizzate inviate tramite il [processo di approvazione dello store di Teams](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), sono attivate per tutti gli utenti. Ad esempio, gli utenti possono usare l'app Planner per creare e gestire le attività del team in Teams.

Per impostazione predefinita, tutte le app fornite da Microsoft, da terze parti e personalizzate sono disponibili ed è possibile attivare o disattivare le singole app. Sono disponibili impostazioni a livello di organizzazione che consente di attivare o disattivare tutte le app di terze parti e/o personalizzate per l'intera organizzazione.

| Chiedersi | Azione |
|--------------|--------|
|Le impostazioni delle app di Team predefinite verranno modificate? | Per altre informazioni sui criteri e le impostazioni che è possibile usare per gestire le app nell'organizzazione, vedere [Impostazioni di amministrazione per le app in Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>Autorizzazioni delle app e altre considerazioni

Le app sono autorizzate dagli utenti e gestite dall'amministratore o dal professionista IT tramite criteri. Tuttavia, le autorizzazioni e il profilo di rischio di un’app sono definiti nell'app stessa.

| Chiedersi | Azione |
|--------------|--------|
|<br>A quali app si vuole consentire l'accesso? A quali non si vuole consentire l'accesso?  | <ul><li>Per un elenco degli elementi che è necessario prendere in considerazione quando si consente l'accesso a un'app, un bot, una scheda o un connettore, vedere [Autorizzazioni e considerazioni sulle app di Microsoft Teams](app-permissions.md).</li><li>Per informazioni su come rendere disponibile un'app agli utenti dell'organizzazione, vedere [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md).</li></ul>|

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Ulteriori decisioni per la distribuzione

È possibile modificare queste impostazioni in base alle esigenze e alla configurazione dell'organizzazione.

### <a name="activity-reports"></a>Report attività

È possibile usare i report attività per scoprire in che modo gli utenti dell'organizzazione usano Teams. Ad esempio, se alcuni utenti non usano ancora Teams, potrebbero non sapere come iniziare oppure come usare Teams per essere più produttivi e collaborativi. L'organizzazione può usare i report attività per stabilire come assegnare la priorità alle attività di formazione e comunicazione. Per visualizzare i report attività è necessario essere un amministratore globale in Office 365 o Microsoft 365, un amministratore del servizio Teams o un amministratore di Skype for Business.

| Chiedersi | Azione |
|--------------|--------|
| <br>Chi ha bisogno di vedere i report attività? L'utente dispone dell'autorizzazione necessaria per farlo? |<ul><li>Se non si vuole assegnare un ruolo di amministratore a un utente, è possibile [assegnare il ruolo Lettore di report](teams-activity-reports.md#reports-reader-role).</li><li>Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Ruoli e autorizzazioni](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [Visualizzare e assegnare i ruoli](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</li></ul> |

### <a name="app-templates"></a>Modelli di app

I modelli di app sono applicazioni pronte per la produzione per Microsoft, gestite dalla community, open-source e disponibili su GitHub. Ogni app contiene le istruzioni dettagliate per la sua distribuzione e installazione nell’organizzazione, ed è un’applicazione pronta all'uso, da installare e usare fin da subito.

È disponibile anche il codice sorgente completo, quindi è possibile esaminarlo in dettaglio oppure creare una copia tramite fork del codice e modificarlo per soddisfare esigenze specifiche.

| Chiedersi | Azione |
|--------------|--------|
| Si vogliono installare modelli di app di Teams, ad esempio Icebreaker? |Per altre informazioni, vedere [Modelli di app per Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
