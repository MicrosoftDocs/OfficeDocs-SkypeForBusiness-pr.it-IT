---
title: 'Lync Server 2013: report di messaggistica istantanea peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 359c3fad7f41d990ffdba3aa533d0d5f10456665
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="56e40-102">Report di messaggistica istantanea peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56e40-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56e40-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="56e40-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="56e40-104">Il report di messaggistica istantanea peer-to-peer fornisce informazioni sulla tendenza sulle sessioni di messaggistica immediata (IM) peer-to-peer, suddivise per pool e per tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="56e40-104">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type.</span></span> <span data-ttu-id="56e40-105">Il report può visualizzare il numero totale di sessioni consentite durante il periodo di tempo specificato, ad esempio giorno per giorno o ora per ora, oppure può visualizzare il numero totale di messaggi istantanei inviati durante il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="56e40-105">The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="56e40-106">Accesso al report di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="56e40-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="56e40-107">È possibile accedere al report di messaggistica istantanea peer-to-peer solo aprendo il [report di riepilogo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="56e40-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="56e40-108">Totale sessioni di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="56e40-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="56e40-109">Totale messaggi di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="56e40-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="56e40-110">Sfruttare al meglio il report di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="56e40-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="56e40-111">Per impostazione predefinita, il rapporto di messaggistica istantanea peer-to-peer Mostra il numero di messaggi per ora (o giorno), a seconda delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="56e40-111">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings).</span></span> <span data-ttu-id="56e40-112">Tuttavia, puoi anche scegliere di visualizzare il giorno per sessioni per ora.</span><span class="sxs-lookup"><span data-stu-id="56e40-112">However, you can also choose to view the day by sessions per hour.</span></span> <span data-ttu-id="56e40-113">A tale scopo, fare clic su **Nascondi/Mostra parametri** nell'angolo in alto a destra della finestra report e quindi fare clic su **conteggio sessioni** nell'elenco **segnala per** .</span><span class="sxs-lookup"><span data-stu-id="56e40-113">To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="56e40-114">Filtri</span><span class="sxs-lookup"><span data-stu-id="56e40-114">Filters</span></span>

<span data-ttu-id="56e40-115">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="56e40-115">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="56e40-116">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="56e40-116">The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="56e40-117">Filtri di report istantanei di messaggistica istantanea peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="56e40-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56e40-118">Nome</span><span class="sxs-lookup"><span data-stu-id="56e40-118">Name</span></span></th>
<th><span data-ttu-id="56e40-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56e40-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56e40-120"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-121">Data e ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="56e40-121">Start date and time for the time range.</span></span> <span data-ttu-id="56e40-122">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56e40-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="56e40-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="56e40-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="56e40-124">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="56e40-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="56e40-125">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="56e40-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="56e40-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="56e40-126">7/7/2012</span></span></p>
<p><span data-ttu-id="56e40-127">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="56e40-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="56e40-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="56e40-128">7/3/2012</span></span></p>
<p><span data-ttu-id="56e40-129">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="56e40-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56e40-130"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-131">Data e ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="56e40-131">End date and time for the time range.</span></span> <span data-ttu-id="56e40-132">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="56e40-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="56e40-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="56e40-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="56e40-134">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="56e40-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="56e40-135">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="56e40-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="56e40-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="56e40-136">7/7/2012</span></span></p>
<p><span data-ttu-id="56e40-137">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="56e40-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="56e40-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="56e40-138">7/3/2012</span></span></p>
<p><span data-ttu-id="56e40-139">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="56e40-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56e40-140"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-141">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="56e40-141">Time interval.</span></span> <span data-ttu-id="56e40-142">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56e40-142">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="56e40-143">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="56e40-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56e40-144">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="56e40-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56e40-145">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="56e40-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="56e40-146">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="56e40-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="56e40-147">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="56e40-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="56e40-148">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="56e40-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56e40-149"><strong>Report di</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-150">Indica i valori da usare nel report.</span><span class="sxs-lookup"><span data-stu-id="56e40-150">Indicates the values to be used in the report.</span></span> <span data-ttu-id="56e40-151">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="56e40-151">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="56e40-152">Conteggio sessioni</span><span class="sxs-lookup"><span data-stu-id="56e40-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="56e40-153">Numero di messaggi</span><span class="sxs-lookup"><span data-stu-id="56e40-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="56e40-154">Metriche per la sessione di messaggistica istantanea peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="56e40-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="56e40-155">Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="56e40-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="56e40-156">Metriche per la sessione di messaggistica istantanea peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="56e40-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56e40-157">Nome</span><span class="sxs-lookup"><span data-stu-id="56e40-157">Name</span></span></th>
<th><span data-ttu-id="56e40-158">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="56e40-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="56e40-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56e40-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56e40-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-161">No</span><span class="sxs-lookup"><span data-stu-id="56e40-161">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-162">Nome del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="56e40-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56e40-163"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-164">No</span><span class="sxs-lookup"><span data-stu-id="56e40-164">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-165">Data e ora in cui sono state svolte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="56e40-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56e40-166"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-167">No</span><span class="sxs-lookup"><span data-stu-id="56e40-167">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-168">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="56e40-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="56e40-169">Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="56e40-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="56e40-170">Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione usato dai partecipanti in una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="56e40-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="56e40-171">Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="56e40-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56e40-172">Nome</span><span class="sxs-lookup"><span data-stu-id="56e40-172">Name</span></span></th>
<th><span data-ttu-id="56e40-173">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="56e40-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="56e40-174">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56e40-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56e40-175"><strong>Tipo di autenticazione</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-176">No</span><span class="sxs-lookup"><span data-stu-id="56e40-176">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-177">Tipo di autenticazione usato dai partecipanti alla sessione.</span><span class="sxs-lookup"><span data-stu-id="56e40-177">Type of authentication used by the session participants.</span></span> <span data-ttu-id="56e40-178">I valori sono in genere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="56e40-178">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="56e40-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="56e40-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="56e40-180">Federata</span><span class="sxs-lookup"><span data-stu-id="56e40-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="56e40-181">PIC</span><span class="sxs-lookup"><span data-stu-id="56e40-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56e40-182"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-183">No</span><span class="sxs-lookup"><span data-stu-id="56e40-183">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-184">Data e ora in cui sono state svolte le sessioni.</span><span class="sxs-lookup"><span data-stu-id="56e40-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56e40-185"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="56e40-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="56e40-186">No</span><span class="sxs-lookup"><span data-stu-id="56e40-186">No</span></span></p></td>
<td><p><span data-ttu-id="56e40-187">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="56e40-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

