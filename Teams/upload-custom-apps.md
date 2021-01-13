---
title: Caricare le app personalizzate nell'interfaccia di amministrazione di Microsoft Teams
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
description: Informazioni su come caricare le app personalizzate nell'App Store dell'organizzazione nell'interfaccia di amministrazione di Microsoft teams.
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831166"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Pubblicare un'app personalizzata caricando un pacchetto dell'app

> [!NOTE]
> Quando pubblichi un'app teams personalizzata, è disponibile per gli utenti nell'App Store dell'organizzazione. Esistono due modi per pubblicare un'app personalizzata e il modo in cui si usa dipende da come si ottiene l'app. **Questo articolo illustra come pubblicare un'app personalizzata caricando un pacchetto dell'app (in formato zip) inviato da uno sviluppatore**. L'altro metodo che approva un'app personalizzata viene usato quando uno sviluppatore Invia un'app direttamente alla pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci</a> app tramite l'API di invio dell'app teams. Per altre informazioni su questo metodo, vedere <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">pubblicare un'app personalizzata inviata tramite l'API di invio dell'app teams</a>.

Questo articolo fornisce indicazioni complete su come portare l'app teams dallo sviluppo alla distribuzione all'individuazione. Questa guida si basa sugli aspetti relativi ai team dell'app ed è destinata ad amministratori e professionisti IT. Per altre informazioni sullo sviluppo di app per Team, vedi la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione per sviluppatori di teams</a>.

![Panoramica della tua app dallo sviluppo alla distribuzione](media/upload-custom-apps.png)

## <a name="develop"></a>Sviluppo

### <a name="create-your-app"></a>Creare la tua app

La piattaforma Microsoft teams per sviluppatori consente agli sviluppatori di integrare facilmente le tue app e i tuoi servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti. Le app create nella piattaforma teams sono ponticelli tra il client teams e i servizi e i flussi di lavoro, che li portano direttamente nel contesto della piattaforma di collaborazione. Per altre informazioni, vedere la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione relativa allo sviluppatore di teams</a>.

## <a name="validate"></a>Convalidare

### <a name="get-the-app-package"></a>Ottenere il pacchetto dell'app

Quando l'app è pronta per l'uso in produzione, lo sviluppatore dovrebbe produrre un pacchetto dell'app. Possono usare <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> per questo. Verrà inviato il file in formato zip.

Microsoft usa <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">queste linee guida</a> per assicurarti che le app siano conformi agli standard di qualità e sicurezza dello Store Global teams app.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Consentire agli utenti attendibili di caricare app personalizzate

Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a utenti e/o trusted di caricare app personalizzate nel tenant di produzione. Puoi usare i <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">criteri di configurazione delle app</a> per eseguire questa operazione.

> [!NOTE]
> Se non si è sicuri di caricare l'app nel tenant di produzione per la convalida, anche per se stessi o per gli utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi descritti in [caricare](#upload) e [configurare e gestire](#set-up-and-manage) le sezioni per pubblicare l'app non convalidata nell'App Store dell'organizzazione. Limita quindi l'accesso all'app solo a te e agli utenti di cui ti fidi. Questi utenti possono quindi ottenere l'app dall'App Store dell'organizzazione per eseguire la convalida. Dopo la convalidazione dell'app, USA gli stessi criteri di autorizzazione per aprire Access ed eseguire il rollback dell'app per l'uso della produzione.

Per consentire agli utenti attendibili di caricare app personalizzate, eseguire le operazioni seguenti:

1. Attivare l'impostazione **Consenti interazione con** le app personalizzate per l'intera organizzazione. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**, quindi fai clic su **impostazioni dell'app a livello di organizzazione**.
    2. In **app personalizzate** attivare Consenti l' **interazione con le app personalizzate** e quindi fare clic su **Salva**.
2. Disattivare l'impostazione **carica app personalizzate** nei criteri di configurazione dell'app globale. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, accedere ai criteri di configurazione delle **app teams**  >  e quindi fare clic sul criterio **globale (a livello di organizzazione)** .
    2. Disattivare **carica app personalizzate** e quindi fare clic su **Salva**.
3. Crea un nuovo criterio di configurazione dell'app che consente di caricare app personalizzate e assegnarlo al set di utenti attendibili. Procedi come segue.
    1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione delle **app teams**  >  e quindi fare clic su **Aggiungi**. Assegnare al nuovo criterio un nome e una descrizione, attivare **carica app personalizzate** e quindi fare clic su **Salva**.
    2. Selezionare il nuovo criterio creato e quindi fare clic su **Gestisci utenti**. Cercare un utente, fare clic su **Aggiungi** e quindi su **applica**. Ripetere questo passaggio per assegnare i criteri a tutti gli utenti attendibili.

        ![Screenshot della pagina "Aggiungi criteri di configurazione dell'app"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.

## <a name="upload"></a>Caricare

Per rendere l'app disponibile per gli utenti nell'App Store dell'organizzazione, carica l'app. Puoi eseguire questa operazione nella pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app</a> dell'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.
2. Fare clic su **carica**, su **Seleziona un file** e quindi selezionare il pacchetto dell'app ricevuto dallo sviluppatore.

   ![Screenshot del caricamento di un'app nell'interfaccia di amministrazione](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurare e gestire

### <a name="control-access-to-the-app"></a>Controllare l'accesso all'app

Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'App Store dell'organizzazione. Per limitare e controllare chi ha l'autorizzazione per l'uso dell'app, puoi creare e assegnare un criterio di autorizzazione per le app. Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gestire i criteri di autorizzazione delle app in teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Aggiungere e installare l'app per individuare gli utenti

Per impostazione predefinita, gli utenti possono trovare l'app che devono passare all'App Store dell'organizzazione e cercarla. Per semplificare l'accesso all'app da parte degli utenti, puoi aggiungere l'app alla barra dell'app in teams. A questo scopo, crea un criterio di configurazione dell'app e assegnalo agli utenti. Per altre informazioni, Vedi <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gestire i criteri di configurazione delle app in teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Eseguire ricerche nel log di controllo per gli eventi delle app Teams

È possibile eseguire una ricerca nel log di controllo per visualizzare l'attività delle app teams nell'organizzazione. Per altre informazioni su come eseguire una ricerca nel log di controllo e visualizzare un elenco di attività di Team registrate nel log di controllo, vedere <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">eseguire la ricerca nel log di controllo per gli eventi in teams</a>.

Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel <a href="https://protection.office.com" target="_blank">centro conformità & sicurezza</a>. Per altre informazioni, vedere <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">attivare o disattivare la ricerca nel log di controllo</a>. Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.

## <a name="discover-and-adopt"></a>Individuare e adottare

Gli utenti che hanno le autorizzazioni per l'app possono trovarlo nell'App Store dell'organizzazione. Passa a **compilato per *il nome dell'organizzazione*** nella pagina app per trovare le app personalizzate dell'organizzazione.

![Screenshot della pagina app che mostra l'app pubblicata ](media/custom-app-lifecycle-discovery.png)

Se hai creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in teams per facilitare l'accesso agli utenti a cui è stato assegnato il criterio.

## <a name="update"></a>Aggiornamento

Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi descritti nelle sezioni [sviluppo](#develop) e [convalida](#validate) .

Puoi aggiornare l'app nella pagina Gestisci app nell'interfaccia di amministrazione di Microsoft teams. A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**. Fare clic sul nome dell'app e quindi su **Aggiorna**. Questa operazione sostituisce l'app esistente e tutti i criteri di autorizzazione delle app e i criteri di configurazione delle app restano applicati per l'app aggiornata.

### <a name="end-user-update-experience"></a>Esperienza di aggiornamento degli utenti finali

Nella maggior parte dei casi, dopo aver completato l'aggiornamento di un'app, la nuova versione viene visualizzata automaticamente per gli utenti finali. Tuttavia, esistono alcuni aggiornamenti al manifesto di <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft teams</a> che richiedono l'accettazione da parte dell'utente:

* È stato aggiunto o rimosso un bot
* Modifica della proprietà "botId" di un bot esistente
* Modifica della proprietà "isNotificationOnly" di un bot esistente
* La proprietà "supportsFiles" del bot è cambiata
* È stata aggiunta o rimossa un'estensione della messaggistica
* È stato aggiunto un nuovo connettore
* È stata aggiunta una nuova scheda statica
* È stata aggiunta una nuova scheda configurabile
* Proprietà all'interno di "webApplicationInfo" modificate

![Screenshot dell'elenco delle app, che mostra le app che hanno una nuova versione disponibile](media/manage-your-custom-apps-update1.png)

![Screenshot dell'opzione di aggiornamento per un'app](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Argomenti correlati

- [Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams](submit-approve-custom-apps.md)
- [Gestire le app nell'interfaccia di amministrazione di Microsoft Teams](manage-apps.md)
- [Gestire le impostazioni e i criteri delle app personalizzate in Teams](teams-custom-app-policies-and-settings.md)
- [Gestire i criteri di autorizzazione delle app in Teams](teams-app-permission-policies.md)
- [Gestire i criteri di configurazione delle app in Teams](teams-app-setup-policies.md)
