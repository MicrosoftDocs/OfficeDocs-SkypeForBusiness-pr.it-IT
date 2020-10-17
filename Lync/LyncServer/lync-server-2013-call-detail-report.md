---
title: 'Lync Server 2013: rapporto dettagli chiamata'
description: 'Lync Server 2013: rapporto dettagli chiamata.'
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
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561772"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="67dd2-103">Rapporto dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67dd2-103">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67dd2-104">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="67dd2-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="67dd2-105">Il rapporto dettagli chiamata fornisce un'occhiata dettagliata a una singola chiamata. il report include quasi tutte le metriche e le statistiche relative alla qualità delle esperienze raccolte da Lync Server, divise in sezioni di report, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67dd2-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="67dd2-106">Informazioni chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-106">Call Information</span></span>

  - <span data-ttu-id="67dd2-107">Metrica dispositivi e segnale chiamante</span><span class="sxs-lookup"><span data-stu-id="67dd2-107">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="67dd2-108">Metrica dispositivi e segnale destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-108">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="67dd2-109">Evento client chiamante</span><span class="sxs-lookup"><span data-stu-id="67dd2-109">Caller Client Event</span></span>

  - <span data-ttu-id="67dd2-110">Evento client destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-110">Callee Client Event</span></span>

  - <span data-ttu-id="67dd2-111">Flusso audio (da chiamante a destinatario chiamata)</span><span class="sxs-lookup"><span data-stu-id="67dd2-111">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="67dd2-112">Flusso video (da chiamante a destinatario chiamata)</span><span class="sxs-lookup"><span data-stu-id="67dd2-112">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="67dd2-113">Flusso audio (da destinatario chiamata a chiamante)</span><span class="sxs-lookup"><span data-stu-id="67dd2-113">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="67dd2-114">Flusso video (da destinatario chiamata a chiamante)</span><span class="sxs-lookup"><span data-stu-id="67dd2-114">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="67dd2-p101">Tenere presente che le categorie e le metriche incluse in un rapporto specifico dipendono da due fattori: il tipo di sessione e il tipo di endpoint usato nella sessione. Ad esempio in una chiamata solo audio non saranno presenti metriche per i flussi video, in quanto la chiamata non presenta alcun flusso video. Analogamente, si potrebbe avere un rapporto in cui sono elencate statistiche del chiamante ma non del destinatario della chiamata. Questa situazione si verifica generalmente quando il destinatario della chiamata non usa un dispositivo compatibile con SIP. Gli endpoint sono responsabili della segnalazione delle statistiche alla fine di una chiamata, ma ad esempio un telefono cellulare (che non ha nulla a che vedere con SIP o statistiche SIP) non è in grado di produrre un rapporto su questo tipo di informazioni. Se si chiama qualcuno che risponde dal telefono cellulare, non verrà prodotto alcun rapporto da quel telefono al termine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="67dd2-121">Il Rapporto dettagli chiamata risulta utile soprattutto quando si prova a stabilire in modo preciso la causa dei problemi di qualità multimediale in una chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="67dd2-122">Accesso al Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="67dd2-123">Si può accedere al Rapporto dettagli chiamata da uno dei rapporti seguenti:</span><span class="sxs-lookup"><span data-stu-id="67dd2-123">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="67dd2-124">Il [rapporto percorso in Lync Server 2013](lync-server-2013-location-report.md) (facendo clic sul volume delle chiamate o sulla metrica percentuale di chiamata scadente)</span><span class="sxs-lookup"><span data-stu-id="67dd2-124">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="67dd2-125">Il [rapporto riepilogativo sulla qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (facendo clic sulla metrica volume chiamata o percentuale chiamate insufficienti)</span><span class="sxs-lookup"><span data-stu-id="67dd2-125">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="67dd2-126">Il [rapporto di confronto qualità multimediale in Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (facendo clic sul [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) e quindi scegliendo la metrica dettaglio).</span><span class="sxs-lookup"><span data-stu-id="67dd2-126">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="67dd2-127">Il [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica volume chiamata o percentuale di chiamate di livello insufficiente)</span><span class="sxs-lookup"><span data-stu-id="67dd2-127">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="67dd2-128">Il [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) (facendo clic sulla metrica dettaglio)</span><span class="sxs-lookup"><span data-stu-id="67dd2-128">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="67dd2-129">Dal rapporto dettagli chiamata è possibile accedere al [rapporto dispositivi in Lync Server 2013](lync-server-2013-device-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="67dd2-129">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="67dd2-130">Dispositivo di acquisizione</span><span class="sxs-lookup"><span data-stu-id="67dd2-130">Capture device</span></span>

  - <span data-ttu-id="67dd2-131">Dispositivo di rendering</span><span class="sxs-lookup"><span data-stu-id="67dd2-131">Render device</span></span>

<span data-ttu-id="67dd2-132">È inoltre possibile accedere al Rapporto tendenze qualità multimediale server facendo clic sulla metrica A/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="67dd2-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="67dd2-133">Utilizzo ottimale del Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="67dd2-p102">Il Rapporto dettagli chiamata include generalmente oltre 250 metriche diverse, tra cui Deviazione timestamp microfono, Tempo rapporto segnale/rumore basso e Tempo rapporto segnale near-end/eco. Se non si ricorda la misura effettiva di tutte queste metriche, provare a posizionare il mouse sull'etichetta della metrica per visualizzare un a descrizione comando della metrica.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="67dd2-p103">In caso di problemi nell'individuazione di una metrica, digitare parte dell'etichetta della metrica nella casella di ricerca e fare clic su Trova. Se ad esempio non si riesce a trovare la metrica Tempo rapporto segnale/rumore basso, digitare SNR nella casella di ricerca e fare clic su Trova.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="67dd2-138">Tenere presente che il report tiene traccia delle informazioni relative a una chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="67dd2-139">La chiamata non è registrata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-139">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="67dd2-140">Filtri</span><span class="sxs-lookup"><span data-stu-id="67dd2-140">Filters</span></span>

<span data-ttu-id="67dd2-p105">Nessuno. Non è possibile applicare filtri nel Rapporto dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="67dd2-143">Metriche</span><span class="sxs-lookup"><span data-stu-id="67dd2-143">Metrics</span></span>

<span data-ttu-id="67dd2-144">Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto dettagli chiamata per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="67dd2-145">Metrica del Rapporto dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="67dd2-145">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67dd2-146">Nome</span><span class="sxs-lookup"><span data-stu-id="67dd2-146">Name</span></span></th>
<th><span data-ttu-id="67dd2-147">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="67dd2-147">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="67dd2-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67dd2-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-149"><strong>PAI chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-149"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-150">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-150">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-p106">PAI (P-Asserted-Identity) dell'utente che ha avviato la chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-153"><strong>URI chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-153"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-154">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-154">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-155">Indirizzo SIP dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-155">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-156"><strong>Endpoint chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-156"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-157">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-157">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-158">Dispositivo utilizzato per effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-158">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-159"><strong>Agente utente chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-159"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-160">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-160">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-161">Software utilizzato nel dispositivo con cui è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-161">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-162"><strong>Inizio chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-162"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-163">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-163">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-164">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-164">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-165"><strong>Chiamata di bypass a Mediation Server</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-165"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-166">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-166">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-167">Indica l'eventuale connessione della chiamata a un gateway vocale PSTN o IP-PBX qualificato senza passare attraverso il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="67dd2-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-168"><strong>Sistema operativo chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-168"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-169">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-169">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-170">Sistema operativo del computer del chiamante.</span><span class="sxs-lookup"><span data-stu-id="67dd2-170">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-171"><strong>CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-171"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-172">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-172">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-173">CPU installata nel computer dell'utente che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-173">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-174"><strong>Numero di core CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-174"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-175">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-175">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-176">Numero di processori nel computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-176">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-177"><strong>Velocità CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-177"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-178">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-178">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-179">Velocità di clock della CPU del computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-180"><strong>Virtualizzazione CPU chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-180"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-181">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-181">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-182">Eventuale virtualizzazione nel computer utilizzato dalla persona che ha avviato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-183"><strong>PAI destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-183"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-184">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-184">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-p107">PAI (P-Asserted-Identity) dell'utente che ha inviato l'invito a partecipare alla chiamata. Questo valore viene utilizzato per trasmettere l'identità comprovata di un utente in una rete attendibile.</span><span class="sxs-lookup"><span data-stu-id="67dd2-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-187"><strong>URI destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-187"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-188">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-188">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-189">Indirizzo SIP dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="67dd2-189">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-190"><strong>Endpoint destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-190"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-191">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-191">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-192">Dispositivo utilizzato per ricevere la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-192">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-193"><strong>Agente utente destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-193"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-194">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-194">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-195">Software utilizzato nel dispositivo con cui è stata ricevuta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-195">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-196"><strong>Durata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-196"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-197">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-197">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-198">Durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-198">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-199"><strong>Flag di avviso bypass multimediale</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-199"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-200">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-200">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-201">Avviso generato quando è stato ignorato il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="67dd2-201">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-202"><strong>Sistema operativo destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-202"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-203">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-203">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-204">Sistema operativo del computer dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="67dd2-204">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-205"><strong>CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-205"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-206">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-206">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-207">CPU installata nel computer dell'utente chiamato.</span><span class="sxs-lookup"><span data-stu-id="67dd2-207">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-208"><strong>Numero di core CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-208"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-209">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-209">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-210">Numero di processori nel computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-210">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67dd2-211"><strong>Velocità CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-211"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-212">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-212">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-213">Velocità di clock della CPU del computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-213">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67dd2-214"><strong>Virtualizzazione CPU destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="67dd2-214"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="67dd2-215">No</span><span class="sxs-lookup"><span data-stu-id="67dd2-215">No</span></span></p></td>
<td><p><span data-ttu-id="67dd2-216">Eventuale virtualizzazione nel computer utilizzato dalla persona chiamata.</span><span class="sxs-lookup"><span data-stu-id="67dd2-216">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

