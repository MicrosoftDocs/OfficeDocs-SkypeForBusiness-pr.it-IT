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
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918651"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="114af-103">Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="114af-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="114af-104">Aprire Microsoft Call Quality Dashboard (Call Quality Dashboard) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (accedere con le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="114af-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="114af-105">Oppure passa all'interfaccia di amministrazione di teams e seleziona **chiama Quality dashboard**.</span><span class="sxs-lookup"><span data-stu-id="114af-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Screenshot del pulsante dashboard qualità chiamata nell'interfaccia di amministrazione di Teams":::

<span data-ttu-id="114af-107">Nella pagina visualizzata fare clic su Accedi e immettere l'account **di** amministratore globale o le informazioni dell'account di amministrazione del servizio Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="114af-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="114af-108">Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="114af-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="114af-109">Tieni presente che potrebbero essere necessarie una o più ore per elaborare dati sufficienti per visualizzare i risultati significativi nei report.</span><span class="sxs-lookup"><span data-stu-id="114af-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="114af-110">Call Quality dashboard mostra la qualità delle chiamate e delle riunioni a livello di organizzazione per Microsoft teams, Skype for business online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="114af-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="114af-111">Per usare Call Quality Dashboard con Skype for Business Server 2019, è necessario configurare il [connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="114af-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="114af-112">Vedere [pianificare il connettore dati chiamata](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="114af-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="114af-113">Assegnare ruoli di amministratore per Access a Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="114af-114">Assegnare [ruoli](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) per accedere a Call Quality dashboard alle persone che devono usarle.</span><span class="sxs-lookup"><span data-stu-id="114af-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="114af-115">Se si vuole che gli utenti non amministratori (ad esempio gli ingegneri del supporto tecnico e gli agenti dell'helpdesk) usino il dashboard qualità chiamata, è possibile assegnare agli utenti uno dei ruoli seguenti, che consente di accedere a Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="114af-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="114af-116">Visualizzare i report</span><span class="sxs-lookup"><span data-stu-id="114af-116">View reports</span></span>  |<span data-ttu-id="114af-117">Visualizzare i campi EUII</span><span class="sxs-lookup"><span data-stu-id="114af-117">View EUII fields</span></span>  |<span data-ttu-id="114af-118">Creare report</span><span class="sxs-lookup"><span data-stu-id="114af-118">Create reports</span></span>  |<span data-ttu-id="114af-119">Caricare i dati dell'edificio</span><span class="sxs-lookup"><span data-stu-id="114af-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="114af-120">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="114af-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="114af-121">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-121">Yes</span></span>         |<span data-ttu-id="114af-122">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-122">Yes</span></span>         |<span data-ttu-id="114af-123">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-123">Yes</span></span>         |<span data-ttu-id="114af-124">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-124">Yes</span></span>         |
|<span data-ttu-id="114af-125">Amministratore del servizio Teams</span><span class="sxs-lookup"><span data-stu-id="114af-125">Teams Service Administrator</span></span>     |<span data-ttu-id="114af-126">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-126">Yes</span></span>         |<span data-ttu-id="114af-127">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-127">Yes</span></span>         |<span data-ttu-id="114af-128">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-128">Yes</span></span>         |<span data-ttu-id="114af-129">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-129">Yes</span></span>         |
|<span data-ttu-id="114af-130">Amministratore comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="114af-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="114af-131">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-131">Yes</span></span>         |<span data-ttu-id="114af-132">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-132">Yes</span></span>         |<span data-ttu-id="114af-133">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-133">Yes</span></span>         |<span data-ttu-id="114af-134">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-134">Yes</span></span>         |
|<span data-ttu-id="114af-135">Tecnico supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="114af-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="114af-136">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-136">Yes</span></span>         |<span data-ttu-id="114af-137">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-137">Yes</span></span>         |<span data-ttu-id="114af-138">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-138">Yes</span></span>         |<span data-ttu-id="114af-139">No</span><span class="sxs-lookup"><span data-stu-id="114af-139">No</span></span>         |
|<span data-ttu-id="114af-140">Specialista supporto comunicazioni Teams</span><span class="sxs-lookup"><span data-stu-id="114af-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="114af-141">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-141">Yes</span></span>         |<span data-ttu-id="114af-142">No</span><span class="sxs-lookup"><span data-stu-id="114af-142">No</span></span>         |<span data-ttu-id="114af-143">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-143">Yes</span></span>         |<span data-ttu-id="114af-144">No</span><span class="sxs-lookup"><span data-stu-id="114af-144">No</span></span>         |
|<span data-ttu-id="114af-145">Amministratore di Skype for business</span><span class="sxs-lookup"><span data-stu-id="114af-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="114af-146">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-146">Yes</span></span>         |<span data-ttu-id="114af-147">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-147">Yes</span></span>         |<span data-ttu-id="114af-148">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-148">Yes</span></span>         |<span data-ttu-id="114af-149">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-149">Yes</span></span>         |
|<span data-ttu-id="114af-150">Lettore globale di Azure AD</span><span class="sxs-lookup"><span data-stu-id="114af-150">Azure AD Global Reader</span></span> |<span data-ttu-id="114af-151">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-151">Yes</span></span>         |<span data-ttu-id="114af-152">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-152">Yes</span></span>         |<span data-ttu-id="114af-153">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-153">Yes</span></span>         |<span data-ttu-id="114af-154">No</span><span class="sxs-lookup"><span data-stu-id="114af-154">No</span></span>         |
|<span data-ttu-id="114af-155">Lettore di report di Office 365<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="114af-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="114af-156">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-156">Yes</span></span>         |<span data-ttu-id="114af-157">No</span><span class="sxs-lookup"><span data-stu-id="114af-157">No</span></span>         |<span data-ttu-id="114af-158">Sì</span><span class="sxs-lookup"><span data-stu-id="114af-158">Yes</span></span>         |<span data-ttu-id="114af-159">No</span><span class="sxs-lookup"><span data-stu-id="114af-159">No</span></span>         |

<span data-ttu-id="114af-160"><sup>1</sup> oltre a leggere i report di Call Quality dashboard, il lettore di report di Office 365 può visualizzare tutti i [report attività](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) nell'interfaccia di amministrazione e tutti i report del [pacchetto di contenuto adoption di Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span><span class="sxs-lookup"><span data-stu-id="114af-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="114af-161">Se non si vedono [EUII (informazioni identificative per gli utenti finali)](CQD-data-and-reports.md#euii-data) e si ha uno dei ruoli consentiti per vedere queste informazioni, tenere presente che Call Quality dashboard mantiene solo EUII per 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="114af-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="114af-162">Viene eliminato qualsiasi valore antecedente a 28 giorni.</span><span class="sxs-lookup"><span data-stu-id="114af-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="114af-163">Per altre informazioni su questi ruoli, vedere [informazioni sui ruoli di amministratore di Office 365](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="114af-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="114af-164">Dopo aver effettuato l'accesso per la prima volta, Call Quality dashboard inizierà a raccogliere ed elaborare i dati.</span><span class="sxs-lookup"><span data-stu-id="114af-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="114af-165">A partire da dicembre 2019, è comunque possibile accedere alla versione precedente di Call Quality Dashboard (cqd.lync.com), anche se il portale legacy fornisce un collegamento all'ultima Call Quality Dashboard (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="114af-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="114af-166">Alla fine, la versione precedente di Call Quality dashboard verrà disattivata.</span><span class="sxs-lookup"><span data-stu-id="114af-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="114af-167">A partire dal 1 ° luglio 2020, la versione precedente di Call Quality dashboard accede ai dati dall'ultima Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="114af-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="114af-168">Eseguire la migrazione di dati e report da una versione precedente di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="114af-169">A partire dal 1 ° luglio 2020, non è più possibile eseguire la migrazione dei dati dell'edificio e i report dal vecchio Call Quality Dashboard ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="114af-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="114af-170">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="114af-171">Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="114af-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="114af-172">Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="114af-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="114af-173">Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="114af-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="114af-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="114af-174">Related topics</span></span>

[<span data-ttu-id="114af-175">Migliorare e monitorare la qualità delle chiamate per i team</span><span class="sxs-lookup"><span data-stu-id="114af-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="114af-176">Che cos'è Call Quality dashboard?</span><span class="sxs-lookup"><span data-stu-id="114af-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="114af-177">Caricare i dati del tenant e della creazione</span><span class="sxs-lookup"><span data-stu-id="114af-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="114af-178">Dati e report di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="114af-179">Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="114af-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="114af-180">Dimensioni e misure disponibili in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="114af-181">Classificazione del flusso in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="114af-182">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="114af-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
