---
title: Gestire l'app turni per l'organizzazione
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come configurare e gestire l'app turni in teams per gli operatori di I FIRSTLINE dell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 405c918dfe71fce02ab19f3ccf49cc124877da41
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820470"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="cf7c6-103">Gestire l'app turni per l'organizzazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf7c6-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf7c6-104">Efficace il 30 giugno 2020, Microsoft StaffHub è stato ritirato.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="cf7c6-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="cf7c6-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="cf7c6-107">StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="cf7c6-108">Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="cf7c6-109">Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="cf7c6-110">Panoramica dei turni</span><span class="sxs-lookup"><span data-stu-id="cf7c6-110">Overview of Shifts</span></span>

<span data-ttu-id="cf7c6-111">L'app turni in Microsoft teams mantiene i dipendenti di I FIRSTLINE connessi e sincronizzati. È stato costruito per la prima volta per la gestione e la comunicazione del tempo veloce ed efficace per i team.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="cf7c6-112">Turni consente ai dipendenti di I FIRSTLINE e ai loro manager di usare i loro dispositivi mobili per gestire le pianificazioni e tenersi in contatto.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="cf7c6-113">I manager creano, aggiornano e gestiscono le pianificazioni di turno per i team.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="cf7c6-114">Possono inviare messaggi a una sola persona ("c'è una fuoriuscita sul pavimento") o all'intero team ("il GM regionale arriva in 20 minuti").</span><span class="sxs-lookup"><span data-stu-id="cf7c6-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="cf7c6-115">Possono anche inviare documenti di policy, notiziari e video.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="cf7c6-116">I dipendenti visualizzano i loro turni imminenti, possono vedere chi altro è programmato per il giorno, richiedere di scambiare o offrire un turno e richiedere il tempo libero.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="cf7c6-117">È importante sapere che i turni attualmente non supportano gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="cf7c6-118">Ciò significa che gli ospiti di un team non possono essere aggiunti o usare le pianificazioni di turni quando l'accesso Guest è attivato in teams.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="cf7c6-119">Per informazioni dettagliate sulle funzionalità di spostamento su piattaforme diverse, vedere [caratteristiche dei team per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="cf7c6-120">Disponibilità di turni</span><span class="sxs-lookup"><span data-stu-id="cf7c6-120">Availability of Shifts</span></span>

<span data-ttu-id="cf7c6-121">Turni è disponibile in tutti gli SKU aziendali in cui è disponibile teams.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="cf7c6-122">Posizione dei dati di turni</span><span class="sxs-lookup"><span data-stu-id="cf7c6-122">Location of Shifts data</span></span>

<span data-ttu-id="cf7c6-123">Turni i dati sono attualmente archiviati in Azure nei data center in Nord America, Europa occidentale e Asia Pacifico.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="cf7c6-124">Per altre informazioni sulla posizione di archiviazione dei dati, vedere [dove sono i dati](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="cf7c6-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="cf7c6-125">Configurare turni</span><span class="sxs-lookup"><span data-stu-id="cf7c6-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="cf7c6-126">Abilitare o disabilitare i turni nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="cf7c6-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="cf7c6-127">Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="cf7c6-128">Puoi disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="cf7c6-129">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, vai alle **app teams**  >  **Manage Apps** .</span><span class="sxs-lookup"><span data-stu-id="cf7c6-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="cf7c6-130">Nell'elenco delle app eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf7c6-130">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="cf7c6-131">Per disattivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi fare clic su **blocca**.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="cf7c6-132">Per attivare i turni per l'organizzazione, cercare l'app turni, selezionarla e quindi fare clic su **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="cf7c6-133">Abilitare o disabilitare turni per utenti specifici dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="cf7c6-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="cf7c6-134">Per consentire o bloccare gli utenti specifici dell'organizzazione dall'uso di turni, verificare che i turni siano attivati per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) e quindi creare un criterio di autorizzazione per le app personalizzate e assegnarlo a tali utenti.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="cf7c6-135">Per altre informazioni, vedere [gestire i criteri di autorizzazione delle app in teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="cf7c6-136">Usare i criteri di configurazione dell'app FirstlineWorker per aggiungere i turni ai team</span><span class="sxs-lookup"><span data-stu-id="cf7c6-136">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="cf7c6-137">I criteri di configurazione delle app consentono di personalizzare i team per evidenziare le app più importanti per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="cf7c6-138">Le app impostate in un criterio sono bloccate alla barra dell'app &mdash; la barra sul lato del client desktop teams e nella parte inferiore dei client per dispositivi mobili in &mdash; cui gli utenti possono accedervi in modo rapido e semplice.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="cf7c6-139">Teams include un criterio di configurazione dell'app FirstlineWorker predefinito che puoi assegnare a dipendenti di I FIRSTLINE nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-139">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="cf7c6-140">Per impostazione predefinita, il criterio include le app attività, turni, chat e chiamate.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="cf7c6-141">Per visualizzare i criteri di FirstlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams accedere ai criteri di configurazione dell'app **Teams app**  >  **App setup policies**.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-141">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="cf7c6-142">![Screenshot dei criteri di configurazione dell'app FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot dei criteri di configurazione dell'app FirstlineWorker nell'interfaccia di amministrazione di Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="cf7c6-142">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="cf7c6-143">Assegnare i criteri di configurazione dell'app FirstlineWorker agli utenti</span><span class="sxs-lookup"><span data-stu-id="cf7c6-143">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="cf7c6-144">Eseguire ricerche nel log di controllo per gli eventi turni</span><span class="sxs-lookup"><span data-stu-id="cf7c6-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="cf7c6-145">**(in anteprima)**</span><span class="sxs-lookup"><span data-stu-id="cf7c6-145">**(in preview)**</span></span>

<span data-ttu-id="cf7c6-146">È possibile eseguire una ricerca nel log di controllo per visualizzare le attività di turni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="cf7c6-147">Per altre informazioni su come eseguire una ricerca nel log di controllo e visualizzare un elenco di [attività di turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [eseguire la ricerca nel log di controllo per gli eventi in teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="cf7c6-148">Prima di eseguire una ricerca nel log di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="cf7c6-149">Per altre informazioni, vedere [attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="cf7c6-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="cf7c6-150">Tieni presente che i dati di controllo sono disponibili solo dal momento in cui hai attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="cf7c6-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf7c6-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cf7c6-151">Related topics</span></span>

- [<span data-ttu-id="cf7c6-152">Sposta la guida per gli operatori di I FIRSTLINE</span><span class="sxs-lookup"><span data-stu-id="cf7c6-152">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="cf7c6-153">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="cf7c6-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
