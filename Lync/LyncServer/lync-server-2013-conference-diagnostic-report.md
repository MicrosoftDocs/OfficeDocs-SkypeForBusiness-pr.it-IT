---
title: 'Lync Server 2013: rapporto di diagnostica conferenze'
description: 'Lync Server 2013: rapporto di diagnostica conferenze.'
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
ms.openlocfilehash: 9d3ef3c78bc2145d907d5a40e1aed95a2f4cb4c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577642"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="0ba18-103">Rapporto di diagnostica conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba18-103">Conference Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ba18-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0ba18-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0ba18-p101">Il Rapporto di diagnostica conferenze fornisce informazioni sull'esito positivo o negativo di tutte le sessioni di conferenza. Si noti che Microsoft Lync Server distingue tra diversi tipi di errore:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p101">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions. Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="0ba18-p102">**Errore previsto**. Un errore previsto è tipicamente un errore solo in senso strettamente tecnico. Si immagini ad esempio che qualcuno avvii una conferenza, ma poi riagganci prima che qualcuno possa parteciparvi. Tecnicamente parlando, si tratta di un errore: la conferenza è stata avviata, ma non completata. Si tratta tuttavia di un errore previsto: se l'organizzatore annulla la conferenza prima che qualcuno possa parteciparvi, non ci si può aspettare che la conferenza venga completata.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="0ba18-p103">**Errore imprevisto**. Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe. Si immagini ad esempio una conferenza che non possa essere tenuta perché non è possibile recuperare il criterio riunione dell'organizzatore. Questo è un errore imprevisto: dopotutto, dovrebbe essere sempre possibile recuperare il criterio riunione di un utente.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="0ba18-p104">Si noti che le metriche di successo, errore previsto ed errore imprevisto potrebbero non sommarsi alla metrica totale delle sessioni. È ad esempio possibile che il report contenga i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ba18-118">Operazioni riuscite</span><span class="sxs-lookup"><span data-stu-id="0ba18-118">Successes</span></span></th>
<th><span data-ttu-id="0ba18-119">Errori previsti</span><span class="sxs-lookup"><span data-stu-id="0ba18-119">Expected failures</span></span></th>
<th><span data-ttu-id="0ba18-120">Errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="0ba18-120">Unexpected failures</span></span></th>
<th><span data-ttu-id="0ba18-121">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="0ba18-121">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-122">2024</span><span class="sxs-lookup"><span data-stu-id="0ba18-122">2024</span></span></p></td>
<td><p><span data-ttu-id="0ba18-123">469</span><span class="sxs-lookup"><span data-stu-id="0ba18-123">469</span></span></p></td>
<td><p><span data-ttu-id="0ba18-124">16 </span><span class="sxs-lookup"><span data-stu-id="0ba18-124">16</span></span></p></td>
<td><p><span data-ttu-id="0ba18-125">2521</span><span class="sxs-lookup"><span data-stu-id="0ba18-125">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ba18-126">Se si somma 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, tuttavia, nella colonna Totale sessioni viene indicato un totale di 2.521 sessioni.</span><span class="sxs-lookup"><span data-stu-id="0ba18-126">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="0ba18-127">Le 12 sessioni "mancanti" sono quelle il cui esito non è stato definito come positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="0ba18-127">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="0ba18-128">A volte si verificherà il caso in cui un prodotto di terze parti introduce un nuovo codice diagnostico non pratico per il Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="0ba18-128">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="0ba18-129">In questi casi le chiamate fatte utilizzando tale prodotto, che presentano quel codice diagnostico, non possono essere categorizzate con Esito positivo, Errore previsto o Errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="0ba18-129">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="0ba18-130">Accesso al Rapporto di diagnostica conferenze</span><span class="sxs-lookup"><span data-stu-id="0ba18-130">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="0ba18-131">È possibile accedere al Rapporto di diagnostica conferenze dalla home page di Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="0ba18-131">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0ba18-132">È possibile accedere al [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba18-132">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0ba18-133">Quantità di errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="0ba18-133">Unexpected failure volume</span></span>

  - <span data-ttu-id="0ba18-134">Quantità di errori previsti</span><span class="sxs-lookup"><span data-stu-id="0ba18-134">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="0ba18-135">Utilizzare al meglio il Rapporto di diagnostica conferenze</span><span class="sxs-lookup"><span data-stu-id="0ba18-135">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="0ba18-136">Il Rapporto di diagnostica conferenze include una serie di grafici.</span><span class="sxs-lookup"><span data-stu-id="0ba18-136">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="0ba18-137">Ogni colonna del grafico è un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="0ba18-137">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="0ba18-138">Se si fa clic su una colonna, sarà possibile eseguire il drill-down [nel rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) per quel periodo di tempo e quel tipo di conferenza.</span><span class="sxs-lookup"><span data-stu-id="0ba18-138">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0ba18-139">Filtri</span><span class="sxs-lookup"><span data-stu-id="0ba18-139">Filters</span></span>

<span data-ttu-id="0ba18-p108">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto di diagnostica conferenze consente di filtrare in base al tipo di conferenza condotto (ad esempio, una conferenza basata su Focus) o al server perimetrale utilizzato nella conferenza. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0ba18-144">Nella tabella che segue sono elencati i filtri applicabili al Rapporto di diagnostica conferenze.</span><span class="sxs-lookup"><span data-stu-id="0ba18-144">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="0ba18-145">Filtri del Rapporto di diagnostica conferenze</span><span class="sxs-lookup"><span data-stu-id="0ba18-145">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ba18-146">Nome</span><span class="sxs-lookup"><span data-stu-id="0ba18-146">Name</span></span></th>
<th><span data-ttu-id="0ba18-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ba18-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-p109">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0ba18-151">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="0ba18-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ba18-p110">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ba18-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0ba18-154">7/7/2012</span></span></p>
<p><span data-ttu-id="0ba18-155">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="0ba18-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ba18-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0ba18-156">7/3/2012</span></span></p>
<p><span data-ttu-id="0ba18-157">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="0ba18-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba18-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-p111">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0ba18-161">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="0ba18-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0ba18-p112">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0ba18-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0ba18-164">7/7/2012</span></span></p>
<p><span data-ttu-id="0ba18-165">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="0ba18-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0ba18-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0ba18-166">7/3/2012</span></span></p>
<p><span data-ttu-id="0ba18-167">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="0ba18-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-168"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-168"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-p113">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0ba18-171">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="0ba18-171">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0ba18-172">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="0ba18-172">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0ba18-173">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="0ba18-173">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0ba18-174">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="0ba18-174">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0ba18-p114">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="0ba18-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba18-177"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-177"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-p115">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-181"><strong>Sessioni conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-181"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-p116">Indica il tipo di sessione di conferenza. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0ba18-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0ba18-184">Tutti</span><span class="sxs-lookup"><span data-stu-id="0ba18-184">[All]</span></span></p></li>
<li><p><span data-ttu-id="0ba18-185">Sessioni Focus</span><span class="sxs-lookup"><span data-stu-id="0ba18-185">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="0ba18-186">Tutte le sessioni MCU</span><span class="sxs-lookup"><span data-stu-id="0ba18-186">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="0ba18-187">IM Conferencing</span><span class="sxs-lookup"><span data-stu-id="0ba18-187">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="0ba18-188">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="0ba18-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="0ba18-189">Conferenze audio/video</span><span class="sxs-lookup"><span data-stu-id="0ba18-189">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0ba18-190">Metriche</span><span class="sxs-lookup"><span data-stu-id="0ba18-190">Metrics</span></span>

<span data-ttu-id="0ba18-191">La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica conferenza per tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="0ba18-191">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="0ba18-192">Metriche del Rapporto di diagnostica conferenze</span><span class="sxs-lookup"><span data-stu-id="0ba18-192">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ba18-193">Nome</span><span class="sxs-lookup"><span data-stu-id="0ba18-193">Name</span></span></th>
<th><span data-ttu-id="0ba18-194">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="0ba18-194">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0ba18-195">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ba18-195">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-196"><strong>Success volume</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-196"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-197">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-197">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-198">Numero totale di conferenze riuscite.</span><span class="sxs-lookup"><span data-stu-id="0ba18-198">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba18-199"><strong>Success percentage</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-199"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-200">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-200">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-p117">Percentuale di conferenze completate con problemi significativi. Questo valore viene calcolato dividendo la quantità di conferenze con esito positivo per il numero totale delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-203"><strong>Expected failure volume</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-203"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-204">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-204">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-205">Numero totale di conferenze in cui &quot; &quot; si è verificato un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="0ba18-205">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0ba18-p118">Per errore previsto si intende un errore che è previsto che si verifichi. Se ad esempio un utente imposta il proprio stato su Non disturbare, è previsto che qualsiasi chiamata effettuata a tale utente non riesca.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba18-208"><strong>Expected failure percentage</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-208"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-209">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-209">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-p119">Percentuale di conferenze in cui si è verificato un errore previsto. Questo valore viene calcolato dividendo la quantità totale di errori previsti per il numero totale di sessioni.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-212"><strong>Unexpected failure volume</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-212"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-213">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-213">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-214">Numero totale di conferenze in cui &quot; si è verificato un errore imprevisto &quot; .</span><span class="sxs-lookup"><span data-stu-id="0ba18-214">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0ba18-p120">Per errore non previsto si intende un errore che si verifica in un sistema che sembrerebbe altrimenti integro. Ad esempio, una chiamata non dovrebbe essere terminata se il chiamante la mette in attesa. Se questo errore si verifica, viene contrassegnato come imprevisto.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ba18-218"><strong>Unexpected failure percentage</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-218"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-219">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-219">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-p121">Percentuale di conferenze in cui si è verificato un errore imprevisto. Questo valore viene calcolato dividendo la quantità totale di errori imprevisti per il numero totale di sessioni.</span><span class="sxs-lookup"><span data-stu-id="0ba18-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ba18-222"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="0ba18-222"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0ba18-223">No</span><span class="sxs-lookup"><span data-stu-id="0ba18-223">No</span></span></p></td>
<td><p><span data-ttu-id="0ba18-224">Numero totale di conferenze, incluse quelle riuscite, non riuscite (per errori previsti e imprevisti) e non categorizzate.</span><span class="sxs-lookup"><span data-stu-id="0ba18-224">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

