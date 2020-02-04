---
title: 'Lync Server 2013: report di diagnostica conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69c63e710463a37eecbb7d20edbe5999d0fbb55f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="95500-102">Report di diagnostica per conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95500-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95500-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="95500-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="95500-104">Il report di diagnostica conferenza fornisce informazioni sull'esito positivo e negativo di tutte le sessioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="95500-105">Si noti che il server Microsoft Lync distingue tra diversi tipi di errore:</span><span class="sxs-lookup"><span data-stu-id="95500-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="95500-106">**Errore previsto**.</span><span class="sxs-lookup"><span data-stu-id="95500-106">**Expected failure**.</span></span> <span data-ttu-id="95500-107">Un errore previsto è in genere un errore solo in senso più tecnico.</span><span class="sxs-lookup"><span data-stu-id="95500-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="95500-108">Ad esempio, supponiamo che qualcuno inizi una conferenza, ma si riaggancia prima che tutti possano partecipare.</span><span class="sxs-lookup"><span data-stu-id="95500-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="95500-109">Tecnicamente si tratta di un errore: la conferenza è stata avviata, ma non è stata completata.</span><span class="sxs-lookup"><span data-stu-id="95500-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="95500-110">Tuttavia, questo è un errore che ci si aspetterebbe di avere: se l'organizzatore Annulla la conferenza prima che tutti possano partecipare, non si prevede che la conferenza venga completata.</span><span class="sxs-lookup"><span data-stu-id="95500-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="95500-111">**Errore imprevisto**.</span><span class="sxs-lookup"><span data-stu-id="95500-111">**Unexpected failure**.</span></span> <span data-ttu-id="95500-112">Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi.</span><span class="sxs-lookup"><span data-stu-id="95500-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="95500-113">Supponiamo ad esempio che non sia possibile tenere una conferenza perché non è stato possibile recuperare i criteri della riunione dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="95500-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="95500-114">Si tratta di un errore imprevisto: dopo tutto, dovresti sempre essere in grado di recuperare i criteri di riunione di un utente.</span><span class="sxs-lookup"><span data-stu-id="95500-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="95500-115">Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="95500-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="95500-116">Ad esempio, è possibile che nel report vengano visualizzati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="95500-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95500-117">Successi</span><span class="sxs-lookup"><span data-stu-id="95500-117">Successes</span></span></th>
<th><span data-ttu-id="95500-118">Errori previsti</span><span class="sxs-lookup"><span data-stu-id="95500-118">Expected failures</span></span></th>
<th><span data-ttu-id="95500-119">Errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="95500-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="95500-120">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="95500-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95500-121">2024</span><span class="sxs-lookup"><span data-stu-id="95500-121">2024</span></span></p></td>
<td><p><span data-ttu-id="95500-122">469</span><span class="sxs-lookup"><span data-stu-id="95500-122">469</span></span></p></td>
<td><p><span data-ttu-id="95500-123">16</span><span class="sxs-lookup"><span data-stu-id="95500-123">16</span></span></p></td>
<td><p><span data-ttu-id="95500-124">2521</span><span class="sxs-lookup"><span data-stu-id="95500-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95500-125">Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni.</span><span class="sxs-lookup"><span data-stu-id="95500-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="95500-126">Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito.</span><span class="sxs-lookup"><span data-stu-id="95500-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="95500-127">A volte succede quando un prodotto di terze parti introduce un nuovo codice diagnostico che non conosce il server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="95500-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="95500-128">In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="95500-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="95500-129">Accesso al report di diagnostica conferenza</span><span class="sxs-lookup"><span data-stu-id="95500-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="95500-130">È possibile accedere al report di diagnostica della conferenza dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="95500-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="95500-131">È possibile accedere al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="95500-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="95500-132">Volume di errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="95500-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="95500-133">Volume di errore previsto</span><span class="sxs-lookup"><span data-stu-id="95500-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="95500-134">Uso ottimale del report di diagnostica conferenza</span><span class="sxs-lookup"><span data-stu-id="95500-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="95500-135">Il report di diagnostica conferenza include una serie di grafici.</span><span class="sxs-lookup"><span data-stu-id="95500-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="95500-136">Ognuna delle colonne visualizzate nel grafico è in realtà un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="95500-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="95500-137">Se si fa clic su una colonna, è possibile eseguire il drill-down [nel report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) per il periodo di tempo e il tipo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="95500-138">Filtri</span><span class="sxs-lookup"><span data-stu-id="95500-138">Filters</span></span>

<span data-ttu-id="95500-139">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="95500-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="95500-140">Ad esempio, il report di diagnostica per le conferenze consente di filtrare in base al tipo di conferenza che viene eseguita, ad esempio una conferenza basata su stato attivo, o dall'Edge Server usato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="95500-141">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="95500-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="95500-142">In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="95500-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="95500-143">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="95500-144">Filtri di report di diagnostica conferenza</span><span class="sxs-lookup"><span data-stu-id="95500-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95500-145">Nome</span><span class="sxs-lookup"><span data-stu-id="95500-145">Name</span></span></th>
<th><span data-ttu-id="95500-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95500-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95500-147"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="95500-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-148">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="95500-148">Start date/time for the time range.</span></span> <span data-ttu-id="95500-149">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="95500-149">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="95500-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="95500-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="95500-151">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="95500-151">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="95500-152">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="95500-152">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="95500-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="95500-153">7/7/2012</span></span></p>
<p><span data-ttu-id="95500-154">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="95500-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="95500-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="95500-155">7/3/2012</span></span></p>
<p><span data-ttu-id="95500-156">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="95500-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95500-157"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="95500-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-158">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="95500-158">End date/time for the time range.</span></span> <span data-ttu-id="95500-159">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="95500-159">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="95500-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="95500-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="95500-161">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="95500-161">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="95500-162">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="95500-162">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="95500-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="95500-163">7/7/2012</span></span></p>
<p><span data-ttu-id="95500-164">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="95500-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="95500-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="95500-165">7/3/2012</span></span></p>
<p><span data-ttu-id="95500-166">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="95500-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95500-167"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="95500-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-168">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="95500-168">Time interval.</span></span> <span data-ttu-id="95500-169">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95500-169">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="95500-170">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="95500-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="95500-171">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="95500-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="95500-172">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="95500-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="95500-173">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="95500-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="95500-174">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="95500-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="95500-175">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="95500-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95500-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="95500-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-177">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="95500-177">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="95500-178">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="95500-178">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="95500-179">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="95500-179">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95500-180"><strong>Sessioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="95500-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-181">Indica il tipo di sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="95500-182">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95500-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="95500-183">Tutti</span><span class="sxs-lookup"><span data-stu-id="95500-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="95500-184">Sessioni di stato attiva</span><span class="sxs-lookup"><span data-stu-id="95500-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="95500-185">Tutte le sessioni MCU</span><span class="sxs-lookup"><span data-stu-id="95500-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="95500-186">Conferenza di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="95500-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="95500-187">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="95500-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="95500-188">Servizi di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="95500-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="95500-189">Metriche</span><span class="sxs-lookup"><span data-stu-id="95500-189">Metrics</span></span>

<span data-ttu-id="95500-190">Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica conferenza per ogni tipo di sessione di conferenza.</span><span class="sxs-lookup"><span data-stu-id="95500-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="95500-191">Metriche del report di diagnostica conferenza</span><span class="sxs-lookup"><span data-stu-id="95500-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95500-192">Nome</span><span class="sxs-lookup"><span data-stu-id="95500-192">Name</span></span></th>
<th><span data-ttu-id="95500-193">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="95500-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="95500-194">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95500-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95500-195"><strong>Volume di successo</strong></span><span class="sxs-lookup"><span data-stu-id="95500-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-196">No</span><span class="sxs-lookup"><span data-stu-id="95500-196">No</span></span></p></td>
<td><p><span data-ttu-id="95500-197">Numero totale di conferenze di successo.</span><span class="sxs-lookup"><span data-stu-id="95500-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95500-198"><strong>Percentuale di successo</strong></span><span class="sxs-lookup"><span data-stu-id="95500-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-199">No</span><span class="sxs-lookup"><span data-stu-id="95500-199">No</span></span></p></td>
<td><p><span data-ttu-id="95500-200">Percentuale di conferenze completate con problemi significativi.</span><span class="sxs-lookup"><span data-stu-id="95500-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="95500-201">Calcolata dividendo il volume di successo per il totale delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="95500-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95500-202"><strong>Volume di errore previsto</strong></span><span class="sxs-lookup"><span data-stu-id="95500-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-203">No</span><span class="sxs-lookup"><span data-stu-id="95500-203">No</span></span></p></td>
<td><p><span data-ttu-id="95500-204">Numero totale di conferenze in cui &quot;si è&quot; verificato un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="95500-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="95500-205">Un errore previsto è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="95500-205">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="95500-206">Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="95500-206">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95500-207"><strong>Percentuale di errore prevista</strong></span><span class="sxs-lookup"><span data-stu-id="95500-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-208">No</span><span class="sxs-lookup"><span data-stu-id="95500-208">No</span></span></p></td>
<td><p><span data-ttu-id="95500-209">Percentuale di conferenze con un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="95500-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="95500-210">Calcolata dividendo il volume di errore previsto per le sessioni totali.</span><span class="sxs-lookup"><span data-stu-id="95500-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95500-211"><strong>Volume di errore imprevisto</strong></span><span class="sxs-lookup"><span data-stu-id="95500-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-212">No</span><span class="sxs-lookup"><span data-stu-id="95500-212">No</span></span></p></td>
<td><p><span data-ttu-id="95500-213">Numero totale di conferenze in cui &quot;si è&quot; verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="95500-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="95500-214">Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="95500-214">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="95500-215">Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="95500-215">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="95500-216">Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="95500-216">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95500-217"><strong>Percentuale di errore imprevisto</strong></span><span class="sxs-lookup"><span data-stu-id="95500-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-218">No</span><span class="sxs-lookup"><span data-stu-id="95500-218">No</span></span></p></td>
<td><p><span data-ttu-id="95500-219">Percentuale di conferenze in cui si è verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="95500-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="95500-220">Calcolata dividendo il volume di errore imprevisto per le sessioni totali.</span><span class="sxs-lookup"><span data-stu-id="95500-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95500-221"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="95500-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="95500-222">No</span><span class="sxs-lookup"><span data-stu-id="95500-222">No</span></span></p></td>
<td><p><span data-ttu-id="95500-223">Numero totale di conferenze, tra cui conferenze di successo, conferenze non riuscite (errori previsti e errori imprevisti) e conferenze Uncategorized.</span><span class="sxs-lookup"><span data-stu-id="95500-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

