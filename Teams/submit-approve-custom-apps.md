---
title: Usare l'API di presentazione delle app di Teams per inviare e approvare le app personalizzate.
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: Scopri come approvare le app personalizzate inviate utilizzando l'API di invio delle app di Teams in Microsoft Teams.
ms.openlocfilehash: 60f9d78d5fdcc51d741fdbefed5c08a487910f22
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299095"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Pubblicare un'app personalizzata inviata tramite l'API di invio delle app di Teams

Questo articolo fornisce indicazioni dall’inizio alla fine su come portare l'app di Teams da sviluppo a distribuzione e infine a individuazione. Otterrai una panoramica delle esperienze connesse che Teams offre attraverso il ciclo di vita delle app per semplificare le modalità di sviluppo, distribuzione e gestione delle app personalizzate nell'app store dell'organizzazione.

Verranno trattate tutte le fasi del ciclo di vita, compreso il modo in cui gli sviluppatori possono utilizzare l'API di presentazione delle app di Teams per inviare le app personalizzate direttamente al centro di amministrazione di Microsoft Teams per la revisione e l'approvazione, il modo in cui impostare i criteri per gestire le app per gli utenti dell'organizzazione e il modo in cui gli utenti le scoprono in Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Panoramica dell'app dallo sviluppo alla distribuzione.":::

Queste linee guida sono incentrate sugli aspetti di Teams dell'app e sono destinate agli amministratori e ai professionisti IT. Per informazioni sullo sviluppo di app di Teams, vedere la [Documentazione per sviluppatori di Teams](/microsoftteams/platform).

> [!NOTE]
> Quando si pubblica un'app di Teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo da usare dipende da come viene ottenuta l'app. Questo articolo si concentra su come approvare e pubblicare un'app personalizzata inviata da uno sviluppatore tramite l'API di presentazione delle app di Teams. L'altro metodo, il caricamento di un'app personalizzata, si utilizza quando uno sviluppatore invia un pacchetto di app in formato .zip. Per altre informazioni su questo metodo, vedere [Pubblicare un'app personalizzata caricando un pacchetto dell'app](/microsoftteams/upload-custom-apps). Il widget Approve App non è disponibile nei tenant GCC.

> [!IMPORTANT]
> Questo metodo non è disponibile negli ambienti GCC. [Caricare un'app personalizzata](upload-custom-apps.md) per pubblicarla in ambienti GCC.

## <a name="develop"></a>Sviluppo

### <a name="create-the-app"></a>Creare l'app

La piattaforma per sviluppatori di Microsoft Teams consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app basate sulla piattaforma di Teams sono ponti tra il client e i servizi e i flussi di lavoro di Teams, inserendoli direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Inviare l'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore può inviare l'app usando l'API di invio di app di Teams, che può essere chiamata da [API Graph](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), un ambiente di sviluppo integrato (IDE) come Visual Studio Code o una piattaforma come Power Apps e Power Virtual Agents. In questo modo l'app è disponibile nella pagina [Gestisci app](/microsoftteams/manage-apps) dell'interfaccia di amministrazione di Teams, in cui è possibile esaminarla e approvarla.

L'API di presentazione delle app di Teams, [basata su Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), consente alla vostra organizzazione di sviluppare sulla piattaforma di vostra scelta e automatizza il processo di presentazione e approvazione delle app personalizzate su Teams.

Ecco un esempio di come si presenta questa fase di invio dell'applicazione in Visual Studio Code:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Screenshot dell'invio dell'app in Visual Studio Code.":::

Tenere presente che l'applicazione non viene ancora pubblicata sull'app store dell'organizzazione. Questo passaggio invia l'app al centro amministrativo di Teams, dove è possibile approvarla per la pubblicazione sull'app store dell'organizzazione.

Per altre informazioni sull'uso dell’API Graph per inviare le app, vedere [qui](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Notifica

È possibile attivare le notifiche per sapere quando gli sviluppatori presentano una nuova domanda da esaminare e approvare. Riceverai anche notifiche quando gli sviluppatori inviano gli aggiornamenti delle app. Per abilitare le notifiche di invio di app nell'interfaccia di amministrazione di Teams, passare a **Notifiche e avvisi** > **[Regole](https://admin.teams.microsoft.com/notifications/rules)** > **Invii di app** e attivare la regola impostando lo stato su **Attivo**. Per impostazione predefinita, questa impostazione è disattivata. Per attivare questa impostazione, è necessario essere un amministratore globale o un amministratore di Teams.

Una volta attivata questa impostazione, si riceveranno le notifiche nel team **Avvisi e notifiche dell'amministratore**, in un nuovo canale denominato **Invii di app**. In alternativa, è possibile scegliere un team e un canale esistenti per ricevere le notifiche a un team e a un canale specifici. A tale scopo, eseguire la procedura seguente:

1. Nella regola **Invio di app** selezionare la casella di controllo **Avviso canale** in **Azioni**.
1. Scegliere il pulsante **Seleziona canale**.
1. Cercare un team da aggiungere.
1. Cercare un canale da aggiungere.
1. Selezionare **Applica**.

   :::image type="content" source="media/channel-alert.png" alt-text="Casella di controllo notifica avvisi canale personalizzato." lightbox="media/channel-alert.png":::

> [!NOTE]
> Selezionare la casella di controllo **Avviso canale predefinito** per ricevere notifiche al team **Avvisi e notifiche amministratore** nel canale **Invii di app**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Casella di controllo notifica avvisi canale predefinito." lightbox="media/default-channel-alert.png":::

È anche possibile configurare le notifiche a un webhook esterno specificando un URL di webhook pubblico dopo aver selezionato la casella di controllo **Webhook**. Un payload di notifica JSON verrà inviato all'URL del webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notifica di invio dell'app." lightbox="media/app-submission-notification.png":::

Dopo aver configurato la regola per gli invii di app, è possibile esaminare le schede di notifica nel canale specificato per visualizzare i dettagli dell'app e selezionare **Visualizza dettagli** per aprire le app nell'interfaccia di amministrazione di Teams.

## <a name="validate"></a>Convalida

La pagina [Gestisci app](/microsoftteams/manage-apps) nell'interfaccia di amministrazione di Teams (nel riquadro di spostamento a sinistra passare alle [**App di Teams** > **Gestisci app**](https://admin.teams.microsoft.com/manage-apps)) offre una visualizzazione di tutte le app di Teams per l'organizzazione. Il widget **Approvazione in sospeso** nella parte superiore della pagina consente di sapere quando un'app personalizzata viene inviata per l'approvazione.

Nella tabella, un'app appena inviata mostra automaticamente lo **Stato di pubblicazione** **Inviato** e **Stato** **Bloccato**. È possibile ordinare la colonna **Stato pubblicazione** in ordine decrescente per trovare rapidamente l'app.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Stato pubblicazione." lightbox="media/custom-app-lifecycle-validate-app.png":::

Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app. Nella scheda **Informazioni** è possibile visualizzare i dettagli sull'app, tra cui descrizione, stato, autore e ID app.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Pagina dei dettagli dell'app per un'app inviata." lightbox="media/custom-app-lifecycle-app-details.png":::

Per altre informazioni sull'uso dell’API Graph per controllare lo **Stato di pubblicazione**, vedere [qui](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Pubblicazione

Quando si è pronti per rendere disponibile l'app agli utenti, pubblicare l'app.

1. Accedi all'interfaccia di amministrazione di Teams e passa alle **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selezionare il nome dell'app per passare alla pagina dei dettagli dell'app e quindi nella casella **Stato pubblicazione** selezionare **Pubblica**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Pulsante Pubblica nella pagina dei dettagli dell'app.":::

Dopo aver pubblicato l'app, lo **Stato di pubblicazione** diventa **Pubblicato** e lo **Stato** diventa **Consentito**.

## <a name="set-up-and-manage"></a>Configurazione e gestione

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare chi è autorizzato a usare l'app, è possibile creare e assegnare criteri di autorizzazione delle app. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire l’individuazione da parte degli utenti

Per impostazione predefinita, gli utenti devono accedere all'app store dell'organizzazione per trovare l’app. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare i log di audit per gli eventi dell'app di Teams

È possibile eseguire ricerche nel log di audit per visualizzare le attività delle app di Teams nell’organizzazione. Per altre informazioni su come eseguire ricerche nel log di controllo e per visualizzare un elenco delle attività di Teams registrate nel log di controllo, vedere [Cercare eventi nel log di controllo in Teams](audit-log-events.md).

Prima di poter eseguire ricerche nel log di audit, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://sip.protection.office.com/). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Identificazione e adozione

Gli utenti che hanno le autorizzazioni per l'app possono trovarla nell'App Store dell'organizzazione. Passare a **Compilato per *Nome dell’organizzazione*** nella pagina App per trovare le app personalizzate dell'organizzazione.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Pagina App che mostra l'app pubblicata." lightbox="media/custom-app-lifecycle-discovery.png":::

Se è stato creato e assegnato un criterio di configurazione delle app, l'app viene aggiunta alla barra delle app in Teams per facilitare l'accesso agli utenti a cui sono stati assegnati i criteri.

## <a name="update"></a>Aggiornamento

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi nella sezione [Sviluppo](#develop).

Quando lo sviluppatore invia un aggiornamento a un'app personalizzata pubblicata, riceverai una notifica nel widget **Approvazione in sospeso** della pagina [Gestisci app](/microsoftteams/manage-apps). Nella tabella, lo **Stato di pubblicazione** dell'app verrà impostato su **Aggiornamento inviato**. Inoltre, riceverai una notifica nel team **Avvisi e notifiche dell'amministratore**, sotto il canale di **Invio dell’app**, se hai attivato le notifiche di presentazione delle app. La scheda di notifica avrà un collegamento per passare direttamente all'app nell'interfaccia di amministrazione di Teams. Per altre informazioni su come attivare le notifiche di invio di app, vedere [Notifica](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Pagina Gestisci app che mostra le richieste in sospeso e lo stato dell'app." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Per rivedere e pubblicare un aggiornamento dell'app:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams passare alle **App di Teams** > **Gestisci app**.
1. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare **Aggiornamento disponibile** per esaminare i dettagli dell'aggiornamento.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Pagina dei dettagli dell'app." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Quando si è pronti, selezionare **Pubblica** per pubblicare l'aggiornamento. Questa operazione sostituisce l'app esistente, aggiorna il numero di versione e imposta lo **Stato di pubblicazione** su **Pubblicato**. Tutti i criteri di autorizzazione dell'app e i criteri di configurazione delle app rimangono applicati per l'app aggiornata.

    Se si rifiuta l'aggiornamento, la versione precedente dell'app rimane pubblicata.

Tenere presente quanto segue:

* Quando un'app viene approvata, chiunque può inviare un aggiornamento all'app. Ciò significa che altri sviluppatori, incluso lo sviluppatore che ha inviato l'app in origine, possono inviare un aggiornamento all'app.
* Quando uno sviluppatore invia un'app e la richiesta è in sospeso, solo lo stesso sviluppatore può inviare un aggiornamento all'app. Gli altri sviluppatori possono inviare un aggiornamento solo dopo l'approvazione dell'app.

Per altre informazioni sull'uso dell’API Graph per aggiornare le app, vedere [qui](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Articoli correlati

* [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md)
* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
* [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
* [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
* [Monitoraggio e avvisi di Teams](alerts/teams-admin-alerts.md)
* [API Microsoft Graph per le app di Teams](alerts/teams-admin-alerts.md)
