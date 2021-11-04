---
title: Upload le app personalizzate nell'interfaccia Microsoft Teams di amministrazione
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
description: Informazioni su come caricare le app personalizzate nell'app store dell'organizzazione nell'Microsoft Teams di amministrazione.
ms.openlocfilehash: f5e2bffa1f725f9fa741d96bdea17be3096f75f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777106"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Pubblicare un'app personalizzata caricando un pacchetto dell'app

> [!NOTE]
> Quando si pubblica un'app di Teams personalizzata, questa è disponibile per gli utenti nell'app store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui si usa dipende da come si ottiene l'app. **Questo articolo illustra come pubblicare un'app** personalizzata caricando un pacchetto dell'app (in .zip) inviato da uno sviluppatore. L'altro metodo, l'approvazione di un'app personalizzata, viene usato <a href="/microsoftteams/manage-apps" target="_blank"></a> quando uno sviluppatore invia un'app direttamente alla pagina Gestisci app tramite l'API Teams App Submission. Per altre informazioni su questo metodo, vedere <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Pubblicare un'app personalizzata inviata</a>tramite l'API Teams di invio delle app.

Questo articolo fornisce indicazioni end-to-end su come portare l'app Teams dallo sviluppo alla distribuzione all'individuazione. Questa guida è incentrata sugli aspetti Teams'app ed è destinata agli amministratori e ai professionisti IT. Per altre informazioni sullo sviluppo di app Teams, vedere la documentazione <a href="/microsoftteams/platform" target="_blank">Teams per sviluppatori.</a>

![Panoramica dell'app, dallo sviluppo alla distribuzione.](media/upload-custom-apps.png)

## <a name="develop"></a>Sviluppo

### <a name="create-your-app"></a>Creare l'app

La Microsoft Teams per sviluppatori consente agli sviluppatori di integrare facilmente le proprie app e i propri servizi per migliorare la produttività, prendere decisioni più rapidamente e creare collaborazione su contenuti e flussi di lavoro esistenti. Le app create sulla piattaforma Teams sono ponti tra il client Teams e i servizi e i flussi di lavoro, che le portano direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la documentazione Teams <a href="/microsoftteams/platform" target="_blank">per sviluppatori.</a>

## <a name="validate"></a>Convalida

### <a name="get-the-app-package"></a>Ottenere il pacchetto dell'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore deve produrre un pacchetto dell'app. Possono usare <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> per questo. Ti invierà il file in .zip formato.

Microsoft usa <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">queste linee guida</a> per garantire che le app siano conformi agli standard di qualità e sicurezza dello store Teams app globali.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Consentire agli utenti attendibili di caricare app personalizzate

Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a se stessi e/o agli utenti attendibili di caricare app personalizzate nel tenant di produzione. A questo <a href="/microsoftteams/teams-app-setup-policies" target="_blank">scopo si usano i criteri</a> di configurazione delle app.

> [!NOTE]
> Se non si riesce a caricare l'app nel tenant di produzione per la convalida, anche per se stessi [](#set-up-and-manage) o per gli utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi descritti in [Upload](#upload) e Configurare e gestire le sezioni per pubblicare l'app non convalidata nell'app store dell'organizzazione. Limitare quindi l'accesso all'app solo a se stessi e agli utenti attendibili. Questi utenti possono quindi ottenere l'app dall'app store dell'organizzazione per eseguire la convalida. Dopo la convalida dell'app, usare gli stessi criteri di autorizzazione per aprire l'accesso e implementare l'app per l'uso in produzione.

Per consentire agli utenti attendibili di caricare app personalizzate, seguire questa procedura:

1. Attivare **l'impostazione Consenti interazione con app personalizzate** a livello di organizzazione. Procedi come segue.
    1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare Teams **app** Gestisci app e quindi fare clic su Impostazioni app a livello  >   **di organizzazione.**
    2. In **App personalizzate** attivare Consenti interazione con app **personalizzate** e quindi fare clic su **Salva.**
2. Disattivare **l'impostazione Upload app personalizzate** nei criteri di configurazione delle app globali. Procedi come segue.
    1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare Teams criteri di configurazione delle app e quindi fare clic sul criterio  >  Globale **(impostazione** predefinita a livello di organizzazione).
    2. Disattivare Upload **app personalizzate** e quindi fare clic su **Salva.**
3. Creare un nuovo criterio di configurazione dell'app che consenta di caricare app personalizzate e assegnarle al set di utenti attendibili. Procedi come segue.
    1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare Teams criteri di configurazione delle **app** e quindi fare  >  clic su **Aggiungi**. Assegnare un nome e una descrizione al nuovo **criterio,** attivare Upload app personalizzate e quindi fare clic su **Salva.**
    2. Selezionare il nuovo criterio creato e quindi fare clic **su Gestisci utenti.** Cercare un utente, fare clic **su Aggiungi** e quindi su **Applica.** Ripetere questo passaggio per assegnare il criterio a tutti gli utenti attendibili.

        ![Screenshot della pagina "Aggiungere criteri di configurazione dell'app"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.

## <a name="upload"></a>Upload

Per rendere l'app disponibile agli utenti nell'app store dell'organizzazione, caricare l'app. È possibile farlo nella pagina <a href="/microsoftteams/manage-apps" target="_blank">Gestisci app dell'interfaccia</a> Microsoft Teams di amministrazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.
2. Fare **Upload**, fare **clic su Seleziona un file** e quindi selezionare il pacchetto dell'app ricevuto dallo sviluppatore.

   ![Screenshot del caricamento di un'app nell'interfaccia di amministrazione.](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'app store dell'organizzazione. Per limitare e controllare gli utenti autorizzati a usare l'app, è possibile creare e assegnare criteri di autorizzazione per l'app. Per altre informazioni, vedere <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Gestire i criteri di autorizzazione delle app in teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per consentire agli utenti di individuare

Per impostazione predefinita, gli utenti possono trovare l'app che devono accedere all'app store dell'organizzazione e cercarla o cercarla. Per consentire agli utenti di accedere facilmente all'app, è possibile aggiungere l'app alla barra dell'app in Teams. A questo scopo, creare un criterio di configurazione dell'app e assegnarlo agli utenti. Per altre informazioni, vedere <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Gestire i criteri di configurazione delle app in teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Cercare nel log di controllo gli Teams dell'app

È possibile eseguire ricerche nel log di controllo per visualizzare Teams attività delle app nell'organizzazione. Per altre informazioni su come eseguire ricerche nel log di controllo e visualizzare un elenco delle attività di Teams registrate nel log di controllo, vedere Cercare eventi nel log di controllo <a href="/microsoftteams/audit-log-events" target="_blank">in Teams</a>.

Prima di poter eseguire ricerche nel log di controllo, è necessario attivare il controllo nel <a href="https://protection.office.com" target="_blank">Centro sicurezza e conformità</a>. Per altre informazioni, vedere <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Attivare o disattivare la ricerca nel log di controllo</a>. Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="discover-and-adopt"></a>Scopri e adotta

Gli utenti che hanno le autorizzazioni per l'app possono trovarla nell'app store dell'organizzazione. Passare a **Creato per il nome *dell'organizzazione*** nella pagina App per trovare le app personalizzate dell'organizzazione.

![Screenshot della pagina App che mostra l'app pubblicata.](media/custom-app-lifecycle-discovery.png)

Se sono stati creati e assegnati criteri di configurazione dell'app, l'app viene aggiunta alla barra dell'app in Teams per un facile accesso per gli utenti a cui è stato assegnato il criterio.

## <a name="update"></a>Update

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi [delle](#develop) sezioni Sviluppo [e](#validate) Convalida.

È possibile aggiornare l'app nella pagina Gestisci app nell'Microsoft Teams di amministrazione. A questo scopo, nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare Teams   >  **app Gestisci app.** Fare clic sul nome dell'app e quindi su **Aggiorna.** In questo modo l'app esistente viene sostituita e tutti i criteri di autorizzazione delle app e i criteri di configurazione dell'app rimangono applicati per l'app aggiornata.

### <a name="end-user-update-experience"></a>Esperienza di aggiornamento dell'utente finale

Nella maggior parte dei casi, dopo aver completato un aggiornamento dell'app, la nuova versione viene visualizzata automaticamente per gli utenti finali. Esistono tuttavia alcuni aggiornamenti del manifesto di Microsoft Teams <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">che</a> richiedono l'accettazione dell'utente per il completamento:

* Un bot è stato aggiunto o rimosso
* La proprietà "botId" di un bot esistente è stata modificata
* Proprietà "isNotificationOnly" di un bot esistente modificata
* La proprietà "supportsFiles" del bot è stata modificata
* È stata aggiunta o rimossa un'estensione di messaggistica
* È stato aggiunto un nuovo connettore
* È stata aggiunta una nuova scheda statica
* È stata aggiunta una nuova scheda configurabile
* Proprietà all'interno di "webApplicationInfo" modificate

![Screenshot dell'elenco delle app che mostra le app che hanno una nuova versione disponibile.](media/manage-your-custom-apps-update1.png)

![Screenshot dell'opzione di aggiornamento per un'app.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Argomenti correlati

- [Pubblicare un'app personalizzata inviata tramite l'API Teams per l'invio di app](submit-approve-custom-apps.md)
- [Gestire le app nell'interfaccia Microsoft Teams di amministrazione](manage-apps.md)
- [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)