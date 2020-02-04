---
title: 'Lync Server 2013: report QoE'
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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="77106-102">Report QoE in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77106-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77106-103">_**Argomento Ultima modifica:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="77106-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="77106-104">Riepilogo QoE/report di tendenza</span><span class="sxs-lookup"><span data-stu-id="77106-104">QoE summary/trend reports</span></span>

<span data-ttu-id="77106-105">I report di riepilogo/tendenze QoE sono utili per trovare i tempi di utilizzo del giorno e per esaminare la qualità dei contenuti multimediali in questi periodi per assicurare che le risorse di rete dell'organizzazione siano sufficienti.</span><span class="sxs-lookup"><span data-stu-id="77106-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="77106-106">L'organizzazione può anche usare i numerosi filtri disponibili nel report per isolare i numeri di prestazioni per determinati percorsi, tipi di client e dispositivi e server.</span><span class="sxs-lookup"><span data-stu-id="77106-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="77106-107">I report di riepilogo/tendenza QoE sono costituiti da:</span><span class="sxs-lookup"><span data-stu-id="77106-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="77106-108">Riepilogo/report di riassunto UC-to-UC</span><span class="sxs-lookup"><span data-stu-id="77106-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="77106-109">Riepilogo PSTN/rapporto tendenza</span><span class="sxs-lookup"><span data-stu-id="77106-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="77106-110">Riepilogo delle conferenze/rapporto sulle tendenze</span><span class="sxs-lookup"><span data-stu-id="77106-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="77106-111">Report prestazioni QoE</span><span class="sxs-lookup"><span data-stu-id="77106-111">QoE performance reports</span></span>

<span data-ttu-id="77106-112">I report sulle prestazioni QoE includono dettagli sui tre report che si concentrano sulle prestazioni QoE di Mediation Server, A/V Conferencing Servers e location endpoint.</span><span class="sxs-lookup"><span data-stu-id="77106-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="77106-113">Report prestazioni Mediation Server</span><span class="sxs-lookup"><span data-stu-id="77106-113">Mediation server performance report</span></span>

<span data-ttu-id="77106-114">Il report prestazioni Mediation Server elenca le metriche conseguite da una o più mediazioni durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="77106-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="77106-115">Le metriche per la gamba del server comunicazioni unificate (UC)-mediazione e il segmento Mediation Server-to-gateway di ogni chiamata vengono segnalate separatamente.</span><span class="sxs-lookup"><span data-stu-id="77106-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="77106-116">Usare questo report per confrontare il volume e le prestazioni dei vari server di mediazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="77106-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="77106-117">Per ogni Mediation Server (e per ogni gamba di chiamata), nel report vengono visualizzati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="77106-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="77106-118">Numero di chiamate</span><span class="sxs-lookup"><span data-stu-id="77106-118">Number of calls</span></span>

  - <span data-ttu-id="77106-119">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="77106-119">Packet Loss</span></span>

  - <span data-ttu-id="77106-120">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="77106-120">Round Trip Time</span></span>

  - <span data-ttu-id="77106-121">Jitter</span><span class="sxs-lookup"><span data-stu-id="77106-121">Jitter</span></span>

  - <span data-ttu-id="77106-122">Punteggio di opinione media conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="77106-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="77106-123">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="77106-123">Sending MOS</span></span>

  - <span data-ttu-id="77106-124">MOS in ascolto</span><span class="sxs-lookup"><span data-stu-id="77106-124">Listening MOS</span></span>

  - <span data-ttu-id="77106-125">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="77106-125">Network MOS</span></span>

  - <span data-ttu-id="77106-126">Degradazione MOS Network</span><span class="sxs-lookup"><span data-stu-id="77106-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="77106-127">Ritorno Echo</span><span class="sxs-lookup"><span data-stu-id="77106-127">Echo Return</span></span>

  - <span data-ttu-id="77106-128">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="77106-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="77106-129">Report prestazioni di un/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="77106-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="77106-130">Il report prestazioni A/V Conferencing Server fornisce elenchi di metriche conseguiti da uno o più server di conferenza A/V durante il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="77106-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="77106-131">Questo report può essere usato per confrontare il volume e le prestazioni dei vari server di conferenza A/V dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="77106-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="77106-132">L'organizzazione può anche isolare il report in modo da mostrare solo l'esperienza per specifici tipi di client, ad esempio client Lync o client PSTN.</span><span class="sxs-lookup"><span data-stu-id="77106-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="77106-133">Per ogni server A/V Conferencing, il report Visualizza le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="77106-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="77106-134">Numero di conferenze</span><span class="sxs-lookup"><span data-stu-id="77106-134">Number of conferences</span></span>

  - <span data-ttu-id="77106-135">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="77106-135">Packet Loss</span></span>

  - <span data-ttu-id="77106-136">Tempo di andata e ritorno</span><span class="sxs-lookup"><span data-stu-id="77106-136">Round Trip Time</span></span>

  - <span data-ttu-id="77106-137">Jitter</span><span class="sxs-lookup"><span data-stu-id="77106-137">Jitter</span></span>

  - <span data-ttu-id="77106-138">Punteggio di opinione media conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="77106-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="77106-139">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="77106-139">Sending MOS</span></span>

  - <span data-ttu-id="77106-140">MOS in ascolto</span><span class="sxs-lookup"><span data-stu-id="77106-140">Listening MOS</span></span>

  - <span data-ttu-id="77106-141">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="77106-141">Network MOS</span></span>

  - <span data-ttu-id="77106-142">Degradazione MOS Network</span><span class="sxs-lookup"><span data-stu-id="77106-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="77106-143">Ritorno Echo</span><span class="sxs-lookup"><span data-stu-id="77106-143">Echo Return</span></span>

  - <span data-ttu-id="77106-144">Livello di segnale</span><span class="sxs-lookup"><span data-stu-id="77106-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="77106-145">Report prestazioni basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="77106-145">Location-based performance report</span></span>

<span data-ttu-id="77106-146">Il report prestazioni basato sulla posizione fornisce un elenco di percorsi di rete e per ogni posizione viene visualizzato il numero di chiamate in ogni intervallo di qualità predeterminato.</span><span class="sxs-lookup"><span data-stu-id="77106-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="77106-147">L'obiettivo di questo report è quello di comprendere la qualità dei contenuti multimediali della maggior parte delle chiamate telefoniche dell'organizzazione per varie posizioni, in modo da poter identificare le posizioni poco performanti e vedere i diversi gradi di qualità dei contenuti multimediali nell'organizzazione posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="77106-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="77106-148">Quando si Visualizza il report, vengono visualizzate diverse tabelle di metriche, ovvero una tabella per ogni metrica a cui l'organizzazione decide di segnalare.</span><span class="sxs-lookup"><span data-stu-id="77106-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="77106-149">Per questo report è possibile scegliere tra le metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="77106-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="77106-150">Punteggio di opinione media conversazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="77106-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="77106-151">MOS di rete</span><span class="sxs-lookup"><span data-stu-id="77106-151">Network MOS</span></span>

  - <span data-ttu-id="77106-152">Degradazione MOS Network</span><span class="sxs-lookup"><span data-stu-id="77106-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="77106-153">Invio di MOS</span><span class="sxs-lookup"><span data-stu-id="77106-153">Sending MOS</span></span>

  - <span data-ttu-id="77106-154">MOS in ascolto</span><span class="sxs-lookup"><span data-stu-id="77106-154">Listening MOS</span></span>

  - <span data-ttu-id="77106-155">Perdita pacchetti</span><span class="sxs-lookup"><span data-stu-id="77106-155">Packet Loss</span></span>

  - <span data-ttu-id="77106-156">Jitter</span><span class="sxs-lookup"><span data-stu-id="77106-156">Jitter</span></span>

  - <span data-ttu-id="77106-157">Latenza</span><span class="sxs-lookup"><span data-stu-id="77106-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

