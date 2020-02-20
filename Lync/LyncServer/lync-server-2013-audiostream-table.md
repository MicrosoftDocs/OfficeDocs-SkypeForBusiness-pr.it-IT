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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="5f340-102">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f340-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f340-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5f340-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5f340-104">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-104">Each record represents one audio stream.</span></span> <span data-ttu-id="5f340-105">Una linea multimediale audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f340-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5f340-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5f340-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5f340-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f340-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5f340-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f340-112">Principale</span><span class="sxs-lookup"><span data-stu-id="5f340-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f340-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5f340-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-115">int</span><span class="sxs-lookup"><span data-stu-id="5f340-115">int</span></span></p></td>
<td><p><span data-ttu-id="5f340-116">Principale</span><span class="sxs-lookup"><span data-stu-id="5f340-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f340-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5f340-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5f340-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5f340-120">Principale</span><span class="sxs-lookup"><span data-stu-id="5f340-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f340-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5f340-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-123">int</span><span class="sxs-lookup"><span data-stu-id="5f340-123">int</span></span></p></td>
<td><p><span data-ttu-id="5f340-124">Principale</span><span class="sxs-lookup"><span data-stu-id="5f340-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5f340-125">ID univoco in una linea multimediale.</span><span class="sxs-lookup"><span data-stu-id="5f340-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-127">int</span><span class="sxs-lookup"><span data-stu-id="5f340-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-128">Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="5f340-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-130">int</span><span class="sxs-lookup"><span data-stu-id="5f340-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-131">Instabilità di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-133">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5f340-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-134">Frequenza media di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-136">decimale (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5f340-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-137">Perdita di pacchetti massima rilevata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-138"><strong>DensitàBurst</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-139">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5f340-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-140">Densità media della perdita di pacchetti durante i burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-142">int</span><span class="sxs-lookup"><span data-stu-id="5f340-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-143">Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-145">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5f340-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-146">Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5f340-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-148">int</span><span class="sxs-lookup"><span data-stu-id="5f340-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-149">Durata media delle pause tra burst della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5f340-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-151">Soglia</span><span class="sxs-lookup"><span data-stu-id="5f340-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-152">Numero di pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-153"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="5f340-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-155">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-157">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-p102">Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</span><span class="sxs-lookup"><span data-stu-id="5f340-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-163">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-164">Degradazione MOS di rete massima durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-166">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-167">Degradazione MOS di rete causata dall'instabilità.</span><span class="sxs-lookup"><span data-stu-id="5f340-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-169">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-170">Degradazione MOS di rete causata dalla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="5f340-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-172">int</span><span class="sxs-lookup"><span data-stu-id="5f340-172">int</span></span></p></td>
<td><p><span data-ttu-id="5f340-173">Stranieri</span><span class="sxs-lookup"><span data-stu-id="5f340-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5f340-174">Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="5f340-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-176">int</span><span class="sxs-lookup"><span data-stu-id="5f340-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-177">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-179">int</span><span class="sxs-lookup"><span data-stu-id="5f340-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-180">Tempo di round trip dalle statistiche RTCP.</span><span class="sxs-lookup"><span data-stu-id="5f340-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="5f340-181">Per una qualità accettabile questo valore deve essere inferiore a 100 ms.</span><span class="sxs-lookup"><span data-stu-id="5f340-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-183">int</span><span class="sxs-lookup"><span data-stu-id="5f340-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-184">Tempo di round trip massimo per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="5f340-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-186">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-187">MOS di rete a banda larga medio per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="5f340-188">Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato.</span><span class="sxs-lookup"><span data-stu-id="5f340-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="5f340-189">L'intervallo è compreso tra [1,0 e 5,0].</span><span class="sxs-lookup"><span data-stu-id="5f340-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-191">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-192">Il MOS di rete a banda larga minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-193"><strong>Valore SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-194">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-195">La media del Punteggio MOS a banda larga stimato per l'audio inviato, inclusi il livello parlato, il livello di rumore e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="5f340-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-197">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-198">Valore SendListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-200">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-201">La media del Punteggio MOS a banda larga stimato per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="5f340-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-203">decimale (3, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-204">RecvListenMOS minimo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-206">po'</span><span class="sxs-lookup"><span data-stu-id="5f340-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-207">Contrassegno che indica se per la chiamata è stato utilizzato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="5f340-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-209">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-210">Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="5f340-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-212">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-213">Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="5f340-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-215">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="5f340-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-216">Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="5f340-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-217"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-218">po'</span><span class="sxs-lookup"><span data-stu-id="5f340-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-219">I dati del flusso sul ricevitore vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="5f340-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-220"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-221">po'</span><span class="sxs-lookup"><span data-stu-id="5f340-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-222">I dati del flusso sul mittente vengono ricevuti.</span><span class="sxs-lookup"><span data-stu-id="5f340-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-224">po'</span><span class="sxs-lookup"><span data-stu-id="5f340-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5f340-225">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="5f340-226">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="5f340-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-228">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-229">Deviazione standard per i tempi di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="5f340-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="5f340-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-232">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-233">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="5f340-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="5f340-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-236">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-237">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="5f340-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="5f340-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-240">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-241">Rapporto dei pacchetti rilasciati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="5f340-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="5f340-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-245">Rapporto dei pacchetti di correzione degli errori di inoltro utilizzati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="5f340-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="5f340-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-249">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="5f340-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="5f340-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-253">Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</span><span class="sxs-lookup"><span data-stu-id="5f340-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="5f340-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-257">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="5f340-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="5f340-258">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-260">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-261">Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="5f340-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="5f340-262">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-264">int</span><span class="sxs-lookup"><span data-stu-id="5f340-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-265">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5f340-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-268">int</span><span class="sxs-lookup"><span data-stu-id="5f340-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-269">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5f340-270">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-272">int</span><span class="sxs-lookup"><span data-stu-id="5f340-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-273">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5f340-274">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-276">int</span><span class="sxs-lookup"><span data-stu-id="5f340-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-277">Quantità media di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5f340-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5f340-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p105">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-283">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p106">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-288">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-290">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p107">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-293">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-295">int</span><span class="sxs-lookup"><span data-stu-id="5f340-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p108">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p109">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p110">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-313">int</span><span class="sxs-lookup"><span data-stu-id="5f340-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p111">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-317">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p112">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-325">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-p113">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="5f340-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5f340-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-332">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="5f340-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="5f340-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-335">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-336">Percentuale della chiamata di cui è stato eseguito il rendering come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="5f340-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="5f340-337">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-340">Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</span><span class="sxs-lookup"><span data-stu-id="5f340-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="5f340-341">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f340-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-343">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-344">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="5f340-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="5f340-345">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f340-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5f340-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5f340-347">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5f340-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f340-348">Percentuale della chiamata acquisita come stereo dalla soppressione dell'eco acustica.</span><span class="sxs-lookup"><span data-stu-id="5f340-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="5f340-349">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f340-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

