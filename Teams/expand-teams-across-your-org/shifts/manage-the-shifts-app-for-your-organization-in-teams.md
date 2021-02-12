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
description: Informazioni su come configurare e gestire l'app Turni in Teams per gli operatori in prima linea nell'organizzazione.
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
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909090"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="fefda-103">Gestire l'app Turni per l'organizzazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fefda-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fefda-104">Microsoft StaffHub è stato ritirato il 30 giugno 2020.</span><span class="sxs-lookup"><span data-stu-id="fefda-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="fefda-105">Stiamo creando funzionalità di StaffHub in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fefda-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="fefda-106">Oggi, Teams include l'app Turni per la gestione della pianificazione e altre funzionalità verranno implementazioni nel tempo.</span><span class="sxs-lookup"><span data-stu-id="fefda-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="fefda-107">StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020.</span><span class="sxs-lookup"><span data-stu-id="fefda-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="fefda-108">Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare Teams.</span><span class="sxs-lookup"><span data-stu-id="fefda-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="fefda-109">Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato.](microsoft-staffhub-to-be-retired.md)</span><span class="sxs-lookup"><span data-stu-id="fefda-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="fefda-110">Panoramica di Turni</span><span class="sxs-lookup"><span data-stu-id="fefda-110">Overview of Shifts</span></span>

<span data-ttu-id="fefda-111">L'app Turni in Microsoft Teams mantiene i dipendenti in prima linea connessi e sincronizzati. È progettato per primo per la gestione del tempo e la comunicazione per i team in modo rapido ed efficace.</span><span class="sxs-lookup"><span data-stu-id="fefda-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="fefda-112">Turni consente ai dipendenti in prima linea e ai loro manager di usare i propri dispositivi mobili per gestire le pianificazioni e restare in contatto.</span><span class="sxs-lookup"><span data-stu-id="fefda-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="fefda-113">I responsabili creano, aggiornano e gestiscono le pianificazioni dei turni per i team.</span><span class="sxs-lookup"><span data-stu-id="fefda-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="fefda-114">Possono inviare messaggi a una persona ("c'è una perdita sul pavimento") o all'intero team ("il responsabile locale arriva tra 20 minuti").</span><span class="sxs-lookup"><span data-stu-id="fefda-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="fefda-115">Possono anche inviare documenti di criteri, bollettini di notizie e video.</span><span class="sxs-lookup"><span data-stu-id="fefda-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="fefda-116">I dipendenti visualizzano i turni programmati, vedono chi altro è pianificato per la giornata, richiedono uno scambio o un'offerta di turno e richiedono un periodo di riposo.</span><span class="sxs-lookup"><span data-stu-id="fefda-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="fefda-117">È importante sapere che Attualmente Turni non supporta gli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="fefda-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="fefda-118">Questo significa che i guest di un team non possono essere aggiunti o utilizzare le pianificazioni dei turni quando l'accesso guest è attivato in Teams.</span><span class="sxs-lookup"><span data-stu-id="fefda-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="fefda-119">Per informazioni dettagliate sulle funzionalità di Turni su piattaforme diverse, vedi le [funzionalità di Teams per piattaforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="fefda-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="fefda-120">Disponibilità di Turni</span><span class="sxs-lookup"><span data-stu-id="fefda-120">Availability of Shifts</span></span>

<span data-ttu-id="fefda-121">Turni è disponibile in tutti gli SKU Enterprise in cui Teams è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fefda-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="fefda-122">Posizione dei dati di Turni</span><span class="sxs-lookup"><span data-stu-id="fefda-122">Location of Shifts data</span></span>

<span data-ttu-id="fefda-123">I dati di Turni sono attualmente archiviati in Azure in data center in America del Nord, Europa occidentale e Asia Pacifico.</span><span class="sxs-lookup"><span data-stu-id="fefda-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="fefda-124">Per altre informazioni sulla posizione di archiviazione dei dati, vedere [Dove sono i dati?](http://o365datacentermap.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="fefda-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="fefda-125">Configurare Turni</span><span class="sxs-lookup"><span data-stu-id="fefda-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="fefda-126">Abilitare o disabilitare Turni nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fefda-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="fefda-127">Turni è abilitato per impostazione predefinita per tutti gli utenti di Teams nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fefda-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="fefda-128">È possibile disattivare o attivare l'app a livello di organizzazione nella pagina Gestisci [app](../../manage-apps.md) nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fefda-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="fefda-129">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa a **Gestisci app**  >  **di** Teams.</span><span class="sxs-lookup"><span data-stu-id="fefda-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="fefda-130">Nell'elenco delle app eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fefda-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="fefda-131">Per disattivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi scegliere **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="fefda-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="fefda-132">Per attivare Turni per l'organizzazione, cercare l'app Turni, selezionarla e quindi scegliere **Consenti.**</span><span class="sxs-lookup"><span data-stu-id="fefda-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="fefda-133">Abilitare o disabilitare Turni per utenti specifici dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="fefda-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="fefda-134">Per consentire o impedire a utenti specifici dell'organizzazione di usare Turni, [](../../manage-apps.md) assicurarsi che l'opzione Turni sia attivata per l'organizzazione nella pagina Gestisci app, quindi creare criteri di autorizzazione per le app personalizzati e assegnarli a tali utenti.</span><span class="sxs-lookup"><span data-stu-id="fefda-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="fefda-135">Per altre informazioni, vedere [Gestire i criteri di autorizzazione per le app in Teams.](../../teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fefda-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="fefda-136">Usare i criteri di configurazione dell'app FrontlineWorker per aggiungere Turni a Teams</span><span class="sxs-lookup"><span data-stu-id="fefda-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="fefda-137">I criteri di configurazione delle app consentono di personalizzare Teams per evidenziare le app più importanti per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fefda-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="fefda-138">Le app impostate in un criterio vengono aggiunte alla barra dell'app sulla barra sul lato del client desktop di Teams e nella parte inferiore dei client mobili di Teams in cui gli utenti possono accedervi rapidamente e &mdash; &mdash; facilmente.</span><span class="sxs-lookup"><span data-stu-id="fefda-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="fefda-139">Teams include un criterio di configurazione predefinito dell'app FrontlineWorker che è possibile assegnare agli operatori sul campo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fefda-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="fefda-140">Per impostazione predefinita, il criterio include le app Attività, Turni, Chat e Chiamate.</span><span class="sxs-lookup"><span data-stu-id="fefda-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="fefda-141">Per visualizzare i criteri di FrontlineWorker, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare a Criteri di configurazione **dell'app Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="fefda-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="fefda-142">![Screenshot dei criteri di configurazione dell'app FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Screenshot del criterio di configurazione dell'app FrontlineWorker nell'interfaccia di amministrazione di Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="fefda-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="fefda-143">Assegnare i criteri di configurazione dell'app FrontlineWorker agli utenti</span><span class="sxs-lookup"><span data-stu-id="fefda-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="fefda-144">Cercare gli eventi di Turni nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="fefda-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="fefda-145">**(in anteprima)**</span><span class="sxs-lookup"><span data-stu-id="fefda-145">**(in preview)**</span></span>

<span data-ttu-id="fefda-146">È possibile eseguire ricerche nel log di controllo per visualizzare le attività di Turni nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fefda-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="fefda-147">Per altre informazioni su come eseguire ricerche nel [](../../audit-log-events.md#shifts-in-teams-activities) log di controllo e per visualizzare un elenco delle attività di Turni registrate nel log di controllo, vedere Cercare gli eventi [nel log di controllo in Teams.](../../audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="fefda-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="fefda-148">Prima di eseguire ricerche nel log di controllo, è necessario attivare il controllo nel Centro [& conformità.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="fefda-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="fefda-149">Per altre informazioni, vedere Attivare o disattivare [la ricerca nel log di controllo.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)</span><span class="sxs-lookup"><span data-stu-id="fefda-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="fefda-150">Tenere presente che i dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="fefda-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fefda-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fefda-151">Related topics</span></span>

- [<span data-ttu-id="fefda-152">Guida turni per i dipendenti in prima linea</span><span class="sxs-lookup"><span data-stu-id="fefda-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="fefda-153">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="fefda-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
