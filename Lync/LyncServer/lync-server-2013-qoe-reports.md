---
title: 'Lync Server 2013: rapporti QoE'
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
ms.openlocfilehash: 353e0941f443e2cb971f8ebd037413232e21b827
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="e5be1-102">Report QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5be1-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5be1-103">_**Ultimo argomento modificato:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="e5be1-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="e5be1-104">Riepilogo QoE/rapporti di tendenza</span><span class="sxs-lookup"><span data-stu-id="e5be1-104">QoE summary/trend reports</span></span>

<span data-ttu-id="e5be1-105">I report di riepilogo/tendenze QoE sono utili per individuare i tempi di utilizzo massimi del giorno ed esaminare la qualità multimediale in quei periodi per garantire che le risorse di rete dell'organizzazione siano sufficienti.</span><span class="sxs-lookup"><span data-stu-id="e5be1-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="e5be1-106">L'organizzazione può anche utilizzare i numerosi filtri disponibili nel report per isolare i numeri di prestazioni per determinati percorsi, tipi di client e dispositivi e server.</span><span class="sxs-lookup"><span data-stu-id="e5be1-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="e5be1-107">I rapporti di riepilogo/trend QoE sono costituiti da:</span><span class="sxs-lookup"><span data-stu-id="e5be1-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="e5be1-108">Report di riepilogo/trend da UC a UC</span><span class="sxs-lookup"><span data-stu-id="e5be1-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="e5be1-109">Riepilogo PSTN/rapporto trend</span><span class="sxs-lookup"><span data-stu-id="e5be1-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="e5be1-110">Riepilogo conferenze/Rapporto tendenze</span><span class="sxs-lookup"><span data-stu-id="e5be1-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="e5be1-111">Rapporti sulle prestazioni QoE</span><span class="sxs-lookup"><span data-stu-id="e5be1-111">QoE performance reports</span></span>

<span data-ttu-id="e5be1-112">I report sulle prestazioni QoE forniscono informazioni dettagliate sui tre rapporti che si concentrano sulle prestazioni QoE di Mediation Server, A/V Conferencing Server e endpoint locations.</span><span class="sxs-lookup"><span data-stu-id="e5be1-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="e5be1-113">Rapporto prestazioni Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e5be1-113">Mediation server performance report</span></span>

<span data-ttu-id="e5be1-114">Il rapporto prestazioni Mediation Server elenca le metriche ottenute da una o più mediazione durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="e5be1-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="e5be1-115">Le metriche per la gamba del server Unified Communications (UC)-to-Mediation e la gamba Mediation Server-to-gateway di ogni chiamata vengono segnalate separatamente.</span><span class="sxs-lookup"><span data-stu-id="e5be1-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="e5be1-116">Utilizzare questo report per confrontare il volume e le prestazioni dei diversi Mediation Server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e5be1-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="e5be1-117">Per ogni Mediation Server (e per ogni gamba di chiamata), il report Visualizza gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5be1-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="e5be1-118">Numero di chiamate</span><span class="sxs-lookup"><span data-stu-id="e5be1-118">Number of calls</span></span>

  - <span data-ttu-id="e5be1-119">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e5be1-119">Packet Loss</span></span>

  - <span data-ttu-id="e5be1-120">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="e5be1-120">Round Trip Time</span></span>

  - <span data-ttu-id="e5be1-121">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e5be1-121">Jitter</span></span>

  - <span data-ttu-id="e5be1-122">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e5be1-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e5be1-123">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e5be1-123">Sending MOS</span></span>

  - <span data-ttu-id="e5be1-124">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e5be1-124">Listening MOS</span></span>

  - <span data-ttu-id="e5be1-125">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-125">Network MOS</span></span>

  - <span data-ttu-id="e5be1-126">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="e5be1-127">Return Echo</span><span class="sxs-lookup"><span data-stu-id="e5be1-127">Echo Return</span></span>

  - <span data-ttu-id="e5be1-128">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="e5be1-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="e5be1-129">Report sulle prestazioni di A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="e5be1-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="e5be1-130">Il rapporto prestazioni A/V Conferencing Server fornisce gli elenchi di metriche ottenute da uno o più server A/V Conferencing durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="e5be1-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="e5be1-131">Questo report può essere utilizzato per confrontare il volume e le prestazioni dei diversi server A/V Conferencing dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e5be1-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="e5be1-132">L'organizzazione può anche isolare il report in modo da mostrare solo l'esperienza per specifici tipi di client, ad esempio client di Lync o client PSTN.</span><span class="sxs-lookup"><span data-stu-id="e5be1-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="e5be1-133">Per ogni server A/V Conferencing, il report Visualizza gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5be1-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="e5be1-134">Numero di conferenze</span><span class="sxs-lookup"><span data-stu-id="e5be1-134">Number of conferences</span></span>

  - <span data-ttu-id="e5be1-135">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e5be1-135">Packet Loss</span></span>

  - <span data-ttu-id="e5be1-136">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="e5be1-136">Round Trip Time</span></span>

  - <span data-ttu-id="e5be1-137">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e5be1-137">Jitter</span></span>

  - <span data-ttu-id="e5be1-138">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e5be1-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e5be1-139">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e5be1-139">Sending MOS</span></span>

  - <span data-ttu-id="e5be1-140">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e5be1-140">Listening MOS</span></span>

  - <span data-ttu-id="e5be1-141">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-141">Network MOS</span></span>

  - <span data-ttu-id="e5be1-142">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="e5be1-143">Return Echo</span><span class="sxs-lookup"><span data-stu-id="e5be1-143">Echo Return</span></span>

  - <span data-ttu-id="e5be1-144">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="e5be1-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="e5be1-145">Report sulle prestazioni basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="e5be1-145">Location-based performance report</span></span>

<span data-ttu-id="e5be1-146">Il report sulle prestazioni basato sulla posizione fornisce un elenco di percorsi di rete e per ogni percorso viene visualizzato il numero di chiamate in ogni intervallo di qualità predeterminato.</span><span class="sxs-lookup"><span data-stu-id="e5be1-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="e5be1-147">L'obiettivo di questo report è quello di fornire informazioni sulla qualità multimediale della maggior parte delle chiamate telefoniche dell'organizzazione per diverse posizioni in modo da poter identificare le posizioni poco performative e vedere i diversi gradi di qualità multimediale nell'organizzazione. posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="e5be1-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="e5be1-148">Quando si Visualizza il report, vengono visualizzate diverse tabelle di metriche, ovvero una tabella per ogni metrica a cui l'organizzazione decide di riferire.</span><span class="sxs-lookup"><span data-stu-id="e5be1-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="e5be1-149">Per questo report è possibile scegliere tra le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5be1-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="e5be1-150">Punteggio di opinione medio di conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="e5be1-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="e5be1-151">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-151">Network MOS</span></span>

  - <span data-ttu-id="e5be1-152">Degradazione MOS di rete</span><span class="sxs-lookup"><span data-stu-id="e5be1-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="e5be1-153">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="e5be1-153">Sending MOS</span></span>

  - <span data-ttu-id="e5be1-154">MOS di attesa</span><span class="sxs-lookup"><span data-stu-id="e5be1-154">Listening MOS</span></span>

  - <span data-ttu-id="e5be1-155">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="e5be1-155">Packet Loss</span></span>

  - <span data-ttu-id="e5be1-156">Instabilità</span><span class="sxs-lookup"><span data-stu-id="e5be1-156">Jitter</span></span>

  - <span data-ttu-id="e5be1-157">Latenza</span><span class="sxs-lookup"><span data-stu-id="e5be1-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

