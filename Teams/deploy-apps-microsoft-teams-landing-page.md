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
ms.openlocfilehash: 9b8d4ca3140b6bd8907938b5c2ac86aeabb39e37
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912625"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>Comprendere le app di Microsoft Teams e le relative funzionalità

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

## <a name="related-articles"></a>Articoli correlati

* [Altre informazioni sui modelli di app per Teams](/microsoftteams/platform/samples/app-templates)
* [Panoramica della gestione e della governance delle app nell'interfaccia di amministrazione di Teams](manage-apps.md)
