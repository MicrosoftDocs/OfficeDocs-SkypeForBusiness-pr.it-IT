---
title: Caricare le app personalizzate nell'interfaccia di amministrazione di Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: Informazioni su come caricare le app personalizzate nell'app store dell'organizzazione nell'interfaccia di amministrazione di Microsoft Teams.
ms.openlocfilehash: 8f7968a53b70ac8ffa871d03adacd648ec047c52
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958051"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Pubblicare un'app personalizzata caricando un pacchetto dell'app

> [!NOTE]
> Quando si pubblica un'app teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui usi dipende da come ottieni l'app. **Questo articolo illustra come pubblicare un'app personalizzata caricando un pacchetto dell'app (in formato .zip) inviato da uno sviluppatore**. L'altro metodo, l'approvazione di un'app personalizzata, viene usato quando uno sviluppatore invia un'app direttamente alla pagina [Gestisci app](manage-apps.md) tramite l'API di invio app di Teams. Per altre informazioni su questo metodo, vedere [Pubblicare un'app personalizzata inviata tramite l'API di invio di app di Teams](submit-approve-custom-apps.md).

Questo articolo fornisce indicazioni end-to-end su come portare l'app Teams dallo sviluppo alla distribuzione alla scoperta. Queste linee guida sono incentrate sugli aspetti di Teams dell'app ed sono destinate agli amministratori e ai professionisti IT. Per altre informazioni sullo sviluppo di app teams, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform/).

![Panoramica dell'app dallo sviluppo alla distribuzione.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Creare l'app

La piattaforma per sviluppatori di Microsoft Teams consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app basate sulla piattaforma Teams sono ponti tra il client di Teams e i servizi e i flussi di lavoro, inserendoli direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la [documentazione per sviluppatori di Teams](/microsoftteams/platform/).

## <a name="validate"></a>Convalidare

### <a name="get-the-app-package"></a>Scarica il pacchetto dell'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore deve produrre un pacchetto di app. Possono usare [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview). Il file verrà inviato in formato .zip.

Tutte le app in Teams Store superano una convalida obbligatoria per [l'app](overview-of-app-validation.md) per garantire la conformità agli standard di qualità e sicurezza dello store globale delle app di Teams. Inoltre, Microsoft invita gli sviluppatori di app a partecipare a un [programma di conformità delle app](overview-of-app-certification.md) facoltativo che indica controlli avanzati per la conformità, la sicurezza e la privacy. Per altre informazioni, vedere [Linee guida per la convalida delle app di Teams](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Consentire agli utenti attendibili di caricare app personalizzate

Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a se stessi e/o utenti attendibili di caricare app personalizzate nel tenant di produzione. A questo scopo si usano i [criteri di configurazione delle app](teams-app-setup-policies.md) .

> [!NOTE]
> Se non si riesce a caricare l'app nel tenant di produzione per la convalida, anche per se stessi o per utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi nelle sezioni [Caricare](#upload) e [configurare e gestire](#set-up-and-manage) l'app non convalidata nell'app store dell'organizzazione. Limitare quindi l'accesso all'app solo a se stessi e agli utenti attendibili. Questi utenti possono quindi ottenere l'app dall'app store dell'organizzazione per eseguire la convalida. Dopo la convalida dell'app, usare gli stessi criteri di autorizzazione per aprire l'accesso e distribuire l'app per l'uso in produzione.

Per consentire a utenti attendibili di caricare app personalizzate, seguire questa procedura:

1. Attiva l'impostazione **Consenti interazione con app personalizzate** a livello di organizzazione. Procedi come segue.

    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare alle app  > **di Teams****Gestire le app** e quindi fare clic su **Impostazioni app a livello di organizzazione**.

    1. In **App personalizzate** attiva **Consenti interazione con le app personalizzate** e quindi fai clic su **Salva**.

1. Disattiva l'impostazione **Carica app personalizzate** nei criteri di configurazione delle app globali. Procedi come segue.

    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di configurazione** **delle app** >  di Teams e quindi fare clic sul criterio **globale (predefinito a livello di organizzazione**).

    1. Disattivare **Carica app personalizzate** e quindi fare clic su **Salva**.

1. Creare un nuovo criterio di configurazione delle app che consente di caricare app personalizzate e assegnarle al set di utenti attendibili. Procedi come segue.

    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a **Criteri di configurazione** **delle app** >  di Teams e quindi fare clic su **Aggiungi**. Assegnare un nome e una descrizione al nuovo criterio, attivare **Carica app personalizzate** e quindi fare clic su **Salva**.

    1. Selezionare il nuovo criterio creato e quindi fare clic su **Gestisci utenti**. Cercare un utente, fare clic su **Aggiungi** e quindi su **Applica**. Ripetere questo passaggio per assegnare il criterio a tutti gli utenti attendibili.

       ![Screenshot della pagina "Aggiungi criteri di configurazione app"](media/manage-your-lob-apps-new-app-setup-policy.png)

Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.

## <a name="upload"></a>Caricare

Per rendere l'app disponibile agli utenti nell'app store dell'organizzazione, caricare l'app.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare alle app  > **di Teams****[Gestire le app](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Seleziona **Carica**, fai clic su **Carica**, seleziona il pacchetto dell'app ricevuto dallo sviluppatore e seleziona **Apri**.

   ![Screenshot del caricamento di un'app nell'interfaccia di amministrazione.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare chi è autorizzato a usare l'app, è possibile creare e assegnare criteri di autorizzazione per l'app. Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire agli utenti di individuare

Per impostazione predefinita, gli utenti possono trovare l'app che devono accedere all'App Store dell'organizzazione ed esplorarla o cercarla. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere [Gestire i criteri di configurazione delle app in teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare gli eventi dell'app Teams nel log di controllo

È possibile eseguire ricerche nel log di controllo per visualizzare l'attività delle app di Teams nell'organizzazione. Per altre informazioni sul controllo delle attività di Teams, vedere [Cercare gli eventi in Teams nel log di controllo](audit-app-management-activities.md).

Prima di poter eseguire ricerche nel log di audit, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://sip.protection.office.com/homepage). Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Scopri e adotta

Gli utenti finali che dispongono delle autorizzazioni per l'app possono trovarla nell'app store dell'organizzazione. Passare a **Built for *Your Organization Name*** nella pagina App per trovare le app personalizzate dell'organizzazione.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Screenshot di Teams Store che mostra un'app personalizzata pubblicata per l'organizzazione" lightbox="media/custom-app-lifecycle-discovery.png":::

Se hai creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in Teams per facilitare l'accesso agli utenti a cui sono stati assegnati i criteri.

## <a name="update"></a>Update

Per aggiornare un'app, gli sviluppatori seguono i passaggi descritti nelle sezioni [Creare l'app](#create-your-app) e [Convalidare](#validate) .

È possibile aggiornare l'app nella pagina Gestisci app nell'interfaccia di amministrazione di Microsoft Teams. A tale scopo, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare alle app  > **di Teams****Gestire le app**. Fare clic sul nome dell'app e quindi su **Aggiorna**. In questo modo l'app esistente viene sostituita e tutti i criteri di autorizzazione e i criteri di configurazione dell'app rimangono applicati per l'app aggiornata.

### <a name="end-user-update-experience"></a>Esperienza di aggiornamento per l'utente finale

Nella maggior parte dei casi, dopo aver completato un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti finali. Per altre informazioni, vedi [Esperienza di aggiornamento per l'utente finale](apps-update-experience.md).

## <a name="remove"></a>Rimuovi

Per rimuovere un'app, procedere come segue:

1. Passare all'interfaccia di amministrazione di Teams.
1. Accedi alla pagina **[Gestisci app](https://admin.teams.microsoft.com/policies/manage-apps)** **delle app delle app** >  di Teams.
1. Fai clic sul nome dell'app per aprire la pagina dei dettagli dell'app.
1. Accanto al banner dell'app selezionare **Azioni** > **Elimina**.
1. Nella finestra di dialogo selezionare **Elimina**.

## <a name="related-articles"></a>Articoli correlati

* [Pubblicare un'app personalizzata inviata tramite l'API di invio dell'app Teams](submit-approve-custom-apps.md)
* [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
* [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
* [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
* [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
