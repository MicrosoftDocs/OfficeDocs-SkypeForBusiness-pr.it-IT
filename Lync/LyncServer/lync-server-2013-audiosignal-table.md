---
title: 'Lync Server 2013: tabella AudioSignal'
description: 'Lync Server 2013: tabella AudioSignal.'
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
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568762"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="63380-103">Tabella AudioSignal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63380-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63380-104">_**Ultimo argomento modificato:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="63380-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="63380-105">Ogni record rappresenta la metrica del segnale audio per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="63380-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="63380-106">In genere, ogni chiamata ha due record, uno è per il chiamante e uno è per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63380-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63380-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="63380-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="63380-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="63380-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="63380-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="63380-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="63380-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="63380-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63380-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="63380-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-112">datetime</span><span class="sxs-lookup"><span data-stu-id="63380-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="63380-113">Principale</span><span class="sxs-lookup"><span data-stu-id="63380-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="63380-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="63380-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63380-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-116">int</span><span class="sxs-lookup"><span data-stu-id="63380-116">int</span></span></p></td>
<td><p><span data-ttu-id="63380-117">Principale</span><span class="sxs-lookup"><span data-stu-id="63380-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="63380-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="63380-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="63380-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="63380-121">Principale</span><span class="sxs-lookup"><span data-stu-id="63380-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="63380-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="63380-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="63380-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-124">po'</span><span class="sxs-lookup"><span data-stu-id="63380-124">bit</span></span></p></td>
<td><p><span data-ttu-id="63380-125">Principale</span><span class="sxs-lookup"><span data-stu-id="63380-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="63380-126">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="63380-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="63380-127">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="63380-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-129">int</span><span class="sxs-lookup"><span data-stu-id="63380-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-130">Rappresenta il livello di segnale audio post-analogico di controllo del guadagno.</span><span class="sxs-lookup"><span data-stu-id="63380-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="63380-131">L'unità di misura per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="63380-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="63380-132">Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="63380-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="63380-133">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="63380-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-135">int</span><span class="sxs-lookup"><span data-stu-id="63380-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-136">Vedere SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="63380-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-138">int</span><span class="sxs-lookup"><span data-stu-id="63380-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-139">Rappresenta il livello di rumore del controllo di guadagno post-analogico.</span><span class="sxs-lookup"><span data-stu-id="63380-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="63380-140">L'unità di misura per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="63380-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="63380-141">Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="63380-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="63380-142">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="63380-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-144">int</span><span class="sxs-lookup"><span data-stu-id="63380-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-145">Vedere SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="63380-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="63380-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-147">int</span><span class="sxs-lookup"><span data-stu-id="63380-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-148">Metrica di miglioramento della perdita di rendimento eco.</span><span class="sxs-lookup"><span data-stu-id="63380-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="63380-149">L'unità di misura per questa metrica è dB.</span><span class="sxs-lookup"><span data-stu-id="63380-149">The unit for this metric is dB.</span></span> <span data-ttu-id="63380-150">I valori più bassi rappresentano un'eco minore.</span><span class="sxs-lookup"><span data-stu-id="63380-150">Lower values represent less echo.</span></span> <span data-ttu-id="63380-151">Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="63380-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="63380-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-153">int</span><span class="sxs-lookup"><span data-stu-id="63380-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-154">Glitch medi per cinque minuti per il rendering degli altoparlanti.</span><span class="sxs-lookup"><span data-stu-id="63380-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="63380-155">Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="63380-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="63380-156">Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="63380-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="63380-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-158">int</span><span class="sxs-lookup"><span data-stu-id="63380-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-159">Glitch media per cinque minuti per l'acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="63380-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="63380-160">Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="63380-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="63380-161">Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="63380-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="63380-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-163">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-164">Velocità della deriva del clock del dispositivo microfono rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="63380-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="63380-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-166">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-167">Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="63380-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="63380-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-169">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-170">Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.</span><span class="sxs-lookup"><span data-stu-id="63380-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="63380-171">Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63380-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="63380-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-173">decimale (9, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-174">Errore medio del timestamp del flusso di rendering dell'altoparlante, in millisecondi, negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63380-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="63380-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-176">smallint</span><span class="sxs-lookup"><span data-stu-id="63380-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-177">La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="63380-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="63380-178">Cause della voce del commutatore vocale:</span><span class="sxs-lookup"><span data-stu-id="63380-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="63380-179">ENTER_VS_BADTS 0X01</span><span class="sxs-lookup"><span data-stu-id="63380-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="63380-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="63380-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="63380-181">ENTER_VS_FORCEORCONVERGENCE 0X04</span><span class="sxs-lookup"><span data-stu-id="63380-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="63380-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="63380-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="63380-183">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="63380-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="63380-184">ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="63380-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="63380-185">Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="63380-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="63380-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-188">Cause di un evento Echo:</span><span class="sxs-lookup"><span data-stu-id="63380-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="63380-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="63380-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="63380-190">ECHO_EVENT_POSTAEC_ECHO 0X02</span><span class="sxs-lookup"><span data-stu-id="63380-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="63380-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="63380-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="63380-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="63380-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="63380-193">ECHO_EVENT_MIC_CLIPPING 0X10</span><span class="sxs-lookup"><span data-stu-id="63380-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="63380-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="63380-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="63380-195">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="63380-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="63380-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-197">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-198">Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="63380-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="63380-199">In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="63380-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="63380-200">Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="63380-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="63380-201">Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="63380-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="63380-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-203">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="63380-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-204">Percentuale di tempo in cui l'eco viene rilevata nel flusso inviato.</span><span class="sxs-lookup"><span data-stu-id="63380-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="63380-205">Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="63380-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-207">int</span><span class="sxs-lookup"><span data-stu-id="63380-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-208">Livello di segnale ricevuto sul Mediation Server dal gateway. Questo è valido solo per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="63380-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="63380-209">L'unità di misura per questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="63380-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="63380-210">Per una buona qualità, l'intervallo accettabile dovrebbe essere [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="63380-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="63380-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-212">int</span><span class="sxs-lookup"><span data-stu-id="63380-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-213">Livello di segnale ricevuto sul Mediation Server dal gateway.</span><span class="sxs-lookup"><span data-stu-id="63380-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="63380-214">Si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="63380-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="63380-215">L'unità di misura per questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="63380-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="63380-216">Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="63380-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="63380-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-218">int</span><span class="sxs-lookup"><span data-stu-id="63380-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-219">Controllo di guadagno automatico (AGC) sul server di Mediation Side.</span><span class="sxs-lookup"><span data-stu-id="63380-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="63380-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-221">galleggiante</span><span class="sxs-lookup"><span data-stu-id="63380-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="63380-222">Il quadrato medio radice (RMS) del segnale in ingresso fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63380-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="63380-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-224">int</span><span class="sxs-lookup"><span data-stu-id="63380-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-225">Livello di segnale ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="63380-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="63380-226">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="63380-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-228">int</span><span class="sxs-lookup"><span data-stu-id="63380-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-229">Livello di segnale ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="63380-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="63380-230">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="63380-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-232">int</span><span class="sxs-lookup"><span data-stu-id="63380-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-233">Livello di rumore ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="63380-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="63380-234">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="63380-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-236">int</span><span class="sxs-lookup"><span data-stu-id="63380-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-237">Livello di rumore ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="63380-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="63380-238">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="63380-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-240">int</span><span class="sxs-lookup"><span data-stu-id="63380-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-241">Livello di segnale inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="63380-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="63380-242">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="63380-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-244">int</span><span class="sxs-lookup"><span data-stu-id="63380-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-245">Livello di segnale inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="63380-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="63380-246">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63380-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="63380-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-248">int</span><span class="sxs-lookup"><span data-stu-id="63380-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-249">Livello di rumore inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="63380-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="63380-250">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63380-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="63380-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="63380-252">int</span><span class="sxs-lookup"><span data-stu-id="63380-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="63380-253">Livello di rumore inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="63380-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="63380-254">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63380-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

