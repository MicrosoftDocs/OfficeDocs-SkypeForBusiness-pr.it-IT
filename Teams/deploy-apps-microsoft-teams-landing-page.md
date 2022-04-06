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
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8579d7c2c49749058c174aa71430803dce63286
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643020"
---
# <a name="about-apps-in-microsoft-teams"></a>Informazioni sulle app in Microsoft Teams

Le app sono un ottimo modo per riunire gli strumenti e i servizi del luogo di lavoro e collaborare con altri utenti. Le app aiutano gli utenti finali a essere più produttivi, collaborativi ed efficaci nelle loro attività quotidiane. Le organizzazioni usano le app per connettersi con i clienti, fornire servizi e condividere informazioni. Le app consentono agli utenti di essere più efficaci Teams chat, riunioni e canali. Esempi sono gli utenti finali che usano un calendario aggiunto in Teams per collaborare rapidamente con altri utenti, un'app con funzionalità di bot che informano gli utenti di QoS di un servizio Web in un canale Teams e un'app per condividere e assegnare attività a vari utenti finali in un canale.

La nostra vasta selezione di app convalidate e sicure nello Store offre agli utenti finali l'accesso agli strumenti e ai servizi di cui l'organizzazione ha bisogno ogni giorno. Microsoft Teams sono app SaaS basate sul Web che non devono essere distribuite. Gli utenti finali possono usare le app in Teams solo in base alle autorizzazioni fornite dall'utente. L'amministratore approva o blocca l'uso di qualsiasi app per gli utenti dell'organizzazione. Puoi controllare la disponibilità di app per tutti gli utenti in riunioni, chat e canali.

Per fornire agli utenti finali le app necessarie, continua a leggere per comprendere i tipi di app e la posizione in cui gli utenti accedono a tali app. Per altre informazioni sull'uso delle app, vedere [Panoramica delle app per gli utenti finali](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

I diversi tipi di app che gli utenti finali possono usare in Teams sono:

* [App di base che fanno parte di Teams](#core-apps).
* Altre [app create da Microsoft](#microsoft-provided-apps).
* [App di terze parti](#third-party-apps-validated-by-microsoft) da partner (convalidate da Microsoft).
* [App personalizzate](#custom-apps) create dalla propria organizzazione.

## <a name="core-apps"></a>App di base

Alcune funzionalità predefinite, ad esempio feed attività, canali di Teams, chat, calendario e chiamate, sono disponibili e aggiunte per impostazione predefinita per facilitare l'accesso per gli utenti finali. Gli amministratori possono modificare il comportamento predefinito usando i criteri [di configurazione](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Le app di base sono le app aggiunte in Teams per impostazione predefinita." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>App fornite da Microsoft

Microsoft fornisce molte app per migliorare la produttività e la collaborazione. L'utente e gli utenti finali possono trovare queste app cercando Microsoft elencato come Publisher nell'interfaccia di amministrazione o elencato come provider nel Team Store.

Teams include un set di app predefinite, tra cui Elenchi, Tasks, Complimento, Approvazioni e altro ancora. È consigliabile includere le app in primo piano di Teams, come ad esempio Planner, nell'implementazione iniziale di Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="App Microsoft nell'Teams di amministrazione" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>App di terze parti convalidate da Microsoft

Oltre alle app fornite da Microsoft, è possibile usare app di terze parti convalidate da Microsoft. Microsoft convalida le funzionalità e la sicurezza di queste app prima di renderle disponibili in Teams Store.

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Esempio di app di terze parti in Teams Store":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>App personalizzate

Le app create dagli sviluppatori nell'organizzazione sono denominate app personalizzate. Lo sviluppo di un'app di questo tipo è commissionato per requisiti specifici dell'organizzazione e sono disponibili controlli per consentire o disattivare tali app. Gli sviluppatori dell'organizzazione possono creare rapidamente soluzioni personalizzate a basso codice usando l'Teams con [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Quando un amministratore consente l'uso di app personalizzate, gli utenti finali trovano queste app facendo  clic su Creato per l'organizzazione nella barra di spostamento sinistra di Teams Store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="App personalizzate in Teams store in Teams desktop" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Informazioni sul sideload delle app personalizzate

Quando si sviluppano app personalizzate e prima di distribuirla agli utenti finali, gli sviluppatori testano le app aggiungendola allo store per testarla da sola o testando con un team in cui l'app viene affiancata. Questo metodo è denominato sideload delle app e si applica solo alle app personalizzate.

Gli sviluppatori possono sideload di un'app per renderla disponibile ai membri di un team specifico, in genere per testare un'app in fase di sviluppo. Questa operazione non richiede l'approvazione dell'amministratore se è consentito il sideload. Gli amministratori possono non consentire il sideload per qualsiasi sviluppatore.

Se si non consente il sideload, gli sviluppatori possono comunque testare le loro app in un [tenant di test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una volta completato lo sviluppo di app personalizzate, gli sviluppatori richiedono agli amministratori di distribuire l'app personalizzata agli utenti finali. Per informazioni dettagliate, [vedere come pubblicare un'app personalizzata](/microsoftteams/upload-custom-apps). Gli amministratori possono consentire o non consentire l'uso di un'app personalizzata per utenti specifici.

### <a name="about-app-templates"></a>Informazioni sui modelli di app

I modelli di app per Teams sono app di esempio funzionali e pronte per la produzione create da Microsoft per illustrare i casi d'uso più diffusi, presentare le procedure consigliate per lo sviluppo di app e fornire app open source che gli sviluppatori possono estendere per creare app personalizzate. Gli sviluppatori dell'organizzazione personalizzano i modelli di app in base alle esigenze dell'organizzazione con semplici modifiche al codice disponibile in GitHub. L'amministratore fornisce queste app come app personalizzate per gli utenti finali.

Per altre informazioni, vedere Modelli [Microsoft Teams app](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Informazioni sulle funzionalità dell'app

Le app di messaggistica includono il contenuto di un'app in un canale o in una chat. Le app di estendibilità delle riunioni integrano le app di uno sviluppatore all'interno delle riunioni e offrono un'esperienza reattiva durante le riunioni. Per fornire varie funzionalità, gli sviluppatori di app sfruttano le funzionalità dell'app seguenti.

I bot forniscono risposte, aggiornamenti e assistenza. Puoi chattare con questi utenti uno-a-uno o all'interno di un canale. Possono essere utili per la gestione delle attività, la programmazione e altro ancora. Ad esempio, è possibile usare l'app Polly per creare sondaggi rapidi, ottenere feedback ed eseguire un controllo a polso.

Le schede aggiunte nella parte superiore di un canale consentono di interagire con contenuti e servizi con un'esperienza simile al Web.
I connettori forniscono contenuti e aggiornamenti dai servizi usati di frequente (ad esempio Jira Cloud e Bitbucket) direttamente in una conversazione di canale.

Le estensioni di messaggistica sono scelte rapide da tastiera per inserire contenuto dell'app o per agire su un messaggio senza che gli utenti finali siano in grado di allontanarsi dalla conversazione. Le estensioni di messaggistica possono contenere comandi di ricerca per gli utenti finali per trovare rapidamente contenuto esterno e inserirlo in un messaggio o in comandi di azione.

Per visualizzare i casi di utilizzo comuni mappati alle funzionalità Teams, vedere Eseguire il mapping dei casi di utilizzo alle Teams [delle app](/microsoftteams/platform/concepts/design/map-use-cases).

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
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
