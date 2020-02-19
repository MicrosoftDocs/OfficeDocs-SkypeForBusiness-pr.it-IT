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
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="80c49-102">Tabella VideoStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80c49-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80c49-103">_**Ultimo argomento modificato:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="80c49-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="80c49-104">Ogni record rappresenta un flusso video.</span><span class="sxs-lookup"><span data-stu-id="80c49-104">Each record represents one video stream.</span></span> <span data-ttu-id="80c49-105">Una linea video multimediale in genere contiene due flussi video.</span><span class="sxs-lookup"><span data-stu-id="80c49-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80c49-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="80c49-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="80c49-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="80c49-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80c49-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-111">datetime</span><span class="sxs-lookup"><span data-stu-id="80c49-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="80c49-112">Principale</span><span class="sxs-lookup"><span data-stu-id="80c49-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="80c49-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80c49-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-115">int</span><span class="sxs-lookup"><span data-stu-id="80c49-115">int</span></span></p></td>
<td><p><span data-ttu-id="80c49-116">Principale</span><span class="sxs-lookup"><span data-stu-id="80c49-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="80c49-117">R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80c49-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="80c49-120">Principale</span><span class="sxs-lookup"><span data-stu-id="80c49-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="80c49-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="80c49-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-123">int</span><span class="sxs-lookup"><span data-stu-id="80c49-123">int</span></span></p></td>
<td><p><span data-ttu-id="80c49-124">Principale</span><span class="sxs-lookup"><span data-stu-id="80c49-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="80c49-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="80c49-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-127">smallint</span><span class="sxs-lookup"><span data-stu-id="80c49-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="80c49-128">Estero, primario</span><span class="sxs-lookup"><span data-stu-id="80c49-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="80c49-129">Descrizione payload.</span><span class="sxs-lookup"><span data-stu-id="80c49-129">Payload description.</span></span> <span data-ttu-id="80c49-130">Per ulteriori informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="80c49-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-132">int</span><span class="sxs-lookup"><span data-stu-id="80c49-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-133">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="80c49-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-135">int</span><span class="sxs-lookup"><span data-stu-id="80c49-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-136">Instabilità massima della rete durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="80c49-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-138">int</span><span class="sxs-lookup"><span data-stu-id="80c49-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-139">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="80c49-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-141">int</span><span class="sxs-lookup"><span data-stu-id="80c49-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-142">Tempo massimo di andata e ritorno per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="80c49-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-144">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-145">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-147">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-148">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-150">int</span><span class="sxs-lookup"><span data-stu-id="80c49-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-151">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="80c49-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-152"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-153">int</span><span class="sxs-lookup"><span data-stu-id="80c49-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-154">Stime della larghezza di banda per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="80c49-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="80c49-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-p103">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="80c49-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-160">int</span><span class="sxs-lookup"><span data-stu-id="80c49-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-161">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="80c49-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-163">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-164">La frequenza fotogrammi video ricevuta.</span><span class="sxs-lookup"><span data-stu-id="80c49-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-166">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-167">Frequenza fotogrammi video inviata.</span><span class="sxs-lookup"><span data-stu-id="80c49-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-169">int</span><span class="sxs-lookup"><span data-stu-id="80c49-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-170">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="80c49-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-172">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-173">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="80c49-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-175">po'</span><span class="sxs-lookup"><span data-stu-id="80c49-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-176">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="80c49-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-178">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-179">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="80c49-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-182">La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="80c49-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-185">La percentuale della chiamata che si trovava sulla risoluzione VGA.</span><span class="sxs-lookup"><span data-stu-id="80c49-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-188">La percentuale della chiamata che si trovava alla risoluzione di HD720.</span><span class="sxs-lookup"><span data-stu-id="80c49-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-191">Percentuale di durata della chiamata senza frame drop.</span><span class="sxs-lookup"><span data-stu-id="80c49-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-194">Percentuale di durata della chiamata con B frame drop.</span><span class="sxs-lookup"><span data-stu-id="80c49-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-197">Percentuale di durata della chiamata con drop frame BP.</span><span class="sxs-lookup"><span data-stu-id="80c49-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-200">Percentuale di durata della chiamata con BPSP frame drop.</span><span class="sxs-lookup"><span data-stu-id="80c49-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="80c49-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-203">Percentuale di durata della chiamata con BPSPI frame drop.</span><span class="sxs-lookup"><span data-stu-id="80c49-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-204"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-205">po'</span><span class="sxs-lookup"><span data-stu-id="80c49-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-206">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="80c49-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-207"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-208">po'</span><span class="sxs-lookup"><span data-stu-id="80c49-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-209">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="80c49-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-211">po'</span><span class="sxs-lookup"><span data-stu-id="80c49-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="80c49-212">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="80c49-213">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="80c49-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-215">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-216">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="80c49-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="80c49-217">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-219">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-220">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="80c49-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="80c49-221">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-223">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-224">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="80c49-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="80c49-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-227">int</span><span class="sxs-lookup"><span data-stu-id="80c49-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-228">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="80c49-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-231">int</span><span class="sxs-lookup"><span data-stu-id="80c49-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-232">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="80c49-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-235">int</span><span class="sxs-lookup"><span data-stu-id="80c49-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-236">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="80c49-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-239">int</span><span class="sxs-lookup"><span data-stu-id="80c49-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-240">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="80c49-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-243">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-244">Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.</span><span class="sxs-lookup"><span data-stu-id="80c49-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="80c49-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-247">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p104">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-255">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-257">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p106">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-260">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-262">int</span><span class="sxs-lookup"><span data-stu-id="80c49-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p107">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-268">int</span><span class="sxs-lookup"><span data-stu-id="80c49-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p108">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-272">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-274">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p109">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-280">int</span><span class="sxs-lookup"><span data-stu-id="80c49-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p110">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-284">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p111">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-290">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-292">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-p112">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="80c49-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="80c49-296">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-298">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="80c49-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-299">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="80c49-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="80c49-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-302">int</span><span class="sxs-lookup"><span data-stu-id="80c49-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-303">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="80c49-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="80c49-304">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-306">smallint</span><span class="sxs-lookup"><span data-stu-id="80c49-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="80c49-307">Stranieri</span><span class="sxs-lookup"><span data-stu-id="80c49-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="80c49-308">Tipo di codec video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="80c49-309">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="80c49-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="80c49-310">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-312">int</span><span class="sxs-lookup"><span data-stu-id="80c49-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-313">Larghezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="80c49-314">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-316">int</span><span class="sxs-lookup"><span data-stu-id="80c49-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-317">Altezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="80c49-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-320">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-321">Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="80c49-322">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-324">int</span><span class="sxs-lookup"><span data-stu-id="80c49-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-325">Velocità in bit massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="80c49-326">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-328">int</span><span class="sxs-lookup"><span data-stu-id="80c49-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-329">Velocità in bit media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-331">int</span><span class="sxs-lookup"><span data-stu-id="80c49-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-332">Numero massimo di flussi video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="80c49-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="80c49-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-335">smallint</span><span class="sxs-lookup"><span data-stu-id="80c49-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="80c49-336">Stranieri</span><span class="sxs-lookup"><span data-stu-id="80c49-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="80c49-337">Codici video utilizzati dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-337">Video codes used by the receiver.</span></span> <span data-ttu-id="80c49-338">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="80c49-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="80c49-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-341">int</span><span class="sxs-lookup"><span data-stu-id="80c49-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-342">Larghezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="80c49-343">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-345">int</span><span class="sxs-lookup"><span data-stu-id="80c49-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-346">Altezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="80c49-347">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-349">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-350">Frequenza media dei fotogrammi video utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="80c49-351">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-353">int</span><span class="sxs-lookup"><span data-stu-id="80c49-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-354">Velocità in bit massima per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="80c49-355">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-357">int</span><span class="sxs-lookup"><span data-stu-id="80c49-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-358">Velocità in bit media per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="80c49-359">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-361">int</span><span class="sxs-lookup"><span data-stu-id="80c49-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-362">Massimi flussi video per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="80c49-363">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-365">int</span><span class="sxs-lookup"><span data-stu-id="80c49-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-366">Flussi video minimi per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="80c49-367">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-369">int</span><span class="sxs-lookup"><span data-stu-id="80c49-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-370">Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="80c49-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="80c49-371">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-373">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-374">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="80c49-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="80c49-375">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-377">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-378">Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</span><span class="sxs-lookup"><span data-stu-id="80c49-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="80c49-379">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="80c49-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-382">Risoluzione minima misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="80c49-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="80c49-383">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-385">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-386">Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="80c49-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="80c49-387">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-389">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-390">Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</span><span class="sxs-lookup"><span data-stu-id="80c49-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="80c49-391">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-394">Percentuale della chiamata che si è verificata alla risoluzione più bassa.</span><span class="sxs-lookup"><span data-stu-id="80c49-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="80c49-395">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="80c49-396">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80c49-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-398">galleggiante</span><span class="sxs-lookup"><span data-stu-id="80c49-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-399">Durata della chiamata in secondi.</span><span class="sxs-lookup"><span data-stu-id="80c49-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="80c49-400">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80c49-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="80c49-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="80c49-402">po'</span><span class="sxs-lookup"><span data-stu-id="80c49-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80c49-403">Indica se i dati sono stati aggregati da più chiamate.</span><span class="sxs-lookup"><span data-stu-id="80c49-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="80c49-404">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80c49-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

