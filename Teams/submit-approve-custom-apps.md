---
title: Usare l'API di invio delle app di Teams per inviare e approvare le app personalizzate
author: guptaashish
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
description: Informazioni su come approvare le app personalizzate inviate con l'API di invio delle app di Teams in Microsoft Teams.
ms.openlocfilehash: 2fb0ab6778a0704b0cb60faef0d0fd739351ee10
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958071"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Pubblicare un'app personalizzata inviata con l'API di invio dell'app Teams

Questo articolo fornisce indicazioni end-to-end su come portare l'app Teams dallo sviluppo alla distribuzione alla scoperta. Verrà fornita una panoramica delle esperienze connesse fornite da Teams per tutto il ciclo di vita delle app per semplificare lo sviluppo, la distribuzione e la gestione di app personalizzate nell'App Store dell'organizzazione.

Tratteremo ogni passaggio del ciclo di vita, incluso il modo in cui gli sviluppatori possono usare l'API di invio di app di Teams per inviare app personalizzate direttamente all'interfaccia di amministrazione di Microsoft Teams da rivedere e approvare, come impostare criteri per gestire le app per gli utenti dell'organizzazione e come gli utenti le individuano in Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Panoramica dell'app dallo sviluppo alla distribuzione.":::

Queste linee guida sono incentrate sugli aspetti di Teams dell'app ed sono destinate agli amministratori e ai professionisti IT. Per informazioni sullo sviluppo di app di Teams, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform).

> [!NOTE]
> Quando si pubblica un'app teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui usi dipende da come ottieni l'app. Questo articolo è incentrato su come approvare e pubblicare un'app personalizzata che uno sviluppatore invia tramite l'API di invio di app di Teams. L'altro metodo, il caricamento di un'app personalizzata, viene usato quando uno sviluppatore invia un pacchetto dell'app in formato .zip. Per altre informazioni su questo metodo, vedere [Pubblicare un'app personalizzata caricando un pacchetto dell'app](/microsoftteams/upload-custom-apps). Il widget approvazione app non è disponibile nei tenant GCC.

> [!IMPORTANT]
> Questo metodo non è attualmente disponibile per gli ambienti GCC. In GCC usare il metodo di *caricamento di un'app personalizzata* .

## <a name="develop"></a>Sviluppo

### <a name="create-the-app"></a>Creare l'app

La piattaforma per sviluppatori di Microsoft Teams consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app basate sulla piattaforma Teams sono ponti tra il client di Teams e i servizi e i flussi di lavoro, inserendoli direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Inviare l'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore può inviare l'app utilizzando l'API invio app Teams, che può essere chiamata da [API Graph](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), un ambiente di sviluppo integrato (IDE) come Visual Studio Code o una piattaforma come Power Apps e Power Virtual Agents. In questo modo l'app è disponibile nella pagina [Gestisci app](/microsoftteams/manage-apps) dell'interfaccia di amministrazione di Teams, dove è possibile rivederla e approvarla.

L'API di invio delle app di Teams, [basata su Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), consente alla tua organizzazione di sviluppare sulla piattaforma che preferisci e automatizza il processo di invio all'approvazione per le app personalizzate su Teams.

Ecco un esempio dell'aspetto di questo passaggio di invio dell'app in Visual Studio Code:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="l'invio di un'app in Visual Studio Code.":::

Tenere presente che l'app non viene ancora pubblicata nell'app store dell'organizzazione. Questo passaggio invia l'app all'interfaccia di amministrazione di Teams, in cui è possibile approvarla per la pubblicazione nell'app store dell'organizzazione.

Per altre informazioni sull'uso della API Graph per l'invio di app, vedi [qui](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Notificare

Puoi attivare le notifiche in modo da sapere quando gli sviluppatori inviano una nuova applicazione per la revisione e l'approvazione. Riceverai anche notifiche quando gli sviluppatori inviano gli aggiornamenti delle app. Per abilitare le notifiche di invio di app nell'interfaccia di amministrazione di Teams, passare a **Notifiche & avvisi** > **Invii all'app** **[Regole](https://admin.teams.microsoft.com/notifications/rules)** >  e attivare la regola impostando lo stato su **Attivo**. Per impostazione predefinita, questa impostazione è disattivata. Per attivare questa impostazione, è necessario essere un amministratore globale o di Teams.

Dopo aver attivato questa impostazione, riceverai le notifiche nel team **di Amministrazione Avvisi e notifiche** in un nuovo canale denominato **Invii di app**. In alternativa, puoi scegliere un team e un canale esistenti per ricevere le notifiche a un team e un canale specifici. A tale scopo, eseguire la procedura seguente:

1. Nella regola **Invio di app** selezionare la casella di **controllo Avviso canale** in **Azioni**.
1. Scegliere il pulsante **Seleziona canale** .
1. Cercare un team da aggiungere.
1. Cercare un canale da aggiungere.
1. Selezionare **Applica**.

   :::image type="content" source="media/channel-alert.png" alt-text="Casella di controllo notifica di avviso canale personalizzato." lightbox="media/channel-alert.png":::

> [!NOTE]
> Selezionare la casella di **controllo Avviso canale predefinito** per ricevere notifiche al team **di Amministrazione avvisi e notifiche** nel canale **Invii di app**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Casella di controllo Notifica di avviso canale predefinita." lightbox="media/default-channel-alert.png":::

È anche possibile configurare le notifiche su un webhook esterno specificando un URL webhook pubblico dopo aver selezionato la casella di controllo **Webhook** . Un payload di notifica JSON verrà inviato all'URL webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notifica di invio di app." lightbox="media/app-submission-notification.png":::

Dopo aver configurato la regola per gli invii di app, è possibile esaminare le schede di notifica nel canale specificato per visualizzare i dettagli dell'app e selezionare **Visualizza dettagli** per aprire le app nell'interfaccia di amministrazione di Teams.

## <a name="validate"></a>Convalidare

La pagina [Gestisci app](/microsoftteams/manage-apps) nell'interfaccia di amministrazione di Teams (nel riquadro di spostamento sinistro, passa alle [**app** >  di Teams **Gestisci app**](https://admin.teams.microsoft.com/manage-apps)), offre una visualizzazione di tutte le app di Teams per l'organizzazione. Il widget **Approvazione in sospeso** nella parte superiore della pagina consente di sapere quando viene inviata un'app personalizzata per l'approvazione.

Nella tabella, un'app appena inviata mostra automaticamente **lo stato Pubblicazione** **inviato** e **lo stato** del **blocco**. È possibile ordinare la colonna **Stato pubblicazione** in ordine decrescente per trovare rapidamente l'app.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Stato pubblicazione." lightbox="media/custom-app-lifecycle-validate-app.png":::

Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app. Nella scheda **Informazioni è** possibile visualizzare i dettagli dell'app, tra cui descrizione, stato, utente di invio e ID app.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Pagina dei dettagli dell'app per un'app inviata." lightbox="media/custom-app-lifecycle-app-details.png":::

Per altre informazioni sull'uso della API Graph per controllare **lo stato pubblicazione**, vedere [qui](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Pubblicare

Quando si è pronti per rendere l'app disponibile agli utenti, pubblicare l'app.

1. Accedere all'interfaccia di amministrazione di Teams e passare alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selezionare il nome dell'app per passare alla pagina dei dettagli dell'app, quindi nella casella **Stato pubblicazione** selezionare **Pubblica**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Pulsante Pubblica nella pagina dei dettagli dell'app.":::

Dopo la pubblicazione dell'app, **lo stato pubblicazione** diventa **Pubblicato** e **lo stato** diventa **Consentito**.

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare chi è autorizzato a usare l'app, è possibile creare e assegnare criteri di autorizzazione per l'app. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire agli utenti di individuare

Per impostazione predefinita, gli utenti possono trovare l'app che devono accedere all'App Store dell'organizzazione ed esplorarla o cercarla. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare gli eventi dell'app Teams nel log di controllo

È possibile eseguire ricerche nel log di controllo per visualizzare l'attività delle app di Teams nell'organizzazione. Per altre informazioni su come eseguire ricerche nel log di controllo e visualizzare un elenco delle attività di Teams registrate nel log di controllo, vedere [Cercare eventi in Teams nel log di controllo](audit-log-events.md).

Prima di poter eseguire ricerche nel log di audit, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://sip.protection.office.com/). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Scopri e adotta

Gli utenti che hanno le autorizzazioni per l'app possono trovarla nell'app store dell'organizzazione. Passare a **Built for *Your Organization Name*** nella pagina App per trovare le app personalizzate dell'organizzazione.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Pagina App che mostra l'app pubblicata." lightbox="media/custom-app-lifecycle-discovery.png":::

Se hai creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in Teams per facilitare l'accesso agli utenti a cui sono stati assegnati i criteri.

## <a name="update"></a>Update

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi descritti nella sezione [Sviluppo](#develop) .

Quando lo sviluppatore invia un aggiornamento a un'app personalizzata pubblicata, si riceverà una notifica nel widget **Approvazione in sospeso** della pagina [Gestisci app](/microsoftteams/manage-apps) . Nella tabella **, lo stato pubblicazione** dell'app verrà impostato su **Aggiornamento inviato**. Se hai attivato le notifiche di invio delle app, riceverai una notifica anche nel team **di avvisi e notifiche di Amministrazione** nel canale **di invio delle app**. La scheda di notifica avrà un collegamento per portarti direttamente all'app nell'interfaccia di amministrazione di Teams. Per altre informazioni su come attivare le notifiche di invio delle app, vedi [Notifica](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Pagina Gestisci app che mostra le richieste in sospeso e lo stato dell'app." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Per rivedere e pubblicare un aggiornamento dell'app:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, passare alle app  > **di Teams****Gestire le app**.
1. Fare clic sul nome dell'app per passare alla pagina dei dettagli dell'app e quindi selezionare **Aggiorna disponibile** per rivedere i dettagli dell'aggiornamento.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Pagina dei dettagli dell'app." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Quando sei pronto, seleziona **Pubblica** per pubblicare l'aggiornamento. In questo modo l'app esistente viene sostituita, il numero di versione viene aggiornato e **lo stato Pubblicazione** diventa **Pubblicato**. Tutti i criteri di autorizzazione e i criteri di configurazione delle app rimangono applicati per l'app aggiornata.

    Se si rifiuta l'aggiornamento, la versione precedente dell'app rimane pubblicata.

Tenere presente quanto segue:

* Quando un'app viene approvata, chiunque può inviare un aggiornamento all'app. Ciò significa che altri sviluppatori, incluso lo sviluppatore che ha inviato originariamente l'app, possono inviare un aggiornamento all'app.
* Quando uno sviluppatore invia un'app e la richiesta è in sospeso, solo lo stesso sviluppatore può inviare un aggiornamento all'app. Altri sviluppatori possono inviare un aggiornamento solo dopo l'approvazione dell'app.

Per altre informazioni sull'uso della API Graph per aggiornare le app, vedere [qui](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Articoli correlati

* [Pubblicare un'app personalizzata caricando un pacchetto dell'app](upload-custom-apps.md)
* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
* [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
* [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
* [Monitoraggio e avvisi di Teams](alerts/teams-admin-alerts.md)
* [App Microsoft API Graph per Teams](alerts/teams-admin-alerts.md)
