---
title: 'Lync Server 2013: report sulle prestazioni del server'
description: 'Lync Server 2013: report sulle prestazioni del server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aed9b3b9eeec4487dce4d401df0d70ffba89677b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543342"
---
# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="797f7-103">Report sulle prestazioni del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="797f7-103">Server Performance Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="797f7-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="797f7-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="797f7-105">Il report sulle prestazioni del server fornisce un elenco dei server Microsoft Lync Server 2013 che hanno riscontrato la percentuale più bassa di chiamate scadenti.</span><span class="sxs-lookup"><span data-stu-id="797f7-105">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="797f7-106">Nel rapporto i server sono suddivisi in base al tipo in modo da riportare statistiche distinte per quelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-106">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="797f7-107">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="797f7-107">Mediation Server</span></span>

  - <span data-ttu-id="797f7-108">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="797f7-108">A/V Conferencing Server</span></span>

  - <span data-ttu-id="797f7-109">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="797f7-109">A/V Edge Server</span></span>

  - <span data-ttu-id="797f7-110">Gateway (Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="797f7-110">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="797f7-111">Gateway (bypass a Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="797f7-111">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="797f7-112">Video (incluse le metriche video per A/V Conferencing Server e A/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="797f7-112">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="797f7-113">Condivisione applicazioni (incluse le metriche di condivisione applicazioni per A/V Conferencing Server e A/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="797f7-113">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="797f7-p102">È importante notare che le classificazioni illustrate in questo rapporto sono relative. Supponiamo ad esempio che il server con le prestazioni peggiori presenti una chiamata di livello insufficiente su 1.000 chiamate effettuate. Si tratta della più che accettabile percentuale dello 0,1%. Se questo è il server con le prestazioni peggiori (ovvero se tutti gli altri server presentano percentuali di chiamate di livello insufficiente inferiori a 0,1%), tale server verrà comunque incluso nel Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="797f7-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="797f7-118">Accesso al Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="797f7-118">Accessing the Server Performance Report</span></span>

<span data-ttu-id="797f7-119">Il Rapporto prestazioni dei server è accessibile dalla home page Rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="797f7-119">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="797f7-120">È possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="797f7-121">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="797f7-121">Call volume</span></span>

  - <span data-ttu-id="797f7-122">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="797f7-122">Poor call percentage</span></span>

<span data-ttu-id="797f7-123">È inoltre possibile eseguire il drill-down al Rapporto tendenze qualità multimediale server facendo clic sulla metrica seguente:</span><span class="sxs-lookup"><span data-stu-id="797f7-123">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="797f7-124">Tendenza</span><span class="sxs-lookup"><span data-stu-id="797f7-124">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="797f7-125">Uso ottimale del Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="797f7-125">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="797f7-p104">Il Rapporto prestazioni dei server offre diversi modi per filtrare i dati; ad esempio è possibile filtrare per tipo di rete (chiamate effettuate da una connessione cablata rispetto a quelle effettuate da una connessione wireless) e tipo di accesso (chiamate effettuate dall'interno del firewall rispetto a quelle effettuate dall'esterno del firewall). Quando si esamina il rapporto sulle prestazioni dei server, è consigliabile fare uso di questi filtri. Si supponga ad esempio di disporre di un Mediation Server con una percentuale di chiamate di livello insufficiente del 3,24%. Se si osservano esclusivamente le chiamate wireless, lo stesso server presenta una percentuale di chiamate di livello insufficiente prossimo al 20%. Ciò significa che il server presenta difficoltà con le chiamate wireless, problema parzialmente nascosto dal fatto che il server non presenta problemi con le chiamate cablate.</span><span class="sxs-lookup"><span data-stu-id="797f7-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="797f7-131">Filtri</span><span class="sxs-lookup"><span data-stu-id="797f7-131">Filters</span></span>

<span data-ttu-id="797f7-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto prestazioni dei server consente di filtrare i dati restituiti in base al tipo di server o al tipo di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dati sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="797f7-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="797f7-136">Nella tabella seguente sono elencati i filtri applicabili al Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="797f7-136">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="797f7-137">Filtri del Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="797f7-137">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="797f7-138">Nome</span><span class="sxs-lookup"><span data-stu-id="797f7-138">Name</span></span></th>
<th><span data-ttu-id="797f7-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="797f7-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="797f7-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p106">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="797f7-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="797f7-143">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="797f7-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="797f7-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="797f7-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="797f7-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="797f7-146">7/7/2012</span></span></p>
<p><span data-ttu-id="797f7-147">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="797f7-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="797f7-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="797f7-148">7/3/2012</span></span></p>
<p><span data-ttu-id="797f7-149">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="797f7-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p108">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="797f7-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="797f7-153">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="797f7-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="797f7-p109">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="797f7-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="797f7-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="797f7-156">7/7/2012</span></span></p>
<p><span data-ttu-id="797f7-157">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="797f7-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="797f7-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="797f7-158">7/3/2012</span></span></p>
<p><span data-ttu-id="797f7-159">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="797f7-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-160"><strong>Tipo di server</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-160"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p110">Indica il tipo di server di cui eseguire il rapporto sulle prestazioni. Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="797f7-163">Tutti</span><span class="sxs-lookup"><span data-stu-id="797f7-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="797f7-164">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="797f7-164">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="797f7-165">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="797f7-165">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="797f7-166">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="797f7-166">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-167"><strong>Primi N elementi</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-167"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p111">Indica il numero di server, in base alla percentuale di chiamate di livello insufficiente, da visualizzare in ogni categoria. Se ad esempio si seleziona <strong>5</strong> verranno visualizzati i cinque server con le prestazioni peggiori. Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="797f7-171">Tutti</span><span class="sxs-lookup"><span data-stu-id="797f7-171">[All]</span></span></p></li>
<li><p><span data-ttu-id="797f7-172">5 </span><span class="sxs-lookup"><span data-stu-id="797f7-172">5</span></span></p></li>
<li><p><span data-ttu-id="797f7-173">10  </span><span class="sxs-lookup"><span data-stu-id="797f7-173">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-174"><strong>Tipo di accesso </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-174"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p112">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="797f7-177">Tutti</span><span class="sxs-lookup"><span data-stu-id="797f7-177">[All]</span></span></p></li>
<li><p><span data-ttu-id="797f7-178">Interno</span><span class="sxs-lookup"><span data-stu-id="797f7-178">Internal</span></span></p></li>
<li><p><span data-ttu-id="797f7-179">Esterno</span><span class="sxs-lookup"><span data-stu-id="797f7-179">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-180"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-180"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p113">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="797f7-183">Tutti</span><span class="sxs-lookup"><span data-stu-id="797f7-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="797f7-184">Cablata</span><span class="sxs-lookup"><span data-stu-id="797f7-184">Wired</span></span></p></li>
<li><p><span data-ttu-id="797f7-185">Wireless</span><span class="sxs-lookup"><span data-stu-id="797f7-185">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-186"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-186"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-p114">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="797f7-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="797f7-189">Tutti</span><span class="sxs-lookup"><span data-stu-id="797f7-189">[All]</span></span></p></li>
<li><p><span data-ttu-id="797f7-190">VPN</span><span class="sxs-lookup"><span data-stu-id="797f7-190">VPN</span></span></p></li>
<li><p><span data-ttu-id="797f7-191">Non VPN</span><span class="sxs-lookup"><span data-stu-id="797f7-191">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="797f7-192">Metriche</span><span class="sxs-lookup"><span data-stu-id="797f7-192">Metrics</span></span>

<span data-ttu-id="797f7-193">La tabella seguente elenca le informazioni disponibili nel Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="797f7-193">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="797f7-194">Metriche del Rapporto prestazioni dei server: riepilogo delle chiamate audio</span><span class="sxs-lookup"><span data-stu-id="797f7-194">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="797f7-195">Nome</span><span class="sxs-lookup"><span data-stu-id="797f7-195">Name</span></span></th>
<th><span data-ttu-id="797f7-196">Possibilità di ordinamento</span><span class="sxs-lookup"><span data-stu-id="797f7-196">Can Sort On</span></span></th>
<th><span data-ttu-id="797f7-197">Descrizione</span><span class="sxs-lookup"><span data-stu-id="797f7-197">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="797f7-198"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-198"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-199">No</span><span class="sxs-lookup"><span data-stu-id="797f7-199">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-200">Nome/indirizzo IP del server.</span><span class="sxs-lookup"><span data-stu-id="797f7-200">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-201"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-201"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-202">No</span><span class="sxs-lookup"><span data-stu-id="797f7-202">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-203">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="797f7-203">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-204"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-204"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-205">No</span><span class="sxs-lookup"><span data-stu-id="797f7-205">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p115">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="797f7-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-208"><strong>Roundtrip (ms) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-208"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-209">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-p116">Tempo medio di roundtrip, in millisecondi, necessario per un pacchetto RTP (Real-Time Transport Protocol) per viaggiare fino a un altro endpoint e tornare indietro. Un roundtrip di 100 millisecondi o meno è considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="797f7-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="797f7-p117">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="797f7-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-214"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-214"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-215">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-216">Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="797f7-216">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="797f7-217">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="797f7-217">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="797f7-218">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="797f7-218">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="797f7-219">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="797f7-219">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="797f7-220">In Lync Server, il Monitoring Server utilizza un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="797f7-220">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="797f7-p119">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="797f7-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-223"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-223"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-224">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-224">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-p120">Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="797f7-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-228"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-228"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-229">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-230">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="797f7-230">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="797f7-231">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="797f7-231">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-232"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-232"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-233">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-p122">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="797f7-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-236"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-236"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-237">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-p123">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="797f7-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-240"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-240"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-241">Sì</span><span class="sxs-lookup"><span data-stu-id="797f7-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="797f7-p124">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="797f7-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="797f7-244">Metriche del Rapporto prestazioni dei server: riepilogo delle videochiamate</span><span class="sxs-lookup"><span data-stu-id="797f7-244">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="797f7-245">Nome</span><span class="sxs-lookup"><span data-stu-id="797f7-245">Name</span></span></th>
<th><span data-ttu-id="797f7-246">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="797f7-246">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="797f7-247">Descrizione</span><span class="sxs-lookup"><span data-stu-id="797f7-247">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="797f7-248"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-248"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-249">No</span><span class="sxs-lookup"><span data-stu-id="797f7-249">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p125">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="797f7-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="797f7-252">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="797f7-252">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="797f7-253">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="797f7-253">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="797f7-254">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="797f7-254">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="797f7-255">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="797f7-255">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="797f7-256">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="797f7-256">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="797f7-257">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="797f7-257">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="797f7-258">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="797f7-258">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-259"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-259"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-260">No</span><span class="sxs-lookup"><span data-stu-id="797f7-260">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-261">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="797f7-261">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-262"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-262"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-263">No</span><span class="sxs-lookup"><span data-stu-id="797f7-263">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p126">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="797f7-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-266"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-266"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-267">No</span><span class="sxs-lookup"><span data-stu-id="797f7-267">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-268">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="797f7-268">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-269"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-269"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-270">No</span><span class="sxs-lookup"><span data-stu-id="797f7-270">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-271">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="797f7-271">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-272"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-272"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-273">No</span><span class="sxs-lookup"><span data-stu-id="797f7-273">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-274">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="797f7-274">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-275"><strong>Velocità media in bit (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-275"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-276">No</span><span class="sxs-lookup"><span data-stu-id="797f7-276">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-277">Velocità in bit video media (in kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="797f7-277">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-278"><strong>Bassa velocità in bit (%)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-278"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-279">No</span><span class="sxs-lookup"><span data-stu-id="797f7-279">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-280">Percentuale della chiamata con velocità in bit bassa.</span><span class="sxs-lookup"><span data-stu-id="797f7-280">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-281"><strong>Perdita di pacchetti in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-281"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-282">No</span><span class="sxs-lookup"><span data-stu-id="797f7-282">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p127">Perdita di pacchetti RTP (Real-Time Transport Protocol) in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="797f7-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-286"><strong>% fotogrammi bloccati</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-286"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-287">No</span><span class="sxs-lookup"><span data-stu-id="797f7-287">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p128">Percentuale di fotogrammi “bloccati”. In un fotogramma bloccato, il video smette di avanzare mentre la parte audio della chiamata prosegue.</span><span class="sxs-lookup"><span data-stu-id="797f7-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-290"><strong>Frequenza media dei fotogrammi in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-290"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-291">No</span><span class="sxs-lookup"><span data-stu-id="797f7-291">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-292">Frequenza media dei fotogrammi per le trasmissioni in uscita durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="797f7-292">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-293"><strong>Frequenza media dei fotogrammi in ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-293"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-294">No</span><span class="sxs-lookup"><span data-stu-id="797f7-294">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-295">Frequenza media dei fotogrammi per le trasmissioni in arrivo durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="797f7-295">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-296"><strong>Bassa frequenza dei fotogrammi in ingresso (%)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-296"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-297">No</span><span class="sxs-lookup"><span data-stu-id="797f7-297">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-298">Percentuale della chiamata con velocità in bit bassa per il video in arrivo.</span><span class="sxs-lookup"><span data-stu-id="797f7-298">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-299"><strong>Integrità client (%)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-299"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="797f7-300">Indica l'integrità relativa del dispositivo client durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="797f7-300">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="797f7-301">Metriche del Rapporto prestazioni dei server: riepilogo delle chiamate di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="797f7-301">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="797f7-302">Nome</span><span class="sxs-lookup"><span data-stu-id="797f7-302">Name</span></span></th>
<th><span data-ttu-id="797f7-303">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="797f7-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="797f7-304">Descrizione</span><span class="sxs-lookup"><span data-stu-id="797f7-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="797f7-305"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-305"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-306">No</span><span class="sxs-lookup"><span data-stu-id="797f7-306">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p129">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="797f7-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="797f7-309">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="797f7-309">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="797f7-310">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="797f7-310">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="797f7-311">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="797f7-311">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="797f7-312">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="797f7-312">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="797f7-313">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="797f7-313">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="797f7-314">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="797f7-314">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="797f7-315">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="797f7-315">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-316"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-316"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-317">No</span><span class="sxs-lookup"><span data-stu-id="797f7-317">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-318">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="797f7-318">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-319"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-319"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-320">No</span><span class="sxs-lookup"><span data-stu-id="797f7-320">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p130">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="797f7-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-323"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-323"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-324">No</span><span class="sxs-lookup"><span data-stu-id="797f7-324">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-325">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="797f7-325">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-326"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-326"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-327">No</span><span class="sxs-lookup"><span data-stu-id="797f7-327">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-328">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="797f7-328">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-329"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="797f7-329"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-330">No</span><span class="sxs-lookup"><span data-stu-id="797f7-330">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-331">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="797f7-331">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-332"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-332"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-333">No</span><span class="sxs-lookup"><span data-stu-id="797f7-333">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-334">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="797f7-334">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="797f7-335">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="797f7-335">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-336"><strong>Media unidirezionale relativa</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-336"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-337">No</span><span class="sxs-lookup"><span data-stu-id="797f7-337">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p132">Media unidirezionale relativa tra due endpoint multimediali. Si tratta di una misurazione della latenza a singolo hop.</span><span class="sxs-lookup"><span data-stu-id="797f7-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="797f7-340"><strong>Latenza media elaborazione sezioni RDP</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-340"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-341">No</span><span class="sxs-lookup"><span data-stu-id="797f7-341">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-p133">Latenza media dell'elaborazione delle sezioni RDP in AS Conferencing Server per la durata della sessione di visualizzazione. Questa metrica non copre la latenza di rete. Una media elevata riflette ritardi maggiori nell'esperienza di visualizzazione. In un server per conferenze sovraccaricato possono verificarsi ritardi medi maggiori.</span><span class="sxs-lookup"><span data-stu-id="797f7-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="797f7-346"><strong>% totale sezioni danneggiate</strong></span><span class="sxs-lookup"><span data-stu-id="797f7-346"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="797f7-347">No</span><span class="sxs-lookup"><span data-stu-id="797f7-347">No</span></span></p></td>
<td><p><span data-ttu-id="797f7-348">Percentuale totale di sezioni RDP danneggiate.</span><span class="sxs-lookup"><span data-stu-id="797f7-348">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

