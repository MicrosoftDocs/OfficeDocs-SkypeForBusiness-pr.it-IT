---
title: Usare l'API di invio di app teams per inviare e approvare le app personalizzate
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come approvare le app personalizzate inviate con l'API di invio di app teams in Microsoft teams.
ms.openlocfilehash: bdd13dbe4db46110250ea380eebd0ea1d011a322
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824917"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams

## <a name="overview"></a>Panoramica

> [!NOTE]
> Quando pubblichi un'app teams personalizzata, è disponibile per gli utenti nell'App Store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui si usa dipende da come si ottiene l'app. **Questo articolo illustra come approvare e pubblicare un'app personalizzata che uno sviluppatore Invia tramite l'API di invio di app teams**. L'altro metodo, che carica un'app personalizzata, viene usato quando uno sviluppatore Invia un pacchetto dell'app in formato zip. Per altre informazioni su questo metodo, vedere <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">pubblicare un'app personalizzata caricando un pacchetto dell'app</a>.
 
Questo articolo fornisce indicazioni complete su come portare l'app teams dallo sviluppo alla distribuzione all'individuazione. Otterrai una panoramica delle esperienze connesse che il team offre in tutto il ciclo di vita dell'app per semplificare la creazione, la distribuzione e la gestione di app personalizzate nell'App Store dell'organizzazione.

Verranno illustrati i passaggi del ciclo di vita, incluso il modo in cui gli sviluppatori possono usare l'API di invio delle app teams per inviare app personalizzate direttamente all'interfaccia di amministrazione di Microsoft teams per la revisione e l'approvazione, come impostare i criteri per la gestione delle app per gli utenti dell'organizzazione e il modo in cui gli utenti li scoprono in teams.

![Panoramica della tua app dallo sviluppo alla distribuzione](media/custom-app-lifecycle.png)

Questa guida si basa sugli aspetti relativi ai team dell'app ed è destinata ad amministratori e professionisti IT. Per informazioni su come sviluppare le app per Team, vedi la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione per sviluppatori teams</a>.

## <a name="develop"></a>Sviluppo

### <a name="create-the-app"></a>Creare l'app

La piattaforma Microsoft teams per sviluppatori consente agli sviluppatori di integrare facilmente le tue app e i tuoi servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app create nella piattaforma teams sono ponticelli tra il client teams e i servizi e i flussi di lavoro, che li portano direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione relativa allo sviluppatore di teams</a>.

### <a name="submit-the-app"></a>Inviare l'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore può inviare l'app usando l'API di invio dell'app teams, che può essere chiamata dall' <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">API del grafico</a>, da un ambiente di sviluppo integrato (IDE), come il codice di Visual Studio, o da una piattaforma come Power Apps e Power Virtual Agents. In questo modo l'app è disponibile nella pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app</a> dell'interfaccia di amministrazione di Microsoft teams, in cui l'amministratore può rivederlo e approvarlo. 

L'API di invio delle app teams, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">basata su Microsoft Graph</a>, consente all'organizzazione di svilupparsi sulla piattaforma di tua scelta e automatizza il processo di approvazione per le app personalizzate in teams.

Ecco un esempio di come si presenta il passaggio di presentazione dell'app nel codice di Visual Studio:

![Screenshot dell'invio di un'app nel codice di Visual Studio](media/custom-app-lifecycle-submit-app.png)

Tieni presente che l'app non viene ancora pubblicata nell'App Store dell'organizzazione. Questo passaggio invia l'app all'interfaccia di amministrazione di Microsoft teams in cui è possibile approvarla per la pubblicazione nell'App Store dell'organizzazione.

Per altre informazioni sull'uso dell'API del grafico per inviare app, Vedi <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">qui</a>.

## <a name="validate"></a>Convalidare

La pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app</a> nell'interfaccia di amministrazione di Microsoft Teams (nella barra di spostamento sinistra passa a **app teams**  >  **Manage Apps**), consente di visualizzare tutte le app teams per l'organizzazione. Il widget **approvazione in sospeso** nella parte superiore della pagina consente di sapere quando un'app personalizzata viene inviata per l'approvazione.

Nella tabella un'app appena presentata Mostra automaticamente **lo stato di pubblicazione** della **presentazione** e **lo stato** del **blocco**. Puoi ordinare la colonna **stato pubblicazione** in ordine decrescente per trovare rapidamente l'app.

![Screenshot della pagina Manage Apps che mostra le richieste in sospeso e lo stato dell'app ](media/custom-app-lifecycle-validate-app.png)

Fare clic sul nome dell'app per accedere alla pagina dei dettagli dell'app. Nella scheda **informazioni** è possibile visualizzare i dettagli relativi all'app, inclusi descrizione, stato, mittente e ID app.

![Screenshot della pagina dei dettagli dell'app per un'app inviata](media/custom-app-lifecycle-app-details.png)

Per altre informazioni sull'uso dell'API del grafico per verificare lo **stato di pubblicazione**, vedere <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">qui</a>.

## <a name="publish"></a>Pubblicare

Quando sei pronto per rendere l'app disponibile agli utenti, pubblica l'app.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Fare clic sul nome dell'app per accedere alla pagina dei dettagli dell'app e quindi nella casella **stato pubblicazione** selezionare **pubblica**.

    Dopo aver pubblicato l'app, lo **stato di pubblicazione** viene modificato in **Published** e lo **stato** viene modificato automaticamente in **allowed**.

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'App Store dell'organizzazione. Per limitare e controllare chi ha l'autorizzazione per l'uso dell'app, puoi creare e assegnare un criterio di autorizzazione per le app. Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gestire i criteri di autorizzazione delle app in teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per individuare gli utenti

Per impostazione predefinita, gli utenti possono trovare l'app che devono passare all'App Store dell'organizzazione e cercarla. Per semplificare l'accesso all'app da parte degli utenti, puoi aggiungere l'app alla barra dell'app in teams. A questo scopo, crea un criterio di configurazione dell'app e assegnalo agli utenti. Per altre informazioni, Vedi <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gestire i criteri di configurazione delle app in teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Eseguire ricerche nel log di controllo per gli eventi delle app Teams

È possibile eseguire una ricerca nel log di controllo per visualizzare l'attività delle app teams nell'organizzazione. Per altre informazioni su come eseguire una ricerca nel log di controllo e visualizzare un elenco di attività di Team registrate nel log di controllo, vedere <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">eseguire la ricerca nel log di controllo per gli eventi in teams</a>.

Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel <a href="https://protection.office.com" target="_blank">centro conformità & sicurezza</a>. Per altre informazioni, vedere <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">attivare o disattivare la ricerca nel log di controllo</a>. Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.

## <a name="discover-and-adopt"></a>Individuare e adottare

Gli utenti che hanno le autorizzazioni per l'app possono trovarlo nell'App Store dell'organizzazione. Passa a **compilato per *il nome dell'organizzazione* ** nella pagina app per trovare le app personalizzate dell'organizzazione.

![Screenshot della pagina app che mostra l'app pubblicata ](media/custom-app-lifecycle-discovery.png)

Se hai creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in teams per facilitare l'accesso agli utenti a cui è stato assegnato il criterio.

## <a name="update"></a>Aggiornamento

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi della sezione [sviluppo](#develop) .

Quando lo sviluppatore Invia un aggiornamento a un'app personalizzata pubblicata, riceverai una notifica nel widget **approvazione in sospeso** della pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app</a> . Nella tabella lo stato di **pubblicazione** dell'app verrà impostato su **Update inviato**.

![Screenshot della pagina Manage Apps che mostra le richieste in sospeso e lo stato dell'app ](media/custom-app-lifecycle-update-submitted.png)

Per rivedere e pubblicare un aggiornamento di un'app:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare **Aggiorna disponibile** per rivedere i dettagli dell'aggiornamento.

    ![Screenshot della pagina Manage Apps che mostra le richieste in sospeso e lo stato dell'app ](media/custom-app-lifecycle-update-app.png)
3. Quando si è pronti, selezionare **pubblica** per pubblicare l'aggiornamento. Questa operazione sostituisce l'app esistente, aggiorna il numero di versione e lo **stato di pubblicazione** viene modificato in **Published**. Tutti i criteri di autorizzazione per le app e i criteri di configurazione delle app restano applicati per l'app aggiornata.

    Se si rifiuta l'aggiornamento, la versione precedente dell'app rimane pubblicata.

Tieni presente quanto segue:

- Quando un'app viene approvata, una qualsiasi può inviare un aggiornamento all'app. Questo significa che altri sviluppatori, incluso lo sviluppatore che ha originariamente inviato l'app, possono inviare un aggiornamento all'app.
- Quando uno sviluppatore Invia un'app e la richiesta è in sospeso, solo lo stesso sviluppatore può inviare un aggiornamento all'app. Altri sviluppatori possono inviare un aggiornamento solo dopo che l'app è stata approvata.

Per altre informazioni sull'uso dell'API del grafico per aggiornare le app, Vedi <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">qui</a>.

### <a name="update-experience-for-users"></a>Esperienza di aggiornamento per gli utenti

Nella maggior parte dei casi, dopo la pubblicazione di un aggiornamento di un'app, la nuova versione viene visualizzata automaticamente per gli utenti. Tuttavia, esistono alcuni aggiornamenti al manifesto di <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft teams</a> che richiedono l'accettazione da parte dell'utente:

* È stato aggiunto o rimosso un bot
* Modifica della proprietà "botId" di un bot esistente
* Modifica della proprietà "isNotificationOnly" di un bot esistente
* La proprietà "supportsFiles" del bot è cambiata
* È stata aggiunta o rimossa un'estensione della messaggistica
* È stato aggiunto un nuovo connettore
* È stata aggiunta una nuova scheda statica
* È stata aggiunta una nuova scheda configurabile
* Proprietà all'interno di "webApplicationInfo" modificate

![Screenshot che mostra le app che hanno una nuova versione disponibile](media/manage-your-custom-apps-update1.png)

![Screenshot dell'opzione di aggiornamento per un'app](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Argomenti correlati

- [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">API Microsoft Graph per le app Teams</a>
