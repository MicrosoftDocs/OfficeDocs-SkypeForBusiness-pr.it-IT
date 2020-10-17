---
title: 'Lync Server 2013: Tabella AudioClientEvent'
description: 'Lync Server 2013: Tabella AudioClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568782"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="f8dc5-103">Tabella AudioClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8dc5-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8dc5-104">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="f8dc5-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="f8dc5-105">Ogni record contiene un evento client per un endpoint in una chiamata audio.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="f8dc5-106">In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8dc5-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f8dc5-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f8dc5-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f8dc5-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f8dc5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-113">Principale</span><span class="sxs-lookup"><span data-stu-id="f8dc5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-116">int</span><span class="sxs-lookup"><span data-stu-id="f8dc5-116">int</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-117">Principale</span><span class="sxs-lookup"><span data-stu-id="f8dc5-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="f8dc5-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-121">Principale</span><span class="sxs-lookup"><span data-stu-id="f8dc5-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-124">po'</span><span class="sxs-lookup"><span data-stu-id="f8dc5-124">bit</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-125">Principale</span><span class="sxs-lookup"><span data-stu-id="f8dc5-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="f8dc5-126">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="f8dc5-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="f8dc5-127">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="f8dc5-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-129">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-130">Percentuale di sessione l'evento NetworkSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f8dc5-131">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-133">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-134">Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f8dc5-135">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-137">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-138">Percentuale di sessione l'evento Delay è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-139">La latenza della rete è grave e influisce sull'esperienza impedendo le comunicazioni interattive</span><span class="sxs-lookup"><span data-stu-id="f8dc5-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-141">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-142">Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-143">La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-145">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-146">Percentuale di sessione l'evento CPU insufficiente è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-147">Non sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità correnti e le applicazioni in uso.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="f8dc5-148">In questo modo le distorsioni vengono causate dal canale audio.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-150">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-151">Percentuale di sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-152">Al fine di prevenire l'eco, il sistema ha immesso half duplex.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-154">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-155">Percentuale di sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-156">Il dispositivo di rendering attualmente utilizzato per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="f8dc5-157">Ciò può causare problemi di tipo audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-159">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-160">Percentuale di sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-161">Il dispositivo di acquisizione attualmente utilizzato per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="f8dc5-162">Ciò può causare problemi di tipo audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-164">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-165">Percentuale di sessione l'evento DeviceGlitches è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-166">Vi sono gravi problemi di rendering dell'audio che causano distorsioni.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="f8dc5-167">Questi difetti possono essere causati da problemi relativi ai driver, dalla tempesta di chiamate di routine posticipate (DPC) e dall'elevato utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-169">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-170">Percentuale di sessione l'evento DeviceLowSNR è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-171">La qualità di acquisizione è molto scarsa, sia molto rumoroso o l'utente sta parlando troppo lontano dal microfono.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="f8dc5-172">Ciò provocherà distorsioni.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-174">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-175">Percentuale di sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-176">Il livello di sintesi vocale dell'utente è troppo basso e il sistema non può aumentare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="f8dc5-177">Questo può causare distorsioni o percepito come un audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-179">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-180">Percentuale di sessione l'evento DeviceClipping è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f8dc5-181">Quando il microfono viene ritagliato da un punto di vista intermedio, la distorsione di fine-estremità si sente a causa del clipping.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="f8dc5-182">È importante evitare il clipping del microfono near-end.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-184">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-185">Percentuale di sessione l'evento cui è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-186">Il dispositivo o il programma di installazione stanno causando l'eco oltre la capacità del sistema di compensare.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-188">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-189">Percentuale di sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-190">La voce dell'utente è troppo bassa rispetto all'acquisizione dell'eco che influisce sull'esperienza degli utenti, in quanto limita la facilità di interruzione di un utente.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="f8dc5-191">Ridurre il volume degli altoparlanti, spostare il microfono più vicino all'oratore.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-193">int</span><span class="sxs-lookup"><span data-stu-id="f8dc5-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8dc5-194">Numero di volte durante la sessione in cui è stato generato l'evento DeviceMultipleEndpoints per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-195">Sono stati rilevati più endpoint audio nella stessa sessione e il sistema ha compensato la riduzione del volume di rendering.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-197">int</span><span class="sxs-lookup"><span data-stu-id="f8dc5-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f8dc5-198">Numero di volte durante la sessione in cui è stato generato l'evento DeviceHowlingEvent per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f8dc5-199">Ciclo di commenti e suggerimenti audio rilevato (causato da più endpoint che condividono il percorso audio).</span><span class="sxs-lookup"><span data-stu-id="f8dc5-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8dc5-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-201">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8dc5-202">Percentuale di sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="f8dc5-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="f8dc5-203">Il dispositivo di rendering è stato impostato su zero volume.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="f8dc5-204">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8dc5-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f8dc5-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f8dc5-206">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f8dc5-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f8dc5-207">Percentuale di sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="f8dc5-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="f8dc5-208">La periferica di rendering è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="f8dc5-209">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8dc5-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

