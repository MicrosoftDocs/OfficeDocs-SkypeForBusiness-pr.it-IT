---
title: Usare l'API per l'invio di app teams per inviare e approvare le app personalizzate
author: cichur
ms.author: v-cichur
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
description: Informazioni su come approvare le app personalizzate inviate con l'API per l'invio di app di Teams in Microsoft Teams.
ms.openlocfilehash: 0003bc218b425383ba117296ba847a637d76ac43
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145803"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Pubblicare un'app personalizzata inviata tramite l'API di invio delle app di Teams

## <a name="overview"></a>Panoramica

> [!NOTE]
> Quando si pubblica un'app di Teams personalizzata, questa è disponibile per gli utenti nello store delle app dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui usarlo dipende da come si ottiene l'app. **Questo articolo illustra come approvare e** pubblicare un'app personalizzata che uno sviluppatore invia tramite l'API di invio delle app di Teams. L'altro metodo, il caricamento di un'app personalizzata, viene usato quando uno sviluppatore invia un pacchetto dell'app in formato ZIP. Per altre informazioni su questo metodo, vedere <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Pubblicare un'app personalizzata caricando un pacchetto dell'app.</a> Il widget approvazione app non è disponibile nei tenant GCC. 

> [!IMPORTANT]
> Questo metodo non è attualmente disponibile per gli ambienti GCC. È necessario usare il *metodo di caricamento di un'app* personalizzata.

Questo articolo fornisce indicazioni end-to-end su come portare l'app Teams dallo sviluppo alla distribuzione all'individuazione. Verrà fornita una panoramica delle esperienze connesse fornite da Teams nell'intero ciclo di vita delle app per semplificare le procedure di sviluppo, distribuzione e gestione di app personalizzate nell'App Store dell'organizzazione.

Ogni fase del ciclo di vita verrà trattata, inclusa la modalità di utilizzo dell'API per l'invio di app di Teams da parte degli sviluppatori per inviare app personalizzate direttamente all'interfaccia di amministrazione di Microsoft Teams, come rivedere e approvare i criteri, come impostare i criteri per gestire le app per gli utenti dell'organizzazione e come gli utenti le individuano in Teams.

![Panoramica dell'app, dallo sviluppo alla distribuzione](media/custom-app-lifecycle.png)

Questa guida è incentrata sugli aspetti di Teams dell'app ed è destinata agli amministratori e ai professionisti IT. Per informazioni sullo sviluppo di app teams, vedere la documentazione per sviluppatori <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">di Teams.</a>

## <a name="develop"></a>Sviluppo

### <a name="create-the-app"></a>Creare l'app

La piattaforma di sviluppo di Microsoft Teams consente agli sviluppatori di integrare facilmente app e servizi personalizzati per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione su contenuti e flussi di lavoro esistenti. Le app create sulla piattaforma Teams sono bridge tra il client di Teams e i servizi e i flussi di lavoro, per portarli direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la documentazione per sviluppatori <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">di Teams.</a>

### <a name="submit-the-app"></a>Inviare l'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore può inviarla usando l'API di invio app di Teams, che può essere chiamata <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">dall'API Graph,</a>da un ambiente di sviluppo integrato come Visual Studio Code o da una piattaforma come Power Apps e Agenti virtuali. In questo modo l'app sarà disponibile nella pagina Gestisci app dell'interfaccia di amministrazione di Microsoft Teams, dove l'amministratore potrà rivedirla e approvarla. <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a>

L'API per l'invio di app di Teams, basata su <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph,</a>consente alla tua organizzazione di sviluppare sulla piattaforma che più ti è stata scelta e automatizza il processo di invio ad approvazione delle app personalizzate su Teams.

Ecco un esempio dell'aspetto di questo passaggio di invio dell'app in Visual Studio Code:

![Invio di un'app in Visual Studio Code](media/custom-app-lifecycle-submit-app.png)

Tenere presente che questa operazione non consente ancora di pubblicare l'app nello store delle app dell'organizzazione. Questo passaggio consente di inviare l'app all'interfaccia di amministrazione di Microsoft Teams, dove è possibile approvarla per la pubblicazione nell'app store dell'organizzazione.

Per altre informazioni sull'uso dell'API Graph per inviare app, vedere <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">qui.</a>

## <a name="validate"></a>Convalida

La <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">pagina Gestisci app</a> nell'interfaccia di amministrazione di Microsoft Teams (nella barra di spostamento sinistra, accedi ad Gestisci app di **Teams),** ti offre una vista di tutte le app  >  di Teams per la tua organizzazione. Il widget **Approvazione in** sospeso nella parte superiore della pagina indica quando un'app personalizzata viene inviata per l'approvazione.

Nella tabella, un'app appena  inviata mostra automaticamente lo stato di pubblicazione **Inviato** e **Lo stato** **Bloccato.** È possibile ordinare la **colonna Stato pubblicazione** in ordine decrescente per trovare rapidamente l'app.

![stato di pubblicazione ](media/custom-app-lifecycle-validate-app.png)

Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app. Nella scheda **Informazioni** è possibile visualizzare i dettagli sull'app, inclusi la descrizione, lo stato, l'inviatore e l'ID dell'app.

![pagina dei dettagli dell'app per un'app inviata](media/custom-app-lifecycle-app-details.png)

Per altre informazioni sull'uso dell'API Graph per controllare lo **stato di pubblicazione,** vedere <a href="https://docs.microsoft.com/graph/api/appcatalogs-list-teamsapps?view=graph-rest-beta&tabs=http#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">qui.</a>

## <a name="publish"></a>Pubblica

Quando si è pronti a rendere l'app disponibile agli utenti, pubblicare l'app.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi nella casella Stato **pubblicazione** selezionare **Pubblica.**

    Dopo la pubblicazione dell'app, lo **stato della** pubblicazione **cambia** in Pubblicato e lo **stato** cambia automaticamente in **Consentito.**

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nello store delle app dell'organizzazione. Per limitare e controllare gli utenti autorizzati a usare l'app, è possibile creare e assegnare criteri di autorizzazione per l'app. Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Gestire i criteri di autorizzazione per le app in Teams.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app che gli utenti possono individuare

Per impostazione predefinita, gli utenti possono trovare l'app che devono accedere all'App Store dell'organizzazione e cercarla o cercarla. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione delle app e assegnarlo agli utenti. Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Gestire i criteri di configurazione delle app in Teams.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare gli eventi dell'app Teams nel log di controllo

È possibile eseguire ricerche nel log di controllo per visualizzare le attività delle app di Teams nell'organizzazione. Per altre informazioni su come eseguire ricerche nel log di controllo e per visualizzare un elenco delle attività di Teams registrate nel log di controllo, vedere Cercare gli eventi <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">nel log di controllo in Teams.</a>

Prima di eseguire ricerche nel log di controllo, è necessario attivare il controllo nel Centro <a href="https://protection.office.com" target="_blank">& conformità.</a> Per altre informazioni, vedere Attivare o disattivare <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">la ricerca nel log di controllo.</a> Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Individuare e adottare

Gli utenti che hanno le autorizzazioni per l'app possono trovarla nello store delle app dell'organizzazione. Passare a **Predefinito per il nome *dell'organizzazione*** nella pagina App per trovare le app personalizzate dell'organizzazione.

![Pagina App che mostra l'app pubblicata ](media/custom-app-lifecycle-discovery.png)

Se è stato creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in Teams per consentire un facile accesso agli utenti a cui sono stati assegnati i criteri.

## <a name="update"></a>Aggiornamento

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi descritti nella [sezione](#develop) Sviluppo.

Quando lo sviluppatore invia un aggiornamento a un'app personalizzata pubblicata, si ottiene una notifica nel **widget** Approvazione in sospeso della pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app.</a> Nella tabella, lo **stato di pubblicazione** dell'app verrà impostato su Aggiorna **inviato.**

![Pagina Gestisci app con le richieste in sospeso e lo stato dell'app ](media/custom-app-lifecycle-update-submitted.png)

Per rivedere e pubblicare un aggiornamento dell'app:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.
2. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare **Aggiorna** disponibile per rivedere i dettagli dell'aggiornamento.

    ![pagina dei dettagli dell'app](media/custom-app-lifecycle-update-app.png)
3. Quando si è pronti, selezionare **Pubblica per** pubblicare l'aggiornamento. Questa operazione sostituisce l'app esistente, aggiorna il numero di versione e cambia lo **stato** Pubblicazione in **Pubblicato.** Tutti i criteri di autorizzazione e di configurazione delle app rimangono applicati all'app aggiornata.

    Se si rifiuta l'aggiornamento, la versione precedente dell'app rimane pubblicata.

Tenere presente quanto segue:

- Quando un'app viene approvata, qualsiasi utente può inviare un aggiornamento all'app. Ciò significa che altri sviluppatori, incluso quello che ha inviato l'app in origine, possono inviare un aggiornamento all'app.
- Quando uno sviluppatore invia un'app e la richiesta è in sospeso, solo lo stesso sviluppatore può inviare un aggiornamento all'app. Gli altri sviluppatori possono inviare un aggiornamento solo dopo l'approvazione dell'app.

Per altre informazioni sull'uso dell'API Graph per aggiornare le app, vedere <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">qui.</a>

### <a name="update-experience-for-users"></a>Esperienza di aggiornamento per gli utenti

Nella maggior parte dei casi, dopo la pubblicazione di un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti. Tuttavia, ci sono alcuni aggiornamenti al manifesto di <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> che richiedono l'accettazione dell'utente per completare:

* È stato aggiunto o rimosso un bot
* La proprietà "botId" di un bot esistente è cambiata
* È stata modificata la proprietà "isNotificationOnly" di un bot esistente
* La proprietà "supportsFiles" del bot è stata modificata
* È stata aggiunta o rimossa un'estensione di messaggistica
* È stato aggiunto un nuovo connettore
* È stata aggiunta una nuova scheda statica
* È stata aggiunta una nuova scheda configurabile
* Proprietà all'interno di "webApplicationInfo" modificate

![Nuova versione disponibile](media/manage-your-custom-apps-update1.png)

![opzione di aggiornamento per un'app](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Argomenti correlati

- [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">API Microsoft Graph per le app di Teams</a>
