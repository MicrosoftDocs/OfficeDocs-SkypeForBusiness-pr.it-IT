---
title: 'Lync Server 2013: rapporto dettagli chiamata'
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
ms.openlocfilehash: 6ef309873ef51e06903123dfb5a1b6ecf68b4ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502753"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="4dec8-102">Rapporto dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dec8-102">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dec8-103">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4dec8-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4dec8-104">Il rapporto dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata. il report include quasi tutte le metriche e le statistiche relative alla qualità delle esperienze raccolte da Lync Server, divise in sezioni di report, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4dec8-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="4dec8-105">Informazioni chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-105">Call Information</span></span>

  - <span data-ttu-id="4dec8-106">Metrica dispositivi e segnale chiamante</span><span class="sxs-lookup"><span data-stu-id="4dec8-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="4dec8-107">Metrica dispositivi e segnale destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="4dec8-108">Evento client chiamante</span><span class="sxs-lookup"><span data-stu-id="4dec8-108">Caller Client Event</span></span>

  - <span data-ttu-id="4dec8-109">Evento client destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-109">Callee Client Event</span></span>

  - <span data-ttu-id="4dec8-110">Flusso audio (da chiamante a destinatario chiamata)</span><span class="sxs-lookup"><span data-stu-id="4dec8-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="4dec8-111">Flusso video (da chiamante a destinatario chiamata)</span><span class="sxs-lookup"><span data-stu-id="4dec8-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="4dec8-112">Flusso audio (da destinatario chiamata a chiamante)</span><span class="sxs-lookup"><span data-stu-id="4dec8-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="4dec8-113">Flusso video (da destinatario chiamata a chiamante)</span><span class="sxs-lookup"><span data-stu-id="4dec8-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="4dec8-p101">Tenere presente che le categorie e le metriche incluse in un rapporto specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usato nella sessione. Ad esempio in una chiamata solo audio non saranno presenti metriche per i flussi video, in quanto la chiamata non presenta alcun flusso video. Analogamente, si potrebbe avere un rapporto in cui sono elencate statistiche del chiamante ma non del destinatario della chiamata. Questa situazione si verifica generalmente quando il destinatario della chiamata non usa un dispositivo compatibile con SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata, ma ad esempio un telefono cellulare (che non ha nulla a che vedere con SIP o statistiche SIP) non è in grado di produrre un rapporto su questo tipo di informazioni. Se si chiama qualcuno che risponde dal telefono cellulare, non verrà prodotto alcun rapporto da quel telefono al termine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="4dec8-120">Il Rapporto dettagli chiamata risulta utile soprattutto quando si prova a stabilire in modo preciso la causa dei problemi di qualità multimediale in una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="4dec8-121">Accesso al Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="4dec8-122">Si può accedere al Rapporto dettagli chiamata da uno dei rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dec8-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="4dec8-123">Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="4dec8-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dec8-124">Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="4dec8-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dec8-125">Il [rapporto di confronto qualità multimediale in Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (facendo clic sul [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) e quindi scegliendo la metrica dettaglio).</span><span class="sxs-lookup"><span data-stu-id="4dec8-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="4dec8-126">Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate di livello insufficiente)</span><span class="sxs-lookup"><span data-stu-id="4dec8-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="4dec8-127">Il [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) (facendo clic sulla metrica dettaglio)</span><span class="sxs-lookup"><span data-stu-id="4dec8-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="4dec8-128">Dal rapporto dettagli chiamata è possibile accedere al [rapporto dispositivi in Lync Server 2013](lync-server-2013-device-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dec8-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4dec8-129">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="4dec8-129">Capture device</span></span>

  - <span data-ttu-id="4dec8-130">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="4dec8-130">Render device</span></span>

<span data-ttu-id="4dec8-131">È inoltre possibile accedere al Rapporto tendenze qualità multimediale server facendo clic sulla metrica A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="4dec8-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="4dec8-132">Utilizzo ottimale del Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="4dec8-p102">Il Rapporto dettagli chiamata include generalmente oltre 250 metriche diverse, tra cui Deviazione timestamp microfono, Tempo rapporto segnale/rumore basso e Tempo rapporto segnale near-end/eco. Se non si ricorda la misura effettiva di tutte queste metriche, provare a posizionare il mouse sull'etichetta della metrica per visualizzare un a descrizione comando della metrica.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="4dec8-p103">In caso di problemi nell'individuazione di una metrica, digitare parte dell'etichetta della metrica nella casella di ricerca e fare clic su Trova. Se ad esempio non si riesce a trovare la metrica Tempo rapporto segnale/rumore basso, digitare SNR nella casella di ricerca e fare clic su Trova.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="4dec8-137">Tenere presente che il report tiene traccia delle informazioni relative a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="4dec8-138">La chiamata non è registrata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4dec8-139">Filtri</span><span class="sxs-lookup"><span data-stu-id="4dec8-139">Filters</span></span>

<span data-ttu-id="4dec8-p105">Nessuno. Non è possibile applicare filtri nel Rapporto dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4dec8-142">Metriche</span><span class="sxs-lookup"><span data-stu-id="4dec8-142">Metrics</span></span>

<span data-ttu-id="4dec8-143">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto dettagli chiamata per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="4dec8-144">Metrica del Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="4dec8-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dec8-145">Nome</span><span class="sxs-lookup"><span data-stu-id="4dec8-145">Name</span></span></th>
<th><span data-ttu-id="4dec8-146">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="4dec8-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4dec8-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4dec8-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-148"><strong>PAI chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-149">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-149">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-p106">PAI (P-Asserted-Identity) dell'utente che ha avviato la chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-152"><strong>URI chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-153">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-153">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-154">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-155"><strong>Endpoint chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-156">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-156">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-157">Dispositivo utilizzato per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-158"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-159">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-159">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-160">Software utilizzato nel dispositivo con cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-161"><strong>Inizio chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-162">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-162">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-163">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-164"><strong>Chiamata di bypass a Mediation Server</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-165">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-165">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-166">Indica l'eventuale connessione della chiamata a un gateway vocale PSTN o IP-PBX qualificato senza passare attraverso il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4dec8-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-167"><strong>Sistema operativo chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-168">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-168">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-169">Sistema operativo del computer del chiamante.</span><span class="sxs-lookup"><span data-stu-id="4dec8-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-170"><strong>CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-171">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-171">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-172">CPU installata nel computer dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-173"><strong>Numero di core CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-174">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-174">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-175">Numero di processori nel computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-176"><strong>Velocità CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-177">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-177">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-178">Velocità di clock della CPU del computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-179"><strong>Virtualizzazione CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-180">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-180">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-181">Eventuale virtualizzazione nel computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-182"><strong>PAI destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-183">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-183">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-p107">PAI (P-Asserted-Identity) dell'utente che ha inviato l'invito a partecipare alla chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="4dec8-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-186"><strong>URI destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-187">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-187">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-188">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="4dec8-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-189"><strong>Endpoint destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-190">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-190">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-191">Dispositivo utilizzato per ricevere la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-192"><strong>Agente utente destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-193">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-193">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-194">Software utilizzato nel dispositivo con cui è stata ricevuta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-195"><strong>Durata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-196">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-196">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-197">Durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-198"><strong>Flag di avviso bypass multimediale</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-199">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-199">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-200">Avviso generato quando è stato ignorato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4dec8-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-201"><strong>Sistema operativo destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-202">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-202">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-203">Sistema operativo del computer dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="4dec8-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-204"><strong>CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-205">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-205">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-206">CPU installata nel computer dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="4dec8-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-207"><strong>Numero di core CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-208">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-208">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-209">Numero di processori nel computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4dec8-210"><strong>Velocità CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-211">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-211">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-212">Velocità di clock della CPU del computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dec8-213"><strong>Virtualizzazione CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4dec8-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="4dec8-214">No</span><span class="sxs-lookup"><span data-stu-id="4dec8-214">No</span></span></p></td>
<td><p><span data-ttu-id="4dec8-215">Eventuale virtualizzazione nel computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="4dec8-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

