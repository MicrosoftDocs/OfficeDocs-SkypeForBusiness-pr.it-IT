---
title: 'Lync Server 2013: report elenco chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="2c51c-102">Report elenco chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c51c-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c51c-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2c51c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2c51c-104">Il report elenco chiamate offre metriche di qualità delle esperienze (QoE) per le singole chiamate effettuate e ricevute nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c51c-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="2c51c-105">Tieni presente che le metriche effettive segnalate dipendono dalla modalità di accesso al report elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c51c-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="2c51c-106">Ad esempio, se si apre il report dal [report dispositivo in Lync Server 2013](lync-server-2013-device-report.md), verranno visualizzate le metriche, come le metriche seguenti, che vengono anche segnalate nel report del dispositivo:</span><span class="sxs-lookup"><span data-stu-id="2c51c-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="2c51c-107">Microfono del chiamante</span><span class="sxs-lookup"><span data-stu-id="2c51c-107">Caller's microphone</span></span>

  - <span data-ttu-id="2c51c-108">Altoparlante del chiamante</span><span class="sxs-lookup"><span data-stu-id="2c51c-108">Caller's speaker</span></span>

  - <span data-ttu-id="2c51c-109">Microfono del destinatario</span><span class="sxs-lookup"><span data-stu-id="2c51c-109">Callee's microphone</span></span>

  - <span data-ttu-id="2c51c-110">Altoparlante del destinatario</span><span class="sxs-lookup"><span data-stu-id="2c51c-110">Callee's speaker</span></span>

  - <span data-ttu-id="2c51c-111">Rapporto tra il tempo di cambio vocale</span><span class="sxs-lookup"><span data-stu-id="2c51c-111">Ratio of voice switch time</span></span>

<span data-ttu-id="2c51c-112">Tuttavia, se si apre il report elenco chiamate dal [report posizione in Lync Server 2013](lync-server-2013-location-report.md), non verrà visualizzata alcuna di queste metriche. vedrai invece le metriche come queste:</span><span class="sxs-lookup"><span data-stu-id="2c51c-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="2c51c-113">Andata e ritorno (MS)</span><span class="sxs-lookup"><span data-stu-id="2c51c-113">Round trip (ms)</span></span>

  - <span data-ttu-id="2c51c-114">Degradazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="2c51c-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="2c51c-115">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="2c51c-115">Packet loss</span></span>

  - <span data-ttu-id="2c51c-116">Jitter (MS)</span><span class="sxs-lookup"><span data-stu-id="2c51c-116">Jitter (ms)</span></span>

<span data-ttu-id="2c51c-117">Queste sono le metriche segnalate nel report posizione.</span><span class="sxs-lookup"><span data-stu-id="2c51c-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="2c51c-118">Tuttavia, dal report elenco chiamate è sempre possibile fare clic sulla metrica Dettagli per specificare le informazioni QoE complete per qualsiasi chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="2c51c-119">Accesso al report elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="2c51c-119">Accessing the Call List Report</span></span>

<span data-ttu-id="2c51c-120">È possibile accedere al report elenco chiamate da uno dei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c51c-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="2c51c-121">[Report posizione in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="2c51c-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2c51c-122">Il [report del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="2c51c-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2c51c-123">[Report di riepilogo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="2c51c-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="2c51c-124">[Report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="2c51c-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="2c51c-125">Dall'interno del report elenco chiamate è possibile accedere al [report dettagli chiamata in Lync Server 2013](lync-server-2013-call-detail-report.md) facendo clic sulla metrica dettaglio.</span><span class="sxs-lookup"><span data-stu-id="2c51c-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="2c51c-126">Sfruttare al meglio il report elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="2c51c-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="2c51c-127">Se non si ricordano le metriche del rapporto elenco chiamate (ad esempio il tempo di cambio di rapporto vocale), tenere il mouse sopra l'etichetta metrica; verrà visualizzata una descrizione comando che consente di visualizzare brevemente la metrica.</span><span class="sxs-lookup"><span data-stu-id="2c51c-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2c51c-128">Filtri</span><span class="sxs-lookup"><span data-stu-id="2c51c-128">Filters</span></span>

<span data-ttu-id="2c51c-129">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2c51c-129">None.</span></span> <span data-ttu-id="2c51c-130">Non è possibile filtrare il report elenco chiamate.</span><span class="sxs-lookup"><span data-stu-id="2c51c-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2c51c-131">Metriche</span><span class="sxs-lookup"><span data-stu-id="2c51c-131">Metrics</span></span>

<span data-ttu-id="2c51c-132">Nella tabella seguente sono elencate le informazioni fornite nel report elenco chiamate per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="2c51c-133">Metriche rapporto elenco chiamate</span><span class="sxs-lookup"><span data-stu-id="2c51c-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c51c-134">Nome</span><span class="sxs-lookup"><span data-stu-id="2c51c-134">Name</span></span></th>
<th><span data-ttu-id="2c51c-135">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="2c51c-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2c51c-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c51c-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-137"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-138">No</span><span class="sxs-lookup"><span data-stu-id="2c51c-138">No</span></span></p></td>
<td><p><span data-ttu-id="2c51c-139">Quando si fa clic su questo elemento, nel report vengono visualizzate altre informazioni sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-140"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-141">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-142">Indirizzo SIP della persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-143"><strong>Chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-144">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-145">Indirizzo SIP della persona che è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-146"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-147">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-148">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-149"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-150">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-151">Data e ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-152"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-153">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-154">Software usato dall'endpoint della persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-155"><strong>Agente utente chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-156">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-157">Software usato dall'endpoint della persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-158"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-159">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-160">Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="2c51c-160">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="2c51c-161">I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="2c51c-161">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2c51c-162">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload.</span><span class="sxs-lookup"><span data-stu-id="2c51c-162">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="2c51c-163">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="2c51c-163">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-164"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-165">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-166">Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2c51c-167">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0.</span><span class="sxs-lookup"><span data-stu-id="2c51c-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2c51c-168">Un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="2c51c-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2c51c-169">Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="2c51c-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2c51c-170">In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="2c51c-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2c51c-171">I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="2c51c-171">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="2c51c-172">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="2c51c-172">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-173"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-174">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-175">Tasso medio di perdita di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="2c51c-175">Average rate of RTP packet loss.</span></span> <span data-ttu-id="2c51c-176">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="2c51c-176">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="2c51c-177">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="2c51c-177">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-178"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-179">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-180">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="2c51c-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2c51c-181">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="2c51c-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-182"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-183">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-184">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="2c51c-184">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="2c51c-185">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="2c51c-185">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-186"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-187">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-188">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="2c51c-188">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="2c51c-189">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="2c51c-189">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c51c-190"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-191">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-192">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="2c51c-192">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="2c51c-193">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="2c51c-193">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c51c-194"><strong>Connettività</strong></span><span class="sxs-lookup"><span data-stu-id="2c51c-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="2c51c-195">Sì</span><span class="sxs-lookup"><span data-stu-id="2c51c-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="2c51c-196">Tipo di collegamento di comunicazione wireless.</span><span class="sxs-lookup"><span data-stu-id="2c51c-196">Type of wireless communication link.</span></span> <span data-ttu-id="2c51c-197">In genere, questa è una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c51c-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c51c-198">Inoltro</span><span class="sxs-lookup"><span data-stu-id="2c51c-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="2c51c-199">Diretto</span><span class="sxs-lookup"><span data-stu-id="2c51c-199">Direct</span></span></p></li>
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

