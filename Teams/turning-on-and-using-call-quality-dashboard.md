---
title: Configurare call quality dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su come attivare e usare il dashboard qualità delle chiamate e ottenere report di riepilogo sulla qualità delle chiamate.
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254269"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="ef8cc-103">Configurare call quality dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="ef8cc-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="ef8cc-104">Aprire microsoft Call Quality Dashboard (CQD) all'indirizzo [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="ef8cc-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="ef8cc-105">Oppure vai all'interfaccia di Teams e seleziona **Call Quality Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'Teams di amministrazione":::

<span data-ttu-id="ef8cc-107">Nella pagina visualizzata fare clic su Accedi **e** immettere l'account amministratore globale o le Microsoft Teams dell'account amministratore.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Administrator account information.</span></span> <span data-ttu-id="ef8cc-108">Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="ef8cc-109">Tenere presente che potrebbero essere sufficienti una o più ore per elaborare dati sufficienti per visualizzare risultati significativi nei report.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="ef8cc-110">CQD mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ef8cc-111">Per usare CQD con Skype for Business Server 2019, è necessario [configurare Call Data Connector.](/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="ef8cc-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="ef8cc-112">Vedere [Pianificare Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="ef8cc-113">Assegnare ruoli di amministratore per l'accesso a CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="ef8cc-114">Assegnare [ruoli](/microsoft-365/admin/add-users/about-admin-roles) per l'accesso a CQD alle persone che devono usarlo.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="ef8cc-115">Se si vuole che gli utenti non amministratori, ad esempio tecnici del supporto tecnico e agenti helpdesk, usino call quality dashboard, è possibile assegnare a tali utenti uno dei ruoli seguenti, che consente l'accesso a CQD.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="ef8cc-116">Visualizzare i report</span><span class="sxs-lookup"><span data-stu-id="ef8cc-116">View reports</span></span>  |<span data-ttu-id="ef8cc-117">Visualizzare i campi EUII</span><span class="sxs-lookup"><span data-stu-id="ef8cc-117">View EUII fields</span></span>  |<span data-ttu-id="ef8cc-118">Creare report</span><span class="sxs-lookup"><span data-stu-id="ef8cc-118">Create reports</span></span>  |<span data-ttu-id="ef8cc-119">Upload di edificio</span><span class="sxs-lookup"><span data-stu-id="ef8cc-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="ef8cc-120">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ef8cc-120">Global Administrator</span></span>     |<span data-ttu-id="ef8cc-121">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-121">Yes</span></span>         |<span data-ttu-id="ef8cc-122">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-122">Yes</span></span>         |<span data-ttu-id="ef8cc-123">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-123">Yes</span></span>         |<span data-ttu-id="ef8cc-124">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-124">Yes</span></span>         |
|<span data-ttu-id="ef8cc-125">Amministratore di Teams</span><span class="sxs-lookup"><span data-stu-id="ef8cc-125">Teams Administrator</span></span>     |<span data-ttu-id="ef8cc-126">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-126">Yes</span></span>         |<span data-ttu-id="ef8cc-127">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-127">Yes</span></span>         |<span data-ttu-id="ef8cc-128">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-128">Yes</span></span>         |<span data-ttu-id="ef8cc-129">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-129">Yes</span></span>         |
|<span data-ttu-id="ef8cc-130">Amministratore comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="ef8cc-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="ef8cc-131">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-131">Yes</span></span>         |<span data-ttu-id="ef8cc-132">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-132">Yes</span></span>         |<span data-ttu-id="ef8cc-133">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-133">Yes</span></span>         |<span data-ttu-id="ef8cc-134">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-134">Yes</span></span>         |
|<span data-ttu-id="ef8cc-135">Tecnico supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="ef8cc-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="ef8cc-136">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-136">Yes</span></span>         |<span data-ttu-id="ef8cc-137">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-137">Yes</span></span>         |<span data-ttu-id="ef8cc-138">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-138">Yes</span></span>         |<span data-ttu-id="ef8cc-139">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-139">No</span></span>         |
|<span data-ttu-id="ef8cc-140">Teams Specialista del supporto per le comunicazioni</span><span class="sxs-lookup"><span data-stu-id="ef8cc-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="ef8cc-141">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-141">Yes</span></span>         |<span data-ttu-id="ef8cc-142">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-142">No</span></span>         |<span data-ttu-id="ef8cc-143">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-143">Yes</span></span>         |<span data-ttu-id="ef8cc-144">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-144">No</span></span>         |
|<span data-ttu-id="ef8cc-145">Skype for Business Amministratore</span><span class="sxs-lookup"><span data-stu-id="ef8cc-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="ef8cc-146">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-146">Yes</span></span>         |<span data-ttu-id="ef8cc-147">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-147">Yes</span></span>         |<span data-ttu-id="ef8cc-148">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-148">Yes</span></span>         |<span data-ttu-id="ef8cc-149">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-149">Yes</span></span>         |
|<span data-ttu-id="ef8cc-150">Lettore globale</span><span class="sxs-lookup"><span data-stu-id="ef8cc-150">Global Reader</span></span> |<span data-ttu-id="ef8cc-151">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-151">Yes</span></span>         |<span data-ttu-id="ef8cc-152">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-152">Yes</span></span>         |<span data-ttu-id="ef8cc-153">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-153">Yes</span></span>         |<span data-ttu-id="ef8cc-154">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-154">No</span></span>         |
|<span data-ttu-id="ef8cc-155">Lettore report<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ef8cc-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="ef8cc-156">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-156">Yes</span></span>         |<span data-ttu-id="ef8cc-157">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-157">No</span></span>         |<span data-ttu-id="ef8cc-158">Sì</span><span class="sxs-lookup"><span data-stu-id="ef8cc-158">Yes</span></span>         |<span data-ttu-id="ef8cc-159">No</span><span class="sxs-lookup"><span data-stu-id="ef8cc-159">No</span></span>         |

<span data-ttu-id="ef8cc-160"><sup>1</sup> Oltre a leggere i report CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) l'utilità per la lettura dei report può visualizzare tutti i report attività nell'interfaccia di amministrazione e tutti i report del pacchetto di [contenuto Microsoft 365 Adoption.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)</span><span class="sxs-lookup"><span data-stu-id="ef8cc-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="ef8cc-161">Se l'interfaccia [EUII (informazioni](CQD-data-and-reports.md#euii-data) identificabili dall'utente finale) non è visualizzata e si ha uno dei ruoli autorizzati a visualizzare queste informazioni, tenere presente che CQD mantiene solo EUII per 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="ef8cc-162">Qualsiasi elemento più vecchio di 28 giorni viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="ef8cc-163">Per altre informazioni su questi ruoli, vedere [Informazioni sui Office 365 di amministratore.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="ef8cc-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="ef8cc-164">Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="ef8cc-165">A partire da dicembre 2019 è ancora possibile accedere alla versione precedente di CQD (cqd.lync.com), anche se il portale legacy offre un collegamento all'ultima versione di CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ef8cc-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="ef8cc-166">Alla fine, la versione precedente di CQD verrà rimossa.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="ef8cc-167">A partire dal 1° luglio 2020, la versione precedente di CQD accede ai dati dall'ultima versione di CQD.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="ef8cc-168">Eseguire la migrazione di dati e report di compilazione dalla versione precedente di CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef8cc-169">A partire dal 1° luglio 2020, non è più possibile eseguire la migrazione di dati e report di generazione dal vecchio CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="ef8cc-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="ef8cc-170">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="ef8cc-171">Novità di gennaio 2020: [Scaricare Power BI di query per CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="ef8cc-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="ef8cc-172">Modelli Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="ef8cc-173">Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="ef8cc-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ef8cc-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ef8cc-174">Related topics</span></span>

[<span data-ttu-id="ef8cc-175">Migliorare e monitorare la qualità delle chiamate per Teams</span><span class="sxs-lookup"><span data-stu-id="ef8cc-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="ef8cc-176">Che cos'è CQD?</span><span class="sxs-lookup"><span data-stu-id="ef8cc-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="ef8cc-177">Upload tenant e edificio</span><span class="sxs-lookup"><span data-stu-id="ef8cc-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="ef8cc-178">Dati e report CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="ef8cc-179">Usare CQD per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="ef8cc-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="ef8cc-180">Dimensioni e misure disponibili in CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="ef8cc-181">Classificazione dei flussi in CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="ef8cc-182">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="ef8cc-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)