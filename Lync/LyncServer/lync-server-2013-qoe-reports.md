---
title: 'Lync Server 2013: rapporti QoE'
description: 'Lync Server 2013: report QoE.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571402"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="e53de-103">Report QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e53de-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e53de-104">_**Ultimo argomento modificato:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="e53de-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="e53de-105">Riepilogo QoE/rapporti di tendenza</span><span class="sxs-lookup"><span data-stu-id="e53de-105">QoE summary/trend reports</span></span>

<span data-ttu-id="e53de-106">I report di riepilogo/tendenze QoE sono utili per individuare i tempi di utilizzo massimi del giorno ed esaminare la qualità multimediale in quei periodi per garantire che le risorse di rete dell'organizzazione siano sufficienti.</span><span class="sxs-lookup"><span data-stu-id="e53de-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="e53de-107">L'organizzazione può anche utilizzare i numerosi filtri disponibili nel report per isolare i numeri di prestazioni per determinati percorsi, tipi di client e dispositivi e server.</span><span class="sxs-lookup"><span data-stu-id="e53de-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="e53de-108">I rapporti di riepilogo/trend QoE sono costituiti da:</span><span class="sxs-lookup"><span data-stu-id="e53de-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="e53de-109">Report di riepilogo/trend da UC a UC</span><span class="sxs-lookup"><span data-stu-id="e53de-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="e53de-110">Riepilogo PSTN/rapporto trend</span><span class="sxs-lookup"><span data-stu-id="e53de-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="e53de-111">Riepilogo conferenze/Rapporto tendenze</span><span class="sxs-lookup"><span data-stu-id="e53de-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="e53de-112">Rapporti sulle prestazioni QoE</span><span class="sxs-lookup"><span data-stu-id="e53de-112">QoE performance reports</span></span>

<span data-ttu-id="e53de-113">I report sulle prestazioni QoE forniscono informazioni dettagliate sui tre rapporti che si concentrano sulle prestazioni QoE di Mediation Server, A/V Conferencing Server e endpoint locations.</span><span class="sxs-lookup"><span data-stu-id="e53de-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="e53de-114">Rapporto prestazioni Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e53de-114">Mediation server performance report</span></span>

<span data-ttu-id="e53de-115">Il rapporto prestazioni Mediation Server elenca le metriche ottenute da una o più mediazione durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="e53de-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="e53de-116">Le metriche per la gamba del server Unified Communications (UC)-to-Mediation e la gamba Mediation Server-to-gateway di ogni chiamata vengono segnalate separatamente.</span><span class="sxs-lookup"><span data-stu-id="e53de-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="e53de-117">Utilizzare questo report per confrontare il volume e le prestazioni dei diversi Mediation Server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e53de-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="e53de-118">Per ogni Mediation Server (e per ogni gamba di chiamata), il report Visualizza gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e53de-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="e53de-119">Numero di chiamate</span><span class="sxs-lookup"><span data-stu-id="e53de-119">Number of calls</span></span>

  - <span data-ttu-id="e53de-120">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e53de-120">Packet Loss</span></span>

  - <span data-ttu-id="e53de-121">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="e53de-121">Round Trip Time</span></span>

  - <span data-ttu-id="e53de-122">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e53de-122">Jitter</span></span>

  - <span data-ttu-id="e53de-123">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e53de-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e53de-124">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e53de-124">Sending MOS</span></span>

  - <span data-ttu-id="e53de-125">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e53de-125">Listening MOS</span></span>

  - <span data-ttu-id="e53de-126">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-126">Network MOS</span></span>

  - <span data-ttu-id="e53de-127">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="e53de-128">Return Echo</span><span class="sxs-lookup"><span data-stu-id="e53de-128">Echo Return</span></span>

  - <span data-ttu-id="e53de-129">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="e53de-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="e53de-130">Report sulle prestazioni di A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="e53de-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="e53de-131">Il rapporto prestazioni A/V Conferencing Server fornisce gli elenchi di metriche ottenute da uno o più server A/V Conferencing durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="e53de-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="e53de-132">Questo report può essere utilizzato per confrontare il volume e le prestazioni dei diversi server A/V Conferencing dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e53de-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="e53de-133">L'organizzazione può anche isolare il report in modo da mostrare solo l'esperienza per specifici tipi di client, ad esempio client di Lync o client PSTN.</span><span class="sxs-lookup"><span data-stu-id="e53de-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="e53de-134">Per ogni server A/V Conferencing, il report Visualizza gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e53de-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="e53de-135">Numero di conferenze</span><span class="sxs-lookup"><span data-stu-id="e53de-135">Number of conferences</span></span>

  - <span data-ttu-id="e53de-136">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e53de-136">Packet Loss</span></span>

  - <span data-ttu-id="e53de-137">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="e53de-137">Round Trip Time</span></span>

  - <span data-ttu-id="e53de-138">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e53de-138">Jitter</span></span>

  - <span data-ttu-id="e53de-139">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e53de-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e53de-140">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e53de-140">Sending MOS</span></span>

  - <span data-ttu-id="e53de-141">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e53de-141">Listening MOS</span></span>

  - <span data-ttu-id="e53de-142">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-142">Network MOS</span></span>

  - <span data-ttu-id="e53de-143">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="e53de-144">Return Echo</span><span class="sxs-lookup"><span data-stu-id="e53de-144">Echo Return</span></span>

  - <span data-ttu-id="e53de-145">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="e53de-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="e53de-146">Report sulle prestazioni basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="e53de-146">Location-based performance report</span></span>

<span data-ttu-id="e53de-147">Il rapporto prestazioni Location-Based fornisce un elenco di percorsi di rete e per ogni percorso viene visualizzato il numero di chiamate in ogni intervallo di qualità predeterminato.</span><span class="sxs-lookup"><span data-stu-id="e53de-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="e53de-148">L'obiettivo di questo report è quello di fornire informazioni sulla qualità multimediale della maggior parte delle chiamate telefoniche dell'organizzazione per diverse posizioni in modo da poter identificare le posizioni scarsamente performanti e vedere i diversi gradi di qualità multimediale nelle diverse posizioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e53de-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="e53de-149">Quando si Visualizza il report, vengono visualizzate diverse tabelle di metriche, ovvero una tabella per ogni metrica a cui l'organizzazione decide di riferire.</span><span class="sxs-lookup"><span data-stu-id="e53de-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="e53de-150">Per questo report è possibile scegliere tra le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e53de-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="e53de-151">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e53de-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e53de-152">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-152">Network MOS</span></span>

  - <span data-ttu-id="e53de-153">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e53de-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="e53de-154">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e53de-154">Sending MOS</span></span>

  - <span data-ttu-id="e53de-155">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e53de-155">Listening MOS</span></span>

  - <span data-ttu-id="e53de-156">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e53de-156">Packet Loss</span></span>

  - <span data-ttu-id="e53de-157">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e53de-157">Jitter</span></span>

  - <span data-ttu-id="e53de-158">Latenza</span><span class="sxs-lookup"><span data-stu-id="e53de-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

