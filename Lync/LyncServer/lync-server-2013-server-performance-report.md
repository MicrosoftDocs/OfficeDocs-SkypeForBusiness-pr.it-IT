---
title: 'Lync Server 2013: report sulle prestazioni del server'
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
ms.openlocfilehash: e60757721a9244a55e7ce341be6834934108858a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="4a780-102">Report sulle prestazioni del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a780-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a780-103">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4a780-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4a780-104">Il report sulle prestazioni del server fornisce un elenco dei server Microsoft Lync Server 2013 che hanno riscontrato la percentuale più bassa di chiamate scadenti.</span><span class="sxs-lookup"><span data-stu-id="4a780-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="4a780-105">Nel rapporto i server sono suddivisi in base al tipo in modo da riportare statistiche distinte per quelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="4a780-106">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="4a780-106">Mediation Server</span></span>

  - <span data-ttu-id="4a780-107">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="4a780-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="4a780-108">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="4a780-108">A/V Edge Server</span></span>

  - <span data-ttu-id="4a780-109">Gateway (Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="4a780-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="4a780-110">Gateway (bypass a Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="4a780-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="4a780-111">Video (incluse le metriche video per A/V Conferencing Server e A/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="4a780-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="4a780-112">Condivisione applicazioni (incluse le metriche di condivisione applicazioni per A/V Conferencing Server e A/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="4a780-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="4a780-p102">È importante notare che le classificazioni illustrate in questo rapporto sono relative. Supponiamo ad esempio che il server con le prestazioni peggiori presenti una chiamata di livello insufficiente su 1.000 chiamate effettuate. Si tratta della più che accettabile percentuale dello 0,1%. Se questo è il server con le prestazioni peggiori (ovvero se tutti gli altri server presentano percentuali di chiamate di livello insufficiente inferiori a 0,1%), tale server verrà comunque incluso nel Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="4a780-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="4a780-117">Accesso al Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="4a780-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="4a780-118">Il Rapporto prestazioni dei server è accessibile dalla home page Rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4a780-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4a780-119">È possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4a780-120">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="4a780-120">Call volume</span></span>

  - <span data-ttu-id="4a780-121">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="4a780-121">Poor call percentage</span></span>

<span data-ttu-id="4a780-122">È inoltre possibile eseguire il drill-down al Rapporto tendenze qualità multimediale server facendo clic sulla metrica seguente:</span><span class="sxs-lookup"><span data-stu-id="4a780-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="4a780-123">Tendenza</span><span class="sxs-lookup"><span data-stu-id="4a780-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="4a780-124">Uso ottimale del Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="4a780-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="4a780-p104">Il Rapporto prestazioni dei server offre diversi modi per filtrare i dati; ad esempio è possibile filtrare per tipo di rete (chiamate effettuate da una connessione cablata rispetto a quelle effettuate da una connessione wireless) e tipo di accesso (chiamate effettuate dall'interno del firewall rispetto a quelle effettuate dall'esterno del firewall). Quando si esamina il rapporto sulle prestazioni dei server, è consigliabile fare uso di questi filtri. Si supponga ad esempio di disporre di un Mediation Server con una percentuale di chiamate di livello insufficiente del 3,24%. Se si osservano esclusivamente le chiamate wireless, lo stesso server presenta una percentuale di chiamate di livello insufficiente prossimo al 20%. Ciò significa che il server presenta difficoltà con le chiamate wireless, problema parzialmente nascosto dal fatto che il server non presenta problemi con le chiamate cablate.</span><span class="sxs-lookup"><span data-stu-id="4a780-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4a780-130">Filtri</span><span class="sxs-lookup"><span data-stu-id="4a780-130">Filters</span></span>

<span data-ttu-id="4a780-p105">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto prestazioni dei server consente di filtrare i dati restituiti in base al tipo di server o al tipo di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso i dati sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="4a780-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4a780-135">Nella tabella seguente sono elencati i filtri applicabili al Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="4a780-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="4a780-136">Filtri del Rapporto prestazioni dei server</span><span class="sxs-lookup"><span data-stu-id="4a780-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a780-137">Name</span><span class="sxs-lookup"><span data-stu-id="4a780-137">Name</span></span></th>
<th><span data-ttu-id="4a780-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a780-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a780-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p106">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="4a780-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4a780-142">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="4a780-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4a780-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="4a780-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4a780-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4a780-145">7/7/2012</span></span></p>
<p><span data-ttu-id="4a780-146">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="4a780-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4a780-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4a780-147">7/3/2012</span></span></p>
<p><span data-ttu-id="4a780-148">Le settimane vengono calcolate sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="4a780-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p108">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="4a780-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4a780-152">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="4a780-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4a780-p109">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="4a780-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4a780-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4a780-155">7/7/2012</span></span></p>
<p><span data-ttu-id="4a780-156">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="4a780-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4a780-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4a780-157">7/3/2012</span></span></p>
<p><span data-ttu-id="4a780-158">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="4a780-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-159"><strong>Tipo di server</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p110">Indica il tipo di server di cui eseguire il rapporto sulle prestazioni. Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4a780-162">Tutti</span><span class="sxs-lookup"><span data-stu-id="4a780-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="4a780-163">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="4a780-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="4a780-164">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="4a780-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="4a780-165">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="4a780-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-166"><strong>Primi N elementi</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p111">Indica il numero di server, in base alla percentuale di chiamate di livello insufficiente, da visualizzare in ogni categoria. Se ad esempio si seleziona <strong>5</strong> verranno visualizzati i cinque server con le prestazioni peggiori. Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4a780-170">Tutti</span><span class="sxs-lookup"><span data-stu-id="4a780-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="4a780-171">5 </span><span class="sxs-lookup"><span data-stu-id="4a780-171">5</span></span></p></li>
<li><p><span data-ttu-id="4a780-172">10 </span><span class="sxs-lookup"><span data-stu-id="4a780-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-173"><strong>Tipo di accesso </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p112">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4a780-176">Tutti</span><span class="sxs-lookup"><span data-stu-id="4a780-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="4a780-177">Interna</span><span class="sxs-lookup"><span data-stu-id="4a780-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="4a780-178">Esterna</span><span class="sxs-lookup"><span data-stu-id="4a780-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-179"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p113">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4a780-182">Tutti</span><span class="sxs-lookup"><span data-stu-id="4a780-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="4a780-183">Cablata</span><span class="sxs-lookup"><span data-stu-id="4a780-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="4a780-184">Wireless</span><span class="sxs-lookup"><span data-stu-id="4a780-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-p114">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a780-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4a780-188">Tutti</span><span class="sxs-lookup"><span data-stu-id="4a780-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="4a780-189">VPN</span><span class="sxs-lookup"><span data-stu-id="4a780-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="4a780-190">Non VPN</span><span class="sxs-lookup"><span data-stu-id="4a780-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4a780-191">Metriche</span><span class="sxs-lookup"><span data-stu-id="4a780-191">Metrics</span></span>

<span data-ttu-id="4a780-192">La tabella seguente elenca le informazioni disponibili nel Rapporto prestazioni dei server.</span><span class="sxs-lookup"><span data-stu-id="4a780-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="4a780-193">Metriche del Rapporto prestazioni dei server: riepilogo delle chiamate audio</span><span class="sxs-lookup"><span data-stu-id="4a780-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a780-194">Name</span><span class="sxs-lookup"><span data-stu-id="4a780-194">Name</span></span></th>
<th><span data-ttu-id="4a780-195">Possibilità di ordinamento</span><span class="sxs-lookup"><span data-stu-id="4a780-195">Can Sort On</span></span></th>
<th><span data-ttu-id="4a780-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a780-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a780-197"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-198">No</span><span class="sxs-lookup"><span data-stu-id="4a780-198">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-199">Nome/indirizzo IP del server.</span><span class="sxs-lookup"><span data-stu-id="4a780-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-200"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-201">No</span><span class="sxs-lookup"><span data-stu-id="4a780-201">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-202">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="4a780-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-203"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-204">No</span><span class="sxs-lookup"><span data-stu-id="4a780-204">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p115">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="4a780-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-207"><strong>Roundtrip (ms) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-208">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-p116">Tempo medio di roundtrip, in millisecondi, necessario per un pacchetto RTP (Real-Time Transport Protocol) per viaggiare fino a un altro endpoint e tornare indietro. Un roundtrip di 100 millisecondi o meno è considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="4a780-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="4a780-p117">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="4a780-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-213"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-214">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-215">Valore medio di degradazione MOS (Mean Opinion Score) osservata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a780-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="4a780-216">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="4a780-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="4a780-217">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="4a780-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="4a780-218">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="4a780-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="4a780-219">In Lync Server, il Monitoring Server utilizza un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a780-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="4a780-p119">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="4a780-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-222"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-223">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-p120">Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="4a780-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-227"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-228">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-229">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="4a780-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4a780-230">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="4a780-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-231"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-232">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-p122">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="4a780-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-235"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-236">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-p123">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="4a780-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-239"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-240">Sì</span><span class="sxs-lookup"><span data-stu-id="4a780-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="4a780-p124">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="4a780-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="4a780-243">Metriche del Rapporto prestazioni dei server: riepilogo delle videochiamate</span><span class="sxs-lookup"><span data-stu-id="4a780-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a780-244">Name</span><span class="sxs-lookup"><span data-stu-id="4a780-244">Name</span></span></th>
<th><span data-ttu-id="4a780-245">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="4a780-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4a780-246">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a780-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a780-247"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-248">No</span><span class="sxs-lookup"><span data-stu-id="4a780-248">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p125">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="4a780-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a780-251">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="4a780-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4a780-252">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="4a780-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4a780-253">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="4a780-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4a780-254">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4a780-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4a780-255">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="4a780-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4a780-256">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="4a780-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4a780-257">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="4a780-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-258"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-259">No</span><span class="sxs-lookup"><span data-stu-id="4a780-259">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-260">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="4a780-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-261"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-262">No</span><span class="sxs-lookup"><span data-stu-id="4a780-262">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p126">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="4a780-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-265"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-266">No</span><span class="sxs-lookup"><span data-stu-id="4a780-266">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-267">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="4a780-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-268"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-269">No</span><span class="sxs-lookup"><span data-stu-id="4a780-269">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-270">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="4a780-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-271"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-272">No</span><span class="sxs-lookup"><span data-stu-id="4a780-272">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-273">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="4a780-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-274"><strong>Velocità media in bit (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-275">No</span><span class="sxs-lookup"><span data-stu-id="4a780-275">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-276">Velocità in bit video media (in kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="4a780-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-277"><strong>Bassa velocità in bit (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-278">No</span><span class="sxs-lookup"><span data-stu-id="4a780-278">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-279">Percentuale della chiamata con velocità in bit bassa.</span><span class="sxs-lookup"><span data-stu-id="4a780-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-280"><strong>Perdita di pacchetti in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-281">No</span><span class="sxs-lookup"><span data-stu-id="4a780-281">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p127">Perdita di pacchetti RTP (Real-Time Transport Protocol) in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="4a780-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-285"><strong>% fotogrammi bloccati</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-286">No</span><span class="sxs-lookup"><span data-stu-id="4a780-286">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p128">Percentuale di fotogrammi “bloccati”. In un fotogramma bloccato, il video smette di avanzare mentre la parte audio della chiamata prosegue.</span><span class="sxs-lookup"><span data-stu-id="4a780-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-289"><strong>Frequenza media dei fotogrammi in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-290">No</span><span class="sxs-lookup"><span data-stu-id="4a780-290">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-291">Frequenza media dei fotogrammi per le trasmissioni in uscita durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a780-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-292"><strong>Frequenza media dei fotogrammi in ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-293">No</span><span class="sxs-lookup"><span data-stu-id="4a780-293">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-294">Frequenza media dei fotogrammi per le trasmissioni in arrivo durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a780-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-295"><strong>Bassa frequenza dei fotogrammi in ingresso (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-296">No</span><span class="sxs-lookup"><span data-stu-id="4a780-296">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-297">Percentuale della chiamata con velocità in bit bassa per il video in arrivo.</span><span class="sxs-lookup"><span data-stu-id="4a780-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-298"><strong>Integrità client (%)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a780-299">Indica l'integrità relativa del dispositivo client durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a780-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="4a780-300">Metriche del Rapporto prestazioni dei server: riepilogo delle chiamate di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="4a780-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a780-301">Name</span><span class="sxs-lookup"><span data-stu-id="4a780-301">Name</span></span></th>
<th><span data-ttu-id="4a780-302">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="4a780-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4a780-303">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a780-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a780-304"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-305">No</span><span class="sxs-lookup"><span data-stu-id="4a780-305">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p129">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="4a780-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a780-308">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="4a780-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="4a780-309">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="4a780-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4a780-310">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="4a780-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="4a780-311">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4a780-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="4a780-312">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="4a780-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="4a780-313">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="4a780-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="4a780-314">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="4a780-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-315"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-316">No</span><span class="sxs-lookup"><span data-stu-id="4a780-316">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-317">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="4a780-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-318"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-319">No</span><span class="sxs-lookup"><span data-stu-id="4a780-319">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p130">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="4a780-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-322"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-323">No</span><span class="sxs-lookup"><span data-stu-id="4a780-323">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-324">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="4a780-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-325"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-326">No</span><span class="sxs-lookup"><span data-stu-id="4a780-326">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-327">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="4a780-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-328"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="4a780-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-329">No</span><span class="sxs-lookup"><span data-stu-id="4a780-329">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-330">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="4a780-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-331"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-332">No</span><span class="sxs-lookup"><span data-stu-id="4a780-332">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-333">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="4a780-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="4a780-334">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="4a780-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-335"><strong>Media unidirezionale relativa</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-336">No</span><span class="sxs-lookup"><span data-stu-id="4a780-336">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p132">Media unidirezionale relativa tra due endpoint multimediali. Si tratta di una misurazione della latenza a singolo hop.</span><span class="sxs-lookup"><span data-stu-id="4a780-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a780-339"><strong>Latenza media elaborazione sezioni RDP</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-340">No</span><span class="sxs-lookup"><span data-stu-id="4a780-340">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-p133">Latenza media dell'elaborazione delle sezioni RDP in AS Conferencing Server per la durata della sessione di visualizzazione. Questa metrica non copre la latenza di rete. Una media elevata riflette ritardi maggiori nell'esperienza di visualizzazione. In un server per conferenze sovraccaricato possono verificarsi ritardi medi maggiori.</span><span class="sxs-lookup"><span data-stu-id="4a780-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a780-345"><strong>% totale sezioni danneggiate</strong></span><span class="sxs-lookup"><span data-stu-id="4a780-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="4a780-346">No</span><span class="sxs-lookup"><span data-stu-id="4a780-346">No</span></span></p></td>
<td><p><span data-ttu-id="4a780-347">Percentuale totale di sezioni RDP danneggiate.</span><span class="sxs-lookup"><span data-stu-id="4a780-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

