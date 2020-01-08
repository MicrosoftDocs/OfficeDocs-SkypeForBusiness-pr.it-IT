---
title: 'Lync Server 2013: report sulle prestazioni del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="29e50-102">Report prestazioni server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29e50-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29e50-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="29e50-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="29e50-104">Il report prestazioni server include un elenco dei server di Microsoft Lync Server 2013 che hanno sperimentato la percentuale più alta di chiamate scadenti.</span><span class="sxs-lookup"><span data-stu-id="29e50-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="29e50-105">Il report suddivide i server per tipo di server, segnalando statistiche separate per i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="29e50-106">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="29e50-106">Mediation Server</span></span>

  - <span data-ttu-id="29e50-107">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="29e50-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="29e50-108">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="29e50-108">A/V Edge Server</span></span>

  - <span data-ttu-id="29e50-109">Gateway (Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="29e50-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="29e50-110">Gateway (bypass Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="29e50-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="29e50-111">Video (incluse le metriche video per i server di servizi di conferenza A/V e i/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="29e50-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="29e50-112">Condivisione di applicazioni (incluse le metriche di condivisione delle applicazioni per i server di servizi di conferenza A/V e i/V Edge Server)</span><span class="sxs-lookup"><span data-stu-id="29e50-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="29e50-113">È importante notare che la classificazione mostrata in questo report è come classifica relativa.</span><span class="sxs-lookup"><span data-stu-id="29e50-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="29e50-114">Supponiamo ad esempio che il server con prestazioni peggiori abbia una chiamata scadente tra le chiamate a 1.000.</span><span class="sxs-lookup"><span data-stu-id="29e50-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="29e50-115">È una percentuale più che accettabile di 1%.</span><span class="sxs-lookup"><span data-stu-id="29e50-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="29e50-116">Tuttavia, se questo è il server più performante che hai (ovvero, se tutti gli altri server hanno una percentuale di chiamata scadente anche inferiore a .1%), il server continuerà a essere visualizzato nel report sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="29e50-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="29e50-117">Accesso al report sulle prestazioni del server</span><span class="sxs-lookup"><span data-stu-id="29e50-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="29e50-118">Il report prestazioni server è accessibile dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="29e50-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="29e50-119">È possibile eseguire il drill-down nel [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="29e50-120">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="29e50-120">Call volume</span></span>

  - <span data-ttu-id="29e50-121">Percentuale di chiamata scadente</span><span class="sxs-lookup"><span data-stu-id="29e50-121">Poor call percentage</span></span>

<span data-ttu-id="29e50-122">È inoltre possibile eseguire il drill-down per il report trend qualità media del server facendo clic sulla metrica seguente:</span><span class="sxs-lookup"><span data-stu-id="29e50-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="29e50-123">Tendenza</span><span class="sxs-lookup"><span data-stu-id="29e50-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="29e50-124">Uso ottimale del report sulle prestazioni del server</span><span class="sxs-lookup"><span data-stu-id="29e50-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="29e50-125">Il report prestazioni server offre diversi modi per filtrare i dati. ad esempio, è possibile filtrare in base al tipo di rete (chiamate effettuate da una connessione cablata e chiamate effettuate da una connessione wireless) e il tipo di accesso (chiamate effettuate dall'interno del firewall e dalle chiamate effettuate dall'esterno del firewall).</span><span class="sxs-lookup"><span data-stu-id="29e50-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="29e50-126">È una buona idea quando si Visualizza il report sulle prestazioni del server per usare questi filtri.</span><span class="sxs-lookup"><span data-stu-id="29e50-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="29e50-127">Supponiamo ad esempio di avere un Mediation Server con una percentuale di chiamata scadente pari a 3,24%.</span><span class="sxs-lookup"><span data-stu-id="29e50-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="29e50-128">Se si osservano solo le chiamate wireless, lo stesso server potrebbe avere una percentuale di chiamata scadente che si avvicina al 20%.</span><span class="sxs-lookup"><span data-stu-id="29e50-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="29e50-129">Ciò significa che il server ha avuto difficoltà con le chiamate wireless, un problema parzialmente oscurato perché il server non aveva problemi con le chiamate cablate.</span><span class="sxs-lookup"><span data-stu-id="29e50-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="29e50-130">Filtri</span><span class="sxs-lookup"><span data-stu-id="29e50-130">Filters</span></span>

<span data-ttu-id="29e50-131">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="29e50-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="29e50-132">Il report sulle prestazioni del server, ad esempio, consente di eseguire operazioni come filtrare i dati restituiti per tipo di server o per tipo di rete (cablata o wireless).</span><span class="sxs-lookup"><span data-stu-id="29e50-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="29e50-133">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="29e50-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="29e50-134">In questo caso, i dati vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="29e50-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="29e50-135">Nella tabella seguente sono elencati i filtri che è possibile usare con il report prestazioni server.</span><span class="sxs-lookup"><span data-stu-id="29e50-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="29e50-136">Filtri dei report sulle prestazioni del server</span><span class="sxs-lookup"><span data-stu-id="29e50-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29e50-137">Nome</span><span class="sxs-lookup"><span data-stu-id="29e50-137">Name</span></span></th>
<th><span data-ttu-id="29e50-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29e50-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e50-139"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-140">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="29e50-140">Start date/time for the time range.</span></span> <span data-ttu-id="29e50-141">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29e50-141">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="29e50-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="29e50-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="29e50-143">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="29e50-143">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="29e50-144">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="29e50-144">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="29e50-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="29e50-145">7/7/2012</span></span></p>
<p><span data-ttu-id="29e50-146">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="29e50-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="29e50-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="29e50-147">7/3/2012</span></span></p>
<p><span data-ttu-id="29e50-148">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="29e50-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-149"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-150">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="29e50-150">End date/time for the time range.</span></span> <span data-ttu-id="29e50-151">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="29e50-151">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="29e50-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="29e50-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="29e50-153">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="29e50-153">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="29e50-154">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="29e50-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="29e50-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="29e50-155">7/7/2012</span></span></p>
<p><span data-ttu-id="29e50-156">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="29e50-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="29e50-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="29e50-157">7/3/2012</span></span></p>
<p><span data-ttu-id="29e50-158">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="29e50-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-159"><strong>Tipo di server</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-160">Indica il tipo di server di cui devono essere segnalate le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="29e50-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="29e50-161">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="29e50-162">Tutti</span><span class="sxs-lookup"><span data-stu-id="29e50-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="29e50-163">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="29e50-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="29e50-164">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="29e50-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="29e50-165">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="29e50-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-166"><strong>Inizio N</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-167">Indica il numero di server (in base alla percentuale di chiamate) da visualizzare in ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="29e50-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="29e50-168">Ad esempio, se si seleziona <strong>5</strong> , vengono visualizzati i cinque server con prestazioni più scarse.</span><span class="sxs-lookup"><span data-stu-id="29e50-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="29e50-169">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="29e50-170">Tutti</span><span class="sxs-lookup"><span data-stu-id="29e50-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="29e50-171">5</span><span class="sxs-lookup"><span data-stu-id="29e50-171">5</span></span></p></li>
<li><p><span data-ttu-id="29e50-172">10</span><span class="sxs-lookup"><span data-stu-id="29e50-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-173"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-174">Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-174">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="29e50-175">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-175">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="29e50-176">Tutti</span><span class="sxs-lookup"><span data-stu-id="29e50-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="29e50-177">Interno</span><span class="sxs-lookup"><span data-stu-id="29e50-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="29e50-178">Esterno</span><span class="sxs-lookup"><span data-stu-id="29e50-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-179"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-180">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-180">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="29e50-181">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-181">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="29e50-182">Tutti</span><span class="sxs-lookup"><span data-stu-id="29e50-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="29e50-183">Cablata</span><span class="sxs-lookup"><span data-stu-id="29e50-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="29e50-184">Wireless</span><span class="sxs-lookup"><span data-stu-id="29e50-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-186">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="29e50-186">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="29e50-187">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="29e50-187">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="29e50-188">Tutti</span><span class="sxs-lookup"><span data-stu-id="29e50-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="29e50-189">VPN</span><span class="sxs-lookup"><span data-stu-id="29e50-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="29e50-190">Non VPN</span><span class="sxs-lookup"><span data-stu-id="29e50-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="29e50-191">Metriche</span><span class="sxs-lookup"><span data-stu-id="29e50-191">Metrics</span></span>

<span data-ttu-id="29e50-192">Nella tabella seguente sono elencate le informazioni fornite nel report sulle prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="29e50-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="29e50-193">Metriche del report sulle prestazioni del server: riepilogo delle chiamate audio</span><span class="sxs-lookup"><span data-stu-id="29e50-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29e50-194">Nome</span><span class="sxs-lookup"><span data-stu-id="29e50-194">Name</span></span></th>
<th><span data-ttu-id="29e50-195">Può ordinare in base a</span><span class="sxs-lookup"><span data-stu-id="29e50-195">Can Sort On</span></span></th>
<th><span data-ttu-id="29e50-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29e50-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e50-197"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-198">No</span><span class="sxs-lookup"><span data-stu-id="29e50-198">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-199">Nome/indirizzo IP del server.</span><span class="sxs-lookup"><span data-stu-id="29e50-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-200"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-201">No</span><span class="sxs-lookup"><span data-stu-id="29e50-201">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-202">Numero totale di chiamate effettuate.</span><span class="sxs-lookup"><span data-stu-id="29e50-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-203"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-204">No</span><span class="sxs-lookup"><span data-stu-id="29e50-204">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-205">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="29e50-205">Total number of calls classified as poor.</span></span> <span data-ttu-id="29e50-206">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="29e50-206">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-207"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-208">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-209">Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="29e50-209">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="29e50-210">I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="29e50-210">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="29e50-211">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="29e50-211">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="29e50-212">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="29e50-212">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-213"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-214">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-215">Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="29e50-216">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0.</span><span class="sxs-lookup"><span data-stu-id="29e50-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="29e50-217">Un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="29e50-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="29e50-218">Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="29e50-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="29e50-219">In Lync Server il server di monitoraggio usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="29e50-220">I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="29e50-220">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="29e50-221">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="29e50-221">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-222"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-223">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-224">Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="29e50-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="29e50-225">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="29e50-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="29e50-226">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="29e50-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-227"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-228">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-229">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="29e50-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="29e50-230">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="29e50-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-231"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-232">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-233">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="29e50-233">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="29e50-234">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="29e50-234">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-235"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-236">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-237">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="29e50-237">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="29e50-238">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="29e50-238">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-239"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-240">Sì</span><span class="sxs-lookup"><span data-stu-id="29e50-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="29e50-241">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="29e50-241">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="29e50-242">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="29e50-242">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="29e50-243">Metriche dei report sulle prestazioni del server: riepilogo videochiamata</span><span class="sxs-lookup"><span data-stu-id="29e50-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29e50-244">Nome</span><span class="sxs-lookup"><span data-stu-id="29e50-244">Name</span></span></th>
<th><span data-ttu-id="29e50-245">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="29e50-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="29e50-246">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29e50-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e50-247"><strong>Tipo di chiamata/tipo di endpoint</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-248">No</span><span class="sxs-lookup"><span data-stu-id="29e50-248">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-249">Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="29e50-249">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="29e50-250">I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="29e50-250">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="29e50-251">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="29e50-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="29e50-252">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="29e50-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="29e50-253">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="29e50-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="29e50-254">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="29e50-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="29e50-255">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="29e50-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="29e50-256">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="29e50-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="29e50-257">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="29e50-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-258"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-259">No</span><span class="sxs-lookup"><span data-stu-id="29e50-259">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-260">Numero totale di chiamate per tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-261"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-262">No</span><span class="sxs-lookup"><span data-stu-id="29e50-262">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-263">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="29e50-263">Total number of calls classified as poor.</span></span> <span data-ttu-id="29e50-264">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="29e50-264">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-265"><strong>Volume chiamata (chiamata wireless)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-266">No</span><span class="sxs-lookup"><span data-stu-id="29e50-266">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-267">Numero totale di chiamate che hanno usato una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="29e50-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-268"><strong>Volume chiamata (chiamata VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-269">No</span><span class="sxs-lookup"><span data-stu-id="29e50-269">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-270">Numero totale di chiamate che hanno usato una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="29e50-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-271"><strong>Volume chiamata (chiamata esterna)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-272">No</span><span class="sxs-lookup"><span data-stu-id="29e50-272">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-273">Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</span><span class="sxs-lookup"><span data-stu-id="29e50-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-274"><strong>Velocità di bit AVG (kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-275">No</span><span class="sxs-lookup"><span data-stu-id="29e50-275">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-276">Velocità in bit video media (in kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="29e50-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-277"><strong>Percentuale di bit bassa</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-278">No</span><span class="sxs-lookup"><span data-stu-id="29e50-278">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-279">Percentuale della chiamata in cui il bit rate è basso.</span><span class="sxs-lookup"><span data-stu-id="29e50-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-280"><strong>Perdita di pacchetti in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-281">No</span><span class="sxs-lookup"><span data-stu-id="29e50-281">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-282">Perdita di pacchetti RTP (Real-Time Transport Protocol) per pacchetti in uscita.</span><span class="sxs-lookup"><span data-stu-id="29e50-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="29e50-283">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="29e50-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="29e50-284">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="29e50-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-285"><strong>Fotogramma congelato%</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-286">No</span><span class="sxs-lookup"><span data-stu-id="29e50-286">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-287">Percentuale di fotogrammi "bloccati".</span><span class="sxs-lookup"><span data-stu-id="29e50-287">Percentage of “frozen” frames.</span></span> <span data-ttu-id="29e50-288">In un fotogramma bloccato il video smette di avanzare mentre la parte audio della chiamata continua.</span><span class="sxs-lookup"><span data-stu-id="29e50-288">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-289"><strong>Frequenza fotogrammi in uscita AVG</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-290">No</span><span class="sxs-lookup"><span data-stu-id="29e50-290">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-291">Frequenza fotogrammi media per le trasmissioni in uscita durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-292"><strong>Frequenza fotogrammi in ingresso AVG</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-293">No</span><span class="sxs-lookup"><span data-stu-id="29e50-293">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-294">Frequenza fotogrammi media per le trasmissioni in arrivo durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-295"><strong>Frequenza fotogrammi ridotta in ingresso%</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-296">No</span><span class="sxs-lookup"><span data-stu-id="29e50-296">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-297">Percentuale della chiamata in cui la velocità in bit per il video in arrivo è bassa.</span><span class="sxs-lookup"><span data-stu-id="29e50-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-298"><strong>Integrità client%</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29e50-299">Indica l'integrità relativa del dispositivo client durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="29e50-300">Metriche del report sulle prestazioni del server: riepilogo delle chiamate di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="29e50-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29e50-301">Nome</span><span class="sxs-lookup"><span data-stu-id="29e50-301">Name</span></span></th>
<th><span data-ttu-id="29e50-302">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="29e50-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="29e50-303">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29e50-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29e50-304"><strong>Tipo di chiamata/tipo di endpoint</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-305">No</span><span class="sxs-lookup"><span data-stu-id="29e50-305">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-306">Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="29e50-306">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="29e50-307">I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="29e50-307">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="29e50-308">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="29e50-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="29e50-309">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="29e50-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="29e50-310">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="29e50-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="29e50-311">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="29e50-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="29e50-312">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="29e50-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="29e50-313">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="29e50-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="29e50-314">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="29e50-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-315"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-316">No</span><span class="sxs-lookup"><span data-stu-id="29e50-316">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-317">Numero totale di chiamate per tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="29e50-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-318"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-319">No</span><span class="sxs-lookup"><span data-stu-id="29e50-319">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-320">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="29e50-320">Total number of calls classified as poor.</span></span> <span data-ttu-id="29e50-321">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="29e50-321">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-322"><strong>Volume chiamata (chiamata wireless)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-323">No</span><span class="sxs-lookup"><span data-stu-id="29e50-323">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-324">Numero totale di chiamate che hanno usato una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="29e50-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-325"><strong>Volume chiamata (chiamata VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-326">No</span><span class="sxs-lookup"><span data-stu-id="29e50-326">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-327">Numero totale di chiamate che hanno usato una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="29e50-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-328"><strong>Volume chiamata (chiamata esterna)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-329">No</span><span class="sxs-lookup"><span data-stu-id="29e50-329">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-330">Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</span><span class="sxs-lookup"><span data-stu-id="29e50-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-331"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-332">No</span><span class="sxs-lookup"><span data-stu-id="29e50-332">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-333">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="29e50-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="29e50-334">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="29e50-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-335"><strong>AVG. un modo relativo</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-336">No</span><span class="sxs-lookup"><span data-stu-id="29e50-336">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-337">Ritardo unidirezionale relativo medio tra due endpoint multimediali.</span><span class="sxs-lookup"><span data-stu-id="29e50-337">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="29e50-338">Si tratta di una misura di latenza single-hop.</span><span class="sxs-lookup"><span data-stu-id="29e50-338">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29e50-339"><strong>Latenza di elaborazione del riquadro media RDP</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-340">No</span><span class="sxs-lookup"><span data-stu-id="29e50-340">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-341">La latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="29e50-341">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="29e50-342">Questa metrica non include la latenza della rete.</span><span class="sxs-lookup"><span data-stu-id="29e50-342">This metric does not cover network latency.</span></span> <span data-ttu-id="29e50-343">Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="29e50-343">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="29e50-344">Un server di conferenza di overload può avere ritardi medi più alti.</span><span class="sxs-lookup"><span data-stu-id="29e50-344">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29e50-345"><strong>Totale riquadro viziato%</strong></span><span class="sxs-lookup"><span data-stu-id="29e50-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="29e50-346">No</span><span class="sxs-lookup"><span data-stu-id="29e50-346">No</span></span></p></td>
<td><p><span data-ttu-id="29e50-347">Percentuale totale di riquadri RDP viziati.</span><span class="sxs-lookup"><span data-stu-id="29e50-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

