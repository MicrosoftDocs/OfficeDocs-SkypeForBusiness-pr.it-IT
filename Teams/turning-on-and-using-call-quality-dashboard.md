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
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162697"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="e4e3e-103">Configurare call quality dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="e4e3e-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="e4e3e-104">Aprire microsoft Call Quality Dashboard (CQD) all'indirizzo [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="e4e3e-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="e4e3e-105">Oppure vai all'interfaccia di amministrazione di Teams e seleziona **Call Quality Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante Dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

<span data-ttu-id="e4e3e-107">Nella pagina visualizzata fare clic su **Accedi e** immettere l'account amministratore globale o le informazioni sull'account di amministratore del servizio Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="e4e3e-108">Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="e4e3e-109">Tenere presente che potrebbero essere sufficienti una o più ore per elaborare dati sufficienti per visualizzare risultati significativi nei report.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="e4e3e-110">CQD mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e4e3e-111">Per usare CQD con Skype for Business Server 2019, è necessario [configurare Call Data Connector.](/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="e4e3e-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="e4e3e-112">Vedere [Pianificare Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-112">See [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="e4e3e-113">Assegnare ruoli di amministratore per l'accesso a CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="e4e3e-114">Assegnare [ruoli](/microsoft-365/admin/add-users/about-admin-roles) per l'accesso a CQD alle persone che devono usarlo.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-114">Assign [roles](/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="e4e3e-115">Se si vuole che gli utenti non amministratori, ad esempio tecnici del supporto tecnico e agenti helpdesk, usino call quality dashboard, è possibile assegnare a tali utenti uno dei ruoli seguenti, che consente l'accesso a CQD.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="e4e3e-116">Visualizzare i report</span><span class="sxs-lookup"><span data-stu-id="e4e3e-116">View reports</span></span>  |<span data-ttu-id="e4e3e-117">Visualizzare i campi EUII</span><span class="sxs-lookup"><span data-stu-id="e4e3e-117">View EUII fields</span></span>  |<span data-ttu-id="e4e3e-118">Creare report</span><span class="sxs-lookup"><span data-stu-id="e4e3e-118">Create reports</span></span>  |<span data-ttu-id="e4e3e-119">Caricare i dati dell'edificio</span><span class="sxs-lookup"><span data-stu-id="e4e3e-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="e4e3e-120">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e4e3e-120">Global Administrator</span></span>     |<span data-ttu-id="e4e3e-121">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-121">Yes</span></span>         |<span data-ttu-id="e4e3e-122">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-122">Yes</span></span>         |<span data-ttu-id="e4e3e-123">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-123">Yes</span></span>         |<span data-ttu-id="e4e3e-124">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-124">Yes</span></span>         |
|<span data-ttu-id="e4e3e-125">Amministratore del servizio Teams</span><span class="sxs-lookup"><span data-stu-id="e4e3e-125">Teams Service Administrator</span></span>     |<span data-ttu-id="e4e3e-126">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-126">Yes</span></span>         |<span data-ttu-id="e4e3e-127">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-127">Yes</span></span>         |<span data-ttu-id="e4e3e-128">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-128">Yes</span></span>         |<span data-ttu-id="e4e3e-129">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-129">Yes</span></span>         |
|<span data-ttu-id="e4e3e-130">Amministratore comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="e4e3e-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="e4e3e-131">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-131">Yes</span></span>         |<span data-ttu-id="e4e3e-132">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-132">Yes</span></span>         |<span data-ttu-id="e4e3e-133">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-133">Yes</span></span>         |<span data-ttu-id="e4e3e-134">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-134">Yes</span></span>         |
|<span data-ttu-id="e4e3e-135">Tecnico supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="e4e3e-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="e4e3e-136">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-136">Yes</span></span>         |<span data-ttu-id="e4e3e-137">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-137">Yes</span></span>         |<span data-ttu-id="e4e3e-138">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-138">Yes</span></span>         |<span data-ttu-id="e4e3e-139">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-139">No</span></span>         |
|<span data-ttu-id="e4e3e-140">Specialista del supporto tecnico di Teams Communications</span><span class="sxs-lookup"><span data-stu-id="e4e3e-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="e4e3e-141">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-141">Yes</span></span>         |<span data-ttu-id="e4e3e-142">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-142">No</span></span>         |<span data-ttu-id="e4e3e-143">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-143">Yes</span></span>         |<span data-ttu-id="e4e3e-144">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-144">No</span></span>         |
|<span data-ttu-id="e4e3e-145">Amministratore di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e4e3e-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="e4e3e-146">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-146">Yes</span></span>         |<span data-ttu-id="e4e3e-147">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-147">Yes</span></span>         |<span data-ttu-id="e4e3e-148">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-148">Yes</span></span>         |<span data-ttu-id="e4e3e-149">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-149">Yes</span></span>         |
|<span data-ttu-id="e4e3e-150">Lettore globale</span><span class="sxs-lookup"><span data-stu-id="e4e3e-150">Global Reader</span></span> |<span data-ttu-id="e4e3e-151">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-151">Yes</span></span>         |<span data-ttu-id="e4e3e-152">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-152">Yes</span></span>         |<span data-ttu-id="e4e3e-153">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-153">Yes</span></span>         |<span data-ttu-id="e4e3e-154">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-154">No</span></span>         |
|<span data-ttu-id="e4e3e-155">Lettore report<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e4e3e-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="e4e3e-156">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-156">Yes</span></span>         |<span data-ttu-id="e4e3e-157">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-157">No</span></span>         |<span data-ttu-id="e4e3e-158">Sì</span><span class="sxs-lookup"><span data-stu-id="e4e3e-158">Yes</span></span>         |<span data-ttu-id="e4e3e-159">No</span><span class="sxs-lookup"><span data-stu-id="e4e3e-159">No</span></span>         |

<span data-ttu-id="e4e3e-160"><sup>1</sup> Oltre a leggere i report CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) l'utilità per la lettura dei report può visualizzare tutti i report attività nell'interfaccia di amministrazione e tutti i report del pacchetto di contenuto [Microsoft 365 Adoption.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)</span><span class="sxs-lookup"><span data-stu-id="e4e3e-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="e4e3e-161">Se l'interfaccia [EUII (informazioni](CQD-data-and-reports.md#euii-data) identificabili dall'utente finale) non è visualizzata e si ha uno dei ruoli autorizzati a visualizzare queste informazioni, tenere presente che CQD mantiene solo EUII per 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="e4e3e-162">Qualsiasi elemento più vecchio di 28 giorni viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="e4e3e-163">Per altre informazioni su questi ruoli, vedere Informazioni sui ruoli di amministratore [di Office 365.](/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="e4e3e-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="e4e3e-164">Dopo la prima volta che si accede, CQD inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="e4e3e-165">A partire da dicembre 2019 è ancora possibile accedere alla versione precedente di CQD (cqd.lync.com), anche se il portale legacy offre un collegamento all'ultima versione di CQD (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e4e3e-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="e4e3e-166">Alla fine, la versione precedente di CQD verrà rimossa.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="e4e3e-167">A partire dal 1° luglio 2020, la versione precedente di CQD accede ai dati dall'ultima versione di CQD.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="e4e3e-168">Eseguire la migrazione di dati e report di compilazione dalla versione precedente di CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4e3e-169">A partire dal 1° luglio 2020, non è più possibile eseguire la migrazione di dati e report di generazione dal vecchio CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="e4e3e-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="e4e3e-170">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="e4e3e-171">Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e4e3e-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="e4e3e-172">Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="e4e3e-173">Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e4e3e-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e4e3e-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e4e3e-174">Related topics</span></span>

[<span data-ttu-id="e4e3e-175">Migliorare e monitorare la qualità delle chiamate per Teams</span><span class="sxs-lookup"><span data-stu-id="e4e3e-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="e4e3e-176">Che cos'è CQD?</span><span class="sxs-lookup"><span data-stu-id="e4e3e-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="e4e3e-177">Caricare i dati del tenant e dell'edificio</span><span class="sxs-lookup"><span data-stu-id="e4e3e-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="e4e3e-178">Dati e report CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="e4e3e-179">Usare CQD per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="e4e3e-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="e4e3e-180">Dimensioni e misure disponibili in CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e4e3e-181">Classificazione dei flussi in CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e4e3e-182">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="e4e3e-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)