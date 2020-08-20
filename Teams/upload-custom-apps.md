---
title: Caricare le app personalizzate nell'interfaccia di amministrazione di Microsoft Teams
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
description: Informazioni su come caricare le app personalizzate nell'App Store dell'organizzazione nell'interfaccia di amministrazione di Microsoft teams.
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583645"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a><span data-ttu-id="ea032-103">Pubblicare un'app personalizzata caricando un pacchetto dell'app</span><span class="sxs-lookup"><span data-stu-id="ea032-103">Publish a custom app by uploading an app package</span></span>

> [!NOTE]
> <span data-ttu-id="ea032-104">Quando pubblichi un'app teams personalizzata, è disponibile per gli utenti nell'App Store dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-104">When you publish a custom Teams app, it's available to users in your organization's app store.</span></span> <span data-ttu-id="ea032-105">Esistono due modi per pubblicare un'app personalizzata e il modo in cui si usa dipende da come si ottiene l'app.</span><span class="sxs-lookup"><span data-stu-id="ea032-105">There are two ways to publish a custom app and the way that you use depends on how you get the app.</span></span> <span data-ttu-id="ea032-106">**Questo articolo illustra come pubblicare un'app personalizzata caricando un pacchetto dell'app (in formato zip) inviato da uno sviluppatore**.</span><span class="sxs-lookup"><span data-stu-id="ea032-106">**This article focuses on how to publish a custom app by uploading an app package (in .zip format) that a developer sends you**.</span></span> <span data-ttu-id="ea032-107">L'altro metodo che approva un'app personalizzata viene usato quando uno sviluppatore Invia un'app direttamente alla pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci</a> app tramite l'API di invio dell'app teams.</span><span class="sxs-lookup"><span data-stu-id="ea032-107">The other method, approving a custom app, is used when a developer submits an app directly to the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page through the Teams App Submission API.</span></span> <span data-ttu-id="ea032-108">Per altre informazioni su questo metodo, vedere <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">pubblicare un'app personalizzata inviata tramite l'API di invio dell'app teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-108">To learn more about that method, see <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.</span></span>

<span data-ttu-id="ea032-109">Questo articolo fornisce indicazioni complete su come portare l'app teams dallo sviluppo alla distribuzione all'individuazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-109">This article provides end-to-end guidance for how to take your Teams app from development to deployment to discovery.</span></span> <span data-ttu-id="ea032-110">Questa guida si basa sugli aspetti relativi ai team dell'app ed è destinata ad amministratori e professionisti IT.</span><span class="sxs-lookup"><span data-stu-id="ea032-110">This guidance focuses on the Teams aspects of the app and is intended for admins and IT pros.</span></span> <span data-ttu-id="ea032-111">Per altre informazioni sullo sviluppo di app per Team, vedi la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione per sviluppatori di teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-111">For more information about developing Teams apps, see the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

![Panoramica della tua app dallo sviluppo alla distribuzione](media/upload-custom-apps.png)

## <a name="develop"></a><span data-ttu-id="ea032-113">Sviluppo</span><span class="sxs-lookup"><span data-stu-id="ea032-113">Develop</span></span>

### <a name="create-your-app"></a><span data-ttu-id="ea032-114">Creare la tua app</span><span class="sxs-lookup"><span data-stu-id="ea032-114">Create your app</span></span>

<span data-ttu-id="ea032-115">La piattaforma Microsoft teams per sviluppatori consente agli sviluppatori di integrare facilmente le tue app e i tuoi servizi per migliorare la produttività, prendere decisioni più velocemente e creare collaborazione attorno a contenuti e flussi di lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="ea032-115">The Microsoft Teams developer platform makes it easy for developers to integrate your own apps and services to improve productivity, make decisions faster, and create collaboration around existing content and workflows.</span></span> <span data-ttu-id="ea032-116">Le app create nella piattaforma teams sono ponticelli tra il client teams e i servizi e i flussi di lavoro, che li portano direttamente nel contesto della piattaforma di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-116">Apps built on the Teams platform are bridges between the Teams client and your services and workflows, bringing them directly into the context of your collaboration platform.</span></span> <span data-ttu-id="ea032-117">Per altre informazioni, vedere la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentazione relativa allo sviluppatore di teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-117">For more information, go to the <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">Teams developer documentation</a>.</span></span>

## <a name="validate"></a><span data-ttu-id="ea032-118">Convalidare</span><span class="sxs-lookup"><span data-stu-id="ea032-118">Validate</span></span>

### <a name="get-the-app-package"></a><span data-ttu-id="ea032-119">Ottenere il pacchetto dell'app</span><span class="sxs-lookup"><span data-stu-id="ea032-119">Get the app package</span></span>

<span data-ttu-id="ea032-120">Quando l'app è pronta per l'uso in produzione, lo sviluppatore dovrebbe produrre un pacchetto dell'app.</span><span class="sxs-lookup"><span data-stu-id="ea032-120">When the app is ready for use in production, the developer should produce an app package.</span></span> <span data-ttu-id="ea032-121">Possono usare <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> per questo.</span><span class="sxs-lookup"><span data-stu-id="ea032-121">They can use <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> for that.</span></span> <span data-ttu-id="ea032-122">Verrà inviato il file in formato zip.</span><span class="sxs-lookup"><span data-stu-id="ea032-122">They'll send you the file in .zip format.</span></span>

<span data-ttu-id="ea032-123">Microsoft usa <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">queste linee guida</a> per assicurarti che le app siano conformi agli standard di qualità e sicurezza dello Store Global teams app.</span><span class="sxs-lookup"><span data-stu-id="ea032-123">Microsoft uses <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">these guidelines</a> to ensure apps comply with the quality and security standards of the global Teams apps store.</span></span>

### <a name="allow-trusted-users-to-upload-custom-apps"></a><span data-ttu-id="ea032-124">Consentire agli utenti attendibili di caricare app personalizzate</span><span class="sxs-lookup"><span data-stu-id="ea032-124">Allow trusted users to upload custom apps</span></span>

<span data-ttu-id="ea032-125">Per verificare che l'app funzioni correttamente nel tenant di produzione, è necessario consentire a utenti e/o trusted di caricare app personalizzate nel tenant di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea032-125">To validate that the app is working correctly in your production tenant, you need to allow yourself and/or trusted users to upload custom apps in the production tenant.</span></span> <span data-ttu-id="ea032-126">Puoi usare i <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">criteri di configurazione delle app</a> per eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-126">You use <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">app setup policies</a> to do this.</span></span>

> [!NOTE]
> <span data-ttu-id="ea032-127">Se non si è sicuri di caricare l'app nel tenant di produzione per la convalida, anche per se stessi o per gli utenti attendibili, è possibile ignorare questo passaggio e seguire i passaggi descritti in [caricare](#upload) e [configurare e gestire](#set-up-and-manage) le sezioni per pubblicare l'app non convalidata nell'App Store dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-127">If you're uncomfortable with uploading the app to your production tenant for validation, even for yourself or trusted users, you can skip this step and follow the steps in the [Upload](#upload) and [Set up and manage](#set-up-and-manage) sections to publish the unvalidated app to your organization's app store.</span></span> <span data-ttu-id="ea032-128">Limita quindi l'accesso all'app solo a te e agli utenti di cui ti fidi.</span><span class="sxs-lookup"><span data-stu-id="ea032-128">Then, restrict access to that app to only yourself and users you trust.</span></span> <span data-ttu-id="ea032-129">Questi utenti possono quindi ottenere l'app dall'App Store dell'organizzazione per eseguire la convalida.</span><span class="sxs-lookup"><span data-stu-id="ea032-129">These users can then get the app from your organization's app store to perform validation.</span></span> <span data-ttu-id="ea032-130">Dopo la convalidazione dell'app, USA gli stessi criteri di autorizzazione per aprire Access ed eseguire il rollback dell'app per l'uso della produzione.</span><span class="sxs-lookup"><span data-stu-id="ea032-130">After the app is validated, use the same permission policies to open access and roll the app out for production use.</span></span>

<span data-ttu-id="ea032-131">Per consentire agli utenti attendibili di caricare app personalizzate, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea032-131">To allow trusted users to upload custom apps, follow these steps:</span></span>

1. <span data-ttu-id="ea032-132">Attivare l'impostazione **Consenti interazione con** le app personalizzate per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-132">Turn on the **Allow interaction with custom apps** org-wide app setting.</span></span> <span data-ttu-id="ea032-133">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="ea032-133">To do this:</span></span>
    1. <span data-ttu-id="ea032-134">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**, quindi fai clic su **impostazioni dell'app a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ea032-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
    2. <span data-ttu-id="ea032-135">In **app personalizzate**attivare Consenti l' **interazione con le app personalizzate**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ea032-135">Under **Custom apps**, turn on **Allow interaction with custom apps**, and then click **Save**.</span></span>
2. <span data-ttu-id="ea032-136">Disattivare l'impostazione **carica app personalizzate** nei criteri di configurazione dell'app globale.</span><span class="sxs-lookup"><span data-stu-id="ea032-136">Turn off the **Upload custom apps** setting in the global app setup policy.</span></span> <span data-ttu-id="ea032-137">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="ea032-137">To do this:</span></span>
    1. <span data-ttu-id="ea032-138">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, accedere ai criteri di configurazione delle **app teams**  >  **Setup policies**e quindi fare clic sul criterio **globale (a livello di organizzazione)** .</span><span class="sxs-lookup"><span data-stu-id="ea032-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Global (Org-wide default)** policy.</span></span>
    2. <span data-ttu-id="ea032-139">Disattivare **carica app personalizzate**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ea032-139">Turn off **Upload custom apps**, and then click **Save**.</span></span>
3. <span data-ttu-id="ea032-140">Crea un nuovo criterio di configurazione dell'app che consente di caricare app personalizzate e assegnarlo al set di utenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea032-140">Create a new app setup policy that allows uploading custom apps and assign it to your set of trusted users.</span></span> <span data-ttu-id="ea032-141">Procedi come segue.</span><span class="sxs-lookup"><span data-stu-id="ea032-141">To do this:</span></span>
    1. <span data-ttu-id="ea032-142">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione delle **app teams**  >  **Setup policies**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ea032-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**, and then click the **Add**.</span></span> <span data-ttu-id="ea032-143">Assegnare al nuovo criterio un nome e una descrizione, attivare **carica app personalizzate**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ea032-143">Give the new policy a name and description, turn on **Upload custom apps**, and then click **Save**.</span></span>
    2. <span data-ttu-id="ea032-144">Selezionare il nuovo criterio creato e quindi fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="ea032-144">Select the new policy you created, and then click **Manage users**.</span></span> <span data-ttu-id="ea032-145">Cercare un utente, fare clic su **Aggiungi**e quindi su **applica**.</span><span class="sxs-lookup"><span data-stu-id="ea032-145">Search for a user, click **Add**, and then click **Apply**.</span></span> <span data-ttu-id="ea032-146">Ripetere questo passaggio per assegnare i criteri a tutti gli utenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea032-146">Repeat this step to assign the policy to all your trusted users.</span></span>

        ![Screenshot della pagina "Aggiungi criteri di configurazione dell'app"](media/manage-your-lob-apps-new-app-setup-policy.png)

    <span data-ttu-id="ea032-148">Questi utenti possono ora caricare il manifesto dell'app per verificare che l'app funzioni correttamente nel tenant di produzione.</span><span class="sxs-lookup"><span data-stu-id="ea032-148">These users can now upload the app manifest to validate that the app is working correctly in the production tenant.</span></span>

## <a name="upload"></a><span data-ttu-id="ea032-149">Caricare</span><span class="sxs-lookup"><span data-stu-id="ea032-149">Upload</span></span>

<span data-ttu-id="ea032-150">Per rendere l'app disponibile per gli utenti nell'App Store dell'organizzazione, carica l'app.</span><span class="sxs-lookup"><span data-stu-id="ea032-150">To make the app available to users in your organization's app store, upload the app.</span></span> <span data-ttu-id="ea032-151">Puoi eseguire questa operazione nella pagina <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gestisci app</a> dell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ea032-151">You can do this on the <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage apps</a> page of the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ea032-152">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps**.</span><span class="sxs-lookup"><span data-stu-id="ea032-152">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="ea032-153">Fare clic su **carica**, su **Seleziona un file**e quindi selezionare il pacchetto dell'app ricevuto dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="ea032-153">Click **Upload**, click **Select a file**, and then select the app package that you received from the developer.</span></span>

   ![Screenshot del caricamento di un'app nell'interfaccia di amministrazione](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a><span data-ttu-id="ea032-155">Configurare e gestire</span><span class="sxs-lookup"><span data-stu-id="ea032-155">Set up and manage</span></span>

### <a name="control-access-to-the-app"></a><span data-ttu-id="ea032-156">Controllare l'accesso all'app</span><span class="sxs-lookup"><span data-stu-id="ea032-156">Control access to the app</span></span>

<span data-ttu-id="ea032-157">Per impostazione predefinita, tutti gli utenti dell'organizzazione possono accedere all'app nell'App Store dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-157">By default, all users in your organization can access the app in your organization's app store.</span></span> <span data-ttu-id="ea032-158">Per limitare e controllare chi ha l'autorizzazione per l'uso dell'app, puoi creare e assegnare un criterio di autorizzazione per le app.</span><span class="sxs-lookup"><span data-stu-id="ea032-158">To restrict and control who has permission to use the app, you can create and assign an app permission policy.</span></span> <span data-ttu-id="ea032-159">Per altre informazioni, vedere <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gestire i criteri di autorizzazione delle app in teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-159">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Manage app permission policies in Teams</a>.</span></span>

### <a name="pin-and-install-the-app-for-users-to-discover"></a><span data-ttu-id="ea032-160">Aggiungere e installare l'app per individuare gli utenti</span><span class="sxs-lookup"><span data-stu-id="ea032-160">Pin and install the app for users to discover</span></span>

<span data-ttu-id="ea032-161">Per impostazione predefinita, gli utenti possono trovare l'app che devono passare all'App Store dell'organizzazione e cercarla.</span><span class="sxs-lookup"><span data-stu-id="ea032-161">By default, for users to find the app they have to go to your organization's app store and browse or search for it.</span></span> <span data-ttu-id="ea032-162">Per semplificare l'accesso all'app da parte degli utenti, puoi aggiungere l'app alla barra dell'app in teams.</span><span class="sxs-lookup"><span data-stu-id="ea032-162">To make it easy for users to get to the app, you can pin the app to the app bar in Teams.</span></span> <span data-ttu-id="ea032-163">A questo scopo, crea un criterio di configurazione dell'app e assegnalo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ea032-163">To do this, create an app setup policy and assign it to users.</span></span> <span data-ttu-id="ea032-164">Per altre informazioni, Vedi <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gestire i criteri di configurazione delle app in teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-164">To learn more, see <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Manage app setup policies in Teams</a>.</span></span>

### <a name="search-the-audit-log-for-teams-app-events"></a><span data-ttu-id="ea032-165">Eseguire ricerche nel log di controllo per gli eventi delle app Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-165">Search the audit log for Teams app events</span></span>

<span data-ttu-id="ea032-166">È possibile eseguire una ricerca nel log di controllo per visualizzare l'attività delle app teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-166">You can search the audit log to view Teams apps activity in your organization.</span></span> <span data-ttu-id="ea032-167">Per altre informazioni su come eseguire una ricerca nel log di controllo e visualizzare un elenco di attività di Team registrate nel log di controllo, vedere <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">eseguire la ricerca nel log di controllo per gli eventi in teams</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-167">To learn more about how to search the audit log and to see a list of Teams activities that are logged in the audit log, see <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Search the audit log for events in Teams</a>.</span></span>

<span data-ttu-id="ea032-168">Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel <a href="https://protection.office.com" target="_blank">centro conformità & sicurezza</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-168">Before you can search the audit log, you have to first turn on auditing in the <a href="https://protection.office.com" target="_blank">Security & Compliance Center</a>.</span></span> <span data-ttu-id="ea032-169">Per altre informazioni, vedere <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">attivare o disattivare la ricerca nel log di controllo</a>.</span><span class="sxs-lookup"><span data-stu-id="ea032-169">To learn more, see <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Turn audit log search on or off</a>.</span></span> <span data-ttu-id="ea032-170">Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="ea032-170">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="discover-and-adopt"></a><span data-ttu-id="ea032-171">Individuare e adottare</span><span class="sxs-lookup"><span data-stu-id="ea032-171">Discover and adopt</span></span>

<span data-ttu-id="ea032-172">Gli utenti che hanno le autorizzazioni per l'app possono trovarlo nell'App Store dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-172">Users who have permissions to the app can find it in your organization's app store.</span></span> <span data-ttu-id="ea032-173">Passa a \*\*compilato per *il nome dell'organizzazione* \*\* nella pagina app per trovare le app personalizzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea032-173">Go to **Built for *Your Organization Name*** on the Apps page to find your organization's custom apps.</span></span>

![<span data-ttu-id="ea032-174">Screenshot della pagina app che mostra l'app pubblicata</span><span class="sxs-lookup"><span data-stu-id="ea032-174">Screenshot of Apps page showing published app</span></span> ](media/custom-app-lifecycle-discovery.png)

<span data-ttu-id="ea032-175">Se hai creato e assegnato un criterio di configurazione dell'app, l'app viene aggiunta alla barra dell'app in teams per facilitare l'accesso agli utenti a cui è stato assegnato il criterio.</span><span class="sxs-lookup"><span data-stu-id="ea032-175">If you created and assigned an app setup policy, the app is pinned to the app bar in Teams for easy access for those users who were assigned the policy.</span></span>

## <a name="update"></a><span data-ttu-id="ea032-176">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ea032-176">Update</span></span>

<span data-ttu-id="ea032-177">Per aggiornare un'app, gli sviluppatori devono continuare a seguire i passaggi descritti nelle sezioni [sviluppo](#develop) e [convalida](#validate) .</span><span class="sxs-lookup"><span data-stu-id="ea032-177">To update an app, developers should continue to follow the steps in the [Develop](#develop) and [Validate](#validate) sections.</span></span>

<span data-ttu-id="ea032-178">Puoi aggiornare l'app nella pagina Gestisci app nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="ea032-178">You can update the app on the Manage apps page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ea032-179">A questo scopo, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **Teams Apps**  >  **Manage Apps**.</span><span class="sxs-lookup"><span data-stu-id="ea032-179">To do this, in the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="ea032-180">Fare clic sul nome dell'app e quindi su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="ea032-180">Click the app name, and then click **Update**.</span></span> <span data-ttu-id="ea032-181">Questa operazione sostituisce l'app esistente e tutti i criteri di autorizzazione delle app e i criteri di configurazione delle app restano applicati per l'app aggiornata.</span><span class="sxs-lookup"><span data-stu-id="ea032-181">Doing this replaces the existing app, and all app permission policies and app setup policies remain enforced for the updated app.</span></span>

### <a name="end-user-update-experience"></a><span data-ttu-id="ea032-182">Esperienza di aggiornamento degli utenti finali</span><span class="sxs-lookup"><span data-stu-id="ea032-182">End user update experience</span></span>

<span data-ttu-id="ea032-183">Nella maggior parte dei casi, dopo aver completato l'aggiornamento di un'app, la nuova versione viene visualizzata automaticamente per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="ea032-183">In most cases, after you complete an app update the new version automatically appears for end users.</span></span> <span data-ttu-id="ea032-184">Tuttavia, esistono alcuni aggiornamenti al manifesto di <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft teams</a> che richiedono l'accettazione da parte dell'utente:</span><span class="sxs-lookup"><span data-stu-id="ea032-184">However, there are some updates to the <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="ea032-185">È stato aggiunto o rimosso un bot</span><span class="sxs-lookup"><span data-stu-id="ea032-185">A bot was added or removed</span></span>
* <span data-ttu-id="ea032-186">Modifica della proprietà "botId" di un bot esistente</span><span class="sxs-lookup"><span data-stu-id="ea032-186">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="ea032-187">Modifica della proprietà "isNotificationOnly" di un bot esistente</span><span class="sxs-lookup"><span data-stu-id="ea032-187">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="ea032-188">La proprietà "supportsFiles" del bot è cambiata</span><span class="sxs-lookup"><span data-stu-id="ea032-188">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="ea032-189">È stata aggiunta o rimossa un'estensione della messaggistica</span><span class="sxs-lookup"><span data-stu-id="ea032-189">A Messaging extension was added or removed</span></span>
* <span data-ttu-id="ea032-190">È stato aggiunto un nuovo connettore</span><span class="sxs-lookup"><span data-stu-id="ea032-190">A new connector was added</span></span>
* <span data-ttu-id="ea032-191">È stata aggiunta una nuova scheda statica</span><span class="sxs-lookup"><span data-stu-id="ea032-191">A new static tab was added</span></span>
* <span data-ttu-id="ea032-192">È stata aggiunta una nuova scheda configurabile</span><span class="sxs-lookup"><span data-stu-id="ea032-192">A new configurable tab was added</span></span>
* <span data-ttu-id="ea032-193">Proprietà all'interno di "webApplicationInfo" modificate</span><span class="sxs-lookup"><span data-stu-id="ea032-193">Properties inside "webApplicationInfo" changed</span></span>

![Screenshot dell'elenco delle app, che mostra le app che hanno una nuova versione disponibile](media/manage-your-custom-apps-update1.png)

![Screenshot dell'opzione di aggiornamento per un'app](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a><span data-ttu-id="ea032-196">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ea032-196">Related topics</span></span>

- [<span data-ttu-id="ea032-197">Pubblicare un'app personalizzata inviata tramite l'API di invio di app Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-197">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
- [<span data-ttu-id="ea032-198">Gestire le app nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-198">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="ea032-199">Gestire le impostazioni e i criteri delle app personalizzate in Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-199">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="ea032-200">Gestire i criteri di autorizzazione delle app in Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-200">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="ea032-201">Gestire i criteri di configurazione delle app in Teams</span><span class="sxs-lookup"><span data-stu-id="ea032-201">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)