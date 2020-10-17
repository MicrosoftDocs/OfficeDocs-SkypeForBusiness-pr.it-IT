---
title: 'Lync Server 2013: tabella AudioStream'
description: 'Lync Server 2013: tabella AudioStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552342"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="aba80-103">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aba80-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aba80-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aba80-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aba80-105">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-105">Each record represents one audio stream.</span></span> <span data-ttu-id="aba80-106">Una linea multimediale audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aba80-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="aba80-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="aba80-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="aba80-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aba80-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-112">datetime</span><span class="sxs-lookup"><span data-stu-id="aba80-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="aba80-113">Principale</span><span class="sxs-lookup"><span data-stu-id="aba80-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="aba80-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aba80-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-116">int</span><span class="sxs-lookup"><span data-stu-id="aba80-116">int</span></span></p></td>
<td><p><span data-ttu-id="aba80-117">Principale</span><span class="sxs-lookup"><span data-stu-id="aba80-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="aba80-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aba80-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="aba80-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aba80-121">Principale</span><span class="sxs-lookup"><span data-stu-id="aba80-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="aba80-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aba80-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-124">int</span><span class="sxs-lookup"><span data-stu-id="aba80-124">int</span></span></p></td>
<td><p><span data-ttu-id="aba80-125">Principale</span><span class="sxs-lookup"><span data-stu-id="aba80-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="aba80-126">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="aba80-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-128">int</span><span class="sxs-lookup"><span data-stu-id="aba80-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-129">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="aba80-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-131">int</span><span class="sxs-lookup"><span data-stu-id="aba80-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-132">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-134">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="aba80-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-135">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-137">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="aba80-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-138">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-139"><strong>DensitàBurst</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-140">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="aba80-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-141">Densità media della perdita di pacchetti durante i burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-143">int</span><span class="sxs-lookup"><span data-stu-id="aba80-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-144">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-146">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="aba80-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-147">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="aba80-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-149">int</span><span class="sxs-lookup"><span data-stu-id="aba80-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-150">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="aba80-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-152">Soglia</span><span class="sxs-lookup"><span data-stu-id="aba80-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-153">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-154"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-155">Soglia</span><span class="sxs-lookup"><span data-stu-id="aba80-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-156">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-158">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-p102">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="aba80-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-164">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-165">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-167">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-168">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="aba80-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-170">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-171">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="aba80-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-173">int</span><span class="sxs-lookup"><span data-stu-id="aba80-173">int</span></span></p></td>
<td><p><span data-ttu-id="aba80-174">Stranieri</span><span class="sxs-lookup"><span data-stu-id="aba80-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aba80-175">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="aba80-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-177">int</span><span class="sxs-lookup"><span data-stu-id="aba80-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-178">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-179"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-180">int</span><span class="sxs-lookup"><span data-stu-id="aba80-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-181">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="aba80-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="aba80-182">Per una qualità accettabile questo valore deve essere inferiore a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="aba80-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-184">int</span><span class="sxs-lookup"><span data-stu-id="aba80-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-185">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="aba80-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-187">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-188">MOS di rete a banda larga medio per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="aba80-189">Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato.</span><span class="sxs-lookup"><span data-stu-id="aba80-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="aba80-190">L'intervallo è compreso tra [1,0 e 5,0].</span><span class="sxs-lookup"><span data-stu-id="aba80-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-192">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-193">Il MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-194"><strong>Valore SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-195">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-196">La media del Punteggio MOS a banda larga stimato per l'audio inviato, inclusi il livello parlato, il livello di rumore e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="aba80-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-198">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-199">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-201">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-202">La media del Punteggio MOS a banda larga stimato per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="aba80-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-204">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-205">RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-207">po'</span><span class="sxs-lookup"><span data-stu-id="aba80-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-208">Contrassegno che indica se per la chiamata è stato utilizzato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="aba80-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-210">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-211">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="aba80-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-213">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-214">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="aba80-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-216">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aba80-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-217">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="aba80-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-218"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-219">po'</span><span class="sxs-lookup"><span data-stu-id="aba80-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-220">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="aba80-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-221"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-222">po'</span><span class="sxs-lookup"><span data-stu-id="aba80-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-223">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="aba80-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-225">po'</span><span class="sxs-lookup"><span data-stu-id="aba80-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aba80-226">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="aba80-227">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="aba80-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-229">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-230">Deviazione standard per i tempi di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="aba80-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="aba80-231">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-233">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-234">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="aba80-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="aba80-235">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-237">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-238">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="aba80-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="aba80-239">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-241">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-242">Rapporto dei pacchetti rilasciati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="aba80-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="aba80-243">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-245">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-246">Rapporto dei pacchetti di correzione degli errori di inoltro utilizzati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="aba80-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="aba80-247">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-249">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-250">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="aba80-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="aba80-251">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-253">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-254">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="aba80-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="aba80-255">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-257">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-258">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="aba80-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="aba80-259">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-261">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-262">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="aba80-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="aba80-263">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-265">int</span><span class="sxs-lookup"><span data-stu-id="aba80-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-266">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="aba80-267">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-269">int</span><span class="sxs-lookup"><span data-stu-id="aba80-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-270">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="aba80-271">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-273">int</span><span class="sxs-lookup"><span data-stu-id="aba80-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-274">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="aba80-275">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-277">int</span><span class="sxs-lookup"><span data-stu-id="aba80-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-278">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aba80-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="aba80-279">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-281">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-284">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p106">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-289">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-291">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p107">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-294">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-296">int</span><span class="sxs-lookup"><span data-stu-id="aba80-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p108">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-300">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-302">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p109">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-306">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-308">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p110">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-312">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-314">int</span><span class="sxs-lookup"><span data-stu-id="aba80-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p111">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-318">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-320">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p112">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-324">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-326">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-p113">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="aba80-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="aba80-330">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-332">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-333">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="aba80-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="aba80-334">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-336">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-337">Percentuale della chiamata di cui è stato eseguito il rendering come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="aba80-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="aba80-338">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-340">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-341">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="aba80-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="aba80-342">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aba80-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-344">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-345">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="aba80-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="aba80-346">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aba80-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="aba80-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="aba80-348">galleggiante</span><span class="sxs-lookup"><span data-stu-id="aba80-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aba80-349">Percentuale della chiamata acquisita come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="aba80-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="aba80-350">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aba80-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

