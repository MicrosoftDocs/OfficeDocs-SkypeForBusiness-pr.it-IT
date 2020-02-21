---
title: 'Lync Server 2013: Rapporto tendenze qualità multimediale server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e7e0f3cfe38a7a1c4802eca16c37a62013cecb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="16b42-102">Rapporto tendenze qualità multimediale server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16b42-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16b42-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="16b42-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="16b42-p101">Il Rapporto tendenze qualità multimediale server offre un modo per confrontare graficamente fino a 5 server relativamente a metriche QoE quali il volume di chiamata, la percentuale di chiamate di livello insufficiente, la perdita di pacchetti e l'instabilità. Ciò agevola attività quali l'identificazione dei server con prestazioni insufficienti, sottoutilizzati o sovrautilizzati.</span><span class="sxs-lookup"><span data-stu-id="16b42-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="16b42-106">Accesso al Rapporto tendenze qualità multimediale server</span><span class="sxs-lookup"><span data-stu-id="16b42-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="16b42-107">Il Rapporto tendenze qualità multimediale server è accessibile da uno o l'altro dei rapporto seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b42-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="16b42-108">[Rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica tendenza)</span><span class="sxs-lookup"><span data-stu-id="16b42-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="16b42-109">[Rapporto dettagli chiamata in Lync server 2013](lync-server-2013-call-detail-report.md) (facendo clic sulla metrica a/V Edge Server.</span><span class="sxs-lookup"><span data-stu-id="16b42-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="16b42-110">Se il chiamante o il destinatario della chiamata è un server, è possibile raggiungere anche il rapporto trend media Quality Server facendo clic sul nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="16b42-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="16b42-111">Uso ottimale del Rapporto tendenze qualità multimediale server</span><span class="sxs-lookup"><span data-stu-id="16b42-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="16b42-112">Quando si fa clic sulla metrica di tendenza sul [rapporto prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) per un server specifico, verrà aperto il rapporto tendenze qualità multimediale server.</span><span class="sxs-lookup"><span data-stu-id="16b42-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="16b42-113">Tuttavia, verrà visualizzata solo un'istanza vuota del rapporto; il server selezionato nel Rapporto prestazioni dei server non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="16b42-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="16b42-114">Sarà invece necessario selezionare il server dal menu a discesa Server.</span><span class="sxs-lookup"><span data-stu-id="16b42-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="16b42-115">Tenere presente che l'elenco a discesa Server include anche un'opzione Seleziona tutto.</span><span class="sxs-lookup"><span data-stu-id="16b42-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="16b42-116">Questa opzione non funziona se sono presenti più di 5 server; il Rapporto tendenze qualità multimediale server è in grado di visualizzare dati per un massimo di 5 server alla volta.</span><span class="sxs-lookup"><span data-stu-id="16b42-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="16b42-117">Nei grafici visualizzati dal rapporto tendenze qualità multimediale server, il volume delle chiamate a punti e la percentuale di chiamate insufficienti sono hotlinks; Se si fa clic su un punto del grafico, verrà aperta un'istanza del [rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) che mostra le chiamate totali (o le chiamate insufficienti) per il periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="16b42-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="16b42-118">Filtri</span><span class="sxs-lookup"><span data-stu-id="16b42-118">Filters</span></span>

<span data-ttu-id="16b42-p104">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto tendenze qualità multimediale server.</span><span class="sxs-lookup"><span data-stu-id="16b42-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="16b42-121">Filtri del Rapporto tendenze qualità multimediale server</span><span class="sxs-lookup"><span data-stu-id="16b42-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16b42-122">Name</span><span class="sxs-lookup"><span data-stu-id="16b42-122">Name</span></span></th>
<th><span data-ttu-id="16b42-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16b42-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16b42-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p105">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="16b42-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="16b42-127">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="16b42-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="16b42-p106">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="16b42-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="16b42-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="16b42-130">7/7/2012</span></span></p>
<p><span data-ttu-id="16b42-131">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="16b42-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="16b42-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="16b42-132">7/3/2012</span></span></p>
<p><span data-ttu-id="16b42-133">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="16b42-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p107">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="16b42-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="16b42-137">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="16b42-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="16b42-p108">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="16b42-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="16b42-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="16b42-140">7/7/2012</span></span></p>
<p><span data-ttu-id="16b42-141">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="16b42-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="16b42-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="16b42-142">7/3/2012</span></span></p>
<p><span data-ttu-id="16b42-143">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="16b42-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-144"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p109">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b42-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="16b42-147">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="16b42-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="16b42-148">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="16b42-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="16b42-149">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="16b42-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="16b42-p110">Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo Giornaliero con la data di inizio 07.07.12 e la data di fine 28.02.12, verranno visualizzati i dati relativi ai giorni da 07.08.12 alle 00.00 a 07.09.12 alle 00.00, ovvero per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="16b42-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-152"><strong>Tipo di server </strong></span><span class="sxs-lookup"><span data-stu-id="16b42-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p111">Tipo di server coinvolto nella chiamata. Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="16b42-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="16b42-155">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="16b42-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="16b42-156">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="16b42-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="16b42-157">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="16b42-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="16b42-158">Gateway (Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="16b42-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="16b42-159">Gateway (bypass a Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="16b42-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="16b42-160">AS Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="16b42-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-161"><strong>Servers</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p112">Nome del server coinvolto nella sessione; questo elenco a discesa viene automaticamente popolato in base al valore del filtro Tipo di server. È possibile selezionare fino a 5 diversi server per la compilazione di un rapporto.</span><span class="sxs-lookup"><span data-stu-id="16b42-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-164"><strong>Tipo di accesso </strong></span><span class="sxs-lookup"><span data-stu-id="16b42-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p113">Indica se il partecipante era connesso alla rete interna o dalla rete esterna. Valori consenti:</span><span class="sxs-lookup"><span data-stu-id="16b42-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="16b42-167">Tutti</span><span class="sxs-lookup"><span data-stu-id="16b42-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="16b42-168">Interna</span><span class="sxs-lookup"><span data-stu-id="16b42-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="16b42-169">Esterna</span><span class="sxs-lookup"><span data-stu-id="16b42-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-170"><strong>Tipo di rete </strong></span><span class="sxs-lookup"><span data-stu-id="16b42-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p114">Indica il tipo di rete a cui era connesso il partecipante. Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="16b42-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="16b42-173">Tutti</span><span class="sxs-lookup"><span data-stu-id="16b42-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="16b42-174">Cablata</span><span class="sxs-lookup"><span data-stu-id="16b42-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="16b42-175">Wireless</span><span class="sxs-lookup"><span data-stu-id="16b42-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-p115">Indica se un partecipante esterno utilizzava una connessione di rete privata virtuale (VPN) durante la sessione. Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="16b42-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="16b42-179">Tutti</span><span class="sxs-lookup"><span data-stu-id="16b42-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="16b42-180">VPN</span><span class="sxs-lookup"><span data-stu-id="16b42-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="16b42-181">Non VPN</span><span class="sxs-lookup"><span data-stu-id="16b42-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="16b42-182">Metriche</span><span class="sxs-lookup"><span data-stu-id="16b42-182">Metrics</span></span>

<span data-ttu-id="16b42-183">Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto tendenze qualità multimediale server.</span><span class="sxs-lookup"><span data-stu-id="16b42-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="16b42-184">Metriche del Rapporto tendenze qualità multimediale server</span><span class="sxs-lookup"><span data-stu-id="16b42-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16b42-185">Name</span><span class="sxs-lookup"><span data-stu-id="16b42-185">Name</span></span></th>
<th><span data-ttu-id="16b42-186">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="16b42-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="16b42-187">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16b42-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16b42-188"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-189">No</span><span class="sxs-lookup"><span data-stu-id="16b42-189">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-190">Numero totale di chiamate</span><span class="sxs-lookup"><span data-stu-id="16b42-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-191"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-192">No</span><span class="sxs-lookup"><span data-stu-id="16b42-192">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-193">Valore medio di degrado di MOS (Media Option score) sperimentato durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="16b42-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="16b42-194">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore pari a 0,5 o meno rappresenta un calo accettabile.</span><span class="sxs-lookup"><span data-stu-id="16b42-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="16b42-195">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="16b42-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="16b42-196">Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="16b42-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="16b42-p117">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="16b42-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-199"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-200">No</span><span class="sxs-lookup"><span data-stu-id="16b42-200">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p118">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="16b42-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-203"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-204">No</span><span class="sxs-lookup"><span data-stu-id="16b42-204">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p119">Tempo medio (in millisecondi) richiesto per il roundtrip di un pacchetto RTP (Real-Time Transport Protocol) verso e da un altro endpoint. I roundtrip che non superano i 200 millisecondi vengono considerati accettabili.</span><span class="sxs-lookup"><span data-stu-id="16b42-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="16b42-p120">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="16b42-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-209"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-210">No</span><span class="sxs-lookup"><span data-stu-id="16b42-210">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p121">Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="16b42-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-214"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-215">No</span><span class="sxs-lookup"><span data-stu-id="16b42-215">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-216">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="16b42-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="16b42-217">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="16b42-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-218"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-219">No</span><span class="sxs-lookup"><span data-stu-id="16b42-219">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p123">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="16b42-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16b42-222"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-223">No</span><span class="sxs-lookup"><span data-stu-id="16b42-223">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p124">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="16b42-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16b42-226"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="16b42-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="16b42-227">No</span><span class="sxs-lookup"><span data-stu-id="16b42-227">No</span></span></p></td>
<td><p><span data-ttu-id="16b42-p125">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="16b42-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

