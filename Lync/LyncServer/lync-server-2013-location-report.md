---
title: 'Lync Server 2013: report posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb42f32313acd3609b21180ddaef90c53c27564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="9cd9b-102">Report posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cd9b-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cd9b-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9cd9b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9cd9b-104">Il report posizione fornisce informazioni sulle metriche di qualità delle chiamate raggruppate in base alla posizione di rete, ossia dalla subnet della rete.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-104">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="9cd9b-105">Se gli utenti riscontrano problemi con le chiamate, questo report consente di determinare se tali problemi sono diffusi o se sono in gran parte confinati in un determinato segmento di rete.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-105">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="9cd9b-106">Accesso al report posizione</span><span class="sxs-lookup"><span data-stu-id="9cd9b-106">Accessing the Location Report</span></span>

<span data-ttu-id="9cd9b-107">Il report posizione è accessibile dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-107">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="9cd9b-108">È possibile eseguire il drill-down nel report elenco chiamate facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-108">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="9cd9b-109">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="9cd9b-109">Call volume</span></span>

  - <span data-ttu-id="9cd9b-110">Percentuale di chiamata scadente</span><span class="sxs-lookup"><span data-stu-id="9cd9b-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9cd9b-111">Filtri</span><span class="sxs-lookup"><span data-stu-id="9cd9b-111">Filters</span></span>

<span data-ttu-id="9cd9b-112">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="9cd9b-113">Ad esempio, il report posizione consente di filtrare in base a elementi come la posizione in cui è stata originata una chiamata o se la chiamata ha avuto luogo in una connessione wireless o cablata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="9cd9b-114">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="9cd9b-115">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9cd9b-116">Nella tabella seguente sono elencati i filtri che è possibile usare con il report posizione.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="9cd9b-117">Filtri per i report posizione</span><span class="sxs-lookup"><span data-stu-id="9cd9b-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cd9b-118">Nome</span><span class="sxs-lookup"><span data-stu-id="9cd9b-118">Name</span></span></th>
<th><span data-ttu-id="9cd9b-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cd9b-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-120"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-121">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-121">Start date/time for the time range.</span></span> <span data-ttu-id="9cd9b-122">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9cd9b-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9cd9b-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9cd9b-124">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="9cd9b-125">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9cd9b-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9cd9b-126">7/7/2012</span></span></p>
<p><span data-ttu-id="9cd9b-127">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="9cd9b-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9cd9b-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9cd9b-128">7/3/2012</span></span></p>
<p><span data-ttu-id="9cd9b-129">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-130"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-131">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-131">End date/time for the time range.</span></span> <span data-ttu-id="9cd9b-132">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9cd9b-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="9cd9b-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9cd9b-134">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="9cd9b-135">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9cd9b-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9cd9b-136">7/7/2012</span></span></p>
<p><span data-ttu-id="9cd9b-137">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="9cd9b-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9cd9b-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9cd9b-138">7/3/2012</span></span></p>
<p><span data-ttu-id="9cd9b-139">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-140"><strong>Posizione del chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-141">Subnet IP dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="9cd9b-142">È possibile selezionare solo <strong>[tutti]</strong> per indicare tutte le subnet.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-143"><strong>Posizione del chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-144">Subnet IP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="9cd9b-145">È possibile selezionare solo <strong>[tutti]</strong> per indicare tutte le subnet.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-146"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-147">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-147">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="9cd9b-148">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-148">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9cd9b-149">Tutti</span><span class="sxs-lookup"><span data-stu-id="9cd9b-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="9cd9b-150">Cablata</span><span class="sxs-lookup"><span data-stu-id="9cd9b-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="9cd9b-151">Wireless</span><span class="sxs-lookup"><span data-stu-id="9cd9b-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-153">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-153">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="9cd9b-154">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cd9b-154">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9cd9b-155">Tutti</span><span class="sxs-lookup"><span data-stu-id="9cd9b-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="9cd9b-156">VPN</span><span class="sxs-lookup"><span data-stu-id="9cd9b-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="9cd9b-157">Non VPN</span><span class="sxs-lookup"><span data-stu-id="9cd9b-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9cd9b-158">Metriche</span><span class="sxs-lookup"><span data-stu-id="9cd9b-158">Metrics</span></span>

<span data-ttu-id="9cd9b-159">Nella tabella seguente sono elencate le informazioni fornite nel report posizione.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="9cd9b-160">Metriche del report posizione</span><span class="sxs-lookup"><span data-stu-id="9cd9b-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cd9b-161">Nome</span><span class="sxs-lookup"><span data-stu-id="9cd9b-161">Name</span></span></th>
<th><span data-ttu-id="9cd9b-162">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="9cd9b-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9cd9b-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cd9b-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-164"><strong>Subnet chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-165">No</span><span class="sxs-lookup"><span data-stu-id="9cd9b-165">No</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-166">Subnet IP dell'utente che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-167"><strong>Subnet chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-168">No</span><span class="sxs-lookup"><span data-stu-id="9cd9b-168">No</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-169">Subnet IP dell'utente che ha ricevuto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-170"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-171">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-172">Numero totale di chiamate inserite.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-173"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-174">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-175">Percentuale di chiamate classificate come chiamate scadenti.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="9cd9b-176">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-177"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-178">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-179">Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-179">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="9cd9b-180">I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-180">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9cd9b-181">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-181">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="9cd9b-182">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-182">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-183"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-184">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-185">Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="9cd9b-186">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="9cd9b-187">Un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="9cd9b-188">Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="9cd9b-189">In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="9cd9b-190">I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-190">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="9cd9b-191">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-191">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-192"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-193">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-194">Tasso medio di perdita di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-194">Average rate of RTP packet loss.</span></span> <span data-ttu-id="9cd9b-195">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-195">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="9cd9b-196">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-196">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-197"><strong>Jitter</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-198">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-199">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9cd9b-200">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-201"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-202">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-203">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-203">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="9cd9b-204">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-204">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cd9b-205"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-206">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-207">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-207">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="9cd9b-208">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-208">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cd9b-209"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="9cd9b-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9cd9b-210">Sì</span><span class="sxs-lookup"><span data-stu-id="9cd9b-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="9cd9b-211">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-211">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="9cd9b-212">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="9cd9b-212">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

