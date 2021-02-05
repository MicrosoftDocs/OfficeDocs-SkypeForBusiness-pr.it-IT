---
title: Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)
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
description: Informazioni su come attivare e usare il dashboard qualità chiamata e ottenere report riepilogativi sulla qualità delle chiamate.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112844"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="d2989-103">Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="d2989-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="d2989-104">Aprire Microsoft Call Quality Dashboard (Call Quality Dashboard) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="d2989-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="d2989-105">Oppure passa all'interfaccia di amministrazione di teams e seleziona **chiama Quality dashboard**.</span><span class="sxs-lookup"><span data-stu-id="d2989-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

<span data-ttu-id="d2989-107">Nella pagina visualizzata fare clic su Accedi e immettere l'account **di** amministratore globale o le informazioni dell'account di amministratore del servizio Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="d2989-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="d2989-108">Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="d2989-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="d2989-109">Tieni presente che potrebbero essere necessarie una o più ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report.</span><span class="sxs-lookup"><span data-stu-id="d2989-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="d2989-110">Call Quality dashboard mostra la qualità delle chiamate e delle riunioni a livello di organizzazione per Microsoft teams, Skype for business online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d2989-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d2989-111">Per usare Call Quality Dashboard con Skype for Business Server 2019, è necessario configurare il [connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="d2989-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="d2989-112">Vedere [pianificare il connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="d2989-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="d2989-113">Assegnare ruoli di amministratore per Access a Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="d2989-114">Assegnare [ruoli](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) per accedere a Call Quality dashboard alle persone che devono usarle.</span><span class="sxs-lookup"><span data-stu-id="d2989-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="d2989-115">Se si vuole che gli utenti non amministratori (ad esempio gli ingegneri del supporto tecnico e gli agenti dell'helpdesk) usino il dashboard qualità chiamata, è possibile assegnare agli utenti uno dei ruoli seguenti, che consente di accedere a Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d2989-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="d2989-116">Visualizzare i report</span><span class="sxs-lookup"><span data-stu-id="d2989-116">View reports</span></span>  |<span data-ttu-id="d2989-117">Visualizzare i campi EUII</span><span class="sxs-lookup"><span data-stu-id="d2989-117">View EUII fields</span></span>  |<span data-ttu-id="d2989-118">Creare report</span><span class="sxs-lookup"><span data-stu-id="d2989-118">Create reports</span></span>  |<span data-ttu-id="d2989-119">Caricare i dati dell'edificio</span><span class="sxs-lookup"><span data-stu-id="d2989-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="d2989-120">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="d2989-120">Global Administrator</span></span>     |<span data-ttu-id="d2989-121">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-121">Yes</span></span>         |<span data-ttu-id="d2989-122">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-122">Yes</span></span>         |<span data-ttu-id="d2989-123">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-123">Yes</span></span>         |<span data-ttu-id="d2989-124">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-124">Yes</span></span>         |
|<span data-ttu-id="d2989-125">Amministratore del servizio Teams</span><span class="sxs-lookup"><span data-stu-id="d2989-125">Teams Service Administrator</span></span>     |<span data-ttu-id="d2989-126">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-126">Yes</span></span>         |<span data-ttu-id="d2989-127">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-127">Yes</span></span>         |<span data-ttu-id="d2989-128">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-128">Yes</span></span>         |<span data-ttu-id="d2989-129">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-129">Yes</span></span>         |
|<span data-ttu-id="d2989-130">Amministratore comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="d2989-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="d2989-131">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-131">Yes</span></span>         |<span data-ttu-id="d2989-132">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-132">Yes</span></span>         |<span data-ttu-id="d2989-133">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-133">Yes</span></span>         |<span data-ttu-id="d2989-134">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-134">Yes</span></span>         |
|<span data-ttu-id="d2989-135">Tecnico supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="d2989-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="d2989-136">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-136">Yes</span></span>         |<span data-ttu-id="d2989-137">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-137">Yes</span></span>         |<span data-ttu-id="d2989-138">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-138">Yes</span></span>         |<span data-ttu-id="d2989-139">No</span><span class="sxs-lookup"><span data-stu-id="d2989-139">No</span></span>         |
|<span data-ttu-id="d2989-140">Specialista supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="d2989-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="d2989-141">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-141">Yes</span></span>         |<span data-ttu-id="d2989-142">No</span><span class="sxs-lookup"><span data-stu-id="d2989-142">No</span></span>         |<span data-ttu-id="d2989-143">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-143">Yes</span></span>         |<span data-ttu-id="d2989-144">No</span><span class="sxs-lookup"><span data-stu-id="d2989-144">No</span></span>         |
|<span data-ttu-id="d2989-145">Amministratore di Skype for business</span><span class="sxs-lookup"><span data-stu-id="d2989-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="d2989-146">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-146">Yes</span></span>         |<span data-ttu-id="d2989-147">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-147">Yes</span></span>         |<span data-ttu-id="d2989-148">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-148">Yes</span></span>         |<span data-ttu-id="d2989-149">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-149">Yes</span></span>         |
|<span data-ttu-id="d2989-150">Lettore globale</span><span class="sxs-lookup"><span data-stu-id="d2989-150">Global Reader</span></span> |<span data-ttu-id="d2989-151">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-151">Yes</span></span>         |<span data-ttu-id="d2989-152">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-152">Yes</span></span>         |<span data-ttu-id="d2989-153">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-153">Yes</span></span>         |<span data-ttu-id="d2989-154">No</span><span class="sxs-lookup"><span data-stu-id="d2989-154">No</span></span>         |
|<span data-ttu-id="d2989-155">Lettore report<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d2989-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="d2989-156">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-156">Yes</span></span>         |<span data-ttu-id="d2989-157">No</span><span class="sxs-lookup"><span data-stu-id="d2989-157">No</span></span>         |<span data-ttu-id="d2989-158">Sì</span><span class="sxs-lookup"><span data-stu-id="d2989-158">Yes</span></span>         |<span data-ttu-id="d2989-159">No</span><span class="sxs-lookup"><span data-stu-id="d2989-159">No</span></span>         |

<span data-ttu-id="d2989-160"><sup>1</sup> oltre a leggere i report di Call Quality dashboard, l'utilità di lettura report può visualizzare tutti i report [attività](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) nell'interfaccia di amministrazione e tutti i report del [pacchetto di contenuto Microsoft adoption 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span><span class="sxs-lookup"><span data-stu-id="d2989-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="d2989-161">Se non si vedono [EUII (informazioni identificative per gli utenti finali)](CQD-data-and-reports.md#euii-data) e si ha uno dei ruoli consentiti per vedere queste informazioni, tenere presente che Call Quality dashboard mantiene solo EUII per 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="d2989-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="d2989-162">Viene eliminato qualsiasi valore antecedente a 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="d2989-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="d2989-163">Per altre informazioni su questi ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="d2989-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="d2989-164">Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="d2989-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="d2989-165">A partire da dicembre 2019, è comunque possibile accedere alla versione precedente di Call Quality Dashboard (cqd.lync.com), anche se il portale legacy fornisce un collegamento all'ultima Call Quality Dashboard (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d2989-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="d2989-166">Alla fine, la versione precedente di Call Quality dashboard verrà disattivata.</span><span class="sxs-lookup"><span data-stu-id="d2989-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="d2989-167">A partire dal 1 ° luglio 2020, la versione precedente di Call Quality dashboard accede ai dati dall'ultima Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d2989-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="d2989-168">Eseguire la migrazione di dati e report da una versione precedente di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2989-169">A partire dal 1 ° luglio 2020, non è più possibile eseguire la migrazione dei dati dell'edificio e i report dal vecchio Call Quality Dashboard ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="d2989-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="d2989-170">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="d2989-171">Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="d2989-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="d2989-172">Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d2989-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="d2989-173">Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="d2989-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d2989-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d2989-174">Related topics</span></span>

[<span data-ttu-id="d2989-175">Migliorare e monitorare la qualità delle chiamate per i team</span><span class="sxs-lookup"><span data-stu-id="d2989-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="d2989-176">Che cos'è Call Quality dashboard?</span><span class="sxs-lookup"><span data-stu-id="d2989-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="d2989-177">Caricare i dati del tenant e della creazione</span><span class="sxs-lookup"><span data-stu-id="d2989-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="d2989-178">Dati e report di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="d2989-179">Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="d2989-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="d2989-180">Dimensioni e misure disponibili in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="d2989-181">Classificazione del flusso in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="d2989-182">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="d2989-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
