---
title: 'Lync Server 2013: Tabella AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="8913e-102">Tabella AudioSignal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8913e-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8913e-103">_**Argomento Ultima modifica:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="8913e-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="8913e-104">Ogni record rappresenta le metriche del segnale audio per un endpoint.</span><span class="sxs-lookup"><span data-stu-id="8913e-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="8913e-105">In genere, ogni chiamata ha due record, uno è per il chiamante e uno per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="8913e-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8913e-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8913e-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8913e-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8913e-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8913e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="8913e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8913e-112">Principale</span><span class="sxs-lookup"><span data-stu-id="8913e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8913e-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8913e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-115">int</span><span class="sxs-lookup"><span data-stu-id="8913e-115">int</span></span></p></td>
<td><p><span data-ttu-id="8913e-116">Principale</span><span class="sxs-lookup"><span data-stu-id="8913e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="8913e-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8913e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8913e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8913e-120">Principale</span><span class="sxs-lookup"><span data-stu-id="8913e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="8913e-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8913e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-123">po'</span><span class="sxs-lookup"><span data-stu-id="8913e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="8913e-124">Principale</span><span class="sxs-lookup"><span data-stu-id="8913e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="8913e-125">0: dati del destinatario</span><span class="sxs-lookup"><span data-stu-id="8913e-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="8913e-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="8913e-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-128">int</span><span class="sxs-lookup"><span data-stu-id="8913e-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-129">Rappresenta il livello di segnale audio per il controllo del guadagno post-analogico.</span><span class="sxs-lookup"><span data-stu-id="8913e-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="8913e-130">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="8913e-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8913e-131">Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8913e-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8913e-132">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="8913e-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-134">int</span><span class="sxs-lookup"><span data-stu-id="8913e-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-135">Vedere SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="8913e-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-137">int</span><span class="sxs-lookup"><span data-stu-id="8913e-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-138">Rappresenta il livello di rumore audio del controllo di guadagno post-analogico.</span><span class="sxs-lookup"><span data-stu-id="8913e-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="8913e-139">L'unità per questa metrica è dBmo.</span><span class="sxs-lookup"><span data-stu-id="8913e-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8913e-140">Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="8913e-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8913e-141">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="8913e-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-143">int</span><span class="sxs-lookup"><span data-stu-id="8913e-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-144">Vedere SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="8913e-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-146">int</span><span class="sxs-lookup"><span data-stu-id="8913e-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-147">Metrica di miglioramento della perdita di echo return.</span><span class="sxs-lookup"><span data-stu-id="8913e-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="8913e-148">L'unità per questa metrica è dB.</span><span class="sxs-lookup"><span data-stu-id="8913e-148">The unit for this metric is dB.</span></span> <span data-ttu-id="8913e-149">I valori più bassi rappresentano meno eco.</span><span class="sxs-lookup"><span data-stu-id="8913e-149">Lower values represent less echo.</span></span> <span data-ttu-id="8913e-150">Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="8913e-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-152">int</span><span class="sxs-lookup"><span data-stu-id="8913e-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-153">Inconvenienti medi per cinque minuti per il rendering del diffusore.</span><span class="sxs-lookup"><span data-stu-id="8913e-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="8913e-154">Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="8913e-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="8913e-155">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="8913e-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-157">int</span><span class="sxs-lookup"><span data-stu-id="8913e-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-158">Glitch media per cinque minuti per l'acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="8913e-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="8913e-159">Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti.</span><span class="sxs-lookup"><span data-stu-id="8913e-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="8913e-160">Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="8913e-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-162">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-163">Velocità di spostamento del dispositivo microfonico, relativo all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="8913e-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-165">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-166">Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="8913e-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-168">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-169">Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.</span><span class="sxs-lookup"><span data-stu-id="8913e-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="8913e-170">Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8913e-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-172">decimale (9; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-173">Messaggio di errore medio del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8913e-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-175">smallint</span><span class="sxs-lookup"><span data-stu-id="8913e-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-176">L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta.</span><span class="sxs-lookup"><span data-stu-id="8913e-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8913e-177">Cause della voce di interruttore vocale:</span><span class="sxs-lookup"><span data-stu-id="8913e-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="8913e-178">ENTER_VS_BADTS 0X01</span><span class="sxs-lookup"><span data-stu-id="8913e-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="8913e-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="8913e-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="8913e-180">ENTER_VS_FORCEORCONVERGENCE 0X04</span><span class="sxs-lookup"><span data-stu-id="8913e-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="8913e-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="8913e-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="8913e-182">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="8913e-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="8913e-183">ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey per scopi di test.</span><span class="sxs-lookup"><span data-stu-id="8913e-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="8913e-184">Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="8913e-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-187">Cause di un evento Echo:</span><span class="sxs-lookup"><span data-stu-id="8913e-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="8913e-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="8913e-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="8913e-189">ECHO_EVENT_POSTAEC_ECHO 0X02</span><span class="sxs-lookup"><span data-stu-id="8913e-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="8913e-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="8913e-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="8913e-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="8913e-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="8913e-192">ECHO_EVENT_MIC_CLIPPING 0X10</span><span class="sxs-lookup"><span data-stu-id="8913e-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="8913e-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="8913e-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="8913e-194">La causa può essere una combinazione di queste singole cause.</span><span class="sxs-lookup"><span data-stu-id="8913e-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-196">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-197">Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono.</span><span class="sxs-lookup"><span data-stu-id="8913e-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="8913e-198">In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi.</span><span class="sxs-lookup"><span data-stu-id="8913e-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="8913e-199">Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="8913e-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="8913e-200">Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8913e-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-202">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="8913e-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-203">Percentuale di tempo in cui Echo viene rilevato in Stream inviato.</span><span class="sxs-lookup"><span data-stu-id="8913e-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="8913e-204">Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</span><span class="sxs-lookup"><span data-stu-id="8913e-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-206">int</span><span class="sxs-lookup"><span data-stu-id="8913e-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-207">Livello di segnale ricevuto sul server Mediation dal gateway; Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8913e-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="8913e-208">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="8913e-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8913e-209">Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="8913e-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-211">int</span><span class="sxs-lookup"><span data-stu-id="8913e-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-212">Livello di segnale ricevuto nel server Mediation dal gateway.</span><span class="sxs-lookup"><span data-stu-id="8913e-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="8913e-213">Questo si applica solo al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8913e-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="8913e-214">L'unità di questa metrica è dBoV.</span><span class="sxs-lookup"><span data-stu-id="8913e-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8913e-215">Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="8913e-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-217">int</span><span class="sxs-lookup"><span data-stu-id="8913e-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-218">Controllo automatico del guadagno (AGC) sul lato Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="8913e-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-220">galleggiante</span><span class="sxs-lookup"><span data-stu-id="8913e-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8913e-221">Il quadrato medio radice (RMS) del segnale in arrivo fino ai primi 30 secondi della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8913e-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-223">int</span><span class="sxs-lookup"><span data-stu-id="8913e-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-224">Livello di segnale ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="8913e-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="8913e-225">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-227">int</span><span class="sxs-lookup"><span data-stu-id="8913e-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-228">Livello di segnale ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="8913e-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="8913e-229">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-231">int</span><span class="sxs-lookup"><span data-stu-id="8913e-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-232">Livello di rumorosità ricevuto sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="8913e-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="8913e-233">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-235">int</span><span class="sxs-lookup"><span data-stu-id="8913e-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-236">Livello di rumorosità ricevuto sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="8913e-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="8913e-237">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-239">int</span><span class="sxs-lookup"><span data-stu-id="8913e-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-240">Livello di segnale inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="8913e-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="8913e-241">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-243">int</span><span class="sxs-lookup"><span data-stu-id="8913e-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-244">Livello di segnale inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="8913e-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="8913e-245">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8913e-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-247">int</span><span class="sxs-lookup"><span data-stu-id="8913e-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-248">Livello di rumorosità inviato sul canale 1.</span><span class="sxs-lookup"><span data-stu-id="8913e-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="8913e-249">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8913e-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8913e-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8913e-251">int</span><span class="sxs-lookup"><span data-stu-id="8913e-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8913e-252">Livello di rumorosità inviato sul canale 2.</span><span class="sxs-lookup"><span data-stu-id="8913e-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="8913e-253">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8913e-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

