---
title: Gestire l'app Turni per l'organizzazione
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Informazioni su come configurare e gestire l’app Turni in Teams per gli operatori sul campo dell’organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909090"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="8fd2d-103">Gestire l'app Turni per l'organizzazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8fd2d-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd2d-104">A partire dal 30 giugno 2020, Microsoft StaffHub è stato ritirato.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="8fd2d-105">Stiamo integrando le funzionalità di StaffHub in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="8fd2d-106">Al momento, Teams include l’app Turni per la gestione delle pianificazioni. Altre funzionalità verranno implementate nel corso del tempo.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="8fd2d-107">StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="8fd2d-108">Chiunque provi ad aprire StaffHub visualizza un messaggio che invita a scaricare Teams.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="8fd2d-109">Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="8fd2d-110">Panoramica di Turni</span><span class="sxs-lookup"><span data-stu-id="8fd2d-110">Overview of Shifts</span></span>

<span data-ttu-id="8fd2d-111">L’app Turni in Microsoft Teams consente agli operatori sul campo di rimanere connessi e sincronizzati. È stata ottimizzata per i dispositivi mobili per rendere veloce ed efficace la gestione del tempo e la comunicazione dei team.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="8fd2d-112">Turni consente agli operatori sul campo e ai loro manager di usare i propri dispositivi mobili per gestire le pianificazioni e mantenersi in contatto.  </span><span class="sxs-lookup"><span data-stu-id="8fd2d-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="8fd2d-113">I manager creano, aggiornano e gestiscono le pianificazioni dei turni per i team.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="8fd2d-114">Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriverà tra 20 minuti").</span><span class="sxs-lookup"><span data-stu-id="8fd2d-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="8fd2d-115">Possono anche inviare documenti con criteri, bollettini di notizie e video.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="8fd2d-116">I dipendenti visualizzano i propri turni successivi, vedono quali sono gli altri colleghi pianificati per la giornata, possono richiedere o offrire un cambio di turno e richiedere un permesso.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="8fd2d-117">Turni attualmente non supporta gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="8fd2d-118">Ciò significa che gli utenti guest in un team non possono essere aggiunti o usare la programmazione dei turni quando l’accesso guest è attivato in Teams.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="8fd2d-119">Per informazioni dettagliate sulle funzionalità di Turni su piattaforme diverse, vedere [Funzionalità di Teams per piattaforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="8fd2d-120">Disponibilità di Turni</span><span class="sxs-lookup"><span data-stu-id="8fd2d-120">Availability of Shifts</span></span>

<span data-ttu-id="8fd2d-121">Turni è disponibile in tutte le SKU Enterprise dove Teams è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="8fd2d-122">Posizione dei dati di Turni</span><span class="sxs-lookup"><span data-stu-id="8fd2d-122">Location of Shifts data</span></span>

<span data-ttu-id="8fd2d-123">I dati di Turni sono attualmente archiviati in Azure nei data center in America del Nord, Europa occidentale e Asia Pacifico.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="8fd2d-124">Per altre informazioni sulla posizione di archiviazione dei dati, vedere [Dove sono i dati?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="8fd2d-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="8fd2d-125">Configurare Turni</span><span class="sxs-lookup"><span data-stu-id="8fd2d-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="8fd2d-126">Abilitare o disabilitare Turni nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8fd2d-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="8fd2d-127">Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams nell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="8fd2d-128">È possibile disattivare o attivare l'app a livello di organizzazione nella pagina [Gestisci app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="8fd2d-129">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Gestisci app**.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="8fd2d-130">Nell'elenco delle app eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fd2d-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="8fd2d-131">Per disattivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi selezionare **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="8fd2d-132">Per attivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi selezionare **Consenti**.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="8fd2d-133">Abilitare o disabilitare Turni per utenti specifici nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8fd2d-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="8fd2d-134">Per consentire o bloccare l'uso di Turni a utenti specifici dell'organizzazione, assicurarsi che Turni sia attivato per l'organizzazione nella pagina [Gestisci app](../../manage-apps.md) e quindi creare criteri di autorizzazione per l’app personalizzati da assegnare a tali utenti.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="8fd2d-135">Per altre informazioni, vedere [Gestire i criteri di autorizzazione delle app in Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="8fd2d-136">Usare il criterio di configurazione dell’app per operatori sul campo per aggiungere Turni a Teams</span><span class="sxs-lookup"><span data-stu-id="8fd2d-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="8fd2d-137">I criteri di configurazione dell’app consentono di personalizzare Teams per evidenziare le app più importanti per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="8fd2d-138">Le app impostate in un criterio vengono aggiunte alla barra delle app&mdash;la barra sul lato del client desktop di Teams e nella parte inferiore dei client mobile di Teams&mdash;dove gli utenti possono accedervi rapidamente e facilmente.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="8fd2d-139">Teams include un criterio predefinito di configurazione dell’app per operatori sul campo che è possibile assegnare agli operatori sul campo dell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="8fd2d-140">Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="8fd2d-141">Per visualizzare il criterio per operatori sul campo, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams, passare ad **App di Teams** > **Criteri di configurazione dell’app**.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="8fd2d-142">![Screenshot del criterio di configurazione dell’app per operatori sul campo](../../media/firstline-worker-app-setup-policy.png "Screenshot del criterio di configurazione dell’app per operatori sul campo nell’interfaccia di amministrazione di Microsoft Teams.")</span><span class="sxs-lookup"><span data-stu-id="8fd2d-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="8fd2d-143">Assegnare il criterio di configurazione dell’app per operatori sul campo agli utenti</span><span class="sxs-lookup"><span data-stu-id="8fd2d-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="8fd2d-144">Cercare nel log di controllo gli eventi di Turni</span><span class="sxs-lookup"><span data-stu-id="8fd2d-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="8fd2d-145">**(in anteprima)**</span><span class="sxs-lookup"><span data-stu-id="8fd2d-145">**(in preview)**</span></span>

<span data-ttu-id="8fd2d-146">È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="8fd2d-147">Per altre informazioni su come eseguire ricerche nel log di controllo e vedere un elenco delle [attività di Turni](../../audit-log-events.md#shifts-in-teams-activities) registrate nel log di controllo, vedere [Cercare nel log di controllo eventi di Teams](../../audit-log-events.md).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="8fd2d-148">Prima di poter eseguire ricerche nel log di controllo, è necessario attivare il controllo nel [Centro sicurezza e conformità](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8fd2d-149">Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="8fd2d-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="8fd2d-150">Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="8fd2d-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8fd2d-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8fd2d-151">Related topics</span></span>

- [<span data-ttu-id="8fd2d-152">Guida di Turni per gli operatori sul campo</span><span class="sxs-lookup"><span data-stu-id="8fd2d-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="8fd2d-153">Assegnare criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="8fd2d-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
