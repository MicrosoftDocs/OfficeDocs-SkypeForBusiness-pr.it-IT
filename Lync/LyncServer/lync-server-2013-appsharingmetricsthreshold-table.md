---
title: 'Lync Server 2013: tabella AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="cea91-102">Tabella AppSharingMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cea91-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cea91-103">_**Argomento Ultima modifica:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="cea91-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="cea91-104">La tabella AppSharingMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cea91-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="cea91-105">Queste soglie vengono usate per determinare se l'esperienza di condivisione dell'applicazione deve essere classificata come scadente.</span><span class="sxs-lookup"><span data-stu-id="cea91-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="cea91-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cea91-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cea91-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cea91-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cea91-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cea91-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-112">int</span><span class="sxs-lookup"><span data-stu-id="cea91-112">int</span></span></p></td>
<td><p><span data-ttu-id="cea91-113">Principale</span><span class="sxs-lookup"><span data-stu-id="cea91-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="cea91-114">Tipo di chiamata inserita.</span><span class="sxs-lookup"><span data-stu-id="cea91-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-116">int</span><span class="sxs-lookup"><span data-stu-id="cea91-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-117">Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cea91-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="cea91-118">Il valore predefinito è 1 milione.</span><span class="sxs-lookup"><span data-stu-id="cea91-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-120">int</span><span class="sxs-lookup"><span data-stu-id="cea91-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-121">Limitazione della larghezza di banda accettabile per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cea91-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="cea91-122">Il valore predefinito è 500000.</span><span class="sxs-lookup"><span data-stu-id="cea91-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-124">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="cea91-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-125">Tasso percentuale ottimale per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cea91-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="cea91-126">Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="cea91-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="cea91-127">Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione.</span><span class="sxs-lookup"><span data-stu-id="cea91-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="cea91-128">Il valore predefinito è 11%.</span><span class="sxs-lookup"><span data-stu-id="cea91-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-130">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="cea91-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-131">tasso percentuale cceptable per i riquadri "viziati" per la classificazione di una qualità di condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cea91-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="cea91-132">Questo valore è la percentuale del contenuto del condivisore che non ha raggiunto il visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="cea91-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="cea91-133">Il contenuto può essere scartato (o viziato) quando il condivisore Elimina i riquadri dall'origine grafica o i riquadri di ASMCU scartano rispettivamente i riquadri di condivisione.</span><span class="sxs-lookup"><span data-stu-id="cea91-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="cea91-134">Il valore predefinito è 36%.</span><span class="sxs-lookup"><span data-stu-id="cea91-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-136">int</span><span class="sxs-lookup"><span data-stu-id="cea91-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-137">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-139">int</span><span class="sxs-lookup"><span data-stu-id="cea91-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-140">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-142">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-143">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-145">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-146">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-148">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-149">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-151">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-152">Questa colonna non viene usata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-154">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-155">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="cea91-156">Si tratta di una misura di latenza single-hop.</span><span class="sxs-lookup"><span data-stu-id="cea91-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="cea91-157">Il valore predefinito è 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="cea91-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="cea91-158">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-160">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-161">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="cea91-162">Si tratta di una misura di latenza single-hop.</span><span class="sxs-lookup"><span data-stu-id="cea91-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="cea91-163">Il valore predefinito è 1,75 secondi.</span><span class="sxs-lookup"><span data-stu-id="cea91-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="cea91-164">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cea91-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-166">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-167">Valore ottimale della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="cea91-168">La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="cea91-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="cea91-169">Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="cea91-170">Un server di conferenza di overload può avere ritardi medi più alti.</span><span class="sxs-lookup"><span data-stu-id="cea91-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="cea91-171">Il valore predefinito è 200ms.</span><span class="sxs-lookup"><span data-stu-id="cea91-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="cea91-172">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cea91-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="cea91-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="cea91-174">galleggiante</span><span class="sxs-lookup"><span data-stu-id="cea91-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cea91-175">Valore accettabile della latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="cea91-176">La latenza è la differenza di orario tra il momento in cui il fotogramma iniziale è codificato nel server (condivisore o MCU a seconda dello scenario) e lo stesso fotogramma iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="cea91-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="cea91-177">Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="cea91-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="cea91-178">Un server di conferenza di overload può avere ritardi medi più alti.</span><span class="sxs-lookup"><span data-stu-id="cea91-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="cea91-179">Il valore predefinito è 200ms.</span><span class="sxs-lookup"><span data-stu-id="cea91-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="cea91-180">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cea91-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

