---
title: 'Lync Server 2013: rapporto elenco chiamate'
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
ms.openlocfilehash: 06486ddc8d84c165422e7f4ffea9bb62be5dd683
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="81336-102">Rapporto elenco chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81336-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81336-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="81336-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="81336-104">Il rapporto Elenco chiamate offre metriche QoE (Quality of Experience) per le singole chiamate effettuate e ricevute nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="81336-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="81336-105">Tenere presente che le metriche effettive riportate dipendono dalla modalità di accesso al rapporto Elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="81336-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="81336-106">Ad esempio, se si apre il report del rapporto [dispositivo in Lync Server 2013](lync-server-2013-device-report.md), vengono visualizzate le metriche, quali le metriche seguenti, che sono state segnalate anche nel rapporto dispositivo:</span><span class="sxs-lookup"><span data-stu-id="81336-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="81336-107">Microfono del chiamante</span><span class="sxs-lookup"><span data-stu-id="81336-107">Caller's microphone</span></span>

  - <span data-ttu-id="81336-108">Altoparlante del chiamante</span><span class="sxs-lookup"><span data-stu-id="81336-108">Caller's speaker</span></span>

  - <span data-ttu-id="81336-109">Microfono del chiamato</span><span class="sxs-lookup"><span data-stu-id="81336-109">Callee's microphone</span></span>

  - <span data-ttu-id="81336-110">Altoparlante del chiamato</span><span class="sxs-lookup"><span data-stu-id="81336-110">Callee's speaker</span></span>

  - <span data-ttu-id="81336-111">Rapporto di tempo commutazione vocale</span><span class="sxs-lookup"><span data-stu-id="81336-111">Ratio of voice switch time</span></span>

<span data-ttu-id="81336-112">Tuttavia, se si apre il rapporto elenco chiamate dal [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md), non verrà visualizzata alcuna di queste metriche. si vedranno invece metriche come queste:</span><span class="sxs-lookup"><span data-stu-id="81336-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="81336-113">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="81336-113">Round trip (ms)</span></span>

  - <span data-ttu-id="81336-114">Degradazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="81336-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="81336-115">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="81336-115">Packet loss</span></span>

  - <span data-ttu-id="81336-116">Instabilità (ms)</span><span class="sxs-lookup"><span data-stu-id="81336-116">Jitter (ms)</span></span>

<span data-ttu-id="81336-p102">Si tratta delle metriche riportate nel Rapporto percorsi. Tuttavia, nel rapporto Elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per ottenere informazioni di QoE complete per qualsiasi chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="81336-119">Accesso al rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="81336-119">Accessing the Call List Report</span></span>

<span data-ttu-id="81336-120">Il rapporto Elenco chiamate è accessibile da qualsiasi dei rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="81336-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="81336-121">Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="81336-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="81336-122">Il [rapporto del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="81336-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="81336-123">Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="81336-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="81336-124">Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="81336-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="81336-125">Dall'interno del rapporto elenco chiamate è possibile accedere al [rapporto dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) facendo clic sulla metrica Dettagli.</span><span class="sxs-lookup"><span data-stu-id="81336-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="81336-126">Uso ottimale del rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="81336-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="81336-127">Se non si è certi del tipo di misurazioni offerte dalle metriche del rapporto Elenco chiamate (ad esempio il rapporto di tempo di commutazione vocale), tenere il puntatore del mouse sull'etichetta per visualizzare una descrizione comandi con informazioni sintetiche sulla metrica in questione.</span><span class="sxs-lookup"><span data-stu-id="81336-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="81336-128">Filtri</span><span class="sxs-lookup"><span data-stu-id="81336-128">Filters</span></span>

<span data-ttu-id="81336-p103">Nessuno. Non è possibile filtrare il rapporto Elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="81336-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="81336-131">Metriche</span><span class="sxs-lookup"><span data-stu-id="81336-131">Metrics</span></span>

<span data-ttu-id="81336-132">La tabella seguente elenca le informazioni disponibili nel rapporto Elenco chiamate per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="81336-133">Metriche del rapporto Elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="81336-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81336-134">Name</span><span class="sxs-lookup"><span data-stu-id="81336-134">Name</span></span></th>
<th><span data-ttu-id="81336-135">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="81336-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="81336-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81336-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81336-137"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="81336-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-138">No</span><span class="sxs-lookup"><span data-stu-id="81336-138">No</span></span></p></td>
<td><p><span data-ttu-id="81336-139">Facendo clic su questo elemento è possibile visualizzare ulteriori informazioni sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-140"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="81336-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-141">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-142">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-143"><strong>Destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="81336-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-144">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-145">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="81336-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-146"><strong>Ora inizio</strong></span><span class="sxs-lookup"><span data-stu-id="81336-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-147">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-148">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-149"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="81336-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-150">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-151">Data e ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-152"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="81336-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-153">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-154">Software utilizzato dall'endpoint dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-155"><strong>Agente utente destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="81336-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-156">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-157">Software utilizzato dall'endpoint dell'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="81336-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-158"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="81336-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-159">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p104">Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.</span><span class="sxs-lookup"><span data-stu-id="81336-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="81336-p105">Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="81336-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-164"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="81336-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-165">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-166">Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="81336-167">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="81336-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="81336-168">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="81336-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="81336-169">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="81336-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="81336-170">In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="81336-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="81336-p107">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="81336-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-173"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="81336-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-174">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p108">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="81336-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-178"><strong>Instabilità</strong></span><span class="sxs-lookup"><span data-stu-id="81336-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-179">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-180">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="81336-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="81336-181">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="81336-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-182"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="81336-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-183">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p110">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="81336-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-186"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="81336-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-187">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p111">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="81336-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81336-190"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="81336-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-191">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p112">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="81336-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81336-194"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="81336-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="81336-195">Sì</span><span class="sxs-lookup"><span data-stu-id="81336-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="81336-p113">Tipo di collegamento di comunicazione wireless. In genere è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="81336-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="81336-198">Relè</span><span class="sxs-lookup"><span data-stu-id="81336-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="81336-199">Diretto</span><span class="sxs-lookup"><span data-stu-id="81336-199">Direct</span></span></p></li>
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

