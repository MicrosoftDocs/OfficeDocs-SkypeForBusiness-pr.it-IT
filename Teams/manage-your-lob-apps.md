---
title: Gestire le app line-of-business in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come portare le app teams personalizzate dallo sviluppo alla distribuzione.
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682726"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Gestire le app line-of-business in Microsoft Teams

Questo articolo fornisce indicazioni complete su come usare l'app teams dallo sviluppo alla distribuzione. Questa guida si basa sugli aspetti relativi ai team dell'app ed è destinata ai professionisti IT. Per altre informazioni sullo sviluppo di app per Team, Vedi [qui](https://docs.microsoft.com/microsoftteams/platform).

![Panoramica della tua app dallo sviluppo alla distribuzione](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Introduzione

Per creare e gestire app line-of-business (LOB) in teams, sono necessari due tenant: un tenant di test per lo sviluppo e un tenant di produzione.

> [!NOTE]
> Se non si dispone già di un tenant di prova, è possibile crearne rapidamente uno e popolarlo con i dati di test usando il programma per sviluppatori di Office 365. [Altre informazioni qui](https://developer.microsoft.com/office/dev-program).

## <a name="step-1-develop-and-test"></a>Passaggio 1: sviluppare e testare

### <a name="create-test-users"></a>Creare utenti di test

Assicurarsi che gli sviluppatori, sia interni che esterni, abbiano account nel tenant di test. Leggi [altre informazioni sull'aggiunta di utenti](https://docs.microsoft.com/office365/admin/add-users/add-users).

### <a name="allow-custom-apps-in-the-test-tenant"></a>Consentire app personalizzate nel tenant di test

Per offrire agli sviluppatori l'accesso necessario per il test, consentire a tutti gli utenti del tenant di test di caricare app personalizzate (nota anche come sideload). In questo modo gli sviluppatori possono caricare un'app personalizzata per l'uso personale o attraverso il tenant di test senza dover inviare l'app allo Store app teams. Il caricamento di un'app personalizzata consente agli sviluppatori di testare un'app prima di distribuirla più ampiamente.

Per consentire agli utenti di caricare app personalizzate, eseguire le operazioni seguenti:

1. Attivare l'impostazione **Consenti interazione con le app personalizzate** a livello di organizzazione. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/)accedere ai**criteri di autorizzazione**delle **app** > teams e quindi fare clic su **impostazioni a livello di organizzazione**.
    2. In **app personalizzate**attivare Consenti l' **interazione con le app personalizzate**e quindi fare clic su **Salva**.

    ![Screenshot dell'impostazione "Consenti interazione con le app personalizzate" a livello di organizzazione](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Attivare l'impostazione **carica app personalizzate** nei criteri di configurazione dell'app globale. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/), accedere ai**criteri di configurazione**delle **app** > teams e quindi fare clic sul criterio **globale (a livello di organizzazione)** .
    2. Attivare **carica app personalizzate**e quindi fare clic su **Salva**.

    ![Screenshot dell'impostazione di criteri di installazione dell'app "carica app personalizzate"](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> C'è anche un'impostazione per l'app carica personalizzata a livello di team. Per impostazione predefinita, questa impostazione è attivata. Tuttavia, se gli sviluppatori non riescono a caricare un'app personalizzata in un team, controlla l'impostazione seguendo la [procedura seguente](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting).

### <a name="create-your-app"></a>Creare la tua app

Gli sviluppatori dovrebbero ora avere ciò che serve per creare la tua app. Vedere [qui](https://docs.microsoft.commicrosoftteams/platform) per indicazioni su questo.

## <a name="step-2-validate-in-production"></a>Passaggio 2: convalidare in produzione

### <a name="get-the-app-package"></a>Ottenere il pacchetto dell'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore dovrebbe produrre un pacchetto dell'app. Possono usare [App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio) per questo. Verrà inviato il file in formato zip.

Microsoft usa [queste linee guida](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval) per assicurarti che le app siano conformi agli standard di qualità e sicurezza dello Store Global teams app.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Consentire agli utenti attendibili di caricare app personalizzate nel tenant di produzione

Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a utenti e/o trusted dell'organizzazione di caricare app personalizzate.  Analogamente a quanto indicato in precedenza in [Consenti app personalizzate nel passaggio del tenant di test](#allow-custom-apps-in-the-test-tenant) , puoi usare i criteri di configurazione delle app per eseguire questa operazione.

> [!NOTE]
> Se non si è in grado di caricare l'app nel tenant di produzione per la convalida, anche per se stessi o per gli utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi 3 e 4 per caricare l'app non convalidata nello Store delle app del tenant. Limita quindi l'accesso all'app solo a te e agli utenti di cui ti fidi. Questi utenti possono quindi ottenere l'app dall'archivio delle app tenant per eseguire la convalida. Dopo la convalidazione dell'app, USA gli stessi criteri di autorizzazione per aprire Access ed eseguire il rollback dell'app per l'uso della produzione.

Per consentire agli utenti attendibili di caricare app personalizzate, eseguire le operazioni seguenti:

1. Attivare l'impostazione **Consenti interazione con le app personalizzate** a livello di organizzazione. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/)accedere ai**criteri di autorizzazione**delle **app** > teams e quindi fare clic su **impostazioni a livello di organizzazione**.
    2. In **app personalizzate**attivare Consenti l' **interazione con le app personalizzate**e quindi fare clic su **Salva**.
2. Disattivare l'impostazione **carica app personalizzate** nei criteri di configurazione dell'app globale. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/), accedere ai**criteri di configurazione**delle **app** > teams e quindi fare clic sul criterio **globale (a livello di organizzazione)** .
    2. Disattivare **carica app personalizzate**e quindi fare clic su **Salva**.
3. Crea un nuovo criterio di configurazione dell'app che consente di caricare app personalizzate e assegnarlo al set di utenti attendibili. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di [amministrazione di Microsoft teams](https://admin.teams.microsoft.com/)accedere ai**criteri di configurazione**delle **app** > teams e quindi fare clic su **Aggiungi**. Assegnare al nuovo criterio un nome e una descrizione, attivare **carica app personalizzate**e quindi fare clic su **Salva**.
    2. Selezionare il nuovo criterio creato e quindi fare clic su **Gestisci utenti**. Cercare un utente, fare clic su **Aggiungi**e quindi su **applica**. Ripetere questo passaggio per assegnare i criteri a tutti gli utenti attendibili.

        ![Screenshot della pagina "Aggiungi criteri di configurazione dell'app"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a>Passaggio 3: caricare il catalogo delle app tenant

Per rendere l'app disponibile per gli utenti nello Store delle app tenant, carica l'app. Puoi eseguire questa operazione usando il client desktop teams. Seguire [questa procedura.](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog)

![Screenshot della pagina delle app](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a>Passaggio 4: configurare e assegnare autorizzazioni

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti hanno accesso a questa app nell'app teams Store. Per limitare e controllare chi ha l'autorizzazione per l'uso dell'app, puoi creare e assegnare un nuovo criterio di autorizzazione per le app. Seguire [questa procedura.](teams-app-permission-policies.md#create-a-custom-app-permission-policy)

![Screenshot della pagina "Aggiungi criteri di autorizzazione per le app"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Aggiungere l'app agli utenti da individuare

Per impostazione predefinita, per consentire agli utenti di trovare l'app, è necessario passare a teams App Store e cercarla. Per semplificare l'accesso all'app da parte degli utenti, puoi aggiungere l'app alla barra dell'app in teams. A questo scopo, crea un nuovo criterio di configurazione dell'app e assegnalo agli utenti. Seguire [questa procedura.](teams-app-setup-policies.md#create-a-custom-app-setup-policy)

![Screenshot del riquadro "Aggiungi app pinne"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Passaggio 5: aggiornare l'app

![Panoramica della tua app dallo sviluppo alla distribuzione](media/manage-your-lob-apps-update.png)

Per aggiornare un'app, gli sviluppatori devono continuare a seguire il [passaggio 1](#step-1-develop-and-test) e il [passaggio 2](#step-2-validate-in-production).

Puoi aggiornare l'app tramite il catalogo delle app tenant. A tale scopo, nel client desktop teams passa a **app** > **create per &lt;il nome&gt;del tenant**, fai clic su **...** nell'angolo in alto a destra dell'app, quindi fare clic su **Aggiorna**. Questa operazione sostituisce l'app esistente nel catalogo delle app tenant e tutti i criteri di autorizzazione e i criteri di configurazione restano applicati per l'app aggiornata. 

![Screenshot dell'aggiornamento di un'app nella pagina delle app](media/manage-your-lob-apps-update-app.png)