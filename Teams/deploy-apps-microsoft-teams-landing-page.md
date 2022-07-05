---
title: Informazioni sulle app in Microsoft Teams
ms.reviewer: ''
description: Scoprire le app e decidere quali app consentire in Teams in base al profilo dell’organizzazione e ai requisiti aziendali.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.subservice: teams-apps
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: f802506ff815745aaf555501e37171ebddfc7f91
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615862"
---
# <a name="about-apps-in-microsoft-teams"></a>Informazioni sulle app in Microsoft Teams

Le app sono un ottimo modo per riunire gli strumenti e i servizi del luogo di lavoro e collaborare con altri utenti. Le app consentono agli utenti finali di essere più produttivi, collaborativi ed efficaci nelle attività quotidiane. Le organizzazioni usano le app per connettersi con i propri clienti, fornire servizi e condividere informazioni. Le app consentono agli utenti di essere più efficaci nelle chat, nelle riunioni e nei canali di Teams. Alcuni esempi sono costituiti da utenti finali che usano un calendario aggiunto in Teams per collaborare rapidamente con altri utenti, un'app con funzionalità bot che informa gli utenti di QoS di un servizio Web in un canale di Teams e un'app per condividere e assegnare attività a vari utenti finali in un canale.

La nostra ampia selezione di app nello store, convalidate e sicure, fornisce agli utenti finali l'accesso agli strumenti e ai servizi di cui l'organizzazione ha bisogno ogni giorno. Le app di Microsoft Teams sono app SaaS basate sul Web che non devono essere distribuite. Gli utenti finali possono usare tali app in Teams solo in base alle [autorizzazioni](https://admin.teams.microsoft.com/policies/app-permission) fornite dall'utente. Gli amministratori approvano o bloccano semplicemente l'uso di qualsiasi app per gli utenti dell'organizzazione. È possibile controllare la disponibilità delle app per tutti gli utenti nelle riunioni, nelle chat e nei canali.

Per fornire agli utenti finali le app di cui hanno bisogno, continuare a leggere per comprendere i tipi di app e la posizione in cui gli utenti accedono a tali app. Per altre informazioni sull'uso delle app, vedere [Panoramica delle app per gli utenti finali](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

I diversi tipi di app che gli utenti finali possono usare in Teams sono:

* [App di base che fanno parte di Teams](#core-apps).
* Altre [app create da Microsoft](#microsoft-provided-apps).
* [App di terze parti](#third-party-apps-validated-by-microsoft) dei partner (convalidate da Microsoft).
* [App personalizzate](#custom-apps) create dalla propria organizzazione.

## <a name="core-apps"></a>App di base

Alcune funzionalità predefinite, come il feed attività, i canali di Teams, le chat, il calendario e le chiamate, sono disponibili e aggiunte per impostazione predefinita per facilitare l'accesso agli utenti finali. Gli amministratori possono modificare il comportamento predefinito usando [i criteri di configurazione](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Le app di base sono costituite dalle app aggiunte in Teams per impostazione predefinita." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>App fornite da Microsoft

Microsoft offre numerose app per migliorare la produttività e la collaborazione. Queste app possono essere individuate dall'utente e dagli utenti finali cercando Microsoft come autore nell'interfaccia di amministrazione o come Provider in Team Store.

Teams include un set di app predefinite, tra cui Elenchi, Tasks, Complimento, Approvazioni e altro ancora. È consigliabile includere le app in primo piano di Teams, come ad esempio Planner, nell'implementazione iniziale di Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="App di Teams nell'interfaccia di amministrazione di Microsoft Teams" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>App di terze parti convalidate da Microsoft

Oltre alle app fornite da Microsoft, è possibile usare app di terze parti convalidate da Microsoft. Microsoft convalida le funzionalità e la sicurezza di queste app prima di renderle disponibili in Teams Store. Per informazioni sui vantaggi della convalida delle app, vedere [Convalida di app di terze parti](overview-of-app-validation.md).

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Esempio di app di terze parti in Teams Store":::

## <a name="custom-apps"></a>App personalizzate

Le app create dagli sviluppatori dell'organizzazione sono denominate app personalizzate. Lo sviluppo di un'app di questo tipo è stato commissionato per requisiti specifici dell'organizzazione e si dispone dei controlli per consentire o disabilitare tali app. Gli sviluppatori nell'organizzazione possono compilare rapidamente soluzioni personalizzate con basso impiego di codice usando l'integrazione di Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Dopo che un amministratore consente l'uso di app personalizzate, gli utenti finali possono trovare tali app facendo clic su **Creato per l'organizzazione** nel riquadro di spostamento sinistro di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="App personalizzate in Teams Store nell'app desktop Teams" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Informazioni sul trasferimento locale di app personalizzate

Durante lo sviluppo di app personalizzate e prima di distribuirle agli utenti finali, gli sviluppatori testano tali app aggiungendole allo Store per testarle autonomamente o con un team in cui ne eseguono il trasferimento locale. Questo metodo è detto trasferimento locale delle app e si applica solo alle app personalizzate.

Gli sviluppatori possono trasferire localmente un'app per renderla disponibile ai membri di un team specifico, in genere per testarla in fase di sviluppo. Ciò non richiede l'approvazione dell'amministratore se è consentito il trasferimento locale. L'amministratore puoi impedire il trasferimento locale per qualsiasi sviluppatore.

Se il trasferimento locale non è consentito, gli sviluppatori possono comunque testare le proprie app in un [tenant di test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una volta completato lo sviluppo di app personalizzate, gli sviluppatori richiedono agli amministratori di distribuire l'app personalizzata agli utenti finali. Per informazioni dettagliate, vedere [come pubblicare un'app personalizzata](/microsoftteams/upload-custom-apps). Gli amministratori possono consentire o impedire l'uso di un'app personalizzata per utenti specifici.

### <a name="about-app-templates"></a>Informazioni sui modelli di app

I modelli di app per Teams sono app di esempio funzionali pronte per la produzione create da Microsoft per illustrare casi d'uso comuni, per presentare procedure consigliate per lo sviluppo di app e per fornire app open source che gli sviluppatori estendono per creare app personalizzate. Gli sviluppatori personalizzano i modelli di app per le esigenze dell'organizzazione con semplici modifiche al codice disponibile in GitHub. L'amministratore offre queste app come app personalizzate agli utenti finali.

Per altre informazioni, vedere [Modelli di app di Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Informazioni sulle funzionalità delle app

Per offrire esperienze avanzate che consentano agli utenti finali di lavorare all'interno di Teams, gli sviluppatori di app sfruttano le funzionalità seguenti. Le estensioni di messaggistica consentono agli utenti di interagire con il client Teams del servizio Web. Gli utenti cercano o avviano azioni in un sistema esterno. È possibile inviare il risultato dell'interazione al client di Teams come scheda con formattazione avanzata. Le app per l'estensibilità delle riunioni integrano le app di uno sviluppatore all'interno delle riunioni e offrono un'esperienza reattiva durante le riunioni.

I bot sono anche chiamati chatbot o bot conversazionali. Si tratta di un'app che esegue attività semplici e ripetitive. L'interazione con un bot può essere una domanda e una risposta rapide oppure una conversazione complessa che fornisce accesso a servizi o assistenza. Gli utenti possono chattare con in modo individuale o in un canale. Ad esempio, è possibile usare l'app Polly per creare sondaggi rapidi, ottenere feedback e controllare l'impulso.

Le schede sono pagine Web con compatibili con Teams aggiunte nella parte superiore di un canale o di una chat. Le schede consentono di interagire con contenuti e servizi con un'esperienza simile al Web. È possibile aggiungere schede come parte di un canale all'interno di un team, una chat di gruppo o un'app personale per un singolo utente.

Webhook e connettori forniscono contenuti e aggiornamenti dai servizi usati di frequente dagli utenti finali (come Jira Cloud e Bitbucket) direttamente in una conversazione del canale. Le app che usano questa funzionalità possono comunicare con app esterne e inviare o ricevere notifiche e messaggi da un servizio esterno.

Le estensioni di messaggistica sono collegamenti per inserire il contenuto dell'app o agire su un messaggio senza che gli utenti finali escano dalla conversazione. Le estensioni di messaggistica possono avere comandi di ricerca che consentono agli utenti finali di trovare rapidamente contenuti esterni e inserirli in un messaggio o in un comando di azione.

Per visualizzare i casi di utilizzo comuni mappati alle funzionalità di Teams, vedere [Mappare i casi d'uso alle funzionalità dell'app Teams](/microsoftteams/platform/concepts/design/map-use-cases).

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
