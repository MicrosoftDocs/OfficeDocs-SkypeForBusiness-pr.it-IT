---
title: 'Lync Server 2013: rapporto località'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f7db796a4edab00918b0353e9b635f4615ba9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="751fa-102">Report percorso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="751fa-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="751fa-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="751fa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="751fa-p101">Nel Rapporto percorsi vengono fornite informazioni sulla metrica di qualità delle chiamate raggruppata per percorso di rete, ovvero per subnet di rete. Se si verificano problemi con le chiamate degli utenti, questo rapporto consente di determinare se i problemi sono diffusi oppure sono circoscritti a un segmento di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="751fa-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="751fa-106">Accesso al Rapporto percorsi</span><span class="sxs-lookup"><span data-stu-id="751fa-106">Accessing the Location Report</span></span>

<span data-ttu-id="751fa-p102">Il Rapporto percorsi è accessibile dalla home page di Relazioni monitoraggio. È possibile eseguire il drill-down fino al Rapporto Elenco chiamate facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="751fa-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="751fa-109">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="751fa-109">Call volume</span></span>

  - <span data-ttu-id="751fa-110">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="751fa-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="751fa-111">Filtri</span><span class="sxs-lookup"><span data-stu-id="751fa-111">Filters</span></span>

<span data-ttu-id="751fa-p103">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il Rapporto percorsi, ad esempio, consente di filtrare in base alla posizione dalla quale è stata originata una chiamata o a seconda che la chiamata sia stata effettuata utilizzando una connessione wireless o cablata. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="751fa-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="751fa-116">Nella tabella che segue sono elencati i filtri applicabili al Rapporto percorsi.</span><span class="sxs-lookup"><span data-stu-id="751fa-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="751fa-117">Filtri del Rapporto percorsi</span><span class="sxs-lookup"><span data-stu-id="751fa-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="751fa-118">Nome</span><span class="sxs-lookup"><span data-stu-id="751fa-118">Name</span></span></th>
<th><span data-ttu-id="751fa-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="751fa-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="751fa-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p104">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="751fa-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="751fa-123">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="751fa-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="751fa-p105">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="751fa-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="751fa-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="751fa-126">7/7/2012</span></span></p>
<p><span data-ttu-id="751fa-127">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="751fa-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="751fa-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="751fa-128">7/3/2012</span></span></p>
<p><span data-ttu-id="751fa-129">Le settimane vengono calcolate sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="751fa-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p106">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="751fa-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="751fa-133">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="751fa-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="751fa-p107">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="751fa-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="751fa-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="751fa-136">7/7/2012</span></span></p>
<p><span data-ttu-id="751fa-137">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="751fa-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="751fa-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="751fa-138">7/3/2012</span></span></p>
<p><span data-ttu-id="751fa-139">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="751fa-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-140"><strong>Località chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p108">Subnet IP dell'utente che ha effettuato la chiamata. È possibile selezionare solo l'opzione <strong>[Tutto]</strong> per indicare tutte le subnet.</span><span class="sxs-lookup"><span data-stu-id="751fa-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-143"><strong>Località destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p109">Subnet IP dell'utente che ha ricevuto la chiamata. È possibile selezionare solo l'opzione <strong>[Tutto]</strong> per indicare tutte le subnet.</span><span class="sxs-lookup"><span data-stu-id="751fa-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-146"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p110">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="751fa-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="751fa-149">Tutti</span><span class="sxs-lookup"><span data-stu-id="751fa-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="751fa-150">Cablata</span><span class="sxs-lookup"><span data-stu-id="751fa-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="751fa-151">Wireless</span><span class="sxs-lookup"><span data-stu-id="751fa-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-p111">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="751fa-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="751fa-155">Tutti</span><span class="sxs-lookup"><span data-stu-id="751fa-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="751fa-156">VPN</span><span class="sxs-lookup"><span data-stu-id="751fa-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="751fa-157">Non VPN</span><span class="sxs-lookup"><span data-stu-id="751fa-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="751fa-158">Metriche</span><span class="sxs-lookup"><span data-stu-id="751fa-158">Metrics</span></span>

<span data-ttu-id="751fa-159">Nella tabella che segue sono elencate le informazioni fornite nel Rapporto percorsi.</span><span class="sxs-lookup"><span data-stu-id="751fa-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="751fa-160">Metriche del Rapporto percorsi</span><span class="sxs-lookup"><span data-stu-id="751fa-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="751fa-161">Nome</span><span class="sxs-lookup"><span data-stu-id="751fa-161">Name</span></span></th>
<th><span data-ttu-id="751fa-162">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="751fa-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="751fa-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="751fa-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="751fa-164"><strong>Subnet chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-165">No</span><span class="sxs-lookup"><span data-stu-id="751fa-165">No</span></span></p></td>
<td><p><span data-ttu-id="751fa-166">Subnet IP dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="751fa-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-167"><strong>Subnet destinatario chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-168">No</span><span class="sxs-lookup"><span data-stu-id="751fa-168">No</span></span></p></td>
<td><p><span data-ttu-id="751fa-169">Subnet IP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="751fa-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-170"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-171">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-172">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="751fa-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-173"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-174">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p112">Percentuale delle chiamate classificate come insufficienti. Una chiamata insufficiente è una chiamata per la quale almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un'instabilità eccessiva.</span><span class="sxs-lookup"><span data-stu-id="751fa-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-177"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-178">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p113">Tempo medio di roundtrip (in millisecondi) richiesto per il viaggio di andata e ritorno di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 100 millisecondi vengono considerati accettabili.</span><span class="sxs-lookup"><span data-stu-id="751fa-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="751fa-p114">Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="751fa-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-183"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-184">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-185">Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="751fa-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="751fa-186">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="751fa-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="751fa-187">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="751fa-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="751fa-188">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="751fa-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="751fa-189">In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="751fa-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="751fa-p116">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="751fa-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-192"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-193">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p117">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono in genere causate da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un server di contenuti multimediali sovraccarico. La perdita di pacchetti di solito genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="751fa-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-197"><strong>Instabilità</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-198">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-199">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="751fa-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="751fa-200">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="751fa-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-201"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-202">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p119">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="751fa-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="751fa-205"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-206">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p120">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="751fa-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="751fa-209"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="751fa-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="751fa-210">Sì</span><span class="sxs-lookup"><span data-stu-id="751fa-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="751fa-p121">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="751fa-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

