---
title: 'Lync Server 2013: Tabella AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="173c4-102">Tabella AudioClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="173c4-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="173c4-103">_**Argomento Ultima modifica:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="173c4-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="173c4-104">Ogni record contiene un evento client per un endpoint in una chiamata audio.</span><span class="sxs-lookup"><span data-stu-id="173c4-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="173c4-105">In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="173c4-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="173c4-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="173c4-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="173c4-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="173c4-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="173c4-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="173c4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="173c4-112">Principale</span><span class="sxs-lookup"><span data-stu-id="173c4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="173c4-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="173c4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-115">int</span><span class="sxs-lookup"><span data-stu-id="173c4-115">int</span></span></p></td>
<td><p><span data-ttu-id="173c4-116">Principale</span><span class="sxs-lookup"><span data-stu-id="173c4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="173c4-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="173c4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="173c4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="173c4-120">Principale</span><span class="sxs-lookup"><span data-stu-id="173c4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="173c4-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="173c4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-123">po'</span><span class="sxs-lookup"><span data-stu-id="173c4-123">bit</span></span></p></td>
<td><p><span data-ttu-id="173c4-124">Principale</span><span class="sxs-lookup"><span data-stu-id="173c4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="173c4-125">0: dati del destinatario</span><span class="sxs-lookup"><span data-stu-id="173c4-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="173c4-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="173c4-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-128">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-129">Percentuale della sessione l'evento NetworkSendQuality è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="173c4-130">La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.</span><span class="sxs-lookup"><span data-stu-id="173c4-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-132">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-133">Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="173c4-134">La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="173c4-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-136">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-137">Percentuale della sessione che l'evento Delay è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-138">La latenza della rete è grave e ha un impatto sull'esperienza impedendo comunicazioni interattive</span><span class="sxs-lookup"><span data-stu-id="173c4-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-140">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-141">Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-142">La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="173c4-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-144">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-145">Percentuale della sessione l'evento CPU insufficiente è stato generato per lo stato "non valido".</span><span class="sxs-lookup"><span data-stu-id="173c4-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-146">Sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità e le applicazioni correnti in uso.</span><span class="sxs-lookup"><span data-stu-id="173c4-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="173c4-147">Ciò causa distorsioni con il canale audio.</span><span class="sxs-lookup"><span data-stu-id="173c4-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-149">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-150">Percentuale della sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-151">Per evitare l'eco, il sistema ha immesso half duplex.</span><span class="sxs-lookup"><span data-stu-id="173c4-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-153">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-154">Percentuale della sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-155">Il dispositivo di rendering attualmente in uso per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="173c4-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="173c4-156">Ciò può causare problemi audio unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="173c4-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-158">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-159">Percentuale della sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-160">Il dispositivo di acquisizione attualmente in uso per la sessione non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="173c4-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="173c4-161">Ciò può causare problemi audio unidirezionali.</span><span class="sxs-lookup"><span data-stu-id="173c4-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-163">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-164">Percentuale della sessione l'evento DeviceGlitches è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-165">Il rendering dell'audio causa distorsioni è grave.</span><span class="sxs-lookup"><span data-stu-id="173c4-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="173c4-166">Queste anomalie possono essere causate da problemi di driver, rimandi temporali (DPC), e uso elevato della CPU.</span><span class="sxs-lookup"><span data-stu-id="173c4-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-168">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-169">Percentuale della sessione l'evento DeviceLowSNR è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-170">La qualità di acquisizione è molto povera, molto rumorosa o l'utente sta discutendo troppo lontano dal microfono.</span><span class="sxs-lookup"><span data-stu-id="173c4-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="173c4-171">Questo causerà distorsioni.</span><span class="sxs-lookup"><span data-stu-id="173c4-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-173">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-174">Percentuale della sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-175">Il livello del discorso dell'utente è troppo basso e il sistema non può aumentarlo ulteriormente.</span><span class="sxs-lookup"><span data-stu-id="173c4-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="173c4-176">Ciò può causare distorsioni o percepire l'audio unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="173c4-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-178">Decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-179">Percentuale della sessione l'evento DeviceClipping è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="173c4-180">Quando il microfono termina con la fine del discorso, la distorsione viene pronunciata a causa del ritaglio.</span><span class="sxs-lookup"><span data-stu-id="173c4-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="173c4-181">È importante evitare il ritaglio del microfono vicino alla fine.</span><span class="sxs-lookup"><span data-stu-id="173c4-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-183">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-184">Percentuale della sessione l'evento DeviceEchoEvent è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-185">Il dispositivo o la configurazione sta causando l'eco oltre la capacità del sistema di compensare.</span><span class="sxs-lookup"><span data-stu-id="173c4-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-187">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-188">Percentuale della sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-189">Il discorso dell'utente è troppo basso rispetto all'eco che viene acquisito, che ha un impatto sull'esperienza degli utenti, perché limita la facilità di interruzione di un utente.</span><span class="sxs-lookup"><span data-stu-id="173c4-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="173c4-190">Ridurre il volume dell'altoparlante, posizionare il microfono più vicino all'oratore.</span><span class="sxs-lookup"><span data-stu-id="173c4-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-192">int</span><span class="sxs-lookup"><span data-stu-id="173c4-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="173c4-193">Numero di volte durante la sessione l'evento DeviceMultipleEndpoints è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-194">Più endpoint audio nella stessa sessione rilevati e il sistema ha compensato riducendo il volume di rendering.</span><span class="sxs-lookup"><span data-stu-id="173c4-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-196">int</span><span class="sxs-lookup"><span data-stu-id="173c4-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="173c4-197">Numero di volte durante la sessione l'evento DeviceHowlingEvent è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="173c4-198">Loop di feedback audio rilevato (causato da più endpoint che condividono il percorso audio).</span><span class="sxs-lookup"><span data-stu-id="173c4-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="173c4-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-200">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="173c4-201">Percentuale della sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="173c4-202">Il dispositivo di rendering è stato impostato su zero volume.</span><span class="sxs-lookup"><span data-stu-id="173c4-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="173c4-203">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="173c4-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="173c4-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="173c4-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="173c4-205">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="173c4-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="173c4-206">Percentuale della sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="173c4-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="173c4-207">Il dispositivo di rendering è stato disattivato.</span><span class="sxs-lookup"><span data-stu-id="173c4-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="173c4-208">Questa colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="173c4-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

