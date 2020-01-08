---
title: 'Lync Server 2013: Tabella AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="eff73-102">Tabella AudioStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eff73-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eff73-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eff73-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eff73-104">Ogni record rappresenta un flusso audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-104">Each record represents one audio stream.</span></span> <span data-ttu-id="eff73-105">Una linea media audio in genere contiene due flussi audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eff73-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eff73-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eff73-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eff73-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eff73-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="eff73-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="eff73-112">Principale</span><span class="sxs-lookup"><span data-stu-id="eff73-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff73-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eff73-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-115">int</span><span class="sxs-lookup"><span data-stu-id="eff73-115">int</span></span></p></td>
<td><p><span data-ttu-id="eff73-116">Principale</span><span class="sxs-lookup"><span data-stu-id="eff73-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff73-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eff73-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="eff73-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eff73-120">Principale</span><span class="sxs-lookup"><span data-stu-id="eff73-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff73-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="eff73-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-123">int</span><span class="sxs-lookup"><span data-stu-id="eff73-123">int</span></span></p></td>
<td><p><span data-ttu-id="eff73-124">Principale</span><span class="sxs-lookup"><span data-stu-id="eff73-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff73-125">ID univoco all'interno di una linea media.</span><span class="sxs-lookup"><span data-stu-id="eff73-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-127">int</span><span class="sxs-lookup"><span data-stu-id="eff73-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-128">Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="eff73-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-130">int</span><span class="sxs-lookup"><span data-stu-id="eff73-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-131">Variazione massima della rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-133">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="eff73-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-134">Tasso medio di perdita di pacchetti durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-136">decimale (5; 4)</span><span class="sxs-lookup"><span data-stu-id="eff73-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-137">Perdita massima del pacchetto osservata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-139">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="eff73-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-140">Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-142">int</span><span class="sxs-lookup"><span data-stu-id="eff73-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-143">Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-145">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="eff73-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-146">Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="eff73-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-148">int</span><span class="sxs-lookup"><span data-stu-id="eff73-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-149">Durata media degli intervalli tra i burst di perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="eff73-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-151">Int</span><span class="sxs-lookup"><span data-stu-id="eff73-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-152">Conteggio dei pacchetti per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-153"><strong>Larghezza di banda più ampia</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-154">Int</span><span class="sxs-lookup"><span data-stu-id="eff73-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-155">Stime della larghezza di banda per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-157">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-158">Degradazione MOS Network per l'intera chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="eff73-159">L'intervallo è compreso tra 0,0 e 5,0.</span><span class="sxs-lookup"><span data-stu-id="eff73-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="eff73-160">Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="eff73-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="eff73-161">Per una qualità accettabile dovrebbe essere inferiore a 0,5.</span><span class="sxs-lookup"><span data-stu-id="eff73-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-163">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-164">Massimo degrado dei MOS di rete durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-166">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-167">Degradazione dei MOS di rete causata da jitter.</span><span class="sxs-lookup"><span data-stu-id="eff73-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-169">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-170">Degradazione dei MOS di rete causata da perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="eff73-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-172">int</span><span class="sxs-lookup"><span data-stu-id="eff73-172">int</span></span></p></td>
<td><p><span data-ttu-id="eff73-173">Esterna</span><span class="sxs-lookup"><span data-stu-id="eff73-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eff73-174">Codec audio usato per la chiamata, a cui si fa riferimento dalla Tabella PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="eff73-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-176">int</span><span class="sxs-lookup"><span data-stu-id="eff73-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-177">Frequenza di campionamento per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-179">int</span><span class="sxs-lookup"><span data-stu-id="eff73-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-180">Tempo di andata e ritorno dalle statistiche di RTCP.</span><span class="sxs-lookup"><span data-stu-id="eff73-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="eff73-181">Per una qualità accettabile, dovrebbe essere minore di 100ms.</span><span class="sxs-lookup"><span data-stu-id="eff73-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-183">int</span><span class="sxs-lookup"><span data-stu-id="eff73-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-184">Tempo massimo di andata e ritorno per il flusso audio.</span><span class="sxs-lookup"><span data-stu-id="eff73-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-186">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-187">MOS di rete a banda larga media per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="eff73-188">Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati.</span><span class="sxs-lookup"><span data-stu-id="eff73-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="eff73-189">Intervallo è [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="eff73-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-191">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-192">MOS della rete a banda larga minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-194">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-195">Il Punteggio di MOS in ascolto a banda larga previsto medio per l'audio inviato, incluse le caratteristiche del livello vocale, del livello di rumore e del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="eff73-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-197">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-198">SendListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-200">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-201">Il Punteggio di MOS a banda larga previsto medio per l'audio ricevuto dalla rete, tra cui livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="eff73-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-203">decimale (3; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-204">RecvListenMOS minima per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-206">po'</span><span class="sxs-lookup"><span data-stu-id="eff73-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-207">Contrassegno che indica se per la chiamata è stato usato l'audio FEC.</span><span class="sxs-lookup"><span data-stu-id="eff73-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-209">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-210">Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="eff73-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-212">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-213">Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.</span><span class="sxs-lookup"><span data-stu-id="eff73-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-215">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="eff73-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-216">Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.</span><span class="sxs-lookup"><span data-stu-id="eff73-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-217"><strong>In ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-218">po'</span><span class="sxs-lookup"><span data-stu-id="eff73-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-219">Il flusso di dati sul lato ricevitore viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="eff73-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-220"><strong>Outbound</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-221">po'</span><span class="sxs-lookup"><span data-stu-id="eff73-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-222">Il flusso di dati sul lato mittente viene ricevuto.</span><span class="sxs-lookup"><span data-stu-id="eff73-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-224">po'</span><span class="sxs-lookup"><span data-stu-id="eff73-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff73-225">1 indica che la direzione del flusso è dal chiamante al chiamato.</span><span class="sxs-lookup"><span data-stu-id="eff73-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="eff73-226">0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="eff73-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-228">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-229">Deviazione standard per l'orario di arrivo jitter.</span><span class="sxs-lookup"><span data-stu-id="eff73-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="eff73-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-232">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-233">Rapporto massimo dei pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="eff73-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="eff73-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-236">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-237">Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="eff73-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="eff73-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-240">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-241">Rapporto tra i pacchetti eliminati dal guaritore rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="eff73-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="eff73-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-245">Rapporto tra i pacchetti di correzione degli errori in avanti usati rispetto al numero totale di pacchetti ricevuti.</span><span class="sxs-lookup"><span data-stu-id="eff73-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="eff73-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-249">Numero massimo di pacchetti audio compressi dal guaritore.</span><span class="sxs-lookup"><span data-stu-id="eff73-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="eff73-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-253">Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.</span><span class="sxs-lookup"><span data-stu-id="eff73-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="eff73-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-257">Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</span><span class="sxs-lookup"><span data-stu-id="eff73-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="eff73-258">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-260">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-261">Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.</span><span class="sxs-lookup"><span data-stu-id="eff73-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="eff73-262">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-264">int</span><span class="sxs-lookup"><span data-stu-id="eff73-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-265">Quantità minima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff73-266">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-268">int</span><span class="sxs-lookup"><span data-stu-id="eff73-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-269">Quantità massima di stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff73-270">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-272">int</span><span class="sxs-lookup"><span data-stu-id="eff73-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-273">Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff73-274">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-276">int</span><span class="sxs-lookup"><span data-stu-id="eff73-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-277">Importo medio della stima della larghezza di banda misurata durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="eff73-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff73-278">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-281">Importo totale della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-281">Total amount of one-way latency.</span></span> <span data-ttu-id="eff73-282">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-283">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-286">Importo medio della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-286">Average amount of one-way latency.</span></span> <span data-ttu-id="eff73-287">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-288">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-290">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-291">Importo massimo della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="eff73-292">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-293">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-295">int</span><span class="sxs-lookup"><span data-stu-id="eff73-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-296">Occorrenze totali di burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="eff73-297">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="eff73-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff73-298">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-299">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-302">Densità totale burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-302">Total one-way burst density.</span></span> <span data-ttu-id="eff73-303">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="eff73-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff73-304">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-305">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-308">Totale durata burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-308">Total one-way burst duration.</span></span> <span data-ttu-id="eff73-309">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="eff73-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff73-310">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-311">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-313">int</span><span class="sxs-lookup"><span data-stu-id="eff73-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-314">Occorrenze totali unidirezionali Gap.</span><span class="sxs-lookup"><span data-stu-id="eff73-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="eff73-315">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="eff73-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff73-316">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-317">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-320">Densità totale gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-320">Total one-way gap density.</span></span> <span data-ttu-id="eff73-321">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="eff73-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff73-322">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-323">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-325">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-326">Durata totale del gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="eff73-326">Total one-way gap duration.</span></span> <span data-ttu-id="eff73-327">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="eff73-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff73-328">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="eff73-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff73-329">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-332">Percentuale della chiamata decodificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="eff73-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="eff73-333">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-335">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-336">Percentuale della chiamata di cui è stato eseguito il rendering stereo tramite la soppressione dell'Echo acustica.</span><span class="sxs-lookup"><span data-stu-id="eff73-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="eff73-337">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-340">Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.</span><span class="sxs-lookup"><span data-stu-id="eff73-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="eff73-341">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff73-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-343">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-344">Percentuale della chiamata codificata come stereo.</span><span class="sxs-lookup"><span data-stu-id="eff73-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="eff73-345">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff73-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff73-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff73-347">galleggiante</span><span class="sxs-lookup"><span data-stu-id="eff73-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff73-348">Percentuale della chiamata acquisita come stereo dalla soppressione dell'Echo acustica.</span><span class="sxs-lookup"><span data-stu-id="eff73-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="eff73-349">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff73-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

