---
title: 'Lync Server 2013: report di riepilogo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="41f8d-102">Report Riepilogo conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f8d-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41f8d-103">_**Argomento Ultima modifica:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="41f8d-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="41f8d-104">Il report Riepilogo conferenze offre una panoramica complessiva delle sessioni di conferenza online.</span><span class="sxs-lookup"><span data-stu-id="41f8d-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="41f8d-105">Una conferenza include in genere più di 2 utenti e richiede l'uso di servizi di conferenza di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41f8d-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="41f8d-106">In confronto, una sessione peer-to-peer in genere coinvolge solo 2 utenti e non richiede l'uso dei servizi di conferenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41f8d-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="41f8d-107">Le attività peer-to-peer sono segnalate nel [report di riepilogo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="41f8d-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="41f8d-108">Il report Riepilogo conferenza non solo indica il numero di conferenze svolte durante un determinato periodo di tempo (ogni ora, ogni giorno, ogni settimana, ogni mese), ma indica anche il totale delle persone che hanno partecipato a tali conferenze e il numero totale di conferenze esclusive organizzatori.</span><span class="sxs-lookup"><span data-stu-id="41f8d-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="41f8d-109">Un organizzatore "univoco" è chiunque abbia pianificato almeno una conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-109">A "unique” organizer is anyone who schedules at least one conference.</span></span> <span data-ttu-id="41f8d-110">Ad esempio, se Pilar Ackerman pianifica una conferenza che conta come unica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="41f8d-110">For example, if Pilar Ackerman schedules one conference she counts as one unique organizer.</span></span> <span data-ttu-id="41f8d-111">Se Ken REQUESTO programma le conferenze di 148, conta anche come unico organizzatore.</span><span class="sxs-lookup"><span data-stu-id="41f8d-111">If Ken Myer schedules 148 conferences he, too counts as one unique organizer.</span></span> <span data-ttu-id="41f8d-112">Ad esempio, la tabella seguente mostra 8 conferenze programmate, ma solo tre organizzatori unici (Ken, Pilar Ackerman e David AHS).</span><span class="sxs-lookup"><span data-stu-id="41f8d-112">For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41f8d-113">Organizzatore di conferenze</span><span class="sxs-lookup"><span data-stu-id="41f8d-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="41f8d-114">Data conferenza</span><span class="sxs-lookup"><span data-stu-id="41f8d-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-115">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-117">David AHS</span><span class="sxs-lookup"><span data-stu-id="41f8d-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="41f8d-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-119">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-123">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-127">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41f8d-131">Il report Riepilogo conferenza indica anche il numero di conferenze incluse audio e/o video.</span><span class="sxs-lookup"><span data-stu-id="41f8d-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="41f8d-132">Accesso al report di riepilogo conferenza</span><span class="sxs-lookup"><span data-stu-id="41f8d-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="41f8d-133">È possibile accedere al report di riepilogo conferenza dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="41f8d-133">The Conference Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="41f8d-134">È possibile eseguire il drill-down nel report attività conferenza facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="41f8d-134">You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="41f8d-135">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="41f8d-135">Total conferences</span></span>

  - <span data-ttu-id="41f8d-136">Totale partecipanti</span><span class="sxs-lookup"><span data-stu-id="41f8d-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="41f8d-137">Uso ottimale del report di riepilogo conferenza</span><span class="sxs-lookup"><span data-stu-id="41f8d-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="41f8d-138">I valori totali per la maggior parte delle metriche usate nel report di riepilogo conferenza possono essere trovati nella parte inferiore del report. scorrere verso il basso per visualizzare i valori, ad esempio il numero totale di conferenze detenute durante il periodo di tempo specificato, e il numero totale di persone che hanno partecipato a tali conferenze.</span><span class="sxs-lookup"><span data-stu-id="41f8d-138">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences.</span></span> <span data-ttu-id="41f8d-139">Una metrica non totalizzata nella parte inferiore del report è totale organizzatori di conferenze univoci.</span><span class="sxs-lookup"><span data-stu-id="41f8d-139">One metric that is not totaled at the bottom of the report is Total unique conference organizers.</span></span> <span data-ttu-id="41f8d-140">Perché no?</span><span class="sxs-lookup"><span data-stu-id="41f8d-140">Why not?</span></span> <span data-ttu-id="41f8d-141">Ecco un motivo.</span><span class="sxs-lookup"><span data-stu-id="41f8d-141">Here’s one reason.</span></span> <span data-ttu-id="41f8d-142">Supponiamo che tu stia esaminando il valore di un mese di dati.</span><span class="sxs-lookup"><span data-stu-id="41f8d-142">Suppose you are looking at a month's worth of data.</span></span> <span data-ttu-id="41f8d-143">Il giorno 1 hai avuto 34 organizzatori di conferenze univoci; il giorno 2 si sono organizzati 27 organizzatori di conferenze univoci.</span><span class="sxs-lookup"><span data-stu-id="41f8d-143">On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers.</span></span> <span data-ttu-id="41f8d-144">Vuol dire che hai avuto 61 organizzatori di conferenze univoci per questi due giorni?</span><span class="sxs-lookup"><span data-stu-id="41f8d-144">Does that mean you had 61 unique conference organizers for those two days?</span></span> <span data-ttu-id="41f8d-145">Non necessariamente.</span><span class="sxs-lookup"><span data-stu-id="41f8d-145">Not necessarily.</span></span> <span data-ttu-id="41f8d-146">Dopo tutto, tutte le 27 persone che hanno organizzato conferenze il giorno 2 potrebbero essere tra le 34 persone che hanno organizzato conferenze il giorno 1.</span><span class="sxs-lookup"><span data-stu-id="41f8d-146">After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1.</span></span> <span data-ttu-id="41f8d-147">In questo semplice report, ad esempio, si noti che Ken Rein e Pilar Ackerman hanno programmato le conferenze sia in 7/7/2012 che in 7/2/2012:</span><span class="sxs-lookup"><span data-stu-id="41f8d-147">For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41f8d-148">Organizzatore di conferenze</span><span class="sxs-lookup"><span data-stu-id="41f8d-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="41f8d-149">Data conferenza</span><span class="sxs-lookup"><span data-stu-id="41f8d-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-150">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-152">David AHS</span><span class="sxs-lookup"><span data-stu-id="41f8d-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="41f8d-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-154">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-158">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-162">Ken</span><span class="sxs-lookup"><span data-stu-id="41f8d-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="41f8d-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="41f8d-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="41f8d-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="41f8d-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41f8d-166">Per avere un'idea migliore del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo; ad esempio, esamina i dati per mese anziché per giorno.</span><span class="sxs-lookup"><span data-stu-id="41f8d-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="41f8d-167">Filtri</span><span class="sxs-lookup"><span data-stu-id="41f8d-167">Filters</span></span>

<span data-ttu-id="41f8d-168">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="41f8d-168">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="41f8d-169">Ad esempio, il report Riepilogo conferenza consente di scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="41f8d-169">For example, the Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="41f8d-170">In questo caso, le conferenze sono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="41f8d-170">In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="41f8d-171">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="41f8d-172">Filtri di report Riepilogo conferenze</span><span class="sxs-lookup"><span data-stu-id="41f8d-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41f8d-173">Nome</span><span class="sxs-lookup"><span data-stu-id="41f8d-173">Name</span></span></th>
<th><span data-ttu-id="41f8d-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41f8d-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-175"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-176">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="41f8d-176">Start date/time for the time range.</span></span> <span data-ttu-id="41f8d-177">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41f8d-177">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="41f8d-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="41f8d-179">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-179">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="41f8d-180">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="41f8d-180">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="41f8d-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="41f8d-181">7/7/2012</span></span></p>
<p><span data-ttu-id="41f8d-182">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="41f8d-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="41f8d-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="41f8d-183">7/3/2012</span></span></p>
<p><span data-ttu-id="41f8d-184">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-185"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-186">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="41f8d-186">End date/time for the time range.</span></span> <span data-ttu-id="41f8d-187">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41f8d-187">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="41f8d-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="41f8d-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="41f8d-189">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-189">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="41f8d-190">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="41f8d-190">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="41f8d-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="41f8d-191">7/7/2012</span></span></p>
<p><span data-ttu-id="41f8d-192">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="41f8d-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="41f8d-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="41f8d-193">7/3/2012</span></span></p>
<p><span data-ttu-id="41f8d-194">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-195"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-196">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="41f8d-196">Time interval.</span></span> <span data-ttu-id="41f8d-197">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41f8d-197">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="41f8d-198">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="41f8d-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="41f8d-199">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="41f8d-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="41f8d-200">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="41f8d-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="41f8d-201">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="41f8d-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="41f8d-202">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, vengono visualizzati solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="41f8d-202">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="41f8d-203">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="41f8d-203">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="41f8d-204">Metriche</span><span class="sxs-lookup"><span data-stu-id="41f8d-204">Metrics</span></span>

<span data-ttu-id="41f8d-205">Tabella seguente le informazioni fornite dal report di riepilogo conferenze.</span><span class="sxs-lookup"><span data-stu-id="41f8d-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="41f8d-206">Metriche report Riepilogo conferenze</span><span class="sxs-lookup"><span data-stu-id="41f8d-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41f8d-207">Nome</span><span class="sxs-lookup"><span data-stu-id="41f8d-207">Name</span></span></th>
<th><span data-ttu-id="41f8d-208">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="41f8d-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="41f8d-209">Descrizione</span><span class="sxs-lookup"><span data-stu-id="41f8d-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-210"><strong>Oraria</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="41f8d-211"><strong>Quotidiana</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="41f8d-212"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="41f8d-213"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-214">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-214">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-215">Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro.</span><span class="sxs-lookup"><span data-stu-id="41f8d-215">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="41f8d-216">Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="41f8d-216">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="41f8d-217">Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="41f8d-217">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-218"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-219">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-219">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-220">Numero totale di conferenze (indipendentemente dal tipo di conferenza) che si sono svolte.</span><span class="sxs-lookup"><span data-stu-id="41f8d-220">Total number of conferences (regardless of conference type) that were held.</span></span> <span data-ttu-id="41f8d-221">Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-221">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-222"><strong>Totale partecipanti</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-223">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-223">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-224">Numero totale di persone che hanno partecipato alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="41f8d-224">Total number of people who took part in the conferences.</span></span> <span data-ttu-id="41f8d-225">Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="41f8d-225">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-226"><strong>Partecipanti medi per conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-227">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-227">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-228">Numero medio di persone che hanno partecipato a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-228">Average number of people who took part in a given conference.</span></span> <span data-ttu-id="41f8d-229">Determinato dividendo le conferenze totali per il totale dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="41f8d-229">Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-230"><strong>Totale conferenze A/V</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-231">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-231">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-232">Numero totale di conferenze che includono audio o video.</span><span class="sxs-lookup"><span data-stu-id="41f8d-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-233"><strong>Totale minuti di conferenza A/V</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-234">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-234">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-235">Numero totale di minuti dedicati alle conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="41f8d-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="41f8d-236">La metrica totale minuti conferenze A/V riepiloga tutti i tipi di conferenze audio/visive, tra cui: conferenze A/V; Conferenze di messaggistica istantanea; Conferenze di condivisione delle app; Conferenze dati; e conferenze PSTN.</span><span class="sxs-lookup"><span data-stu-id="41f8d-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-237"><strong>Totale minuti partecipanti alla conferenza A/V</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-238">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-238">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-239">Numero totale di minuti per i partecipanti dedicati alle conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="41f8d-239">Total number of participant minutes devoted to audio/video conferencing.</span></span> <span data-ttu-id="41f8d-240">Supponiamo ad esempio che un utente spenda 5 minuti in una conferenza audio/video e un secondo utente passi 3 minuti alla stessa conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-240">For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference.</span></span> <span data-ttu-id="41f8d-241">Il che rende un totale di 8 minuti per i partecipanti: 5 minuti più 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="41f8d-241">That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-242"><strong>Minuti media di conferenza A/V</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-243">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-243">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-244">Numero medio di minuti per conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="41f8d-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41f8d-245"><strong>Numero totale di organizzatori univoci delle conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-246">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-246">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-247">Numero totale di utenti che hanno organizzato almeno una conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-247">Total number of users who organized at least one conference.</span></span> <span data-ttu-id="41f8d-248">Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.</span><span class="sxs-lookup"><span data-stu-id="41f8d-248">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41f8d-249"><strong>Totale messaggi conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="41f8d-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="41f8d-250">No</span><span class="sxs-lookup"><span data-stu-id="41f8d-250">No</span></span></p></td>
<td><p><span data-ttu-id="41f8d-251">Numero totale di messaggi istantanei inviati durante le conferenze.</span><span class="sxs-lookup"><span data-stu-id="41f8d-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

