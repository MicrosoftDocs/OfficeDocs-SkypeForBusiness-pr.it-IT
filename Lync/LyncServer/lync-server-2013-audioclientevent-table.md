---
title: 'Lync Server 2013: Tabella AudioClientEvent'
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
ms.openlocfilehash: d93a9cd9276ba2bdaacf892ca0ab3f4240458503
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="7e3fe-102">Tabella AudioClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e3fe-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e3fe-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="7e3fe-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="7e3fe-104">Ogni record contiene un evento client per un endpoint in una chiamata audio.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="7e3fe-105">In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e3fe-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7e3fe-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7e3fe-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7e3fe-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7e3fe-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-112">Principale</span><span class="sxs-lookup"><span data-stu-id="7e3fe-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-115">int</span><span class="sxs-lookup"><span data-stu-id="7e3fe-115">int</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-116">Principale</span><span class="sxs-lookup"><span data-stu-id="7e3fe-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e3fe-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-120">Principale</span><span class="sxs-lookup"><span data-stu-id="7e3fe-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-123">po'</span><span class="sxs-lookup"><span data-stu-id="7e3fe-123">bit</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-124">Principale</span><span class="sxs-lookup"><span data-stu-id="7e3fe-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e3fe-125">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="7e3fe-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="7e3fe-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="7e3fe-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-128">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-129">Percentuale di sessione l'evento NetworkSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="7e3fe-130">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-132">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-133">Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="7e3fe-134">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-136">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-137">Percentuale di sessione l'evento Delay è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-138">La latenza della rete è grave e influisce sull'esperienza impedendo le comunicazioni interattive</span><span class="sxs-lookup"><span data-stu-id="7e3fe-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-140">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-141">Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-142">La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-144">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-145">Percentuale di sessione l'evento CPU insufficiente è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-146">Non sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità correnti e le applicazioni in uso.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="7e3fe-147">In questo modo le distorsioni vengono causate dal canale audio.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-149">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-150">Percentuale di sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-151">Al fine di prevenire l'eco, il sistema ha immesso half duplex.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-153">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-154">Percentuale di sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-155">Il dispositivo di rendering attualmente utilizzato per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="7e3fe-156">Ciò può causare problemi di tipo audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-158">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-159">Percentuale di sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-160">Il dispositivo di acquisizione attualmente utilizzato per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="7e3fe-161">Ciò può causare problemi di tipo audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-163">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-164">Percentuale di sessione l'evento DeviceGlitches è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-165">Vi sono gravi problemi di rendering dell'audio che causano distorsioni.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="7e3fe-166">Questi difetti possono essere causati da problemi relativi ai driver, dalla tempesta di chiamate di routine posticipate (DPC) e dall'elevato utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-168">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-169">Percentuale di sessione l'evento DeviceLowSNR è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-170">La qualità di acquisizione è molto scarsa, sia molto rumoroso o l'utente sta parlando troppo lontano dal microfono.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="7e3fe-171">Ciò provocherà distorsioni.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-173">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-174">Percentuale di sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-175">Il livello di sintesi vocale dell'utente è troppo basso e il sistema non può aumentare ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="7e3fe-176">Questo può causare distorsioni o percepito come un audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-178">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-179">Percentuale di sessione l'evento DeviceClipping è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="7e3fe-180">Quando il microfono viene ritagliato da un punto di vista intermedio, la distorsione di fine-estremità si sente a causa del clipping.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="7e3fe-181">È importante evitare il clipping del microfono near-end.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-183">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-184">Percentuale di sessione l'evento cui è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-185">Il dispositivo o il programma di installazione stanno causando l'eco oltre la capacità del sistema di compensare.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-187">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-188">Percentuale di sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-189">La voce dell'utente è troppo bassa rispetto all'acquisizione dell'eco che influisce sull'esperienza degli utenti, in quanto limita la facilità di interruzione di un utente.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="7e3fe-190">Ridurre il volume degli altoparlanti, spostare il microfono più vicino all'oratore.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-192">int</span><span class="sxs-lookup"><span data-stu-id="7e3fe-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e3fe-193">Numero di volte durante la sessione in cui è stato generato l'evento DeviceMultipleEndpoints per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-194">Sono stati rilevati più endpoint audio nella stessa sessione e il sistema ha compensato la riduzione del volume di rendering.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-196">int</span><span class="sxs-lookup"><span data-stu-id="7e3fe-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e3fe-197">Numero di volte durante la sessione in cui è stato generato l'evento DeviceHowlingEvent per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="7e3fe-198">Ciclo di commenti e suggerimenti audio rilevato (causato da più endpoint che condividono il percorso audio).</span><span class="sxs-lookup"><span data-stu-id="7e3fe-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e3fe-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-200">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e3fe-201">Percentuale di sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="7e3fe-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="7e3fe-202">Il dispositivo di rendering è stato impostato su zero volume.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="7e3fe-203">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e3fe-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7e3fe-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7e3fe-205">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7e3fe-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e3fe-206">Percentuale di sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="7e3fe-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="7e3fe-207">La periferica di rendering è stata disattivata.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="7e3fe-208">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e3fe-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

