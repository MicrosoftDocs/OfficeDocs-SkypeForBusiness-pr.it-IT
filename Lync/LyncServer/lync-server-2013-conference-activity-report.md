---
title: 'Lync Server 2013: report attività conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="0b07b-102">Report attività conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b07b-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b07b-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0b07b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0b07b-104">Il report attività conferenza consente di rispondere a domande di questo tipo: il numero di conferenze che si svolgono ogni giorno e quando si svolgono le conferenze?</span><span class="sxs-lookup"><span data-stu-id="0b07b-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="0b07b-105">Informazioni come questa sono utili non solo per i propri diritti, ma anche come strumento di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="0b07b-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="0b07b-106">Supponiamo ad esempio che gli utenti si lamentino che la rete sembra particolarmente lenta a metà giornata.</span><span class="sxs-lookup"><span data-stu-id="0b07b-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="0b07b-107">Una breve panoramica dei report sulle attività di conferenza può suggerire un motivo: molte più conferenze vengono programmate tra le ore 10:00 AM e 2:00 PM in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0b07b-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="0b07b-108">Se la rete lenta causa problemi, è possibile incoraggiare gli utenti a ripianificare alcune conferenze durante i periodi di traffico meno pesante del giorno.</span><span class="sxs-lookup"><span data-stu-id="0b07b-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="0b07b-109">Accesso al report attività conferenza</span><span class="sxs-lookup"><span data-stu-id="0b07b-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="0b07b-110">Il report attività conferenza viene eseguito dal [report di riepilogo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b07b-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="0b07b-111">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="0b07b-111">Total conferences</span></span>

  - <span data-ttu-id="0b07b-112">Totale partecipanti</span><span class="sxs-lookup"><span data-stu-id="0b07b-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="0b07b-113">Sfruttare al meglio il report attività conferenza</span><span class="sxs-lookup"><span data-stu-id="0b07b-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="0b07b-114">Per impostazione predefinita, il report attività conferenza Mostra il numero totale di conferenze per il periodo di tempo specificato, ad esempio il numero totale di conferenze per giorno o il numero totale di conferenze per ora del giorno.</span><span class="sxs-lookup"><span data-stu-id="0b07b-114">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="0b07b-115">Tuttavia, è anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo o il numero totale di minuti del partecipante.</span><span class="sxs-lookup"><span data-stu-id="0b07b-115">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="0b07b-116">A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro e quindi selezionare una delle operazioni seguenti nell'elenco a discesa report per:</span><span class="sxs-lookup"><span data-stu-id="0b07b-116">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="0b07b-117">Conteggio partecipanti</span><span class="sxs-lookup"><span data-stu-id="0b07b-117">Participant count</span></span>

  - <span data-ttu-id="0b07b-118">Minuti per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="0b07b-118">Participant minutes</span></span>

  - <span data-ttu-id="0b07b-119">Conteggio conferenze</span><span class="sxs-lookup"><span data-stu-id="0b07b-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0b07b-120">Filtri</span><span class="sxs-lookup"><span data-stu-id="0b07b-120">Filters</span></span>

<span data-ttu-id="0b07b-121">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="0b07b-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0b07b-122">Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-122">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="0b07b-123">Filtri di report attività conferenza</span><span class="sxs-lookup"><span data-stu-id="0b07b-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b07b-124">Nome</span><span class="sxs-lookup"><span data-stu-id="0b07b-124">Name</span></span></th>
<th><span data-ttu-id="0b07b-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b07b-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-126"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-127">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0b07b-127">Start date/time for the time range.</span></span> <span data-ttu-id="0b07b-128">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b07b-128">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0b07b-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0b07b-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0b07b-130">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="0b07b-130">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0b07b-131">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0b07b-131">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0b07b-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0b07b-132">7/7/2012</span></span></p>
<p><span data-ttu-id="0b07b-133">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="0b07b-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0b07b-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0b07b-134">7/3/2012</span></span></p>
<p><span data-ttu-id="0b07b-135">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="0b07b-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b07b-136"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-137">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0b07b-137">End date/time for the time range.</span></span> <span data-ttu-id="0b07b-138">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0b07b-138">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0b07b-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0b07b-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0b07b-140">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="0b07b-140">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0b07b-141">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0b07b-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0b07b-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0b07b-142">7/7/2012</span></span></p>
<p><span data-ttu-id="0b07b-143">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="0b07b-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0b07b-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0b07b-144">7/3/2012</span></span></p>
<p><span data-ttu-id="0b07b-145">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="0b07b-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-146"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-147">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0b07b-147">Time interval.</span></span> <span data-ttu-id="0b07b-148">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b07b-148">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0b07b-149">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="0b07b-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0b07b-150">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="0b07b-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0b07b-151">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="0b07b-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0b07b-152">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="0b07b-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0b07b-153">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="0b07b-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="0b07b-154">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="0b07b-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b07b-155"><strong>Report di</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-156">Indica i valori da usare nel report.</span><span class="sxs-lookup"><span data-stu-id="0b07b-156">Indicates the values to be used in the report.</span></span> <span data-ttu-id="0b07b-157">È possibile selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b07b-157">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0b07b-158">Conteggio partecipanti</span><span class="sxs-lookup"><span data-stu-id="0b07b-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="0b07b-159">Minuti per i partecipanti</span><span class="sxs-lookup"><span data-stu-id="0b07b-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="0b07b-160">Conteggio conferenze</span><span class="sxs-lookup"><span data-stu-id="0b07b-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="0b07b-161">Metriche per le conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="0b07b-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="0b07b-162">Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="0b07b-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="0b07b-163">Metriche per le conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="0b07b-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b07b-164">Nome</span><span class="sxs-lookup"><span data-stu-id="0b07b-164">Name</span></span></th>
<th><span data-ttu-id="0b07b-165">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="0b07b-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0b07b-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b07b-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-168">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-168">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-169">Nome del pool di registrazione o del server perimetrale usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b07b-170"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-171">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-171">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-172">Data e ora in cui si è tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-173"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-174">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-174">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-175">Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="0b07b-176">Metriche per le conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="0b07b-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="0b07b-177">Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni tipo di server.</span><span class="sxs-lookup"><span data-stu-id="0b07b-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="0b07b-178">Metriche per le conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="0b07b-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b07b-179">Nome</span><span class="sxs-lookup"><span data-stu-id="0b07b-179">Name</span></span></th>
<th><span data-ttu-id="0b07b-180">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="0b07b-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0b07b-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b07b-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-182"><strong>Tipo di server conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-183">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-183">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-184">Tipo di server usato nella conferenza, in genere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b07b-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0b07b-185">Web Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="0b07b-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="0b07b-186">Server di conferenza di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0b07b-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="0b07b-187">Server delle conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="0b07b-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="0b07b-188">AV Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="0b07b-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="0b07b-189">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0b07b-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b07b-190"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-191">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-191">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-192">Data e ora in cui si è tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b07b-193"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="0b07b-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="0b07b-194">No</span><span class="sxs-lookup"><span data-stu-id="0b07b-194">No</span></span></p></td>
<td><p><span data-ttu-id="0b07b-195">Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.</span><span class="sxs-lookup"><span data-stu-id="0b07b-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

