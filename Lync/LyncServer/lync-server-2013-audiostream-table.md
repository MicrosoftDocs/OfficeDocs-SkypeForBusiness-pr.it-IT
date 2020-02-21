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
ms.openlocfilehash: e2da0884915f44246e316f80cb9fd35fb7aecaad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="fe008-102">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe008-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe008-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fe008-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fe008-104">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-104">Each record represents one audio stream.</span></span> <span data-ttu-id="fe008-105">Una linea multimediale audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe008-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fe008-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fe008-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fe008-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe008-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fe008-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fe008-112">Principale</span><span class="sxs-lookup"><span data-stu-id="fe008-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe008-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fe008-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-115">int</span><span class="sxs-lookup"><span data-stu-id="fe008-115">int</span></span></p></td>
<td><p><span data-ttu-id="fe008-116">Principale</span><span class="sxs-lookup"><span data-stu-id="fe008-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe008-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fe008-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fe008-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fe008-120">Principale</span><span class="sxs-lookup"><span data-stu-id="fe008-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe008-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="fe008-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-123">int</span><span class="sxs-lookup"><span data-stu-id="fe008-123">int</span></span></p></td>
<td><p><span data-ttu-id="fe008-124">Principale</span><span class="sxs-lookup"><span data-stu-id="fe008-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe008-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="fe008-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-127">int</span><span class="sxs-lookup"><span data-stu-id="fe008-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-128">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="fe008-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-130">int</span><span class="sxs-lookup"><span data-stu-id="fe008-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-131">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-133">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fe008-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-134">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-136">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="fe008-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-137">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-138"><strong>DensitàBurst</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-139">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fe008-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-140">Densità media della perdita di pacchetti durante i burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-142">int</span><span class="sxs-lookup"><span data-stu-id="fe008-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-143">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-145">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="fe008-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-146">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="fe008-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-148">int</span><span class="sxs-lookup"><span data-stu-id="fe008-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-149">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="fe008-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-151">Soglia</span><span class="sxs-lookup"><span data-stu-id="fe008-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-152">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-153"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="fe008-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-155">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-157">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-p102">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="fe008-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-163">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-164">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-166">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-167">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="fe008-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-169">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-170">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="fe008-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-172">int</span><span class="sxs-lookup"><span data-stu-id="fe008-172">int</span></span></p></td>
<td><p><span data-ttu-id="fe008-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="fe008-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fe008-174">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="fe008-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-176">int</span><span class="sxs-lookup"><span data-stu-id="fe008-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-177">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-179">int</span><span class="sxs-lookup"><span data-stu-id="fe008-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-180">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="fe008-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="fe008-181">Per una qualità accettabile questo valore deve essere inferiore a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="fe008-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-183">int</span><span class="sxs-lookup"><span data-stu-id="fe008-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-184">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="fe008-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-186">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-187">MOS di rete a banda larga medio per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="fe008-188">Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato.</span><span class="sxs-lookup"><span data-stu-id="fe008-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="fe008-189">L'intervallo è compreso tra [1,0 e 5,0].</span><span class="sxs-lookup"><span data-stu-id="fe008-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-191">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-192">Il MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-193"><strong>Valore SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-194">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-195">La media del Punteggio MOS a banda larga stimato per l'audio inviato, inclusi il livello parlato, il livello di rumore e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="fe008-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-197">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-198">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-200">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-201">La media del Punteggio MOS a banda larga stimato per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="fe008-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-203">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-204">RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-206">po'</span><span class="sxs-lookup"><span data-stu-id="fe008-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-207">Contrassegno che indica se per la chiamata è stato utilizzato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="fe008-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-209">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-210">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="fe008-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-212">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-213">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="fe008-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-215">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="fe008-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-216">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="fe008-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-217"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-218">po'</span><span class="sxs-lookup"><span data-stu-id="fe008-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-219">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="fe008-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-220"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-221">po'</span><span class="sxs-lookup"><span data-stu-id="fe008-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-222">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="fe008-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-224">po'</span><span class="sxs-lookup"><span data-stu-id="fe008-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fe008-225">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="fe008-226">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="fe008-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-228">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-229">Deviazione standard per i tempi di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="fe008-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="fe008-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-232">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-233">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="fe008-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fe008-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-236">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-237">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="fe008-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="fe008-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-240">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-241">Rapporto dei pacchetti rilasciati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="fe008-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fe008-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-245">Rapporto dei pacchetti di correzione degli errori di inoltro utilizzati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="fe008-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="fe008-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-249">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="fe008-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="fe008-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-253">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="fe008-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="fe008-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-257">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="fe008-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="fe008-258">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-260">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-261">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="fe008-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="fe008-262">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-264">int</span><span class="sxs-lookup"><span data-stu-id="fe008-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-265">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fe008-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-268">int</span><span class="sxs-lookup"><span data-stu-id="fe008-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-269">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fe008-270">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-272">int</span><span class="sxs-lookup"><span data-stu-id="fe008-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-273">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fe008-274">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-276">int</span><span class="sxs-lookup"><span data-stu-id="fe008-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-277">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fe008-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fe008-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-283">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p106">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-288">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-290">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p107">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-293">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-295">int</span><span class="sxs-lookup"><span data-stu-id="fe008-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p108">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p109">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p110">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-313">int</span><span class="sxs-lookup"><span data-stu-id="fe008-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p111">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-317">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p112">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-325">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-p113">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="fe008-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fe008-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-332">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="fe008-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="fe008-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-335">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-336">Percentuale della chiamata di cui è stato eseguito il rendering come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="fe008-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fe008-337">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-340">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="fe008-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="fe008-341">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe008-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-343">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-344">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="fe008-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="fe008-345">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe008-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fe008-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fe008-347">galleggiante</span><span class="sxs-lookup"><span data-stu-id="fe008-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe008-348">Percentuale della chiamata acquisita come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="fe008-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="fe008-349">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe008-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

