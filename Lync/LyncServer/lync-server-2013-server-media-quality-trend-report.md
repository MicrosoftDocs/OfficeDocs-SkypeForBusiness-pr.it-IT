---
title: 'Lync Server 2013: report trend qualità media del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc60cd4c0d8d00fa67a5fe77ca70e61058191baa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="e332d-102">Report trend qualità media server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e332d-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e332d-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e332d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e332d-104">Il report tendenze per la qualità dei contenuti multimediali consente di confrontare graficamente fino a 5 Server per la qualità delle metriche dell'esperienza, ad esempio il volume delle chiamate, la percentuale di chiamata scadente, la perdita di pacchetti e il jitter.</span><span class="sxs-lookup"><span data-stu-id="e332d-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="e332d-105">In questo modo, è più facile eseguire operazioni come identificare i server che eseguono in modo poco corretto, identificare i server sottoutilizzati o identificare i server che vengono sovrautilizzati.</span><span class="sxs-lookup"><span data-stu-id="e332d-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="e332d-106">Accesso al report trend qualità media del server</span><span class="sxs-lookup"><span data-stu-id="e332d-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="e332d-107">È possibile accedere al report trend qualità media del server da uno dei report seguenti:</span><span class="sxs-lookup"><span data-stu-id="e332d-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="e332d-108">[Report prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica di tendenza)</span><span class="sxs-lookup"><span data-stu-id="e332d-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="e332d-109">[Report dettagli chiamata in Lync server 2013](lync-server-2013-call-detail-report.md) (facendo clic sulla metrica a/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="e332d-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="e332d-110">Se il chiamante o il visitatore è un server, è anche possibile raggiungere il report trend media per la qualità del server facendo clic sul nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="e332d-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="e332d-111">Sfruttare al meglio il report trend di qualità media del server</span><span class="sxs-lookup"><span data-stu-id="e332d-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="e332d-112">Quando si fa clic sulla metrica di tendenza nel [report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) per un server specifico, verrà aperto il report trend qualità media del server.</span><span class="sxs-lookup"><span data-stu-id="e332d-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="e332d-113">Verrà tuttavia visualizzata solo un'istanza vuota del report. il server selezionato nel report prestazioni server non verrà visualizzato sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="e332d-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="e332d-114">È invece necessario selezionare il server dall'elenco a discesa Server.</span><span class="sxs-lookup"><span data-stu-id="e332d-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="e332d-115">Tieni presente che anche l'elenco a discesa dei server include un'opzione Seleziona tutto.</span><span class="sxs-lookup"><span data-stu-id="e332d-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="e332d-116">Questa opzione non funziona se si hanno più di 5 Server; il report trend Quality media server può visualizzare solo i dati per un massimo di 5 server alla volta.</span><span class="sxs-lookup"><span data-stu-id="e332d-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="e332d-117">Nei grafici visualizzati dal report trend qualità media del server, i punti etichettati volume chiamata e percentuale di chiamata scadente sono hotlinks; Se si fa clic su un punto del grafico, verrà aperta un'istanza del [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) che mostra le chiamate totali (o chiamate non consentite) per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="e332d-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e332d-118">Filtri</span><span class="sxs-lookup"><span data-stu-id="e332d-118">Filters</span></span>

<span data-ttu-id="e332d-119">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e332d-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e332d-120">Nella tabella seguente sono elencati i filtri che è possibile usare con il report trend qualità media del server.</span><span class="sxs-lookup"><span data-stu-id="e332d-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="e332d-121">Filtri per i report sulle tendenze della qualità multimediale del server</span><span class="sxs-lookup"><span data-stu-id="e332d-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e332d-122">Nome</span><span class="sxs-lookup"><span data-stu-id="e332d-122">Name</span></span></th>
<th><span data-ttu-id="e332d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e332d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e332d-124"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-125">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="e332d-125">Start date/time for the time range.</span></span> <span data-ttu-id="e332d-126">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e332d-126">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e332d-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e332d-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e332d-128">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="e332d-128">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e332d-129">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="e332d-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e332d-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e332d-130">7/7/2012</span></span></p>
<p><span data-ttu-id="e332d-131">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="e332d-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e332d-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e332d-132">7/3/2012</span></span></p>
<p><span data-ttu-id="e332d-133">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="e332d-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-134"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-135">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="e332d-135">End date/time for the time range.</span></span> <span data-ttu-id="e332d-136">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e332d-136">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e332d-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e332d-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e332d-138">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="e332d-138">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e332d-139">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="e332d-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e332d-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e332d-140">7/7/2012</span></span></p>
<p><span data-ttu-id="e332d-141">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="e332d-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e332d-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e332d-142">7/3/2012</span></span></p>
<p><span data-ttu-id="e332d-143">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="e332d-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-144"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-145">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="e332d-145">Time interval.</span></span> <span data-ttu-id="e332d-146">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e332d-146">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e332d-147">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="e332d-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e332d-148">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="e332d-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e332d-149">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="e332d-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e332d-150">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="e332d-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="e332d-151">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 8/7/2012 e una data di fine 9/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="e332d-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-152"><strong>Tipo di server</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-153">Tipo di server coinvolto nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="e332d-153">Type of server involved in the call.</span></span> <span data-ttu-id="e332d-154">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="e332d-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e332d-155">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e332d-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="e332d-156">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="e332d-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="e332d-157">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="e332d-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="e332d-158">Gateway (Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="e332d-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="e332d-159">Gateway (bypass Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="e332d-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="e332d-160">COME server delle conferenze</span><span class="sxs-lookup"><span data-stu-id="e332d-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-161"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-162">Nome del server coinvolto nella sessione; Questo elenco a discesa viene compilato automaticamente in base al valore del filtro del tipo di server.</span><span class="sxs-lookup"><span data-stu-id="e332d-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="e332d-163">Quando si compila un report, è possibile selezionare fino a 5 server diversi.</span><span class="sxs-lookup"><span data-stu-id="e332d-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-164"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-165">Indica se il partecipante ha effettuato l'accesso alla rete interna o alla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="e332d-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="e332d-166">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="e332d-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e332d-167">Tutti</span><span class="sxs-lookup"><span data-stu-id="e332d-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="e332d-168">Interno</span><span class="sxs-lookup"><span data-stu-id="e332d-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="e332d-169">Esterno</span><span class="sxs-lookup"><span data-stu-id="e332d-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-170"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-171">Indica il tipo di rete a cui il partecipante è connesso.</span><span class="sxs-lookup"><span data-stu-id="e332d-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="e332d-172">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="e332d-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e332d-173">Tutti</span><span class="sxs-lookup"><span data-stu-id="e332d-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="e332d-174">Cablata</span><span class="sxs-lookup"><span data-stu-id="e332d-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="e332d-175">Wireless</span><span class="sxs-lookup"><span data-stu-id="e332d-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-177">Indica se un partecipante esterno usa una connessione VPN (Virtual Private Network) durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="e332d-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="e332d-178">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="e332d-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e332d-179">Tutti</span><span class="sxs-lookup"><span data-stu-id="e332d-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="e332d-180">VPN</span><span class="sxs-lookup"><span data-stu-id="e332d-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="e332d-181">Non VPN</span><span class="sxs-lookup"><span data-stu-id="e332d-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e332d-182">Metriche</span><span class="sxs-lookup"><span data-stu-id="e332d-182">Metrics</span></span>

<span data-ttu-id="e332d-183">Nella tabella seguente sono elencate le informazioni disponibili nel report trend qualità media del server.</span><span class="sxs-lookup"><span data-stu-id="e332d-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="e332d-184">Metriche dei report sulle tendenze della qualità multimediale del server</span><span class="sxs-lookup"><span data-stu-id="e332d-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e332d-185">Nome</span><span class="sxs-lookup"><span data-stu-id="e332d-185">Name</span></span></th>
<th><span data-ttu-id="e332d-186">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="e332d-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e332d-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e332d-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e332d-188"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-189">No</span><span class="sxs-lookup"><span data-stu-id="e332d-189">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-190">Numero totale di chiamate.</span><span class="sxs-lookup"><span data-stu-id="e332d-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-191"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-192">No</span><span class="sxs-lookup"><span data-stu-id="e332d-192">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-193">Valore medio della degradazione MOS (Media Option score) sperimentata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e332d-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="e332d-194">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="e332d-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="e332d-195">Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="e332d-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="e332d-196">Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="e332d-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="e332d-197">I valori di degradazione elevati possono essere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless oppure un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="e332d-197">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="e332d-198">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="e332d-198">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-199"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-200">No</span><span class="sxs-lookup"><span data-stu-id="e332d-200">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-201">Numero totale di chiamate classificate come scarse.</span><span class="sxs-lookup"><span data-stu-id="e332d-201">The total number of calls classified as poor.</span></span> <span data-ttu-id="e332d-202">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="e332d-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-203"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-204">No</span><span class="sxs-lookup"><span data-stu-id="e332d-204">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-205">Intervallo di tempo medio (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un punto finale e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="e332d-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="e332d-206">I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="e332d-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e332d-207">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="e332d-207">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="e332d-208">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="e332d-208">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-209"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-210">No</span><span class="sxs-lookup"><span data-stu-id="e332d-210">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-211">Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="e332d-211">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="e332d-212">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="e332d-212">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="e332d-213">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="e332d-213">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-214"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-215">No</span><span class="sxs-lookup"><span data-stu-id="e332d-215">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-216">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="e332d-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e332d-217">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="e332d-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-218"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-219">No</span><span class="sxs-lookup"><span data-stu-id="e332d-219">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-220">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="e332d-220">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e332d-221">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="e332d-221">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e332d-222"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-223">No</span><span class="sxs-lookup"><span data-stu-id="e332d-223">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-224">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="e332d-224">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e332d-225">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="e332d-225">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e332d-226"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="e332d-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e332d-227">No</span><span class="sxs-lookup"><span data-stu-id="e332d-227">No</span></span></p></td>
<td><p><span data-ttu-id="e332d-228">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="e332d-228">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="e332d-229">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="e332d-229">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

