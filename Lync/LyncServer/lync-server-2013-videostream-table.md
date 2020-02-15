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
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="12148-102">Tabella VideoStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12148-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12148-103">_**Ultimo argomento modificato:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="12148-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="12148-104">Ogni record rappresenta un flusso video.</span><span class="sxs-lookup"><span data-stu-id="12148-104">Each record represents one video stream.</span></span> <span data-ttu-id="12148-105">Una linea video multimediale in genere contiene due flussi video.</span><span class="sxs-lookup"><span data-stu-id="12148-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12148-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="12148-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="12148-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="12148-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="12148-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="12148-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="12148-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="12148-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12148-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="12148-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-111">datetime</span><span class="sxs-lookup"><span data-stu-id="12148-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="12148-112">Principale</span><span class="sxs-lookup"><span data-stu-id="12148-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="12148-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="12148-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="12148-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-115">int</span><span class="sxs-lookup"><span data-stu-id="12148-115">int</span></span></p></td>
<td><p><span data-ttu-id="12148-116">Principale</span><span class="sxs-lookup"><span data-stu-id="12148-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="12148-117">R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="12148-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="12148-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="12148-120">Principale</span><span class="sxs-lookup"><span data-stu-id="12148-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="12148-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="12148-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="12148-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-123">int</span><span class="sxs-lookup"><span data-stu-id="12148-123">int</span></span></p></td>
<td><p><span data-ttu-id="12148-124">Principale</span><span class="sxs-lookup"><span data-stu-id="12148-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="12148-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="12148-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="12148-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-127">smallint</span><span class="sxs-lookup"><span data-stu-id="12148-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="12148-128">Estero, primario</span><span class="sxs-lookup"><span data-stu-id="12148-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="12148-129">Descrizione payload.</span><span class="sxs-lookup"><span data-stu-id="12148-129">Payload description.</span></span> <span data-ttu-id="12148-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="12148-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="12148-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-132">int</span><span class="sxs-lookup"><span data-stu-id="12148-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-133">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="12148-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-135">int</span><span class="sxs-lookup"><span data-stu-id="12148-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-136">Instabilità massima della rete durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="12148-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="12148-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-138">int</span><span class="sxs-lookup"><span data-stu-id="12148-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-139">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="12148-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-141">int</span><span class="sxs-lookup"><span data-stu-id="12148-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-142">Tempo massimo di andata e ritorno per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="12148-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="12148-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-144">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-145">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-147">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-148">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="12148-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-150">int</span><span class="sxs-lookup"><span data-stu-id="12148-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-151">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="12148-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-152"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="12148-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-153">int</span><span class="sxs-lookup"><span data-stu-id="12148-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-154">Stime della larghezza di banda per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="12148-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="12148-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="12148-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-p103">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="12148-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="12148-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-160">int</span><span class="sxs-lookup"><span data-stu-id="12148-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-161">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="12148-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="12148-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-163">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-164">La frequenza fotogrammi video ricevuta.</span><span class="sxs-lookup"><span data-stu-id="12148-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="12148-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-166">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-167">Frequenza fotogrammi video inviata.</span><span class="sxs-lookup"><span data-stu-id="12148-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-169">int</span><span class="sxs-lookup"><span data-stu-id="12148-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-170">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="12148-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="12148-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-172">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-173">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="12148-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="12148-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-175">po'</span><span class="sxs-lookup"><span data-stu-id="12148-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-176">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="12148-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="12148-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-178">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-179">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="12148-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-182">La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="12148-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-185">La percentuale della chiamata che si trovava sulla risoluzione VGA.</span><span class="sxs-lookup"><span data-stu-id="12148-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-188">La percentuale della chiamata che si trovava alla risoluzione di HD720.</span><span class="sxs-lookup"><span data-stu-id="12148-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-191">Percentuale di durata della chiamata senza frame drop.</span><span class="sxs-lookup"><span data-stu-id="12148-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-194">Percentuale di durata della chiamata con B frame drop.</span><span class="sxs-lookup"><span data-stu-id="12148-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-197">Percentuale di durata della chiamata con drop frame BP.</span><span class="sxs-lookup"><span data-stu-id="12148-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-200">Percentuale di durata della chiamata con BPSP frame drop.</span><span class="sxs-lookup"><span data-stu-id="12148-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="12148-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="12148-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-203">Percentuale di durata della chiamata con BPSPI frame drop.</span><span class="sxs-lookup"><span data-stu-id="12148-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-204"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="12148-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-205">po'</span><span class="sxs-lookup"><span data-stu-id="12148-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-206">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="12148-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-207"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="12148-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-208">po'</span><span class="sxs-lookup"><span data-stu-id="12148-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-209">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="12148-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="12148-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-211">po'</span><span class="sxs-lookup"><span data-stu-id="12148-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="12148-212">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="12148-213">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="12148-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-215">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-216">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="12148-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="12148-217">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-219">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-220">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="12148-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="12148-221">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-223">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-224">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="12148-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="12148-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="12148-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-227">int</span><span class="sxs-lookup"><span data-stu-id="12148-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-228">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="12148-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-231">int</span><span class="sxs-lookup"><span data-stu-id="12148-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-232">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="12148-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="12148-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-235">int</span><span class="sxs-lookup"><span data-stu-id="12148-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-236">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="12148-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="12148-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-239">int</span><span class="sxs-lookup"><span data-stu-id="12148-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-240">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="12148-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="12148-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-243">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-244">Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.</span><span class="sxs-lookup"><span data-stu-id="12148-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="12148-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="12148-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-247">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p104">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="12148-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-255">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-257">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p106">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-260">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="12148-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-262">int</span><span class="sxs-lookup"><span data-stu-id="12148-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p107">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="12148-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-268">int</span><span class="sxs-lookup"><span data-stu-id="12148-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p108">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-272">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="12148-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-274">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p109">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="12148-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-280">int</span><span class="sxs-lookup"><span data-stu-id="12148-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p110">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-284">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="12148-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p111">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-290">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="12148-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-292">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-p112">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="12148-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="12148-296">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="12148-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-298">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="12148-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-299">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="12148-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="12148-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="12148-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-302">int</span><span class="sxs-lookup"><span data-stu-id="12148-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-303">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="12148-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="12148-304">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="12148-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-306">smallint</span><span class="sxs-lookup"><span data-stu-id="12148-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="12148-307">Stranieri</span><span class="sxs-lookup"><span data-stu-id="12148-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12148-308">Tipo di codec video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="12148-309">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="12148-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="12148-310">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="12148-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-312">int</span><span class="sxs-lookup"><span data-stu-id="12148-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-313">Larghezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="12148-314">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="12148-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-316">int</span><span class="sxs-lookup"><span data-stu-id="12148-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-317">Altezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="12148-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="12148-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-320">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-321">Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="12148-322">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="12148-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-324">int</span><span class="sxs-lookup"><span data-stu-id="12148-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-325">Velocità in bit massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="12148-326">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="12148-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-328">int</span><span class="sxs-lookup"><span data-stu-id="12148-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-329">Velocità in bit media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-331">int</span><span class="sxs-lookup"><span data-stu-id="12148-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-332">Numero massimo di flussi video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="12148-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="12148-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="12148-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-335">smallint</span><span class="sxs-lookup"><span data-stu-id="12148-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="12148-336">Stranieri</span><span class="sxs-lookup"><span data-stu-id="12148-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="12148-337">Codici video utilizzati dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-337">Video codes used by the receiver.</span></span> <span data-ttu-id="12148-338">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="12148-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="12148-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="12148-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-341">int</span><span class="sxs-lookup"><span data-stu-id="12148-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-342">Larghezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="12148-343">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="12148-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-345">int</span><span class="sxs-lookup"><span data-stu-id="12148-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-346">Altezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="12148-347">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="12148-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-349">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-350">Frequenza media dei fotogrammi video utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="12148-351">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="12148-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-353">int</span><span class="sxs-lookup"><span data-stu-id="12148-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-354">Velocità in bit massima per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="12148-355">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="12148-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-357">int</span><span class="sxs-lookup"><span data-stu-id="12148-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-358">Velocità in bit media per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="12148-359">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="12148-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-361">int</span><span class="sxs-lookup"><span data-stu-id="12148-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-362">Massimi flussi video per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="12148-363">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="12148-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-365">int</span><span class="sxs-lookup"><span data-stu-id="12148-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-366">Flussi video minimi per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="12148-367">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="12148-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-369">int</span><span class="sxs-lookup"><span data-stu-id="12148-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-370">Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="12148-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="12148-371">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="12148-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-373">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-374">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="12148-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="12148-375">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-377">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-378">Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</span><span class="sxs-lookup"><span data-stu-id="12148-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="12148-379">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="12148-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="12148-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-382">Risoluzione minima misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="12148-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="12148-383">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-385">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-386">Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="12148-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="12148-387">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-389">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-390">Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</span><span class="sxs-lookup"><span data-stu-id="12148-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="12148-391">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="12148-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-394">Percentuale della chiamata che si è verificata alla risoluzione più bassa.</span><span class="sxs-lookup"><span data-stu-id="12148-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="12148-395">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="12148-396">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12148-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="12148-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-398">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12148-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-399">Durata della chiamata in secondi.</span><span class="sxs-lookup"><span data-stu-id="12148-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="12148-400">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12148-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="12148-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="12148-402">po'</span><span class="sxs-lookup"><span data-stu-id="12148-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12148-403">Indica se i dati sono stati aggregati da più chiamate.</span><span class="sxs-lookup"><span data-stu-id="12148-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="12148-404">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12148-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

