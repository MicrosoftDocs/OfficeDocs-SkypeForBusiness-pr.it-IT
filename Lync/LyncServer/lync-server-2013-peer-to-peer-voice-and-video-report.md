---
title: 'Lync Server 2013: report vocale e video peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="b8153-102">Report vocale e video peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8153-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8153-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b8153-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b8153-104">Il report vocale e video peer-to-peer fornisce un'analisi dettagliata della distribuzione delle chiamate vocali e video in un determinato periodo di tempo, ad esempio chiamate per ora o chiamate per giorno.</span><span class="sxs-lookup"><span data-stu-id="b8153-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="b8153-105">Il report offre anche l'opzione di visualizzare tutte le chiamate vocali e video effettuate o di visualizzare solo le chiamate di successo o non riuscito.</span><span class="sxs-lookup"><span data-stu-id="b8153-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="b8153-106">I report mostrano le informazioni sulle chiamate suddivise nei raggruppamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="b8153-107">Chiamate per pool</span><span class="sxs-lookup"><span data-stu-id="b8153-107">Calls per pool</span></span>

  - <span data-ttu-id="b8153-108">Chiamate per tipo di chiamata, ad esempio Lync per una chiamata Lync e una chiamata Lync a una persona nella rete PSTN</span><span class="sxs-lookup"><span data-stu-id="b8153-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="b8153-109">Chiamate per tipo di accesso (gli utenti hanno effettuato l'accesso alla rete interna e agli utenti connessi alla rete esterna)</span><span class="sxs-lookup"><span data-stu-id="b8153-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="b8153-110">Chiamate per Mediation Server</span><span class="sxs-lookup"><span data-stu-id="b8153-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="b8153-111">Per accedere al report vocale e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="b8153-112">È possibile accedere al report vocale e video peer-to-peer solo aprendo il report di riepilogo attività peer-to-peer e quindi facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="b8153-113">Totale sessioni audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="b8153-114">Totale minuti audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="b8153-115">Totale sessioni video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="b8153-116">Totale minuti di video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="b8153-117">Per sfruttare al meglio il rapporto voce e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="b8153-118">È possibile filtrare il report vocale e video peer-to-peer in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="b8153-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="b8153-119">Tuttavia, le opzioni di filtro sono nascoste dalla visualizzazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b8153-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="b8153-120">Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante **Mostra/Nascondi parametri** nell'angolo in alto a destra della finestra del report.</span><span class="sxs-lookup"><span data-stu-id="b8153-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b8153-121">Filtri</span><span class="sxs-lookup"><span data-stu-id="b8153-121">Filters</span></span>

<span data-ttu-id="b8153-122">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="b8153-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="b8153-123">Nella tabella seguente sono elencati i filtri che è possibile usare con il report vocale e video peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="b8153-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="b8153-124">Filtri di report vocali e video peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b8153-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8153-125">Nome</span><span class="sxs-lookup"><span data-stu-id="b8153-125">Name</span></span></th>
<th><span data-ttu-id="b8153-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8153-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8153-127"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-128">Data e ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b8153-128">Start date and time for the time range.</span></span> <span data-ttu-id="b8153-129">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8153-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b8153-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b8153-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b8153-131">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="b8153-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b8153-132">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b8153-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b8153-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b8153-133">7/7/2012</span></span></p>
<p><span data-ttu-id="b8153-134">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b8153-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b8153-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b8153-135">7/3/2012</span></span></p>
<p><span data-ttu-id="b8153-136">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="b8153-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-137"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-138">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b8153-138">End date/time for the time range.</span></span> <span data-ttu-id="b8153-139">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b8153-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b8153-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b8153-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b8153-141">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="b8153-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="b8153-142">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b8153-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b8153-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b8153-143">7/7/2012</span></span></p>
<p><span data-ttu-id="b8153-144">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b8153-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b8153-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b8153-145">7/3/2012</span></span></p>
<p><span data-ttu-id="b8153-146">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="b8153-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-147"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-148">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="b8153-148">Time interval.</span></span> <span data-ttu-id="b8153-149">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-150">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="b8153-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b8153-151">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="b8153-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b8153-152">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="b8153-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b8153-153">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="b8153-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b8153-154">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="b8153-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="b8153-155">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="b8153-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-156"><strong>Tipo di elemento multimediale</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-157">Indica il tipo di elemento multimediale usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="b8153-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="b8153-158">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-159">Sia</span><span class="sxs-lookup"><span data-stu-id="b8153-159">Both</span></span></p></li>
<li><p><span data-ttu-id="b8153-160">Audio</span><span class="sxs-lookup"><span data-stu-id="b8153-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="b8153-161">Video</span><span class="sxs-lookup"><span data-stu-id="b8153-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-162"><strong>Disposizione chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-163">Indica l'esito positivo o negativo della sessione.</span><span class="sxs-lookup"><span data-stu-id="b8153-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="b8153-164">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-165">Tutti</span><span class="sxs-lookup"><span data-stu-id="b8153-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="b8153-166">Chiamate di successo</span><span class="sxs-lookup"><span data-stu-id="b8153-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="b8153-167">Chiamate non riuscite</span><span class="sxs-lookup"><span data-stu-id="b8153-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-168"><strong>Report di</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-169">Indica i valori da usare nel report.</span><span class="sxs-lookup"><span data-stu-id="b8153-169">Indicates the values to be used in the report.</span></span> <span data-ttu-id="b8153-170">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-171">Conteggio sessioni</span><span class="sxs-lookup"><span data-stu-id="b8153-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="b8153-172">Minuti di chiamata</span><span class="sxs-lookup"><span data-stu-id="b8153-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="b8153-173">Metriche per l'attività vocale e video peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="b8153-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="b8153-174">Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="b8153-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="b8153-175">Metriche per l'attività vocale e video peer-to-peer per pool</span><span class="sxs-lookup"><span data-stu-id="b8153-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8153-176">Nome</span><span class="sxs-lookup"><span data-stu-id="b8153-176">Name</span></span></th>
<th><span data-ttu-id="b8153-177">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="b8153-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b8153-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8153-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8153-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-180">No</span><span class="sxs-lookup"><span data-stu-id="b8153-180">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-181">Nome del pool di registrazione o del server perimetrale usato per la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8153-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-182"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-183">No</span><span class="sxs-lookup"><span data-stu-id="b8153-183">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-184">Periodo di data e ora in cui la chiamata ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="b8153-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-185"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-186">No</span><span class="sxs-lookup"><span data-stu-id="b8153-186">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-187">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b8153-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="b8153-188">Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="b8153-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="b8153-189">Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="b8153-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="b8153-190">Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata</span><span class="sxs-lookup"><span data-stu-id="b8153-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8153-191">Nome</span><span class="sxs-lookup"><span data-stu-id="b8153-191">Name</span></span></th>
<th><span data-ttu-id="b8153-192">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="b8153-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b8153-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8153-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8153-194"><strong>Tipo di chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-195">No</span><span class="sxs-lookup"><span data-stu-id="b8153-195">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-196">Indica il tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="b8153-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="b8153-197">I valori sono uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-198">UC-to-UC</span><span class="sxs-lookup"><span data-stu-id="b8153-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="b8153-199">UC-to-PSTN</span><span class="sxs-lookup"><span data-stu-id="b8153-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="b8153-200">PSTN-to-UC</span><span class="sxs-lookup"><span data-stu-id="b8153-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="b8153-201">PSTN-to-PSTN</span><span class="sxs-lookup"><span data-stu-id="b8153-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-202"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-203">No</span><span class="sxs-lookup"><span data-stu-id="b8153-203">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-204">Periodo di data e ora in cui la chiamata ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="b8153-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-205"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-206">No</span><span class="sxs-lookup"><span data-stu-id="b8153-206">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-207">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b8153-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="b8153-208">Metriche per l'attività voce e video peer-to-peer per tipo di accesso</span><span class="sxs-lookup"><span data-stu-id="b8153-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="b8153-209">Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="b8153-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="b8153-210">Metriche per l'attività voce e video peer-to-peer per tipo di accesso</span><span class="sxs-lookup"><span data-stu-id="b8153-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8153-211">Nome</span><span class="sxs-lookup"><span data-stu-id="b8153-211">Name</span></span></th>
<th><span data-ttu-id="b8153-212">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="b8153-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b8153-213">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8153-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8153-214"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-215">No</span><span class="sxs-lookup"><span data-stu-id="b8153-215">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-216">Indica se i client hanno eseguito l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b8153-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="b8153-217">I valori sono in genere uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8153-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b8153-218">Interno</span><span class="sxs-lookup"><span data-stu-id="b8153-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="b8153-219">Esterno</span><span class="sxs-lookup"><span data-stu-id="b8153-219">External</span></span></p></li>
<li><p><span data-ttu-id="b8153-220">Misto</span><span class="sxs-lookup"><span data-stu-id="b8153-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-221"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-222">No</span><span class="sxs-lookup"><span data-stu-id="b8153-222">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-223">Periodo di data e ora in cui la chiamata ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="b8153-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-224"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-225">No</span><span class="sxs-lookup"><span data-stu-id="b8153-225">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-226">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b8153-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="b8153-227">Metriche per l'attività di voce e video peer-to-peer da Mediation Server</span><span class="sxs-lookup"><span data-stu-id="b8153-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="b8153-228">Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b8153-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="b8153-229">Metriche per l'attività di voce e video peer-to-peer da Mediation Server</span><span class="sxs-lookup"><span data-stu-id="b8153-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8153-230">Nome</span><span class="sxs-lookup"><span data-stu-id="b8153-230">Name</span></span></th>
<th><span data-ttu-id="b8153-231">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="b8153-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b8153-232">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8153-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8153-233"><strong>Mediation Server</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-234">No</span><span class="sxs-lookup"><span data-stu-id="b8153-234">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-235">Nome del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b8153-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8153-236"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-237">No</span><span class="sxs-lookup"><span data-stu-id="b8153-237">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-238">Periodo di data e ora in cui la chiamata ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="b8153-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8153-239"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b8153-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b8153-240">No</span><span class="sxs-lookup"><span data-stu-id="b8153-240">No</span></span></p></td>
<td><p><span data-ttu-id="b8153-241">Numero totale di sessioni o conteggio totale dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b8153-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

