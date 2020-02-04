---
title: 'Lync Server 2013: report di riepilogo attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="b23c7-102">Report di riepilogo attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b23c7-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b23c7-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b23c7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b23c7-104">Il report di riepilogo attività peer-to-peer offre una visualizzazione complessiva delle sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="b23c7-105">Una sessione peer-to-peer in genere coinvolge solo due utenti e non richiede l'uso dei servizi di conferenza di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b23c7-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="b23c7-106">In confronto, una conferenza coinvolge in genere più di due utenti e richiede l'uso di servizi di conferenza di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b23c7-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="b23c7-107">L'attività conferenza viene segnalata nel report di riepilogo conferenza.</span><span class="sxs-lookup"><span data-stu-id="b23c7-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="b23c7-108">Il report di riepilogo attività peer-to-peer consente di rispondere a domande come le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b23c7-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="b23c7-109">Quanti messaggi istantanei peer-to-peer i miei utenti inviano in un giorno tipico?</span><span class="sxs-lookup"><span data-stu-id="b23c7-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="b23c7-110">I miei utenti sfruttano effettivamente le funzionalità di condivisione delle applicazioni e di trasferimento di file di Lync Server?</span><span class="sxs-lookup"><span data-stu-id="b23c7-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="b23c7-111">Gli utenti si lamentano che la rete sembra lenta in determinate ore del giorno.</span><span class="sxs-lookup"><span data-stu-id="b23c7-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="b23c7-112">Quanti minuti sono dedicati alle sessioni audio e video peer-to-peer in questi periodi di tempo?</span><span class="sxs-lookup"><span data-stu-id="b23c7-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="b23c7-113">Accesso al report di riepilogo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="b23c7-114">È possibile accedere al report di riepilogo attività peer-to-peer dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b23c7-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="b23c7-115">Per aprire il [report di messaggistica istantanea peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , fare clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b23c7-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b23c7-116">Totale sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="b23c7-117">Totale messaggi di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="b23c7-118">Analogamente, è possibile aprire il report vocale e video peer-to-peer facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b23c7-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="b23c7-119">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="b23c7-120">Totale minuti sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="b23c7-121">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="b23c7-122">Totale minuti sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="b23c7-123">Sfruttare al meglio il rapporto di riepilogo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="b23c7-124">Nella parte inferiore del report di riepilogo attività peer-to-peer si trovano i totali per le metriche, ad esempio le sessioni di messaggistica istantanea Total peer-to-peer e i messaggi di messaggistica istantanea totali peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="b23c7-125">In questo modo è disponibile un breve riepilogo delle informazioni dettagliate presenti nel corpo del report.</span><span class="sxs-lookup"><span data-stu-id="b23c7-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b23c7-126">Filtri</span><span class="sxs-lookup"><span data-stu-id="b23c7-126">Filters</span></span>

<span data-ttu-id="b23c7-127">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="b23c7-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b23c7-128">Il report di riepilogo attività peer-to-peer, ad esempio, consente di scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="b23c7-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="b23c7-129">In questo caso, attività raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="b23c7-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b23c7-130">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="b23c7-131">Filtri dei report di riepilogo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b23c7-132">Nome</span><span class="sxs-lookup"><span data-stu-id="b23c7-132">Name</span></span></th>
<th><span data-ttu-id="b23c7-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b23c7-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-134"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-135">Data e ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b23c7-135">Start date and time for the time range.</span></span> <span data-ttu-id="b23c7-136">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b23c7-136">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b23c7-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b23c7-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="b23c7-138">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-138">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b23c7-139">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b23c7-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b23c7-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="b23c7-140">7/17/12012</span></span></p>
<p><span data-ttu-id="b23c7-141">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b23c7-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b23c7-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="b23c7-142">7/13/2012</span></span></p>
<p><span data-ttu-id="b23c7-143">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-144"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-145">Data e ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b23c7-145">End date and time for the time range.</span></span> <span data-ttu-id="b23c7-146">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b23c7-146">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b23c7-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b23c7-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="b23c7-148">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-148">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b23c7-149">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b23c7-149">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b23c7-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="b23c7-150">7/17/12012</span></span></p>
<p><span data-ttu-id="b23c7-151">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b23c7-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b23c7-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="b23c7-152">7/13/2012</span></span></p>
<p><span data-ttu-id="b23c7-153">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-154"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-155">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b23c7-155">Time interval.</span></span> <span data-ttu-id="b23c7-156">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b23c7-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b23c7-157">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="b23c7-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b23c7-158">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="b23c7-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b23c7-159">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="b23c7-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b23c7-160">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="b23c7-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b23c7-161">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="b23c7-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="b23c7-162">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/17/12012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/12012 12:00 da AM a 9/7/12012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="b23c7-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b23c7-163">Metriche</span><span class="sxs-lookup"><span data-stu-id="b23c7-163">Metrics</span></span>

<span data-ttu-id="b23c7-164">Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="b23c7-165">Metriche rapporto di riepilogo attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b23c7-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b23c7-166">Nome</span><span class="sxs-lookup"><span data-stu-id="b23c7-166">Name</span></span></th>
<th><span data-ttu-id="b23c7-167">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="b23c7-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b23c7-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b23c7-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-169"><strong>Oraria</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="b23c7-170"><strong>Quotidiana</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="b23c7-171"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="b23c7-172"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-173">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-173">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-174">Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro.</span><span class="sxs-lookup"><span data-stu-id="b23c7-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="b23c7-175">Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b23c7-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="b23c7-176">Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/17/12012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="b23c7-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-177"><strong>Totale sessioni peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-178">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-178">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-179">Numero totale di sessioni peer-to-peer condotte, indipendentemente dal tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="b23c7-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-180"><strong>Totale sessioni di messaggistica istantanea peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-181">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-181">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-182">Numero totale di sessioni di messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="b23c7-183">Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-184"><strong>Totale messaggi di messaggistica istantanea peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-185">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-185">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-186">Numero totale di messaggi istantanei inviati nelle sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="b23c7-187">Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-188"><strong>Totale sessioni audio peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-189">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-189">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-190">Numero totale di chiamate audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="b23c7-191">Quando si fa clic su questo campo, nel report viene visualizzato il report vocale e video peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-192"><strong>Totale minuti sessioni audio peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-193">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-193">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-194">Quantità totale di tempo trascorso nelle sessioni audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="b23c7-195">Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-196"><strong>Minuti medi della sessione audio peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-197">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-197">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-198">Intervallo di tempo medio trascorso nelle sessioni audio peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="b23c7-199">Calcolata dividendo il tempo totale della sessione audio in base al numero totale di sessioni audio.</span><span class="sxs-lookup"><span data-stu-id="b23c7-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-200"><strong>Totale sessioni video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-201">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-201">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-202">Numero totale di chiamate video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="b23c7-203">Tieni presente che le sessioni video vengono conteggiate anche come sessioni audio: ogni sessione video viene conteggiata come una sessione video e una sessione audio.</span><span class="sxs-lookup"><span data-stu-id="b23c7-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="b23c7-204">Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-205"><strong>Totale minuti sessioni video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-206">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-206">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-207">Quantità totale di tempo trascorso nelle sessioni video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="b23c7-208">Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="b23c7-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-209"><strong>Minuti media sessione video peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-210">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-210">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-211">Intervallo di tempo medio trascorso nelle sessioni video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b23c7-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="b23c7-212">Calcolata dividendo il tempo totale della sessione video in base al numero totale di sessioni video.</span><span class="sxs-lookup"><span data-stu-id="b23c7-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b23c7-213"><strong>Totale sessioni di trasferimento di file peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-214">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-214">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-215">Numero totale di sessioni peer-to-peer che includevano i trasferimenti di file.</span><span class="sxs-lookup"><span data-stu-id="b23c7-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23c7-216"><strong>Totale sessioni di condivisione applicazioni peer-to-peer</strong></span><span class="sxs-lookup"><span data-stu-id="b23c7-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b23c7-217">No</span><span class="sxs-lookup"><span data-stu-id="b23c7-217">No</span></span></p></td>
<td><p><span data-ttu-id="b23c7-218">Numero totale di sessioni peer-to-peer che includevano la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b23c7-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

