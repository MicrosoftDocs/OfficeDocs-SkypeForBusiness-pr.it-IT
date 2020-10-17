---
title: 'Lync Server 2013: tabella VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518563"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="7294b-102">Tabella VideoStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7294b-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7294b-103">_**Ultimo argomento modificato:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="7294b-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="7294b-104">Ogni record rappresenta un flusso video.</span><span class="sxs-lookup"><span data-stu-id="7294b-104">Each record represents one video stream.</span></span> <span data-ttu-id="7294b-105">Una linea video multimediale in genere contiene due flussi video.</span><span class="sxs-lookup"><span data-stu-id="7294b-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7294b-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7294b-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7294b-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7294b-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7294b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7294b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7294b-112">Principale</span><span class="sxs-lookup"><span data-stu-id="7294b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7294b-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7294b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-115">int</span><span class="sxs-lookup"><span data-stu-id="7294b-115">int</span></span></p></td>
<td><p><span data-ttu-id="7294b-116">Principale</span><span class="sxs-lookup"><span data-stu-id="7294b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7294b-117">R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7294b-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7294b-120">Principale</span><span class="sxs-lookup"><span data-stu-id="7294b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7294b-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7294b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-123">int</span><span class="sxs-lookup"><span data-stu-id="7294b-123">int</span></span></p></td>
<td><p><span data-ttu-id="7294b-124">Principale</span><span class="sxs-lookup"><span data-stu-id="7294b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7294b-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="7294b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="7294b-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="7294b-128">Estero, primario</span><span class="sxs-lookup"><span data-stu-id="7294b-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="7294b-129">Descrizione payload.</span><span class="sxs-lookup"><span data-stu-id="7294b-129">Payload description.</span></span> <span data-ttu-id="7294b-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7294b-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-132">int</span><span class="sxs-lookup"><span data-stu-id="7294b-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-133">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="7294b-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-135">int</span><span class="sxs-lookup"><span data-stu-id="7294b-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-136">Instabilità massima della rete durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="7294b-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-138">int</span><span class="sxs-lookup"><span data-stu-id="7294b-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-139">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="7294b-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-141">int</span><span class="sxs-lookup"><span data-stu-id="7294b-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-142">Tempo massimo di andata e ritorno per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="7294b-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-144">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-145">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-147">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-148">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-150">int</span><span class="sxs-lookup"><span data-stu-id="7294b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-151">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="7294b-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-152"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-153">int</span><span class="sxs-lookup"><span data-stu-id="7294b-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-154">Stime della larghezza di banda per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="7294b-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="7294b-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-p103">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="7294b-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-160">int</span><span class="sxs-lookup"><span data-stu-id="7294b-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-161">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="7294b-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-163">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-164">La frequenza fotogrammi video ricevuta.</span><span class="sxs-lookup"><span data-stu-id="7294b-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-166">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-167">Frequenza fotogrammi video inviata.</span><span class="sxs-lookup"><span data-stu-id="7294b-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-169">int</span><span class="sxs-lookup"><span data-stu-id="7294b-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-170">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="7294b-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-172">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-173">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="7294b-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-175">po'</span><span class="sxs-lookup"><span data-stu-id="7294b-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-176">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="7294b-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-178">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-179">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="7294b-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-182">La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="7294b-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-185">La percentuale della chiamata che si trovava sulla risoluzione VGA.</span><span class="sxs-lookup"><span data-stu-id="7294b-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-188">La percentuale della chiamata che si trovava alla risoluzione di HD720.</span><span class="sxs-lookup"><span data-stu-id="7294b-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-191">Percentuale di durata della chiamata senza frame drop.</span><span class="sxs-lookup"><span data-stu-id="7294b-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-194">Percentuale di durata della chiamata con B frame drop.</span><span class="sxs-lookup"><span data-stu-id="7294b-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-197">Percentuale di durata della chiamata con drop frame BP.</span><span class="sxs-lookup"><span data-stu-id="7294b-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-200">Percentuale di durata della chiamata con BPSP frame drop.</span><span class="sxs-lookup"><span data-stu-id="7294b-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="7294b-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-203">Percentuale di durata della chiamata con BPSPI frame drop.</span><span class="sxs-lookup"><span data-stu-id="7294b-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-204"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-205">po'</span><span class="sxs-lookup"><span data-stu-id="7294b-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-206">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="7294b-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-207"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-208">po'</span><span class="sxs-lookup"><span data-stu-id="7294b-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-209">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="7294b-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-211">po'</span><span class="sxs-lookup"><span data-stu-id="7294b-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7294b-212">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="7294b-213">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="7294b-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-215">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-216">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="7294b-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="7294b-217">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-219">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-220">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="7294b-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="7294b-221">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-223">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-224">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="7294b-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="7294b-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-227">int</span><span class="sxs-lookup"><span data-stu-id="7294b-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-228">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7294b-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-231">int</span><span class="sxs-lookup"><span data-stu-id="7294b-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-232">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7294b-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-235">int</span><span class="sxs-lookup"><span data-stu-id="7294b-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-236">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7294b-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-239">int</span><span class="sxs-lookup"><span data-stu-id="7294b-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-240">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7294b-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-243">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-244">Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.</span><span class="sxs-lookup"><span data-stu-id="7294b-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="7294b-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-247">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p104">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-255">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-257">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p106">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-260">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-262">int</span><span class="sxs-lookup"><span data-stu-id="7294b-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p107">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-268">int</span><span class="sxs-lookup"><span data-stu-id="7294b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p108">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-272">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-274">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p109">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-280">int</span><span class="sxs-lookup"><span data-stu-id="7294b-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p110">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-284">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p111">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-290">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-292">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-p112">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="7294b-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7294b-296">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-298">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7294b-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-299">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="7294b-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="7294b-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-302">int</span><span class="sxs-lookup"><span data-stu-id="7294b-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-303">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="7294b-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="7294b-304">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-306">smallint</span><span class="sxs-lookup"><span data-stu-id="7294b-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="7294b-307">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7294b-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7294b-308">Tipo di codec video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="7294b-309">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7294b-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7294b-310">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-312">int</span><span class="sxs-lookup"><span data-stu-id="7294b-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-313">Larghezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="7294b-314">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-316">int</span><span class="sxs-lookup"><span data-stu-id="7294b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-317">Altezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="7294b-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-320">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-321">Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="7294b-322">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-324">int</span><span class="sxs-lookup"><span data-stu-id="7294b-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-325">Velocità in bit massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="7294b-326">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-328">int</span><span class="sxs-lookup"><span data-stu-id="7294b-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-329">Velocità in bit media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-331">int</span><span class="sxs-lookup"><span data-stu-id="7294b-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-332">Numero massimo di flussi video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="7294b-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="7294b-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-335">smallint</span><span class="sxs-lookup"><span data-stu-id="7294b-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="7294b-336">Stranieri</span><span class="sxs-lookup"><span data-stu-id="7294b-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7294b-337">Codici video utilizzati dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-337">Video codes used by the receiver.</span></span> <span data-ttu-id="7294b-338">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="7294b-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7294b-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-341">int</span><span class="sxs-lookup"><span data-stu-id="7294b-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-342">Larghezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="7294b-343">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-345">int</span><span class="sxs-lookup"><span data-stu-id="7294b-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-346">Altezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="7294b-347">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-349">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-350">Frequenza media dei fotogrammi video utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="7294b-351">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-353">int</span><span class="sxs-lookup"><span data-stu-id="7294b-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-354">Velocità in bit massima per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="7294b-355">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-357">int</span><span class="sxs-lookup"><span data-stu-id="7294b-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-358">Velocità in bit media per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="7294b-359">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-361">int</span><span class="sxs-lookup"><span data-stu-id="7294b-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-362">Massimi flussi video per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="7294b-363">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-365">int</span><span class="sxs-lookup"><span data-stu-id="7294b-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-366">Flussi video minimi per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="7294b-367">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-369">int</span><span class="sxs-lookup"><span data-stu-id="7294b-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-370">Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="7294b-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="7294b-371">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-373">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-374">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="7294b-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="7294b-375">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-377">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-378">Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</span><span class="sxs-lookup"><span data-stu-id="7294b-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="7294b-379">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="7294b-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-382">Risoluzione minima misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7294b-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="7294b-383">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-385">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-386">Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="7294b-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="7294b-387">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-389">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-390">Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</span><span class="sxs-lookup"><span data-stu-id="7294b-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="7294b-391">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-394">Percentuale della chiamata che si è verificata alla risoluzione più bassa.</span><span class="sxs-lookup"><span data-stu-id="7294b-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="7294b-395">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="7294b-396">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7294b-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-398">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7294b-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-399">Durata della chiamata in secondi.</span><span class="sxs-lookup"><span data-stu-id="7294b-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="7294b-400">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7294b-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="7294b-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="7294b-402">po'</span><span class="sxs-lookup"><span data-stu-id="7294b-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7294b-403">Indica se i dati sono stati aggregati da più chiamate.</span><span class="sxs-lookup"><span data-stu-id="7294b-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="7294b-404">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7294b-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

