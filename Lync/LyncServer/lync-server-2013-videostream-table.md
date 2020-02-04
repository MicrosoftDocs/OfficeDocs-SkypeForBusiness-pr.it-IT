---
title: 'Lync Server 2013: Tabella VideoStream'
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
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="b6835-102">Tabella VideoStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6835-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6835-103">_**Argomento Ultima modifica:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="b6835-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="b6835-104">Ogni record rappresenta un flusso video.</span><span class="sxs-lookup"><span data-stu-id="b6835-104">Each record represents one video stream.</span></span> <span data-ttu-id="b6835-105">Una linea media video in genere contiene due flussi video.</span><span class="sxs-lookup"><span data-stu-id="b6835-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6835-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b6835-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b6835-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b6835-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6835-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="b6835-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b6835-112">Principale</span><span class="sxs-lookup"><span data-stu-id="b6835-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6835-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6835-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-115">int</span><span class="sxs-lookup"><span data-stu-id="b6835-115">int</span></span></p></td>
<td><p><span data-ttu-id="b6835-116">Principale</span><span class="sxs-lookup"><span data-stu-id="b6835-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6835-117">R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6835-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b6835-120">Principale</span><span class="sxs-lookup"><span data-stu-id="b6835-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6835-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6835-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-123">int</span><span class="sxs-lookup"><span data-stu-id="b6835-123">int</span></span></p></td>
<td><p><span data-ttu-id="b6835-124">Principale</span><span class="sxs-lookup"><span data-stu-id="b6835-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6835-125">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="b6835-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-127">smallint</span><span class="sxs-lookup"><span data-stu-id="b6835-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="b6835-128">Estero, primario</span><span class="sxs-lookup"><span data-stu-id="b6835-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="b6835-129">Descrizione payload.</span><span class="sxs-lookup"><span data-stu-id="b6835-129">Payload description.</span></span> <span data-ttu-id="b6835-130">Per altre informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6835-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-132">int</span><span class="sxs-lookup"><span data-stu-id="b6835-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-133">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="b6835-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-135">int</span><span class="sxs-lookup"><span data-stu-id="b6835-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-136">Jitter della rete massimo durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="b6835-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-138">int</span><span class="sxs-lookup"><span data-stu-id="b6835-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-139">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="b6835-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-141">int</span><span class="sxs-lookup"><span data-stu-id="b6835-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-142">Tempo massimo di andata e ritorno per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="b6835-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-144">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-145">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-147">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-148">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-150">int</span><span class="sxs-lookup"><span data-stu-id="b6835-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-151">Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).</span><span class="sxs-lookup"><span data-stu-id="b6835-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-152"><strong>Larghezza di banda più ampia</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-153">int</span><span class="sxs-lookup"><span data-stu-id="b6835-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-154">Stime della larghezza di banda per il flusso video.</span><span class="sxs-lookup"><span data-stu-id="b6835-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-156">codice.caratt(9</span><span class="sxs-lookup"><span data-stu-id="b6835-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-157">Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel.</span><span class="sxs-lookup"><span data-stu-id="b6835-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="b6835-158">Segnalato come stringa.</span><span class="sxs-lookup"><span data-stu-id="b6835-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-160">int</span><span class="sxs-lookup"><span data-stu-id="b6835-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-161">Velocità in bit media del flusso video.</span><span class="sxs-lookup"><span data-stu-id="b6835-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-163">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-164">Frequenza fotogrammi video ricevuta.</span><span class="sxs-lookup"><span data-stu-id="b6835-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-166">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-167">Frequenza fotogrammi video inviata.</span><span class="sxs-lookup"><span data-stu-id="b6835-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-169">int</span><span class="sxs-lookup"><span data-stu-id="b6835-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-170">Velocità in bit massima video durante la sessione video.</span><span class="sxs-lookup"><span data-stu-id="b6835-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-172">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-173">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="b6835-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-175">po'</span><span class="sxs-lookup"><span data-stu-id="b6835-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-176">Non disponibile.</span><span class="sxs-lookup"><span data-stu-id="b6835-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-177"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-178">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-179">Percentuale di fotogrammi video totali persi.</span><span class="sxs-lookup"><span data-stu-id="b6835-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-182">Percentuale della chiamata alla risoluzione CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="b6835-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-185">Percentuale della chiamata con risoluzione VGA.</span><span class="sxs-lookup"><span data-stu-id="b6835-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-188">Percentuale della chiamata alla risoluzione di HD720.</span><span class="sxs-lookup"><span data-stu-id="b6835-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-191">Percentuale della durata della chiamata senza drop frame.</span><span class="sxs-lookup"><span data-stu-id="b6835-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-194">Percentuale della durata della chiamata con la riduzione del fotogramma B.</span><span class="sxs-lookup"><span data-stu-id="b6835-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-197">Percentuale della durata della chiamata con il frame drop di BP.</span><span class="sxs-lookup"><span data-stu-id="b6835-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-200">Percentuale della durata della chiamata con il frame drop di BPSP.</span><span class="sxs-lookup"><span data-stu-id="b6835-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="b6835-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-203">Percentuale della durata della chiamata con il frame drop di BPSPI.</span><span class="sxs-lookup"><span data-stu-id="b6835-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-204"><strong>In ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-205">po'</span><span class="sxs-lookup"><span data-stu-id="b6835-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-206">Il flusso di dati sul lato ricevitore viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="b6835-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-207"><strong>Outbound</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-208">po'</span><span class="sxs-lookup"><span data-stu-id="b6835-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-209">Il flusso di dati sul lato mittente viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="b6835-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-211">po'</span><span class="sxs-lookup"><span data-stu-id="b6835-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6835-212">1 indica che la direzione del flusso è dal chiamante al chiamato.</span><span class="sxs-lookup"><span data-stu-id="b6835-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="b6835-213">0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="b6835-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-215">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-216">Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.</span><span class="sxs-lookup"><span data-stu-id="b6835-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="b6835-217">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-219">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-220">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="b6835-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="b6835-221">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-223">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-224">Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="b6835-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="b6835-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-227">int</span><span class="sxs-lookup"><span data-stu-id="b6835-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-228">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b6835-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-231">int</span><span class="sxs-lookup"><span data-stu-id="b6835-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-232">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b6835-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-235">int</span><span class="sxs-lookup"><span data-stu-id="b6835-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-236">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b6835-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-239">int</span><span class="sxs-lookup"><span data-stu-id="b6835-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-240">Importo medio della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="b6835-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-243">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-244">Percentuale della chiamata in cui l'endpoint ha determinato che la connessione di rete non supporta il video MultiView.</span><span class="sxs-lookup"><span data-stu-id="b6835-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="b6835-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-247">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-248">Importo totale della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-248">Total amount of one-way latency.</span></span> <span data-ttu-id="b6835-249">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-253">Importo medio della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-253">Average amount of one-way latency.</span></span> <span data-ttu-id="b6835-254">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-255">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-257">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-258">Importo massimo della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="b6835-259">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-260">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-262">int</span><span class="sxs-lookup"><span data-stu-id="b6835-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-263">Occorrenze totali di burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="b6835-264">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="b6835-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b6835-265">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-268">int</span><span class="sxs-lookup"><span data-stu-id="b6835-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-269">Densità totale burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-269">Total one-way burst density.</span></span> <span data-ttu-id="b6835-270">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="b6835-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b6835-271">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-272">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-274">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-275">Totale durata burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-275">Total one-way burst duration.</span></span> <span data-ttu-id="b6835-276">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="b6835-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="b6835-277">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-280">int</span><span class="sxs-lookup"><span data-stu-id="b6835-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-281">Occorrenze totali unidirezionali Gap.</span><span class="sxs-lookup"><span data-stu-id="b6835-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="b6835-282">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="b6835-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b6835-283">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-284">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-287">Densità totale gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-287">Total one-way gap density.</span></span> <span data-ttu-id="b6835-288">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="b6835-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b6835-289">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-290">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-292">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-293">Durata totale del gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b6835-293">Total one-way gap duration.</span></span> <span data-ttu-id="b6835-294">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="b6835-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="b6835-295">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="b6835-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="b6835-296">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-297"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-298">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="b6835-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-299">Frequenza con cui sono stati persi i pacchetti video.</span><span class="sxs-lookup"><span data-stu-id="b6835-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="b6835-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-302">int</span><span class="sxs-lookup"><span data-stu-id="b6835-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-303">Quantità media di larghezza di banda allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="b6835-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="b6835-304">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-306">smallint</span><span class="sxs-lookup"><span data-stu-id="b6835-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="b6835-307">Esterna</span><span class="sxs-lookup"><span data-stu-id="b6835-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6835-308">Tipo di codec video usati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="b6835-309">Per altre informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6835-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b6835-310">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-312">int</span><span class="sxs-lookup"><span data-stu-id="b6835-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-313">Larghezza di risoluzione usata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="b6835-314">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-316">int</span><span class="sxs-lookup"><span data-stu-id="b6835-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-317">Altezza di risoluzione usata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="b6835-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-320">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-321">Trasmissione media della frequenza dei fotogrammi video usata dal mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="b6835-322">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-324">int</span><span class="sxs-lookup"><span data-stu-id="b6835-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-325">Velocità in bit massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="b6835-326">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-328">int</span><span class="sxs-lookup"><span data-stu-id="b6835-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-329">Velocità in bit media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-331">int</span><span class="sxs-lookup"><span data-stu-id="b6835-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-332">Numero massimo di flussi video usati dal mittente.</span><span class="sxs-lookup"><span data-stu-id="b6835-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="b6835-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-335">smallint</span><span class="sxs-lookup"><span data-stu-id="b6835-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="b6835-336">Esterna</span><span class="sxs-lookup"><span data-stu-id="b6835-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6835-337">Codici video usati dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-337">Video codes used by the receiver.</span></span> <span data-ttu-id="b6835-338">Per altre informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="b6835-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b6835-339">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-341">int</span><span class="sxs-lookup"><span data-stu-id="b6835-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-342">Larghezza di risoluzione usata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="b6835-343">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-345">int</span><span class="sxs-lookup"><span data-stu-id="b6835-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-346">Altezza di risoluzione usata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="b6835-347">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-348"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-349">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-350">Frequenza fotogrammi video media usata dal destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="b6835-351">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-353">int</span><span class="sxs-lookup"><span data-stu-id="b6835-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-354">Velocità in bit massima per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="b6835-355">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-357">int</span><span class="sxs-lookup"><span data-stu-id="b6835-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-358">Velocità in bit media per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="b6835-359">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-361">int</span><span class="sxs-lookup"><span data-stu-id="b6835-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-362">Flussi video massimo per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="b6835-363">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-365">int</span><span class="sxs-lookup"><span data-stu-id="b6835-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-366">Flussi video minimi per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="b6835-367">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-369">int</span><span class="sxs-lookup"><span data-stu-id="b6835-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-370">Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</span><span class="sxs-lookup"><span data-stu-id="b6835-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="b6835-371">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-372"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-373">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-374">Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.</span><span class="sxs-lookup"><span data-stu-id="b6835-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="b6835-375">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-376"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-377">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-378">Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</span><span class="sxs-lookup"><span data-stu-id="b6835-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="b6835-379">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-381">codice.caratt(9</span><span class="sxs-lookup"><span data-stu-id="b6835-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-382">Risoluzione minima misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6835-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="b6835-383">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-385">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-386">Percentuale della chiamata sotto la soglia di velocità in bit ridotta (70 kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="b6835-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="b6835-387">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-388"><strong>Flussi</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-389">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-390">Percentuale della chiamata sotto la soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</span><span class="sxs-lookup"><span data-stu-id="b6835-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="b6835-391">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-392"><strong>Causa</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-394">Percentuale della chiamata che si è verificata alla risoluzione più bassa.</span><span class="sxs-lookup"><span data-stu-id="b6835-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="b6835-395">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="b6835-396">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6835-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-398">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b6835-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-399">Lunghezza della chiamata in secondi.</span><span class="sxs-lookup"><span data-stu-id="b6835-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="b6835-400">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6835-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="b6835-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="b6835-402">po'</span><span class="sxs-lookup"><span data-stu-id="b6835-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6835-403">Indica se i dati sono stati aggregati da più chiamate.</span><span class="sxs-lookup"><span data-stu-id="b6835-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="b6835-404">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6835-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

