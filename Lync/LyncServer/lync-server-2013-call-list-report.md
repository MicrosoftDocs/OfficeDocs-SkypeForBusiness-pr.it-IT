---
title: 'Lync Server 2013: rapporto elenco chiamate'
description: 'Lync Server 2013: rapporto elenco chiamate.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561692"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="8c303-103">Rapporto elenco chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c303-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c303-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8c303-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8c303-105">Il rapporto Elenco chiamate offre metriche QoE (Quality of Experience) per le singole chiamate effettuate e ricevute nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c303-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="8c303-106">Tenere presente che le metriche effettive riportate dipendono dalla modalità di accesso al rapporto Elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="8c303-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="8c303-107">Ad esempio, se si apre il report del rapporto [dispositivo in Lync Server 2013](lync-server-2013-device-report.md), vengono visualizzate le metriche, quali le metriche seguenti, che sono state segnalate anche nel rapporto dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8c303-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="8c303-108">Microfono del chiamante</span><span class="sxs-lookup"><span data-stu-id="8c303-108">Caller's microphone</span></span>

  - <span data-ttu-id="8c303-109">Altoparlante del chiamante</span><span class="sxs-lookup"><span data-stu-id="8c303-109">Caller's speaker</span></span>

  - <span data-ttu-id="8c303-110">Microfono del chiamato</span><span class="sxs-lookup"><span data-stu-id="8c303-110">Callee's microphone</span></span>

  - <span data-ttu-id="8c303-111">Altoparlante del chiamato</span><span class="sxs-lookup"><span data-stu-id="8c303-111">Callee's speaker</span></span>

  - <span data-ttu-id="8c303-112">Rapporto di tempo commutazione vocale</span><span class="sxs-lookup"><span data-stu-id="8c303-112">Ratio of voice switch time</span></span>

<span data-ttu-id="8c303-113">Tuttavia, se si apre il rapporto elenco chiamate dal [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md), non verrà visualizzata alcuna di queste metriche. si vedranno invece metriche come queste:</span><span class="sxs-lookup"><span data-stu-id="8c303-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="8c303-114">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="8c303-114">Round trip (ms)</span></span>

  - <span data-ttu-id="8c303-115">Degradazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="8c303-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="8c303-116">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="8c303-116">Packet loss</span></span>

  - <span data-ttu-id="8c303-117">Instabilità (ms)</span><span class="sxs-lookup"><span data-stu-id="8c303-117">Jitter (ms)</span></span>

<span data-ttu-id="8c303-p102">Si tratta delle metriche riportate nel Rapporto percorsi. Tuttavia, nel rapporto Elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per ottenere informazioni di QoE complete per qualsiasi chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="8c303-120">Accesso al rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="8c303-120">Accessing the Call List Report</span></span>

<span data-ttu-id="8c303-121">Il rapporto Elenco chiamate è accessibile da qualsiasi dei rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c303-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="8c303-122">Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="8c303-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="8c303-123">Il [rapporto del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="8c303-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="8c303-124">Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="8c303-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="8c303-125">Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="8c303-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="8c303-126">Dall'interno del rapporto elenco chiamate è possibile accedere al [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) facendo clic sulla metrica Dettagli.</span><span class="sxs-lookup"><span data-stu-id="8c303-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="8c303-127">Uso ottimale del rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="8c303-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="8c303-128">Se non si è certi del tipo di misurazioni offerte dalle metriche del rapporto Elenco chiamate (ad esempio il rapporto di tempo di commutazione vocale), tenere il puntatore del mouse sull'etichetta per visualizzare una descrizione comandi con informazioni sintetiche sulla metrica in questione.</span><span class="sxs-lookup"><span data-stu-id="8c303-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8c303-129">Filtri</span><span class="sxs-lookup"><span data-stu-id="8c303-129">Filters</span></span>

<span data-ttu-id="8c303-p103">Nessuno. Non è possibile filtrare il rapporto Elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="8c303-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8c303-132">Metriche</span><span class="sxs-lookup"><span data-stu-id="8c303-132">Metrics</span></span>

<span data-ttu-id="8c303-133">La tabella seguente elenca le informazioni disponibili nel rapporto Elenco chiamate per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="8c303-134">Metriche del rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="8c303-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c303-135">Nome</span><span class="sxs-lookup"><span data-stu-id="8c303-135">Name</span></span></th>
<th><span data-ttu-id="8c303-136">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="8c303-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8c303-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c303-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c303-138"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-139">No</span><span class="sxs-lookup"><span data-stu-id="8c303-139">No</span></span></p></td>
<td><p><span data-ttu-id="8c303-140">Facendo clic su questo elemento è possibile visualizzare ulteriori informazioni sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-141"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-142">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-143">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-144"><strong>Destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-145">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-146">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="8c303-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-147"><strong>Ora inizio</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-148">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-149">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-150"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-151">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-152">Data e ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-153"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-154">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-155">Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-156"><strong>Agente utente destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-157">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-158">Software utilizzato dall'endpoint dell'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="8c303-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-159"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-160">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p104">Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.</span><span class="sxs-lookup"><span data-stu-id="8c303-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8c303-p105">Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="8c303-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-165"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-166">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-167">Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="8c303-168">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="8c303-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="8c303-169">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="8c303-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="8c303-170">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="8c303-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="8c303-171">In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c303-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="8c303-p107">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="8c303-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-174"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-175">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p108">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="8c303-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-179"><strong>Instabilità</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-180">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-181">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="8c303-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8c303-182">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="8c303-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-183"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-184">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p110">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="8c303-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-187"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-188">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p111">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="8c303-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c303-191"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-192">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p112">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="8c303-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c303-195"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="8c303-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="8c303-196">Sì</span><span class="sxs-lookup"><span data-stu-id="8c303-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="8c303-p113">Tipo di collegamento di comunicazione wireless. In genere è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c303-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8c303-199">Relè</span><span class="sxs-lookup"><span data-stu-id="8c303-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="8c303-200">Diretto</span><span class="sxs-lookup"><span data-stu-id="8c303-200">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

