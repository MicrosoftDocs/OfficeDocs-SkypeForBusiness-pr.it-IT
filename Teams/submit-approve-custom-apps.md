---
title: Usare l'API Teams di invio delle app per inviare e approvare le app personalizzate
author: cichur
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come approvare le app personalizzate inviate con l'API Teams per l'invio di app in Microsoft Teams.
ms.openlocfilehash: ff115ab34c30bf2acfc7f24407045c1d44c4eade
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745512"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Pubblicare un'app personalizzata inviata tramite l'API Teams per l'invio di app

## <a name="overview"></a>Panoramica

> [!NOTE]
> Quando si pubblica un'app di Teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui si usa dipende da come si ottiene l'app. **Questo articolo illustra come approvare** e pubblicare un'app personalizzata che uno sviluppatore invia tramite l'API Teams di invio delle app. L'altro metodo, il caricamento di un'app personalizzata, viene usato quando uno sviluppatore invia un pacchetto dell'app in .zip formato. Per altre informazioni su questo metodo, vedere <a href="/microsoftteams/upload-custom-apps" target="_blank">Pubblicare un'app personalizzata caricando un pacchetto dell'app.</a> Il widget approva app non è disponibile nei tenant GCC app. 

> [!IMPORTANT]
> Questo metodo non è attualmente disponibile per gli GCC locali. È necessario usare il *metodo di caricamento di un'app* personalizzata.

Questo articolo fornisce indicazioni end-to-end su come portare l'app Teams dallo sviluppo alla distribuzione all'individuazione. Si otterrà una panoramica delle esperienze connesse Teams nel ciclo di vita dell'app per semplificare le procedure di sviluppo, distribuzione e gestione di app personalizzate nell'app store dell'organizzazione.

Verranno esaminati tutti i passaggi del ciclo di vita, incluso il modo in cui gli sviluppatori possono usare l'API di invio delle app di Teams per inviare app personalizzate direttamente all'interfaccia di amministrazione di Microsoft Teams per poterle rivedere e approvare, come impostare criteri per gestire le app per gli utenti dell'organizzazione e come vengono individuate dagli utenti in Teams.

![Panoramica dell'app, dallo sviluppo alla distribuzione.](media/custom-app-lifecycle.png)

Questa guida è incentrata sugli aspetti Teams'app ed è destinata agli amministratori e ai professionisti IT. Per informazioni sullo sviluppo di Teams app, vedere la documentazione <a href="/microsoftteams/platform" target="_blank">Teams per sviluppatori.</a>

## <a name="develop"></a>Sviluppo

### <a name="create-the-app"></a>Creare l'app

La Microsoft Teams per sviluppatori consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più rapidamente e creare collaborazione su contenuti e flussi di lavoro esistenti. Le app create sulla piattaforma Teams sono ponti tra il client Teams e i servizi e i flussi di lavoro, che le portano direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la documentazione Teams <a href="/microsoftteams/platform" target="_blank">per sviluppatori.</a>

### <a name="submit-the-app"></a>Inviare l'app

Quando l'app è pronta per l'uso nell'ambiente di produzione, lo sviluppatore può inviare l'app usando l'API di invio dell'app Teams, che può essere chiamata [dall'API Graph](/graph/api/teamsapp-publish), da un ambiente di sviluppo integrato (IDE) come Visual Studio Code o da una piattaforma come Power Apps e Power Virtual Agents. In questo modo l'app sarà disponibile nella pagina Gestisci <a href="/microsoftteams/manage-apps" target="_blank">app</a> dell'interfaccia di amministrazione di Microsoft Teams, in cui l'amministratore potrà rivedirla e approvarla.

L'API di invio delle app di Teams, basata su <a href="/graph/api/teamsapp-publish" target="_blank">Microsoft Graph,</a>consente all'organizzazione di svilupparsi sulla piattaforma scelta e automatizza il processo di invio all'approvazione per le app personalizzate in Teams.

Ecco un esempio dell'aspetto di questo passaggio di invio dell'app in Visual Studio Code:

![invio di un'app in Visual Studio Code.](media/custom-app-lifecycle-submit-app.png)

Tenere presente che l'app non viene ancora pubblicata nell'app store dell'organizzazione. Questo passaggio invia l'app all'interfaccia Microsoft Teams di amministrazione, dove è possibile approvarla per la pubblicazione nell'app store dell'organizzazione.

Per altre informazioni sull'uso dell'API Graph per inviare app, vedere <a href="/graph/api/teamsapp-publish" target="_blank">qui</a>.

## <a name="validate"></a>Convalida

La <a href="/microsoftteams/manage-apps" target="_blank">pagina</a> Gestisci app nell'interfaccia di amministrazione di Microsoft Teams (nel riquadro di spostamento sinistro passare **Teams app** Gestisci  >  **app)** offre una visualizzazione di tutte le app Teams per l'organizzazione. Il widget **Approvazione** in sospeso nella parte superiore della pagina indica quando un'app personalizzata viene inviata per l'approvazione.

Nella tabella, un'app appena  inviata mostra automaticamente lo stato Di pubblicazione **inviato** e **lo stato** **Bloccato**. È possibile ordinare la **colonna Stato pubblicazione** in ordine decrescente per trovare rapidamente l'app.

![stato di pubblicazione .](media/custom-app-lifecycle-validate-app.png)

Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app. Nella scheda **Informazioni** è possibile visualizzare i dettagli sull'app, tra cui descrizione, stato, mittente e ID app.

![pagina dei dettagli dell'app per un'app inviata.](media/custom-app-lifecycle-app-details.png)

Per altre informazioni sull'uso dell'API Graph per controllare lo **stato di pubblicazione,** vedere <a href="/graph/api/appcatalogs-list-teamsapps" target="_blank">qui</a>.

## <a name="publish"></a>Pubblica

Quando si è pronti per rendere disponibile l'app agli utenti, pubblicare l'app.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi nella casella **Stato pubblicazione** selezionare **Pubblica.**

    Dopo la pubblicazione dell'app, lo stato **della** pubblicazione viene modificato in **Pubblicato** e **lo stato** viene automaticamente modificato in **Consentito**.

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare gli utenti autorizzati a usare l'app, è possibile creare e assegnare criteri di autorizzazione per l'app. Per altre informazioni, vedere <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Gestire i criteri di autorizzazione delle app in teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire agli utenti di individuare

Per impostazione predefinita, gli utenti possono trovare l'app che devono accedere all'app store dell'organizzazione e cercarla o cercarla. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Gestire i criteri di configurazione delle app in teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare gli eventi dell'app Teams nel log di controllo

È possibile eseguire ricerche nel log di controllo per visualizzare Teams attività delle app nell'organizzazione. Per altre informazioni su come eseguire ricerche nel log di controllo e visualizzare un elenco delle attività di Teams registrate nel log di controllo, vedere Cercare eventi nel log di controllo <a href="/microsoftteams/audit-log-events" target="_blank">in Teams</a>.

Prima di poter eseguire ricerche nel log di controllo, è necessario attivare il controllo nel <a href="https://protection.office.com" target="_blank">Centro sicurezza e conformità</a>. Per altre informazioni, vedere <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Attivare o disattivare la ricerca nel log di controllo</a>. Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Scopri e adotta

Gli utenti che hanno le autorizzazioni per l'app possono trovarla nell'app store dell'organizzazione. Passare a **Creato per il nome *dell'organizzazione*** nella pagina App per trovare le app personalizzate dell'organizzazione.

![Pagina App che mostra l'app pubblicata.](media/custom-app-lifecycle-discovery.png)

Se sono stati creati e assegnati criteri di configurazione dell'app, l'app viene aggiunta alla barra dell'app in Teams per un facile accesso per gli utenti a cui è stato assegnato il criterio.

## <a name="update"></a>Update

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi della [sezione](#develop) Sviluppo.

Quando lo sviluppatore invia un aggiornamento a un'app personalizzata pubblicata, si otterrà una notifica nel **widget** Approvazione in sospeso della <a href="/microsoftteams/manage-apps" target="_blank">pagina Gestisci</a> app. Nella tabella lo stato **di pubblicazione dell'app** sarà impostato su **Aggiorna inviato.**

![Pagina Gestisci app che mostra le richieste in sospeso e lo stato dell'app.](media/custom-app-lifecycle-update-submitted.png)

Per rivedere e pubblicare un aggiornamento dell'app:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare **Aggiorna** disponibile per esaminare i dettagli dell'aggiornamento.

    ![pagina dei dettagli dell'app.](media/custom-app-lifecycle-update-app.png)
3. Al termine, selezionare Pubblica **per** pubblicare l'aggiornamento. In questo modo l'app esistente viene sostituita, il numero di versione viene aggiornato e lo **stato di pubblicazione** viene modificato in **Pubblicato.** Tutti i criteri di autorizzazione delle app e i criteri di configurazione delle app rimangono applicati per l'app aggiornata.

    Se si rifiuta l'aggiornamento, la versione precedente dell'app rimane pubblicata.

Tenere presente quanto segue:

- Quando un'app viene approvata, qualsiasi utente può inviare un aggiornamento all'app. Questo significa che altri sviluppatori, incluso lo sviluppatore che ha originariamente inviato l'app, possono inviare un aggiornamento all'app.
- Quando uno sviluppatore invia un'app e la richiesta è in sospeso, solo lo stesso sviluppatore può inviare un aggiornamento all'app. Gli altri sviluppatori possono inviare un aggiornamento solo dopo l'approvazione dell'app.

Per altre informazioni sull'uso dell'API Graph per aggiornare le app, vedere <a href="/graph/api/teamsapp-update">qui</a>.

## <a name="related-topics"></a>Argomenti correlati

- [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md)
- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- <a href="/graph/api/resources/teamsapp" target="_blank">API di microsoft Graph per Teams app</a>
