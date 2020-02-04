---
title: 'Lync Server 2013: report di confronto qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="8b612-102">Report di confronto qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b612-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b612-103">_**Argomento Ultima modifica:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="8b612-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="8b612-104">Il report di confronto qualità multimediale consente di confrontare i valori della qualità delle chiamate per i diversi tipi di chiamate audio, ad esempio le chiamate effettuate tramite una rete wireless o le chiamate effettuate tramite una connessione cablata.</span><span class="sxs-lookup"><span data-stu-id="8b612-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="8b612-105">Accesso al report di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="8b612-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="8b612-106">È possibile accedere al report di confronto qualità multimediale dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="8b612-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8b612-107">Filtri</span><span class="sxs-lookup"><span data-stu-id="8b612-107">Filters</span></span>

<span data-ttu-id="8b612-108">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="8b612-108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8b612-109">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di confronto qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="8b612-109">The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="8b612-110">Filtri di report di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="8b612-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b612-111">Nome</span><span class="sxs-lookup"><span data-stu-id="8b612-111">Name</span></span></th>
<th><span data-ttu-id="8b612-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b612-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b612-113"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-114">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8b612-114">Start date/time for the time range.</span></span> <span data-ttu-id="8b612-115">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8b612-115">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8b612-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b612-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b612-117">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="8b612-117">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8b612-118">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8b612-118">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b612-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b612-119">7/7/2012</span></span></p>
<p><span data-ttu-id="8b612-120">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8b612-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b612-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b612-121">7/3/2012</span></span></p>
<p><span data-ttu-id="8b612-122">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="8b612-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-123"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-124">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8b612-124">End date/time for the time range.</span></span> <span data-ttu-id="8b612-125">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8b612-125">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8b612-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b612-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b612-127">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="8b612-127">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8b612-128">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="8b612-128">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b612-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b612-129">7/7/2012</span></span></p>
<p><span data-ttu-id="8b612-130">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="8b612-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b612-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b612-131">7/3/2012</span></span></p>
<p><span data-ttu-id="8b612-132">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="8b612-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-133"><strong>Chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-134">Tipo di chiamata da usare come elemento di confronto principale.</span><span class="sxs-lookup"><span data-stu-id="8b612-134">Type of call to be used as the main comparison item.</span></span> <span data-ttu-id="8b612-135">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="8b612-135">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b612-136">Tutti</span><span class="sxs-lookup"><span data-stu-id="8b612-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b612-137">Esterno</span><span class="sxs-lookup"><span data-stu-id="8b612-137">External</span></span></p></li>
<li><p><span data-ttu-id="8b612-138">Interno</span><span class="sxs-lookup"><span data-stu-id="8b612-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="8b612-139">VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-140">Non VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-141">Cablata</span><span class="sxs-lookup"><span data-stu-id="8b612-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-142">Wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="8b612-143">Esterna e cablata</span><span class="sxs-lookup"><span data-stu-id="8b612-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-144">Esterno e wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="8b612-145">Esterna e VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-146">Esterno e non VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-147">Interni e cablati</span><span class="sxs-lookup"><span data-stu-id="8b612-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-148">Interni e wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-149"><strong>Confronto con le chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-150">Tipo di chiamata da usare come elemento di confronto secondario.</span><span class="sxs-lookup"><span data-stu-id="8b612-150">Type of call to be used as the secondary comparison item.</span></span> <span data-ttu-id="8b612-151">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="8b612-151">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b612-152">Tutti</span><span class="sxs-lookup"><span data-stu-id="8b612-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b612-153">Esterno</span><span class="sxs-lookup"><span data-stu-id="8b612-153">External</span></span></p></li>
<li><p><span data-ttu-id="8b612-154">Interno</span><span class="sxs-lookup"><span data-stu-id="8b612-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="8b612-155">VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-156">Non VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-157">Cablata</span><span class="sxs-lookup"><span data-stu-id="8b612-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-158">Wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="8b612-159">Esterna e cablata</span><span class="sxs-lookup"><span data-stu-id="8b612-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-160">Esterno e wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="8b612-161">Esterna e VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-162">Esterno e non VPN</span><span class="sxs-lookup"><span data-stu-id="8b612-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="8b612-163">Interni e cablati</span><span class="sxs-lookup"><span data-stu-id="8b612-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="8b612-164">Interni e wireless</span><span class="sxs-lookup"><span data-stu-id="8b612-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-165"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-166">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8b612-166">Time interval.</span></span> <span data-ttu-id="8b612-167">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b612-167">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b612-168">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="8b612-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8b612-169">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="8b612-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8b612-170">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="8b612-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8b612-171">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="8b612-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="8b612-172">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="8b612-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8b612-173">Metriche</span><span class="sxs-lookup"><span data-stu-id="8b612-173">Metrics</span></span>

<span data-ttu-id="8b612-174">Nella tabella seguente sono elencate le informazioni fornite nel report di confronto qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="8b612-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="8b612-175">Metriche del report di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="8b612-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b612-176">Nome</span><span class="sxs-lookup"><span data-stu-id="8b612-176">Name</span></span></th>
<th><span data-ttu-id="8b612-177">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="8b612-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b612-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b612-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b612-179"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-180">No</span><span class="sxs-lookup"><span data-stu-id="8b612-180">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-181">Numero totale di chiamate.</span><span class="sxs-lookup"><span data-stu-id="8b612-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-182"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-183">No</span><span class="sxs-lookup"><span data-stu-id="8b612-183">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-184">Importo medio della degradazione MOS (media Opinion Score) con esperienza durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b612-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="8b612-185">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="8b612-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="8b612-186">Storicamente, i punteggi degli opinion media sono stati calcolati avendo gli utenti valutano la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="8b612-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="8b612-187">Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b612-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="8b612-188">I valori di degradazione elevati possono essere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless oppure un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="8b612-188">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="8b612-189">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="8b612-189">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-190"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-191">No</span><span class="sxs-lookup"><span data-stu-id="8b612-191">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-192">Numero totale di chiamate classificate come scarse.</span><span class="sxs-lookup"><span data-stu-id="8b612-192">The total number of calls classified as poor.</span></span> <span data-ttu-id="8b612-193">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="8b612-193">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-194"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-195">No</span><span class="sxs-lookup"><span data-stu-id="8b612-195">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-196">Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="8b612-196">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="8b612-197">I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="8b612-197">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8b612-198">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="8b612-198">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="8b612-199">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="8b612-199">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-200"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-201">No</span><span class="sxs-lookup"><span data-stu-id="8b612-201">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-202">Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="8b612-202">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="8b612-203">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="8b612-203">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="8b612-204">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="8b612-204">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-205"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-206">No</span><span class="sxs-lookup"><span data-stu-id="8b612-206">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-207">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="8b612-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8b612-208">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="8b612-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-209"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-210">No</span><span class="sxs-lookup"><span data-stu-id="8b612-210">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-211">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="8b612-211">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="8b612-212">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="8b612-212">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b612-213"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-214">No</span><span class="sxs-lookup"><span data-stu-id="8b612-214">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-215">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="8b612-215">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="8b612-216">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="8b612-216">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b612-217"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="8b612-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b612-218">No</span><span class="sxs-lookup"><span data-stu-id="8b612-218">No</span></span></p></td>
<td><p><span data-ttu-id="8b612-219">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="8b612-219">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="8b612-220">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="8b612-220">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

