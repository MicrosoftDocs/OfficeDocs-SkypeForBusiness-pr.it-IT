---
title: 'Lync Server 2013: report di riepilogo diagnostica chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="75072-102">Report riepilogo diagnostica chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75072-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75072-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="75072-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="75072-104">Il report riepilogo diagnostica chiamata offre una panoramica complessiva delle sessioni peer-to-peer e di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-104">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="75072-105">Il report Mostra la frequenza di errore complessiva per entrambi i tipi di sessioni e interrompe ulteriormente le informazioni di errore in base al tipo di modalità di sessione:</span><span class="sxs-lookup"><span data-stu-id="75072-105">The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="75072-106">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="75072-106">Instant messaging</span></span>

  - <span data-ttu-id="75072-107">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="75072-107">Application sharing</span></span>

  - <span data-ttu-id="75072-108">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="75072-108">File transfer</span></span>

  - <span data-ttu-id="75072-109">Audio</span><span class="sxs-lookup"><span data-stu-id="75072-109">Audio</span></span>

  - <span data-ttu-id="75072-110">Video</span><span class="sxs-lookup"><span data-stu-id="75072-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="75072-111">Accesso al report di riepilogo diagnostica chiamata</span><span class="sxs-lookup"><span data-stu-id="75072-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="75072-112">Il report riepilogo diagnostica chiamata è accessibile dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="75072-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="75072-113">Nel report di riepilogo diagnostica chiamata è possibile accedere al [report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) facendo clic sulla metrica tasso di errore nella sezione Riepilogo sessione peer-to-peer del report.</span><span class="sxs-lookup"><span data-stu-id="75072-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="75072-114">È anche possibile accedere al [report di diagnostica conferenza in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) facendo clic su una delle metriche di conferenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="75072-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="75072-115">Tasso di errore complessivo della sessione</span><span class="sxs-lookup"><span data-stu-id="75072-115">Overall session failure rate</span></span>

  - <span data-ttu-id="75072-116">Tasso di errore dello stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="75072-116">Focus failure rate</span></span>

  - <span data-ttu-id="75072-117">Tasso di errore MCU</span><span class="sxs-lookup"><span data-stu-id="75072-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="75072-118">Uso ottimale del report di riepilogo diagnostica chiamata</span><span class="sxs-lookup"><span data-stu-id="75072-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="75072-119">Il report riepilogo diagnostica chiamata include grafici che confrontano i tassi di errore per le varie modalità usate in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75072-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="75072-120">Le colonne in questi grafici sono in realtà hotlinks; ad esempio, se si fa clic sulla colonna messaggistica istantanea per le sessioni peer-to-peer, sarà possibile eseguire il drill-down in un'istanza del [report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un report che fornisce informazioni aggiuntive su tutte le sessioni di messaggistica istantanea incluse nel report di riepilogo di diagnostica delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="75072-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="75072-121">Filtri</span><span class="sxs-lookup"><span data-stu-id="75072-121">Filters</span></span>

<span data-ttu-id="75072-122">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="75072-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="75072-123">Ad esempio, il report riepilogo diagnostica chiamata consente di filtrare in base a un pool di registrazione o a un server perimetrale usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="75072-123">For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session.</span></span> <span data-ttu-id="75072-124">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="75072-124">You can also choose how data should be grouped.</span></span> <span data-ttu-id="75072-125">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="75072-125">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="75072-126">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo di diagnostica chiamata.</span><span class="sxs-lookup"><span data-stu-id="75072-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="75072-127">Filtri dei report di riepilogo delle chiamate di diagnostica</span><span class="sxs-lookup"><span data-stu-id="75072-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75072-128">Nome</span><span class="sxs-lookup"><span data-stu-id="75072-128">Name</span></span></th>
<th><span data-ttu-id="75072-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75072-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75072-130"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="75072-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-131">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="75072-131">Start date/time for the time range.</span></span> <span data-ttu-id="75072-132">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="75072-132">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="75072-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="75072-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="75072-134">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="75072-134">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="75072-135">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="75072-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="75072-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="75072-136">7/7/2012</span></span></p>
<p><span data-ttu-id="75072-137">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="75072-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="75072-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="75072-138">7/3/2012</span></span></p>
<p><span data-ttu-id="75072-139">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="75072-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-140"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="75072-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-141">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="75072-141">End date/time for the time range.</span></span> <span data-ttu-id="75072-142">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="75072-142">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="75072-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="75072-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="75072-144">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="75072-144">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="75072-145">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="75072-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="75072-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="75072-146">7/7/2012</span></span></p>
<p><span data-ttu-id="75072-147">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="75072-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="75072-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="75072-148">7/3/2012</span></span></p>
<p><span data-ttu-id="75072-149">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="75072-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75072-150"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="75072-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-151">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="75072-151">Time interval.</span></span> <span data-ttu-id="75072-152">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="75072-152">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="75072-153">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="75072-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="75072-154">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="75072-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="75072-155">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="75072-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="75072-156">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="75072-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="75072-157">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="75072-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="75072-158">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="75072-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="75072-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-160">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="75072-160">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="75072-161">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="75072-161">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="75072-162">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="75072-162">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="75072-163">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="75072-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="75072-164">Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo di diagnostica delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="75072-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="75072-165">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="75072-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75072-166">Nome</span><span class="sxs-lookup"><span data-stu-id="75072-166">Name</span></span></th>
<th><span data-ttu-id="75072-167">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="75072-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="75072-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75072-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75072-169"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="75072-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-170">No</span><span class="sxs-lookup"><span data-stu-id="75072-170">No</span></span></p></td>
<td><p><span data-ttu-id="75072-171">Numero totale di sessioni peer-to-peer condotte.</span><span class="sxs-lookup"><span data-stu-id="75072-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-172"><strong>Tasso di errore</strong></span><span class="sxs-lookup"><span data-stu-id="75072-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-173">No</span><span class="sxs-lookup"><span data-stu-id="75072-173">No</span></span></p></td>
<td><p><span data-ttu-id="75072-174">Percentuale di sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-174">Percentage of peer-to-peer sessions that failed.</span></span> <span data-ttu-id="75072-175">Quando si fa clic su questo elemento, il report Mostra il rapporto di diagnostica attività peer-to-peer, in cui vengono visualizzate informazioni più dettagliate sulle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-175">When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="75072-176">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="75072-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="75072-177">Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica delle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="75072-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="75072-178">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="75072-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75072-179">Nome</span><span class="sxs-lookup"><span data-stu-id="75072-179">Name</span></span></th>
<th><span data-ttu-id="75072-180">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="75072-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="75072-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75072-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75072-182"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="75072-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-183">No</span><span class="sxs-lookup"><span data-stu-id="75072-183">No</span></span></p></td>
<td><p><span data-ttu-id="75072-184">Numero totale di conferenze condotte.</span><span class="sxs-lookup"><span data-stu-id="75072-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-185"><strong>Totale delle sessioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="75072-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-186">No</span><span class="sxs-lookup"><span data-stu-id="75072-186">No</span></span></p></td>
<td><p><span data-ttu-id="75072-187">Numero totale di sessioni di conferenza condotte.</span><span class="sxs-lookup"><span data-stu-id="75072-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75072-188"><strong>Tasso di errore complessivo della sessione</strong></span><span class="sxs-lookup"><span data-stu-id="75072-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-189">No</span><span class="sxs-lookup"><span data-stu-id="75072-189">No</span></span></p></td>
<td><p><span data-ttu-id="75072-190">Percentuale delle sessioni di conferenza totale non riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-191"><strong>Sessioni di stato attiva</strong></span><span class="sxs-lookup"><span data-stu-id="75072-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-192">No</span><span class="sxs-lookup"><span data-stu-id="75072-192">No</span></span></p></td>
<td><p><span data-ttu-id="75072-193">Numero totale di sessioni di conferenza basate su stato non riuscito.</span><span class="sxs-lookup"><span data-stu-id="75072-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75072-194"><strong>Tasso di errore dello stato di avanzamento</strong></span><span class="sxs-lookup"><span data-stu-id="75072-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-195">No</span><span class="sxs-lookup"><span data-stu-id="75072-195">No</span></span></p></td>
<td><p><span data-ttu-id="75072-196">Percentuale delle sessioni di conferenza basate su stato non riuscito.</span><span class="sxs-lookup"><span data-stu-id="75072-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75072-197"><strong>Sessioni MCU</strong></span><span class="sxs-lookup"><span data-stu-id="75072-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-198">No</span><span class="sxs-lookup"><span data-stu-id="75072-198">No</span></span></p></td>
<td><p><span data-ttu-id="75072-199">Numero totale di conferenze basate su server di conferenza (precedentemente noto come unità di controllo multipunto o MCU) che non sono state riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75072-200"><strong>Tasso di errore MCU</strong></span><span class="sxs-lookup"><span data-stu-id="75072-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="75072-201">No</span><span class="sxs-lookup"><span data-stu-id="75072-201">No</span></span></p></td>
<td><p><span data-ttu-id="75072-202">Percentuale delle conferenze basate su server di conferenza (precedentemente note come unità di controllo multipunto o MCU) che non sono state riuscite.</span><span class="sxs-lookup"><span data-stu-id="75072-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

