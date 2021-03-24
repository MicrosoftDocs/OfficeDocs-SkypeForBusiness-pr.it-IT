---
title: Che cos'è Call Quality Dashboard (CQD)?
ms.author: serdars
author: SerdarSoysal
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
description: Informazioni su Call Quality Dashboard (CQD) e su come usarlo per visualizzare i report sulla qualità delle riunioni e delle chiamate in Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094940"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="5ea77-103">Che cos'è Call Quality Dashboard (CQD)?</span><span class="sxs-lookup"><span data-stu-id="5ea77-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="5ea77-104">Microsoft Call Quality Dashboard (CQD) - mostra la qualità delle chiamate e delle riunioni, a livello di organizzazione, per Microsoft Teams, Skype for Business Online e [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019. </span><span class="sxs-lookup"><span data-stu-id="5ea77-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="5ea77-105">L'ultima versione di CQD include un feed di dati quasi in tempo reale [(NRT),](CQD-data-and-reports.md)il che significa che i record delle chiamate sono disponibili in CQD entro 30 minuti dalla fine di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="5ea77-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="5ea77-106">Dove CQD include dati di informazioni identificabili per l'utente finale [(EUII),](CQD-data-and-reports.md#euii-data)viene gestito allo stesso modo di [EUII in Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="5ea77-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="5ea77-107">CQD è progettato per aiutare gli amministratori di Teams, gli amministratori di Skype for Business e i tecnici di rete a monitorare la qualità delle chiamate e delle riunioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ea77-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="5ea77-108">Si userà CQD per ottimizzare la **rete per** migliorare la qualità delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5ea77-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="5ea77-109">Quando è necessario esaminare le informazioni di chiamata e riunione per un utente **specifico,** usare i dati CQD insieme all'analisi [delle chiamate per utente.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="5ea77-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="5ea77-110">Ad esempio, usando CQD, è possibile determinare che la scarsa qualità delle chiamate di un utente (osservata con l'analisi delle chiamate per utente) è dovuta a un problema di rete che interessa anche molti altri utenti.</span><span class="sxs-lookup"><span data-stu-id="5ea77-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="5ea77-111">CQD acquisisce sia l'esperienza delle singole chiamate che la qualità generale delle chiamate effettuate con Teams o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5ea77-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="5ea77-112">Con CQD, i modelli complessivi possono diventare evidenti, quindi i tecnici di rete possono effettuare valutazioni informate sulla qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="5ea77-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="5ea77-113">CQD fornisce report sulle metriche sulla qualità delle chiamate che forniscono informazioni approfondite sulla qualità complessiva delle chiamate, i flussi server-client, i flussi client-client e il contratto di servizio sulla [qualità vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="5ea77-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="5ea77-115">In CQD ti consigliamo di caricare informazioni sull'edificio e sull'endpoint, che ti consentono di usare i report di Location-Enhanced per analizzare la qualità e l'affidabilità delle chiamate all'interno dell'edificio di un utente.</span><span class="sxs-lookup"><span data-stu-id="5ea77-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="5ea77-116">I dati possono essere valutati per determinare se il problema è isolato per un singolo utente o interessa un segmento più ampio di utenti.</span><span class="sxs-lookup"><span data-stu-id="5ea77-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="5ea77-117">Per attivare le visualizzazioni specifiche dell'edificio o [dell'endpoint](CQD-upload-tenant-building-data.md) in CQD, un amministratore deve caricare le informazioni sull'edificio o sull'endpoint nella pagina di caricamento dei dati del **tenant** CQD.</span><span class="sxs-lookup"><span data-stu-id="5ea77-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![Screenshot dei report Location-Enhanced di Call Quality Dashboard.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="5ea77-119">Non perderti [](quality-of-experience-review-guide.md) l'articolo Gestire la qualità delle chiamate e delle riunioni, che offre indicazioni approfondite per l'amministratore o il tecnico del supporto tecnico di Teams responsabile della gestione della qualità del servizio in Teams.</span><span class="sxs-lookup"><span data-stu-id="5ea77-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="5ea77-120">Versione precedente di CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="5ea77-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="5ea77-121">La versione corrente di CQD ( https://CQD.Teams.microsoft.com) sostituisce la versione precedente di CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="5ea77-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="5ea77-122">Puoi comunque usare CQD.lync.com (disponibile nell'interfaccia di amministrazione di Skype for Business), ma a partire dal 1° luglio 2020, usa i dati di CQD. Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5ea77-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="5ea77-123">A breve l'accesso a CQD.lync.com verrà disattivato, quindi è consigliabile passare a CQD. Teams.microsoft.com se non è già stato fatto.</span><span class="sxs-lookup"><span data-stu-id="5ea77-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ea77-124">A partire dal 1° luglio 2020, non è più possibile visualizzare o modificare i dati dell'edificio o della query dal vecchio CQD (CQD.lync.com).</span><span class="sxs-lookup"><span data-stu-id="5ea77-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="5ea77-125">Se non è ancora stata eseguita la migrazione di questi dati da CQD.lync.com e se ne ha ancora bisogno, registrare un ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ea77-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="5ea77-126">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="5ea77-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="5ea77-127">Novità di gennaio 2020: [Scaricare i modelli di query di Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="5ea77-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="5ea77-128">Modelli di Power BI personalizzabili che è possibile usare per analizzare e segnalare i dati CQD.</span><span class="sxs-lookup"><span data-stu-id="5ea77-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="5ea77-129">Leggere [Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="5ea77-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="5ea77-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5ea77-130">Related topics</span></span>

[<span data-ttu-id="5ea77-131">Migliorare e monitorare la qualità delle chiamate per Teams</span><span class="sxs-lookup"><span data-stu-id="5ea77-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="5ea77-132">Configurare call quality dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="5ea77-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="5ea77-133">Caricare i dati del tenant e dell'edificio</span><span class="sxs-lookup"><span data-stu-id="5ea77-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="5ea77-134">Dati e report CQD</span><span class="sxs-lookup"><span data-stu-id="5ea77-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="5ea77-135">Usare CQD per gestire la qualità delle chiamate e delle riunioni</span><span class="sxs-lookup"><span data-stu-id="5ea77-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="5ea77-136">Dimensioni e misure disponibili in CQD</span><span class="sxs-lookup"><span data-stu-id="5ea77-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="5ea77-137">Classificazione dei flussi in CQD</span><span class="sxs-lookup"><span data-stu-id="5ea77-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="5ea77-138">Usare Power BI per analizzare i dati CQD</span><span class="sxs-lookup"><span data-stu-id="5ea77-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="5ea77-139">Risoluzione dei problemi di Teams</span><span class="sxs-lookup"><span data-stu-id="5ea77-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)