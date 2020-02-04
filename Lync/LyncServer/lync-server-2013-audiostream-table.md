---
title: 'Lync Server 2013: Tabella AudioStream'
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="9fa44-102">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fa44-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fa44-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9fa44-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9fa44-104">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-104">Each record represents one audio stream.</span></span> <span data-ttu-id="9fa44-105">Una linea media audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fa44-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9fa44-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9fa44-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9fa44-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="9fa44-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fa44-112">Principale</span><span class="sxs-lookup"><span data-stu-id="9fa44-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9fa44-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9fa44-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-115">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-115">int</span></span></p></td>
<td><p><span data-ttu-id="9fa44-116">Principale</span><span class="sxs-lookup"><span data-stu-id="9fa44-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9fa44-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9fa44-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9fa44-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9fa44-120">Principale</span><span class="sxs-lookup"><span data-stu-id="9fa44-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="9fa44-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9fa44-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-123">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-123">int</span></span></p></td>
<td><p><span data-ttu-id="9fa44-124">Principale</span><span class="sxs-lookup"><span data-stu-id="9fa44-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="9fa44-125">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="9fa44-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-127">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-128">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="9fa44-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-130">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-131">Variazione massima della rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-133">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="9fa44-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-134">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-136">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="9fa44-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-137">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-139">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="9fa44-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-140">Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-142">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-143">Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-145">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="9fa44-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-146">Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-148">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-149">Durata media degli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-151">Int</span><span class="sxs-lookup"><span data-stu-id="9fa44-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-152">Conteggio dei pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-153"><strong>Larghezza di banda più ampia</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-154">Int</span><span class="sxs-lookup"><span data-stu-id="9fa44-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-155">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-157">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-158">Degradazione MOS Network per l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="9fa44-159">L'intervallo è compreso tra 0,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="9fa44-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="9fa44-160">Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="9fa44-161">Per una qualità accettabile dovrebbe essere inferiore a 0,5.</span><span class="sxs-lookup"><span data-stu-id="9fa44-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-163">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-164">Massimo degrado dei MOS di rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-166">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-167">Degradazione dei MOS di rete causata da jitter.</span><span class="sxs-lookup"><span data-stu-id="9fa44-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-169">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-170">Degradazione dei MOS di rete causata da perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-172">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-172">int</span></span></p></td>
<td><p><span data-ttu-id="9fa44-173">Esterna</span><span class="sxs-lookup"><span data-stu-id="9fa44-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9fa44-174">Codec audio usato per la chiamata, a cui si fa riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="9fa44-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-176">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-177">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-179">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-180">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="9fa44-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="9fa44-181">Per una qualità accettabile, dovrebbe essere minore di 100ms.</span><span class="sxs-lookup"><span data-stu-id="9fa44-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-183">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-184">Tempo massimo di andata e ritorno per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="9fa44-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-186">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-187">MOS di rete a banda larga media per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="9fa44-188">Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati.</span><span class="sxs-lookup"><span data-stu-id="9fa44-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="9fa44-189">Intervallo è [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="9fa44-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-191">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-192">MOS della rete a banda larga minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-194">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-195">Il Punteggio di MOS in ascolto a banda larga previsto medio per l'audio inviato, incluse le caratteristiche del livello vocale, del livello di rumore e del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="9fa44-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-197">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-198">SendListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-200">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-201">Il Punteggio di MOS a banda larga previsto medio per l'audio ricevuto dalla rete, tra cui livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="9fa44-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-203">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-204">RecvListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-206">po'</span><span class="sxs-lookup"><span data-stu-id="9fa44-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-207">Contrassegno che indica se per la chiamata è stato usato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="9fa44-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-209">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-210">Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="9fa44-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-212">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-213">Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="9fa44-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-215">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9fa44-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-216">Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.</span><span class="sxs-lookup"><span data-stu-id="9fa44-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-217"><strong>In ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-218">po'</span><span class="sxs-lookup"><span data-stu-id="9fa44-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-219">Il flusso di dati sul lato ricevitore viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="9fa44-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-220"><strong>Outbound</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-221">po'</span><span class="sxs-lookup"><span data-stu-id="9fa44-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-222">Il flusso di dati sul lato mittente viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="9fa44-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-224">po'</span><span class="sxs-lookup"><span data-stu-id="9fa44-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9fa44-225">1 indica che la direzione del flusso è dal chiamante al chiamato.</span><span class="sxs-lookup"><span data-stu-id="9fa44-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="9fa44-226">0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="9fa44-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-228">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-229">Deviazione standard per l'orario di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="9fa44-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="9fa44-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-232">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-233">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="9fa44-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="9fa44-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-236">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-237">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="9fa44-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="9fa44-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-240">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-241">Rapporto tra i pacchetti eliminati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="9fa44-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-245">Rapporto tra i pacchetti di correzione degli errori in avanti usati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="9fa44-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-249">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="9fa44-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="9fa44-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-253">Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.</span><span class="sxs-lookup"><span data-stu-id="9fa44-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="9fa44-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-257">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="9fa44-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="9fa44-258">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-260">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-261">Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="9fa44-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="9fa44-262">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-264">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-265">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9fa44-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-268">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-269">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9fa44-270">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-272">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-273">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9fa44-274">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-276">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-277">Importo medio della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9fa44-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="9fa44-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-281">Importo totale della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-281">Total amount of one-way latency.</span></span> <span data-ttu-id="9fa44-282">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-283">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-286">Importo medio della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-286">Average amount of one-way latency.</span></span> <span data-ttu-id="9fa44-287">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-288">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-290">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-291">Importo massimo della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="9fa44-292">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-293">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-295">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-296">Occorrenze totali di burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="9fa44-297">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="9fa44-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9fa44-298">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-302">Densità totale burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-302">Total one-way burst density.</span></span> <span data-ttu-id="9fa44-303">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="9fa44-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9fa44-304">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-308">Totale durata burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-308">Total one-way burst duration.</span></span> <span data-ttu-id="9fa44-309">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="9fa44-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9fa44-310">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-313">int</span><span class="sxs-lookup"><span data-stu-id="9fa44-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-314">Occorrenze totali unidirezionali Gap.</span><span class="sxs-lookup"><span data-stu-id="9fa44-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="9fa44-315">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="9fa44-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9fa44-316">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-317">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-320">Densità totale gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-320">Total one-way gap density.</span></span> <span data-ttu-id="9fa44-321">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="9fa44-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9fa44-322">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-325">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-326">Durata totale del gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="9fa44-326">Total one-way gap duration.</span></span> <span data-ttu-id="9fa44-327">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="9fa44-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9fa44-328">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="9fa44-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="9fa44-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-332">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="9fa44-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="9fa44-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-335">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-336">Percentuale della chiamata di cui è stato eseguito il rendering stereo tramite la soppressione dell'Echo acustica.</span><span class="sxs-lookup"><span data-stu-id="9fa44-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="9fa44-337">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-340">Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.</span><span class="sxs-lookup"><span data-stu-id="9fa44-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="9fa44-341">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fa44-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-343">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-344">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="9fa44-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="9fa44-345">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fa44-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="9fa44-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="9fa44-347">galleggiante</span><span class="sxs-lookup"><span data-stu-id="9fa44-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9fa44-348">Percentuale della chiamata acquisita come stereo dalla soppressione dell'Echo acustica.</span><span class="sxs-lookup"><span data-stu-id="9fa44-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="9fa44-349">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fa44-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

