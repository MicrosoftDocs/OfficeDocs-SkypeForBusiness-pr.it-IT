---
title: "Lync Server 2013: report sull'ora di partecipazione alla conferenza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="7c835-102">Report sull'ora di partecipazione alla conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c835-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c835-103">_**Argomento Ultima modifica:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="7c835-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="7c835-104">Il riepilogo dell'ora di partecipazione alla conferenza consente di determinare il tempo impiegato dagli utenti per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-104">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="7c835-105">Il report Mostra il tempo medio di partecipazione (in millisecondi) e fornisce anche una ripartizione che consente di conoscere il numero di utenti che hanno potuto partecipare a una conferenza in 2 secondi o meno, il numero di utenti necessari tra 2 e 5 secondi per partecipare alla conferenza e così via.</span><span class="sxs-lookup"><span data-stu-id="7c835-105">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="7c835-106">Accesso al report tempo di partecipazione alla conferenza</span><span class="sxs-lookup"><span data-stu-id="7c835-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="7c835-107">È possibile accedere al report Time join della conferenza dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="7c835-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7c835-108">Filtri</span><span class="sxs-lookup"><span data-stu-id="7c835-108">Filters</span></span>

<span data-ttu-id="7c835-109">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="7c835-109">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7c835-110">Nella tabella seguente sono elencati i filtri che è possibile usare con il report tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-110">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="7c835-111">Filtri per i report sull'ora di conferenza</span><span class="sxs-lookup"><span data-stu-id="7c835-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c835-112">Nome</span><span class="sxs-lookup"><span data-stu-id="7c835-112">Name</span></span></th>
<th><span data-ttu-id="7c835-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c835-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c835-114"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-115">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7c835-115">Start date/time for the time range.</span></span> <span data-ttu-id="7c835-116">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7c835-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7c835-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7c835-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7c835-118">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="7c835-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7c835-119">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7c835-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7c835-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7c835-120">7/7/2012</span></span></p>
<p><span data-ttu-id="7c835-121">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7c835-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7c835-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7c835-122">7/3/2012</span></span></p>
<p><span data-ttu-id="7c835-123">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="7c835-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-124"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-125">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7c835-125">End date/time for the time range.</span></span> <span data-ttu-id="7c835-126">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7c835-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7c835-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7c835-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7c835-128">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="7c835-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7c835-129">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="7c835-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7c835-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7c835-130">7/7/2012</span></span></p>
<p><span data-ttu-id="7c835-131">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="7c835-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7c835-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7c835-132">7/3/2012</span></span></p>
<p><span data-ttu-id="7c835-133">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="7c835-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-134"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-135">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7c835-135">Time interval.</span></span> <span data-ttu-id="7c835-136">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c835-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c835-137">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="7c835-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7c835-138">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="7c835-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7c835-139">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="7c835-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7c835-140">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="7c835-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7c835-141">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="7c835-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="7c835-142">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="7c835-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-144">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="7c835-144">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="7c835-145">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="7c835-145">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="7c835-146">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="7c835-146">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-147"><strong>Sessioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-148">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="7c835-148">Type of session.</span></span> <span data-ttu-id="7c835-149">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="7c835-149">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c835-150">Tutti</span><span class="sxs-lookup"><span data-stu-id="7c835-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="7c835-151">Sessioni di stato attiva (lo stato principale è lo stato di policy e il gestore di stato per le riunioni online e coordina tutti gli aspetti di una conferenza</span><span class="sxs-lookup"><span data-stu-id="7c835-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="7c835-152">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="7c835-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="7c835-153">Servizi di conferenza A/V</span><span class="sxs-lookup"><span data-stu-id="7c835-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="7c835-154">Se si seleziona [tutti], nella parte superiore del report verrà visualizzato il tempo totale di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-154">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="7c835-155">Tieni presente che questi totali sono solo per le conferenze pianificate con Microsoft Exchange o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="7c835-155">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7c835-156">Metriche</span><span class="sxs-lookup"><span data-stu-id="7c835-156">Metrics</span></span>

<span data-ttu-id="7c835-157">Nella tabella seguente sono elencate le informazioni fornite nel report tempo di partecipazione alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="7c835-158">Metriche del report Time join conferenza</span><span class="sxs-lookup"><span data-stu-id="7c835-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c835-159">Nome</span><span class="sxs-lookup"><span data-stu-id="7c835-159">Name</span></span></th>
<th><span data-ttu-id="7c835-160">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="7c835-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7c835-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c835-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c835-162"><strong>Data</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="7c835-163">Il titolo effettivo per questa metrica sarà diverso a seconda dell'intervallo selezionato.</span><span class="sxs-lookup"><span data-stu-id="7c835-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="7c835-164">No</span><span class="sxs-lookup"><span data-stu-id="7c835-164">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-165">Data e ora in cui la conferenza ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="7c835-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-166"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-167">No</span><span class="sxs-lookup"><span data-stu-id="7c835-167">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-168">Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.</span><span class="sxs-lookup"><span data-stu-id="7c835-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-169"><strong>Media (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-170">No</span><span class="sxs-lookup"><span data-stu-id="7c835-170">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-171">Intervallo di tempo medio (in millisecondi) che ha richiesto ai partecipanti di partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-172"><strong>Sessioni &lt; 2 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-173">No</span><span class="sxs-lookup"><span data-stu-id="7c835-173">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-174">Numero di partecipanti che hanno potuto partecipare alla conferenza in meno di 2 secondi.</span><span class="sxs-lookup"><span data-stu-id="7c835-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-175"><strong>Sessioni &lt; 2 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-176">No</span><span class="sxs-lookup"><span data-stu-id="7c835-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-177"><strong>Sessioni 2-5 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-178">No</span><span class="sxs-lookup"><span data-stu-id="7c835-178">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-179">Numero di partecipanti che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-180"><strong>Sessioni 2-5 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-181">No</span><span class="sxs-lookup"><span data-stu-id="7c835-181">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-182">Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-183"><strong>Sessioni 5-10 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-184">No</span><span class="sxs-lookup"><span data-stu-id="7c835-184">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-185">Numero di partecipanti che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-186"><strong>Sessioni 5-10 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-187">No</span><span class="sxs-lookup"><span data-stu-id="7c835-187">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-188">Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c835-189"><strong>Sessioni &gt; di 10 secondi, volume</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-190">No</span><span class="sxs-lookup"><span data-stu-id="7c835-190">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-191">Numero di partecipanti che hanno richiesto più di 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c835-192"><strong>Sessioni &gt; di 10 secondi, percentuale</strong></span><span class="sxs-lookup"><span data-stu-id="7c835-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7c835-193">No</span><span class="sxs-lookup"><span data-stu-id="7c835-193">No</span></span></p></td>
<td><p><span data-ttu-id="7c835-194">Percentuale dei partecipanti totali alle chiamate che hanno richiesto più di 10 secondi per partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="7c835-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

