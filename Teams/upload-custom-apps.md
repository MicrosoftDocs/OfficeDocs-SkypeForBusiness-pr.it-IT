---
title: Caricare le app personalizzate nell'interfaccia di amministrazione di Microsoft Teams
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
ms.localizationpriority: high
search.appverid: MET150
description: Informazioni su come caricare le app personalizzate nell'app store dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: 52977d9663f5dbee915e2227075127fe1c6575ad
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299025"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Pubblicare un'app personalizzata caricando un pacchetto dell'app

> [!NOTE]
> Quando si pubblica un'app di Teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo da usare dipende da come viene ottenuta l'app. **Questo articolo illustra come pubblicare un'app personalizzata caricando un pacchetto dell'app (in formato .zip) inviato da uno sviluppatore**. L'altro metodo, l'approvazione di un'app personalizzata, viene usato quando uno sviluppatore invia un'app direttamente alla pagina [Gestisci app](manage-apps.md) tramite l'API di invio app di Teams. Per altre informazioni su questo metodo, vedere [Pubblicare un'app personalizzata inviata tramite l'API di invio app di Teams](submit-approve-custom-apps.md).

Questo articolo fornisce indicazioni dall’inizio alla fine su come portare l'app di Teams da sviluppo a distribuzione e infine a individuazione. Queste linee guida sono incentrate sugli aspetti di Teams dell'app e sono destinate agli amministratori e ai professionisti IT. Per altre informazioni sullo sviluppo di app di Teams, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform/).

![Panoramica dell'app dallo sviluppo alla distribuzione.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Creazione di un’app personale

La piattaforma per sviluppatori di Microsoft Teams consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app basate sulla piattaforma di Teams sono ponti tra il client e i servizi e i flussi di lavoro di Teams, inserendoli direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform/).

## <a name="validate"></a>Convalida

### <a name="get-the-app-package"></a>Ottenere il pacchetto dell'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore deve produrre un pacchetto dell’app. È possibile che venga usata l’applicazione [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview). Il file verrà inviato in formato .zip.

Tutte le app nello store di Teams superano una [convalida app](overview-of-app-validation.md) obbligatoria per garantire la conformità con standard di qualità e sicurezza dell’app store globale di Teams. Inoltre, Microsoft incoraggia vivamente gli sviluppatori di app a partecipare a un [programma di conformità delle app](overview-of-app-certification.md) facoltativo che indica controlli avanzati di conformità, sicurezza e privacy. Per altre informazioni, vedere [Linee guida per la convalida delle app di Teams](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Consentire ad utenti attendibili di caricare app personalizzate

Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a se stessi e/o ad utenti attendibili di caricare app personalizzate nel tenant di produzione. A questo scopo si usano i [criteri di configurazione delle app](teams-app-setup-policies.md).

> [!NOTE]
> Se non si riesce a caricare l'app nel tenant di produzione per la convalida, anche per se stessi o per utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi nelle sezioni [Carica](#upload) e [Configura e gestisci](#set-up-and-manage) per pubblicare l’app non convalidata nell'app store dell'organizzazione. Limitare quindi l'accesso all'app solo a se stessi e agli utenti attendibili. Questi utenti possono quindi ottenere l'app dall'app store dell'organizzazione per eseguire la convalida. Dopo la convalida dell'app, usare gli stessi criteri di autorizzazione per aprire l'accesso e distribuire l'app per l'uso in produzione.

Per consentire ad utenti attendibili di caricare app personalizzate, seguire questa procedura:

1. Attiva l'impostazione a livello di organizzazione **Consenti interazione con app personalizzate**. Procedere come segue.

    1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app** e quindi fare clic su **Impostazioni app a livello di organizzazione**.

    1. In **App personalizzate** attivare **Consenti interazione con app personalizzate** e quindi fare clic su **Salva**.

1. Disattivare l'impostazione **Carica app personalizzate** nei criteri di configurazione delle app globali. Procedere come segue.

    1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare a **App di Teams** > **Imposta criteri** e quindi fare clic sul criterio **globale (predefinito a livello di organizzazione)**.

    1. Disattivare **Carica app personalizzate** e quindi fare clic su **Salva**.

1. Creare un nuovo criterio di configurazione delle app che consente di caricare app personalizzate e assegnarle al set di utenti attendibili. Procedere come segue.

    1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **App di Teams** > **Criteri di configurazione** e quindi fare clic su **Aggiungi**. Assegnare un nome e una descrizione al nuovo criterio, attivare **Carica app personalizzate** e quindi fare clic su **Salva**.

    1. Selezionare il nuovo criterio creato e quindi fare clic su **Gestisci utenti**. Cercare un utente, fare clic su **Aggiungi** e quindi su **Applica**. Ripetere questo passaggio per assegnare il criterio a tutti gli utenti attendibili.

       ![Screenshot della pagina "Aggiungi criteri di configurazione delle app"](media/manage-your-lob-apps-new-app-setup-policy.png)

Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.

## <a name="upload"></a>Caricamento

Per rendere l'app disponibile agli utenti nell'app store dell'organizzazione, carica l'app.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selezionare **Carica**, fare clic su **Carica**, selezionare il pacchetto dell'app ricevuto dallo sviluppatore e selezionare **Apri**.

   ![Screenshot del caricamento di un'app nell'interfaccia di amministrazione.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurazione e gestione

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare chi è autorizzato a usare l'app, è possibile creare e assegnare criteri di autorizzazione delle app. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire l’individuazione da parte degli utenti

Per impostazione predefinita, gli utenti devono accedere all'app store dell'organizzazione per trovare l’app. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare i log di audit per gli eventi dell'app di Teams

È possibile eseguire ricerche nel log di audit per visualizzare le attività delle app di Teams nell’organizzazione. Per altre informazioni sul controllo delle attività di Teams, vedere [Cercare i log di audit per gli eventi in Teams](audit-app-management-activities.md).

Prima di poter eseguire ricerche nel log di audit, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://sip.protection.office.com/homepage). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Identificazione e adozione

Gli utenti finali che dispongono delle autorizzazioni per l'app possono trovarla nell'app store dell'organizzazione. Passare a **Compilato per *Nome dell’organizzazione*** nella pagina App per trovare le app personalizzate dell'organizzazione.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Screenshot dello store di Teams che mostra un'app personalizzata pubblicata per l'organizzazione" lightbox="media/custom-app-lifecycle-discovery.png":::

Se è stato creato e assegnato un criterio di configurazione delle app, l'app viene aggiunta alla barra delle app in Teams per facilitare l'accesso agli utenti a cui sono stati assegnati i criteri.

## <a name="update"></a>Aggiornamento

Per aggiornare un'app, gli sviluppatori seguono i passaggi descritti nelle sezioni [Creazione di un’app personale](#create-your-app) e [Convalida](#validate).

È possibile aggiornare l'app nella pagina Gestisci app nell'interfaccia di amministrazione di Microsoft Teams. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**. Fare clic sul nome dell'app e quindi su **Aggiorna**. In questo modo l'app esistente viene sostituita e tutti i criteri di autorizzazione e di configurazione delle app rimangono applicati per l'app aggiornata.

### <a name="end-user-update-experience"></a>Esperienza di aggiornamento per l'utente finale

Nella maggior parte dei casi, dopo aver completato un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti finali. Per altre informazioni, vedere [Esperienza di aggiornamento per l'utente finale](apps-update-experience.md).

## <a name="remove"></a>Rimozione

Per rimuovere un'app, procedere come segue:

1. Passare all'interfaccia di amministrazione di Teams.
1. Accedere alla pagina **App di Teams** > **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Fare clic sul nome dell'app per aprire la pagina dei dettagli dell'app.
1. Accanto al banner dell'app, selezionare **Azioni** > **Elimina**.
1. Nella finestra di dialogo selezionare **Elimina**.

## <a name="related-articles"></a>Articoli correlati

* [Pubblicare un'app personalizzata inviata tramite l'API di l’invio app di Teams](submit-approve-custom-apps.md)
* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
* [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
* [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
