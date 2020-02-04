---
title: 'Lync Server 2013: report dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffbfa8c3553b33f75b0f014265f93cccf46e7de6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="7087a-102">Report dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7087a-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7087a-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="7087a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="7087a-104">Il report dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata; il report include quasi tutta la qualità delle metriche delle esperienze e delle statistiche raccolte da Lync Server, suddivise in sezioni di report, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7087a-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="7087a-105">Informazioni sulle chiamate</span><span class="sxs-lookup"><span data-stu-id="7087a-105">Call Information</span></span>

  - <span data-ttu-id="7087a-106">Metriche del segnale e del dispositivo chiamante</span><span class="sxs-lookup"><span data-stu-id="7087a-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="7087a-107">Dispositivo chiamato e metriche del segnale</span><span class="sxs-lookup"><span data-stu-id="7087a-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="7087a-108">Evento del client chiamante</span><span class="sxs-lookup"><span data-stu-id="7087a-108">Caller Client Event</span></span>

  - <span data-ttu-id="7087a-109">Evento client chiamato</span><span class="sxs-lookup"><span data-stu-id="7087a-109">Callee Client Event</span></span>

  - <span data-ttu-id="7087a-110">Flusso audio (chiamante)</span><span class="sxs-lookup"><span data-stu-id="7087a-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="7087a-111">Flusso video (chiamante)</span><span class="sxs-lookup"><span data-stu-id="7087a-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="7087a-112">Flusso audio (chiamato dal chiamante)</span><span class="sxs-lookup"><span data-stu-id="7087a-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="7087a-113">Flusso video (chiamato dal chiamante)</span><span class="sxs-lookup"><span data-stu-id="7087a-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="7087a-114">Tieni presente che le categorie e le metriche visualizzate in un report specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usati nella sessione.</span><span class="sxs-lookup"><span data-stu-id="7087a-114">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session.</span></span> <span data-ttu-id="7087a-115">Ad esempio, una chiamata solo audio non riporta le metriche per i flussi video; Questo perché la chiamata non ha un flusso video.</span><span class="sxs-lookup"><span data-stu-id="7087a-115">For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream.</span></span> <span data-ttu-id="7087a-116">Analogamente, è possibile che sia presente un report che elenca le statistiche del chiamante ma non le statistiche chiamate.</span><span class="sxs-lookup"><span data-stu-id="7087a-116">Likewise, you might have a report that lists caller statistics but not callee statistics.</span></span> <span data-ttu-id="7087a-117">In genere perché il destinatario non usa un dispositivo conforme a SIP.</span><span class="sxs-lookup"><span data-stu-id="7087a-117">That's typically because the callee was not using a SIP-compliant device.</span></span> <span data-ttu-id="7087a-118">Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata; Tuttavia, un cellulare (che non conosce le statistiche SIP o SIP) non è in grado di segnalare questo tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="7087a-118">Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information.</span></span> <span data-ttu-id="7087a-119">Se si chiama qualcuno e si risponde al telefono cellulare, non si riceverà un report dal telefono cellulare al termine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-119">If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="7087a-120">Il report dettagli chiamata è molto utile quando si prova a determinare esattamente il motivo per cui una determinata chiamata ha riscontrato problemi di qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="7087a-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="7087a-121">Accesso al report dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="7087a-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="7087a-122">È possibile accedere al report dettagli chiamata da uno dei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="7087a-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="7087a-123">[Report posizione in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="7087a-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="7087a-124">[Report di riepilogo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="7087a-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="7087a-125">[Report di confronto qualità multimediale in Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (fare clic sul [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) e quindi fare clic sulla metrica dettaglio).</span><span class="sxs-lookup"><span data-stu-id="7087a-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="7087a-126">[Report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sul volume delle chiamate o sulla metrica della percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="7087a-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="7087a-127">[Report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) (facendo clic sulla metrica dettaglio)</span><span class="sxs-lookup"><span data-stu-id="7087a-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="7087a-128">Dall'interno del report dettagli chiamata è possibile accedere al [report del dispositivo in Lync Server 2013](lync-server-2013-device-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="7087a-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7087a-129">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="7087a-129">Capture device</span></span>

  - <span data-ttu-id="7087a-130">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="7087a-130">Render device</span></span>

<span data-ttu-id="7087a-131">È anche possibile accedere al report trend qualità media del server facendo clic sulla metrica A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="7087a-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="7087a-132">Sfruttare al meglio il report dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="7087a-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="7087a-133">Il report dettagli chiamata in genere include più di 250 metriche diverse, inclusi elementi come la deriva del timestamp del microfono, l'ora bassa di SNR e la fine del tempo di Echo.</span><span class="sxs-lookup"><span data-stu-id="7087a-133">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time.</span></span> <span data-ttu-id="7087a-134">Se non si riesce a ricordare ciò che tutte queste metriche effettivamente misurano, provare a tenere il mouse sopra l'etichetta metrica; spesso, viene visualizzata una descrizione comando che descrive la metrica.</span><span class="sxs-lookup"><span data-stu-id="7087a-134">If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="7087a-135">In caso di problemi con l'individuazione di una metrica, digitare parte dell'etichetta metrica nella casella di ricerca e quindi fare clic su trova.</span><span class="sxs-lookup"><span data-stu-id="7087a-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="7087a-136">Ad esempio, se non si riesce a trovare la metrica per l'ora bassa SNR, digitare SNR nella casella di ricerca e quindi fare clic su trova.</span><span class="sxs-lookup"><span data-stu-id="7087a-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="7087a-137">Tieni presente che il report tiene traccia solo delle informazioni su una chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="7087a-138">La chiamata stessa non viene registrata.</span><span class="sxs-lookup"><span data-stu-id="7087a-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7087a-139">Filtri</span><span class="sxs-lookup"><span data-stu-id="7087a-139">Filters</span></span>

<span data-ttu-id="7087a-140">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7087a-140">None.</span></span> <span data-ttu-id="7087a-141">Non è possibile filtrare il report dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-141">You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7087a-142">Metriche</span><span class="sxs-lookup"><span data-stu-id="7087a-142">Metrics</span></span>

<span data-ttu-id="7087a-143">Nella tabella seguente sono elencate le informazioni fornite nel report dettagli chiamata per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="7087a-144">Metriche report dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="7087a-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7087a-145">Nome</span><span class="sxs-lookup"><span data-stu-id="7087a-145">Name</span></span></th>
<th><span data-ttu-id="7087a-146">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="7087a-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7087a-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7087a-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7087a-148"><strong>Chiamante PAI</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-149">No</span><span class="sxs-lookup"><span data-stu-id="7087a-149">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-150">P-asserzione-identità dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-150">P-Asserted-Identity of the user who initiated the call.</span></span> <span data-ttu-id="7087a-151">La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="7087a-151">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-152"><strong>URI chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-153">No</span><span class="sxs-lookup"><span data-stu-id="7087a-153">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-154">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-155"><strong>Endpoint chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-156">No</span><span class="sxs-lookup"><span data-stu-id="7087a-156">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-157">Dispositivo usato per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-158"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-159">No</span><span class="sxs-lookup"><span data-stu-id="7087a-159">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-160">Software usato nel dispositivo che ha eseguito la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-161"><strong>Inizio chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-162">No</span><span class="sxs-lookup"><span data-stu-id="7087a-162">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-163">Data e ora in cui la chiamata è stata inizialmente inserita.</span><span class="sxs-lookup"><span data-stu-id="7087a-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-164"><strong>Chiamata di bypass di Mediation Server</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-165">No</span><span class="sxs-lookup"><span data-stu-id="7087a-165">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-166">Indica se la chiamata è connessa a un gateway vocale PSTN o a un IP-PBX qualificato senza passare tramite Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7087a-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-167"><strong>Sistema operativo chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-168">No</span><span class="sxs-lookup"><span data-stu-id="7087a-168">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-169">Sistema operativo del computer del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7087a-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-170"><strong>CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-171">No</span><span class="sxs-lookup"><span data-stu-id="7087a-171">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-172">CPU installata nel computer dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-173"><strong>Numero di core della CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-174">No</span><span class="sxs-lookup"><span data-stu-id="7087a-174">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-175">Numero del processore nel computer usato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-176"><strong>Velocità della CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-177">No</span><span class="sxs-lookup"><span data-stu-id="7087a-177">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-178">Velocità di clock della CPU del computer usato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-179"><strong>Virtualizzazione della CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-180">No</span><span class="sxs-lookup"><span data-stu-id="7087a-180">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-181">Virtualizzazione (se presenti) usata nel computer usato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-182"><strong>Chiamata PAI</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-183">No</span><span class="sxs-lookup"><span data-stu-id="7087a-183">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-184">P-asserzione-identità dell'utente invitato a partecipare alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-184">P-Asserted-Identity of the user who was invited to join the call.</span></span> <span data-ttu-id="7087a-185">La P-Asserted-Identity viene usata per trasmettere l'identità comprovata di un utente all'interno di una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="7087a-185">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-186"><strong>URI chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-187">No</span><span class="sxs-lookup"><span data-stu-id="7087a-187">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-188">Indirizzo SIP dell'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7087a-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-189"><strong>Endpoint chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-190">No</span><span class="sxs-lookup"><span data-stu-id="7087a-190">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-191">Dispositivo usato per ricevere la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-192"><strong>Agente utente chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-193">No</span><span class="sxs-lookup"><span data-stu-id="7087a-193">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-194">Software usato nel dispositivo che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-195"><strong>Durata</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-196">No</span><span class="sxs-lookup"><span data-stu-id="7087a-196">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-197">Intervallo di tempo per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-198"><strong>Contrassegno di avviso di bypass multimediale</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-199">No</span><span class="sxs-lookup"><span data-stu-id="7087a-199">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-200">Avviso emesso quando il Mediation Server è stato ignorato.</span><span class="sxs-lookup"><span data-stu-id="7087a-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-201"><strong>Sistema operativo chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-202">No</span><span class="sxs-lookup"><span data-stu-id="7087a-202">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-203">Sistema operativo del computer per l'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7087a-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-204"><strong>CPU chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-205">No</span><span class="sxs-lookup"><span data-stu-id="7087a-205">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-206">CPU installata nel computer dell'utente che è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="7087a-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-207"><strong>Numero di nucleo chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-208">No</span><span class="sxs-lookup"><span data-stu-id="7087a-208">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-209">Numero del processore nel computer usato dalla persona che è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7087a-210"><strong>Velocità della CPU chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-211">No</span><span class="sxs-lookup"><span data-stu-id="7087a-211">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-212">Velocità di clock della CPU del computer usato dalla persona che è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7087a-213"><strong>Virtualizzazione della CPU chiamato</strong></span><span class="sxs-lookup"><span data-stu-id="7087a-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="7087a-214">No</span><span class="sxs-lookup"><span data-stu-id="7087a-214">No</span></span></p></td>
<td><p><span data-ttu-id="7087a-215">Virtualizzazione (se presenti) usata nel computer usato dalla persona che è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="7087a-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

