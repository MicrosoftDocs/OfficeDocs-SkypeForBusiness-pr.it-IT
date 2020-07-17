---
title: Che cos'è Call Quality Dashboard (Call Quality Dashboard)?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni su Call Quality Dashboard (Call Quality Dashboard) e su come usarlo per visualizzare i report sulla qualità delle riunioni e delle chiamate in Microsoft teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088244"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="e8c43-103">Che cos'è Call Quality Dashboard (Call Quality Dashboard)?</span><span class="sxs-lookup"><span data-stu-id="e8c43-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="e8c43-104">Microsoft Call Quality Dashboard (Call Quality Dashboard)- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) -Mostra la qualità delle chiamate e delle riunioni a **livello di organizzazione**per Microsoft teams, Skype for business online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e8c43-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="e8c43-105">La versione più recente di Call Quality dashboard include un [feed di dati in tempo reale (NRT)](CQD-data-and-reports.md), che indica che i record di chiamata sono disponibili in Call Quality dashboard entro 30 minuti dalla fine di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e8c43-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="e8c43-106">Ovunque Call Quality dashboard includa [dati di identificazione dell'utente finale (EUII)](CQD-data-and-reports.md#euii-data), viene gestito allo stesso modo di EUII in [Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span><span class="sxs-lookup"><span data-stu-id="e8c43-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="e8c43-107">Call Quality dashboard è progettato per aiutare gli amministratori del team, gli amministratori di Skype for business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e8c43-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="e8c43-108">Userai Call Quality dashboard per **ottimizzare la rete** per migliorare la qualità delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c43-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="e8c43-109">Quando devi esaminare le informazioni di chiamata e riunione per un **utente specifico**, USA i dati di Call Quality dashboard in combinazione con le [analisi delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)per utente.</span><span class="sxs-lookup"><span data-stu-id="e8c43-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="e8c43-110">Usando Call Quality dashboard, ad esempio, puoi determinare che la qualità di chiamata scadente di un utente (che hai osservato usando l'analisi delle chiamate per utente) è dovuta a un problema di rete che interessa anche molti altri utenti.</span><span class="sxs-lookup"><span data-stu-id="e8c43-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="e8c43-111">Call Quality dashboard acquisisce sia l'esperienza di chiamata individuale che la qualità complessiva delle chiamate effettuate tramite teams o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e8c43-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="e8c43-112">Con Call Quality dashboard, i modelli generali possono diventare evidenti, in modo che gli ingegneri di rete possano effettuare valutazioni informate sulla qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="e8c43-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="e8c43-113">Call Quality dashboard fornisce report sulle metriche di qualità delle chiamate che consentono di comprendere la qualità complessiva delle chiamate, i flussi client-server, i flussi client-client e la qualità della voce [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span><span class="sxs-lookup"><span data-stu-id="e8c43-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot del dashboard qualità chiamata.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="e8c43-115">In Call Quality dashboard invitiamo a caricare le informazioni sulla creazione e sull'endpoint, che consente di usare report con funzionalità avanzate per analizzare la qualità e l'affidabilità delle chiamate all'interno di un edificio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e8c43-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="e8c43-116">I dati possono essere valutati per determinare se il problema è isolato da un singolo utente o influisce su un segmento più grande di utenti.</span><span class="sxs-lookup"><span data-stu-id="e8c43-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="e8c43-117">Per attivare visualizzazioni specifiche di un edificio o di un endpoint in Call Quality dashboard, un amministratore deve [caricare le informazioni sulla compilazione o sull'endpoint](CQD-upload-tenant-building-data.md) nella pagina di **caricamento dei dati del tenant** di Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="e8c43-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Screenshot dei report di posizione avanzata di Call Quality dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="e8c43-119">Non perdere l'articolo [Gestisci la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md) , che offre indicazioni approfondite per l'amministratore del team o il tecnico del supporto responsabile della gestione della qualità dei servizi in teams.</span><span class="sxs-lookup"><span data-stu-id="e8c43-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="e8c43-120">Versione precedente di Call Quality Dashboard (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="e8c43-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="e8c43-121">La versione corrente di Call Quality Dashboard ( https://CQD.Teams.microsoft.com) sostituisce la versione precedente di Call Quality Dashboard ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="e8c43-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="e8c43-122">È comunque possibile usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for business), ma dal 1 ° luglio 2020 USA i dati di Call Quality dashboard. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e8c43-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="e8c43-123">Disattiveremo presto l'accesso a CQD.lync.com, quindi devi trasferirti in Call Quality dashboard. Teams.microsoft.com se non è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="e8c43-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8c43-124">A partire dal 1 ° luglio 2020, non è più possibile visualizzare o modificare l'edificio o i dati di query dal vecchio Call Quality Dashboard (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="e8c43-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="e8c43-125">Se non sono già stati migrati questi dati da CQD.lync.com e ne è ancora necessario, registrare un ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="e8c43-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="e8c43-126">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="e8c43-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="e8c43-127">Novità di gennaio 2020: [scaricare i modelli di query di Power BI per Call Quality dashboard](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="e8c43-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="e8c43-128">Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati di Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="e8c43-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="e8c43-129">Leggere [usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="e8c43-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="e8c43-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e8c43-130">Related topics</span></span>

[<span data-ttu-id="e8c43-131">Migliorare e monitorare la qualità delle chiamate per i team</span><span class="sxs-lookup"><span data-stu-id="e8c43-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="e8c43-132">Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="e8c43-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="e8c43-133">Caricare i dati del tenant e della creazione</span><span class="sxs-lookup"><span data-stu-id="e8c43-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="e8c43-134">Dati e report di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="e8c43-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="e8c43-135">Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="e8c43-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="e8c43-136">Dimensioni e misure disponibili in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="e8c43-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e8c43-137">Classificazione del flusso in Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="e8c43-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e8c43-138">Usare Power BI per analizzare i dati di Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="e8c43-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="e8c43-139">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="e8c43-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)