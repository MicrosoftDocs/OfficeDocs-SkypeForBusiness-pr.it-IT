---
title: 'Lync Server 2013: tabella VideoStream'
description: 'Lync Server 2013: tabella VideoStream.'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567992"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="bf950-103">Tabella VideoStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf950-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf950-104">_**Ultimo argomento modificato:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="bf950-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="bf950-105">Ogni record rappresenta un flusso video.</span><span class="sxs-lookup"><span data-stu-id="bf950-105">Each record represents one video stream.</span></span> <span data-ttu-id="bf950-106">Una linea video multimediale in genere contiene due flussi video.</span><span class="sxs-lookup"><span data-stu-id="bf950-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf950-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bf950-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bf950-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bf950-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf950-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bf950-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="bf950-113">Principale</span><span class="sxs-lookup"><span data-stu-id="bf950-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="bf950-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bf950-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-116">int</span><span class="sxs-lookup"><span data-stu-id="bf950-116">int</span></span></p></td>
<td><p><span data-ttu-id="bf950-117">Principale</span><span class="sxs-lookup"><span data-stu-id="bf950-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="bf950-118">R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bf950-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bf950-121">Principale</span><span class="sxs-lookup"><span data-stu-id="bf950-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="bf950-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="bf950-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-124">int</span><span class="sxs-lookup"><span data-stu-id="bf950-124">int</span></span></p></td>
<td><p><span data-ttu-id="bf950-125">Principale</span><span class="sxs-lookup"><span data-stu-id="bf950-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="bf950-126">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="bf950-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-128">smallint</span><span class="sxs-lookup"><span data-stu-id="bf950-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="bf950-129">Estero, primario</span><span class="sxs-lookup"><span data-stu-id="bf950-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="bf950-130">Descrizione payload.</span><span class="sxs-lookup"><span data-stu-id="bf950-130">Payload description.</span></span> <span data-ttu-id="bf950-131">Per ulteriori informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf950-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-133">int</span><span class="sxs-lookup"><span data-stu-id="bf950-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-134">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="bf950-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-136">int</span><span class="sxs-lookup"><span data-stu-id="bf950-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-137">Instabilità massima della rete durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="bf950-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-138"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-139">int</span><span class="sxs-lookup"><span data-stu-id="bf950-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-140">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="bf950-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-142">int</span><span class="sxs-lookup"><span data-stu-id="bf950-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-143">Tempo massimo di andata e ritorno per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="bf950-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-145">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-146">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-148">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-149">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-151">int</span><span class="sxs-lookup"><span data-stu-id="bf950-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-152">Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</span><span class="sxs-lookup"><span data-stu-id="bf950-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-153"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-154">int</span><span class="sxs-lookup"><span data-stu-id="bf950-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-155">Stime della larghezza di banda per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="bf950-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-157">char (9)</span><span class="sxs-lookup"><span data-stu-id="bf950-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-p103">Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</span><span class="sxs-lookup"><span data-stu-id="bf950-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-161">int</span><span class="sxs-lookup"><span data-stu-id="bf950-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-162">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="bf950-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-164">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-165">La frequenza fotogrammi video ricevuta.</span><span class="sxs-lookup"><span data-stu-id="bf950-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-167">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-168">Frequenza fotogrammi video inviata.</span><span class="sxs-lookup"><span data-stu-id="bf950-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-170">int</span><span class="sxs-lookup"><span data-stu-id="bf950-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-171">Velocità in bit video massima durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="bf950-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-173">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-174">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="bf950-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-176">po'</span><span class="sxs-lookup"><span data-stu-id="bf950-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-177">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="bf950-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-179">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-180">La percentuale di frame video totali persi.</span><span class="sxs-lookup"><span data-stu-id="bf950-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-183">La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="bf950-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-186">La percentuale della chiamata che si trovava sulla risoluzione VGA.</span><span class="sxs-lookup"><span data-stu-id="bf950-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-189">La percentuale della chiamata che si trovava alla risoluzione di HD720.</span><span class="sxs-lookup"><span data-stu-id="bf950-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-192">Percentuale di durata della chiamata senza frame drop.</span><span class="sxs-lookup"><span data-stu-id="bf950-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-195">Percentuale di durata della chiamata con B frame drop.</span><span class="sxs-lookup"><span data-stu-id="bf950-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-198">Percentuale di durata della chiamata con drop frame BP.</span><span class="sxs-lookup"><span data-stu-id="bf950-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-201">Percentuale di durata della chiamata con BPSP frame drop.</span><span class="sxs-lookup"><span data-stu-id="bf950-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="bf950-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-204">Percentuale di durata della chiamata con BPSPI frame drop.</span><span class="sxs-lookup"><span data-stu-id="bf950-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-205"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-206">po'</span><span class="sxs-lookup"><span data-stu-id="bf950-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-207">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="bf950-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-208"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-209">po'</span><span class="sxs-lookup"><span data-stu-id="bf950-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-210">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="bf950-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-212">po'</span><span class="sxs-lookup"><span data-stu-id="bf950-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bf950-213">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="bf950-214">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="bf950-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-216">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-217">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="bf950-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="bf950-218">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-220">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-221">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="bf950-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="bf950-222">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-224">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-225">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="bf950-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="bf950-226">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-228">int</span><span class="sxs-lookup"><span data-stu-id="bf950-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-229">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="bf950-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-232">int</span><span class="sxs-lookup"><span data-stu-id="bf950-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-233">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="bf950-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-236">int</span><span class="sxs-lookup"><span data-stu-id="bf950-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-237">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="bf950-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-240">int</span><span class="sxs-lookup"><span data-stu-id="bf950-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-241">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="bf950-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-245">Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.</span><span class="sxs-lookup"><span data-stu-id="bf950-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="bf950-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p104">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-251">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-253">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-256">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-258">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p106">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-261">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-263">int</span><span class="sxs-lookup"><span data-stu-id="bf950-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p107">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-267">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-269">int</span><span class="sxs-lookup"><span data-stu-id="bf950-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p108">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-273">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-275">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p109">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-279">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-281">int</span><span class="sxs-lookup"><span data-stu-id="bf950-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p110">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-285">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-287">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p111">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-291">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-293">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-p112">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="bf950-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="bf950-297">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-299">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bf950-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-300">Frequenza di perdita dei pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="bf950-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="bf950-301">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-303">int</span><span class="sxs-lookup"><span data-stu-id="bf950-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-304">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="bf950-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="bf950-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-307">smallint</span><span class="sxs-lookup"><span data-stu-id="bf950-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="bf950-308">Stranieri</span><span class="sxs-lookup"><span data-stu-id="bf950-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf950-309">Tipo di codec video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="bf950-310">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf950-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="bf950-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-313">int</span><span class="sxs-lookup"><span data-stu-id="bf950-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-314">Larghezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="bf950-315">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-317">int</span><span class="sxs-lookup"><span data-stu-id="bf950-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-318">Altezza della risoluzione utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="bf950-319">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-321">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-322">Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="bf950-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-325">int</span><span class="sxs-lookup"><span data-stu-id="bf950-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-326">Velocità in bit massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="bf950-327">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-329">int</span><span class="sxs-lookup"><span data-stu-id="bf950-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-330">Velocità in bit media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-332">int</span><span class="sxs-lookup"><span data-stu-id="bf950-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-333">Numero massimo di flussi video utilizzati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bf950-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="bf950-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-336">smallint</span><span class="sxs-lookup"><span data-stu-id="bf950-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="bf950-337">Stranieri</span><span class="sxs-lookup"><span data-stu-id="bf950-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bf950-338">Codici video utilizzati dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-338">Video codes used by the receiver.</span></span> <span data-ttu-id="bf950-339">Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="bf950-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="bf950-340">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-342">int</span><span class="sxs-lookup"><span data-stu-id="bf950-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-343">Larghezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="bf950-344">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-346">int</span><span class="sxs-lookup"><span data-stu-id="bf950-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-347">Altezza della risoluzione utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="bf950-348">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-350">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-351">Frequenza media dei fotogrammi video utilizzata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="bf950-352">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-354">int</span><span class="sxs-lookup"><span data-stu-id="bf950-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-355">Velocità in bit massima per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="bf950-356">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-358">int</span><span class="sxs-lookup"><span data-stu-id="bf950-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-359">Velocità in bit media per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="bf950-360">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-362">int</span><span class="sxs-lookup"><span data-stu-id="bf950-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-363">Massimi flussi video per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="bf950-364">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-366">int</span><span class="sxs-lookup"><span data-stu-id="bf950-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-367">Flussi video minimi per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="bf950-368">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-370">int</span><span class="sxs-lookup"><span data-stu-id="bf950-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-371">Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="bf950-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="bf950-372">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-374">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-375">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="bf950-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="bf950-376">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-378">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-379">Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</span><span class="sxs-lookup"><span data-stu-id="bf950-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="bf950-380">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-382">char (9)</span><span class="sxs-lookup"><span data-stu-id="bf950-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-383">Risoluzione minima misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bf950-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="bf950-384">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-386">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-387">Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="bf950-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="bf950-388">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-390">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-391">Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</span><span class="sxs-lookup"><span data-stu-id="bf950-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="bf950-392">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-394">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-395">Percentuale della chiamata che si è verificata alla risoluzione più bassa.</span><span class="sxs-lookup"><span data-stu-id="bf950-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="bf950-396">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="bf950-397">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf950-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-399">galleggiante</span><span class="sxs-lookup"><span data-stu-id="bf950-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-400">Durata della chiamata in secondi.</span><span class="sxs-lookup"><span data-stu-id="bf950-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="bf950-401">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf950-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="bf950-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="bf950-403">po'</span><span class="sxs-lookup"><span data-stu-id="bf950-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bf950-404">Indica se i dati sono stati aggregati da più chiamate.</span><span class="sxs-lookup"><span data-stu-id="bf950-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="bf950-405">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf950-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

