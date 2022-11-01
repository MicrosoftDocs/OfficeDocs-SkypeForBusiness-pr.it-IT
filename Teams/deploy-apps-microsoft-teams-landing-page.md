---
title: Informazioni sulle app in Microsoft Teams
ms.reviewer: ''
description: Scoprire le app e decidere quali app consentire in Teams in base al profilo dell’organizzazione e ai requisiti aziendali.
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 83654452460da41bf72b0feca30d3373de1533ef
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795428"
---
# <a name="understand-microsoft-teams-apps"></a>Informazioni sulle app di Microsoft Teams

Le app in Teams aiutano gli utenti a riunire gli strumenti e i servizi del luogo di lavoro e a collaborare con altri utenti. Esempi sono l'utilizzo da parte degli utenti finali di un'app Calendario in Teams per collaborare rapidamente con gli altri, un'app con funzionalità bot che informa gli utenti sulla qualità di un servizio web in un canale Teams e un'app per condividere e assegnare compiti a vari utenti finali in un canale. Le app di Microsoft Teams sono app SaaS basate sul Web che non devono essere distribuite localmente.

Gli amministratori impostano un processo di governance delle app che bilancia i requisiti ad ampio raggio degli utenti finali con i criteri, gli standard e i profili di rischio dell'organizzazione.

Il nostro ampio [catalogo](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) di app Teams convalidate e sicure offre agli utenti finali l'accesso agli strumenti e ai servizi di cui l'organizzazione ha bisogno ogni giorno. L'interfaccia di amministrazione di Teams fornisce agli amministratori configurazioni e controlli di livello enterprise per gestire le app. Puoi controllare la disponibilità delle app per ogni utente nei vari contesti, ad esempio riunione, chat e canali.

Questo articolo illustra i tipi di app e la posizione in cui gli utenti accedono a tali app. Per altre informazioni sull'uso delle app, leggere [Panoramica delle app per gli utenti finali](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

I diversi tipi di app che gli utenti finali possono usare in Teams sono:

* [App di base che fanno parte di Teams](#core-apps).
* Altre [app create da Microsoft](#apps-created-by-microsoft).
* [App di terze parti](#third-party-apps-created-by-independent-app-developers) create da partner (convalidate da Microsoft).
* [App personalizzate](#custom-apps-created-within-an-organization-for-internal-use) create dalla propria organizzazione.

## <a name="core-apps"></a>App di base

Alcune funzionalità di Teams, come il feed attività, i canali, le chat, il calendario e le chiamate, sono disponibili per impostazione predefinita e aggiunte per impostazione predefinita per facilitare l'accesso agli utenti finali. Per gli operatori sul campo, sono disponibili e aggiunti solo le attività, i turni, la chat e le chiamate. Gli amministratori possono modificare questo comportamento predefinito usando [i criteri di configurazione](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Le app di base sono costituite dalle app aggiunte in Teams per impostazione predefinita." lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>App create da Microsoft

Microsoft offre numerose app per migliorare la produttività e la collaborazione. Queste app possono essere individuate dall'utente e dagli utenti finali cercando Microsoft come autore nell'interfaccia di amministrazione di Teams o come Provider nello store di Teams.

Teams include un set di app predefinite, tra cui Elenchi, Tasks, Complimento, Approvazioni e altro ancora. Si consiglia di includere le app in evidenza, come Planner, nel lancio iniziale di Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Screenshot che mostra un elenco di app Microsoft nell'interfaccia di amministrazione di Teams." lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>App di terze parti create da sviluppatori di app indipendenti

Oltre alle app fornite da Microsoft, è possibile usare app di terze parti. Microsoft convalida in modo rigoroso la funzionalità e la sicurezza di tutte queste app. I test manuali e automatizzati elaborati vengono eseguiti prima di rendere queste app disponibili in Teams Store e molti test continuano a una cadenza regolare anche dopo la pubblicazione delle app in tempo reale. Per informazioni sui vantaggi della convalida delle app, vedere [Convalida di app di terze parti](overview-of-app-validation.md). Alcune app sottoscrivono il programma di [conformità Microsoft](overview-of-app-certification.md) per essere sottoposte a più livelli di ulteriori controlli oltre la convalida.

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Screenshot di un esempio di app di terze parti presenti nello store di Teams.":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>App personalizzate create all'interno di un'organizzazione per uso interno

Le app create dagli sviluppatori dell'organizzazione sono denominate app personalizzate. (o Line-of-business app). L'organizzazione può richiedere la creazione di app personalizzate per requisiti specifici dell'organizzazione. Hai il controllo per consentire o bloccare tali app per l'intera organizzazione o per utenti specifici. Gli sviluppatori nell'organizzazione possono compilare soluzioni personalizzate con basso impiego di codice usando l'integrazione di Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Dopo che un amministratore consente l'uso di app personalizzate, gli utenti finali possono trovare tali app selezionando **Creato per l'organizzazione** nel riquadro di spostamento sinistro di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Schermata delle app personalizzate nello store di Teams nell'app desktop di Teams." lightbox="media/built-for-your-org2.png":::

Per altre informazioni, vedere [Comprendere e gestire le app personalizzate e trasferite localmente](custom-app-overview.md).

## <a name="about-app-templates"></a>Informazioni sui modelli di app

Usando i metodi di sviluppo delle app, Microsoft crea e fornisce app di esempio funzionali e pronte per la produzione. Collettivamente, queste app sono denominate modelli di app per Teams e sono fornite per:

* Illustrare alcuni casi di utilizzo della collaborazione in Teams.
* Metti in mostra le procedure consigliate e i metodi per lo sviluppo di app.
* Fornisci app open source che gli sviluppatori possono estendere per creare le proprie app.

Gli sviluppatori dell'organizzazione personalizzano i modelli di app con semplici modifiche al codice sorgente fornito. Queste app vengono fornite come app personalizzate per gli utenti finali, per soddisfare qualsiasi esigenza dell'organizzazione.

Per altre informazioni, vedere [Modelli di app di Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Informazioni sulle funzionalità delle app

Le funzionalità dell'app Teams sono le funzionalità principali che possono essere integrate in un'app per consentire l'integrazione e l'interazione.

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Immagine che mostra le funzionalità dell'app di un'app di Microsoft Teams." border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

Per offrire un'esperienza completa che consenta agli utenti finali di lavorare all'interno di Teams, gli sviluppatori di app creano app utilizzando le funzionalità seguenti:

* **Bot**: i bot sono anche chiamati chatbot o bot conversazionali. Si tratta di un'app che esegue attività semplici e ripetitive. L'interazione con un bot può essere una domanda e una risposta rapide oppure una conversazione complessa che fornisce accesso a servizi o assistenza. Gli utenti possono avere una conversazione con un bot in una chat personale, un canale o una chat di gruppo. Per altre informazioni, vedere [Bot in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots).

  Teams supporta i bot all'interno di chat e canali privati. Gli amministratori possono controllare se in un’organizzazione di Microsoft 365 o Office 365 è consentito l'uso di bot. Per informazioni sull'attivazione o la disattivazione dei bot personalizzati, vedere [Panoramica della gestione e della governance delle app nell'interfaccia di amministrazione di Teams](manage-apps.md).

* **Schede**: Le schede sono pagine Web con supporto per Teams aggiunte nella parte superiore di un canale o di una chat. Le schede consentono di interagire con contenuti e servizi con un'esperienza simile al Web. Si tratta di semplici tag html <iframe\> che puntano ai domini dichiarati nel manifesto dell'app e possono essere aggiunti come parte di un canale all'interno di un team, una chat di gruppo o un'app personale per un singolo utente. Per altre informazioni, vedere [le schede di Microsoft Teams](/microsoftteams/platform/tabs/what-are-tabs).

  In ogni chat privata, le schede Conversazioni, File, Organizzazione e Attività vengono create per impostazione predefinita. Oltre a queste schede predefinite, gli sviluppatori possono progettare e aggiungere schede personalizzate. Per altre informazioni, vedere [Usare schede predefinite e personalizzate in Teams](/microsoftteams/platform/tabs/what-are-tabs).

* **Webhook e connettori**: Webhook e connettori consentono di connettere i servizi Web a canali e team in Microsoft Teams. Webhooks sono callback HTTP definito dall'utente che notifica agli utenti qualsiasi azione che è stata eseguita nel canale Teams. È un modo per un'app di ottenere dati in tempo reale. I connettori consentono agli utenti di abbonarsi per ricevere notifiche e messaggi dai servizi Web. Per altre informazioni, vedere [Webhook e connettori](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors).

  Per consentire agli utenti di usare connettori personalizzati in Teams, vedere [Usare connettori personalizzati in Teams](office-365-custom-connectors.md).

* **Estensioni di messaggistica**: le estensioni di messaggistica sono collegamenti per inserire il contenuto dell'app o per agire su un messaggio senza che gli utenti finali debba uscire dalla conversazione. Gli utenti possono eseguire ricerche o avviare azioni in un sistema esterno dall'area di composizione del messaggio, dalla casella di comando o direttamente da un messaggio. Per altre informazioni, vedere [Estensioni dei messaggi](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet).

* **Estensioni delle riunioni**: gli utenti possono migliorare l'esperienza delle riunioni integrando schede, bot ed estensioni di messaggi all'interno delle riunioni e aumentando la produttività delle riunioni. È possibile identificare i vari ruoli e tipi di utente dei partecipanti, ricevere eventi di riunione e generare finestre di dialogo in riunione. Per altre informazioni, vedere [Riunioni di App per Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings).

* **Schede e moduli attività**: le schede forniscono agli utenti vari messaggi visivi, audio e selezionabili e aiutano nel flusso delle conversazioni. I moduli attività consentono di creare esperienze popup modali in Microsoft Teams. Sono utili per iniziare e completare le attività o per visualizzare informazioni complete, ad esempio video o dashboard di Power Business Intelligence (BI). Per altre informazioni, vedere [Schede e moduli attività](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules).

Per visualizzare i casi d'uso comuni mappati alle funzionalità di Teams, vedere [Mappare i casi d'uso alle funzionalità dell'app Teams](/microsoftteams/platform/concepts/design/map-use-cases).

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->

## <a name="related-articles"></a>Articoli correlati

* [Altre informazioni sui modelli di app per Teams](/microsoftteams/platform/samples/app-templates).

* [Panoramica della gestione e della governance delle app nell'interfaccia di amministrazione di Teams](manage-apps.md)

* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
