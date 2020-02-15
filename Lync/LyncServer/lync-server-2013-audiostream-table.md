---
title: 'Lync Server 2013: tabella AudioStream'
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
ms.openlocfilehash: 44f41dc95e1c7c39a0c9c2cc4dd0a3a2462083e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="25a1c-102">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25a1c-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25a1c-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="25a1c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="25a1c-104">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-104">Each record represents one audio stream.</span></span> <span data-ttu-id="25a1c-105">Una linea multimediale audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25a1c-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="25a1c-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="25a1c-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="25a1c-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="25a1c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="25a1c-112">Principale</span><span class="sxs-lookup"><span data-stu-id="25a1c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="25a1c-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="25a1c-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-115">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-115">int</span></span></p></td>
<td><p><span data-ttu-id="25a1c-116">Principale</span><span class="sxs-lookup"><span data-stu-id="25a1c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="25a1c-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="25a1c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="25a1c-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="25a1c-120">Principale</span><span class="sxs-lookup"><span data-stu-id="25a1c-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="25a1c-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="25a1c-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-123">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-123">int</span></span></p></td>
<td><p><span data-ttu-id="25a1c-124">Principale</span><span class="sxs-lookup"><span data-stu-id="25a1c-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="25a1c-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="25a1c-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-127">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-128">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="25a1c-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-130">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-131">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-133">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="25a1c-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-134">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-136">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="25a1c-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-137">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-138"><strong>DensitàBurst</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-139">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="25a1c-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-140">Densità media della perdita di pacchetti durante i burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-142">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-143">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-145">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="25a1c-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-146">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-148">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-149">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-151">Soglia</span><span class="sxs-lookup"><span data-stu-id="25a1c-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-152">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-153"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="25a1c-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-155">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-157">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-p102">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-163">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-164">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-166">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-167">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="25a1c-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-169">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-170">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-172">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-172">int</span></span></p></td>
<td><p><span data-ttu-id="25a1c-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="25a1c-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="25a1c-174">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="25a1c-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-176">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-177">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-179">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-180">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="25a1c-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="25a1c-181">Per una qualità accettabile questo valore deve essere inferiore a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="25a1c-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-183">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-184">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="25a1c-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-186">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-187">MOS di rete a banda larga medio per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="25a1c-188">Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato.</span><span class="sxs-lookup"><span data-stu-id="25a1c-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="25a1c-189">L'intervallo è compreso tra [1,0 e 5,0].</span><span class="sxs-lookup"><span data-stu-id="25a1c-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-191">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-192">Il MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-193"><strong>Valore SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-194">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-195">La media del Punteggio MOS a banda larga stimato per l'audio inviato, inclusi il livello parlato, il livello di rumore e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="25a1c-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-197">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-198">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-200">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-201">La media del Punteggio MOS a banda larga stimato per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="25a1c-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-203">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-204">RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-206">po'</span><span class="sxs-lookup"><span data-stu-id="25a1c-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-207">Contrassegno che indica se per la chiamata è stato utilizzato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="25a1c-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-209">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-210">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="25a1c-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-212">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-213">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="25a1c-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-215">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="25a1c-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-216">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="25a1c-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-217"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-218">po'</span><span class="sxs-lookup"><span data-stu-id="25a1c-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-219">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-220"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-221">po'</span><span class="sxs-lookup"><span data-stu-id="25a1c-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-222">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-224">po'</span><span class="sxs-lookup"><span data-stu-id="25a1c-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="25a1c-225">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="25a1c-226">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="25a1c-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-228">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-229">Deviazione standard per i tempi di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="25a1c-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="25a1c-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-232">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-233">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="25a1c-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="25a1c-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-236">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-237">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="25a1c-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="25a1c-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-240">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-241">Rapporto dei pacchetti rilasciati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="25a1c-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-245">Rapporto dei pacchetti di correzione degli errori di inoltro utilizzati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="25a1c-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="25a1c-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-249">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="25a1c-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="25a1c-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-253">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="25a1c-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="25a1c-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-257">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="25a1c-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="25a1c-258">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-260">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-261">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="25a1c-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="25a1c-262">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-264">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-265">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="25a1c-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-268">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-269">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="25a1c-270">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-272">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-273">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="25a1c-274">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-276">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-277">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25a1c-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="25a1c-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-283">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p106">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-288">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-290">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p107">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-293">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-295">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p108">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p109">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p110">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-313">int</span><span class="sxs-lookup"><span data-stu-id="25a1c-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p111">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-317">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p112">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-325">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-p113">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25a1c-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="25a1c-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-332">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="25a1c-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="25a1c-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-335">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-336">Percentuale della chiamata di cui è stato eseguito il rendering come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="25a1c-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="25a1c-337">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-340">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="25a1c-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="25a1c-341">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25a1c-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-343">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-344">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="25a1c-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="25a1c-345">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25a1c-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="25a1c-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="25a1c-347">galleggiante</span><span class="sxs-lookup"><span data-stu-id="25a1c-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="25a1c-348">Percentuale della chiamata acquisita come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="25a1c-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="25a1c-349">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25a1c-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

