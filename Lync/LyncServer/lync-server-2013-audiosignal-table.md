---
title: 'Lync Server 2013: tabella AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="7ffef-102">Tabella AudioSignal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ffef-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ffef-103">_**Ultimo argomento modificato:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="7ffef-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="7ffef-104">Ogni record rappresenta la metrica del segnale audio per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ffef-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="7ffef-105">In genere, ogni chiamata ha due record, uno è per il chiamante e uno è per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ffef-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ffef-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7ffef-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7ffef-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7ffef-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7ffef-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7ffef-112">Principale</span><span class="sxs-lookup"><span data-stu-id="7ffef-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ffef-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7ffef-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-115">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-115">int</span></span></p></td>
<td><p><span data-ttu-id="7ffef-116">Principale</span><span class="sxs-lookup"><span data-stu-id="7ffef-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ffef-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7ffef-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="7ffef-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7ffef-120">Principale</span><span class="sxs-lookup"><span data-stu-id="7ffef-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ffef-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7ffef-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-123">po'</span><span class="sxs-lookup"><span data-stu-id="7ffef-123">bit</span></span></p></td>
<td><p><span data-ttu-id="7ffef-124">Principale</span><span class="sxs-lookup"><span data-stu-id="7ffef-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ffef-125">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="7ffef-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="7ffef-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="7ffef-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-128">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-129">Rappresenta il livello di segnale audio post-analogico di controllo del guadagno.</span><span class="sxs-lookup"><span data-stu-id="7ffef-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="7ffef-130">L'unità di misura per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="7ffef-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="7ffef-131">Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="7ffef-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="7ffef-132">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="7ffef-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-134">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-135">Vedere SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="7ffef-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-137">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-138">Rappresenta il livello di rumore del controllo di guadagno post-analogico.</span><span class="sxs-lookup"><span data-stu-id="7ffef-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="7ffef-139">L'unità di misura per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="7ffef-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="7ffef-140">Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="7ffef-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="7ffef-141">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="7ffef-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-143">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-144">Vedere SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="7ffef-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-146">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-147">Metrica di miglioramento della perdita di rendimento eco.</span><span class="sxs-lookup"><span data-stu-id="7ffef-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="7ffef-148">L'unità di misura per questa metrica è dB.</span><span class="sxs-lookup"><span data-stu-id="7ffef-148">The unit for this metric is dB.</span></span> <span data-ttu-id="7ffef-149">I valori più bassi rappresentano un'eco minore.</span><span class="sxs-lookup"><span data-stu-id="7ffef-149">Lower values represent less echo.</span></span> <span data-ttu-id="7ffef-150">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="7ffef-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-152">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-153">Glitch medi per cinque minuti per il rendering degli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="7ffef-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="7ffef-154">Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="7ffef-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="7ffef-155">Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="7ffef-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-157">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-158">Glitch media per cinque minuti per l'acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="7ffef-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="7ffef-159">Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="7ffef-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="7ffef-160">Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="7ffef-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-162">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-163">Velocità della deriva del clock del dispositivo microfono rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="7ffef-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-165">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-166">Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="7ffef-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-168">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-169">Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="7ffef-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="7ffef-170">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ffef-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-172">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-173">Errore medio del timestamp del flusso di rendering dell'altoparlante, in millisecondi, negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ffef-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-175">smallint</span><span class="sxs-lookup"><span data-stu-id="7ffef-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-176">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="7ffef-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="7ffef-177">Cause della voce del commutatore vocale:</span><span class="sxs-lookup"><span data-stu-id="7ffef-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="7ffef-178">ENTER_VS_BADTS 0X01</span><span class="sxs-lookup"><span data-stu-id="7ffef-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="7ffef-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="7ffef-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="7ffef-180">ENTER_VS_FORCEORCONVERGENCE 0X04</span><span class="sxs-lookup"><span data-stu-id="7ffef-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="7ffef-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="7ffef-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="7ffef-182">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="7ffef-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="7ffef-183">ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="7ffef-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="7ffef-184">Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="7ffef-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-187">Cause di un evento Echo:</span><span class="sxs-lookup"><span data-stu-id="7ffef-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="7ffef-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="7ffef-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="7ffef-189">ECHO_EVENT_POSTAEC_ECHO 0X02</span><span class="sxs-lookup"><span data-stu-id="7ffef-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="7ffef-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="7ffef-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="7ffef-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="7ffef-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="7ffef-192">ECHO_EVENT_MIC_CLIPPING 0X10</span><span class="sxs-lookup"><span data-stu-id="7ffef-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="7ffef-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="7ffef-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="7ffef-194">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="7ffef-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-196">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-197">Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="7ffef-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="7ffef-198">In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="7ffef-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="7ffef-199">Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="7ffef-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="7ffef-200">Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ffef-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-202">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7ffef-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-203">Percentuale di tempo in cui l'eco viene rilevata nel flusso inviato.</span><span class="sxs-lookup"><span data-stu-id="7ffef-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="7ffef-204">Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="7ffef-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-206">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-207">Livello di segnale ricevuto sul Mediation Server dal gateway. Questo è valido solo per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7ffef-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="7ffef-208">L'unità di misura per questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="7ffef-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="7ffef-209">Per una buona qualità, l'intervallo accettabile dovrebbe essere [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="7ffef-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-211">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-212">Livello di segnale ricevuto sul Mediation Server dal gateway.</span><span class="sxs-lookup"><span data-stu-id="7ffef-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="7ffef-213">Si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7ffef-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="7ffef-214">L'unità di misura per questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="7ffef-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="7ffef-215">Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="7ffef-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-217">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-218">Controllo di guadagno automatico (AGC) sul server di Mediation Side.</span><span class="sxs-lookup"><span data-stu-id="7ffef-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-220">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7ffef-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7ffef-221">Il quadrato medio radice (RMS) del segnale in ingresso fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ffef-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-223">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-224">Livello di segnale ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="7ffef-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="7ffef-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-227">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-228">Livello di segnale ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="7ffef-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="7ffef-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-231">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-232">Livello di rumore ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="7ffef-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="7ffef-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-235">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-236">Livello di rumore ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="7ffef-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="7ffef-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-239">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-240">Livello di segnale inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="7ffef-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="7ffef-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-243">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-244">Livello di segnale inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="7ffef-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="7ffef-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ffef-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-247">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-248">Livello di rumore inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="7ffef-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="7ffef-249">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7ffef-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="7ffef-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="7ffef-251">int</span><span class="sxs-lookup"><span data-stu-id="7ffef-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ffef-252">Livello di rumore inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="7ffef-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="7ffef-253">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ffef-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

