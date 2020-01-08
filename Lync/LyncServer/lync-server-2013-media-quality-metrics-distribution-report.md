---
title: 'Lync Server 2013: report di distribuzione delle metriche per la qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="15b55-102">Report di distribuzione delle metriche di qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b55-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b55-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="15b55-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="15b55-104">Il report di distribuzione delle metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica di qualità dell'esperienza, ad esempio jitter o perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="15b55-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="15b55-105">Supponiamo ad esempio che gli utenti facciano un totale di 10 telefonate; Queste 10 chiamate segnalano i tempi di andata e ritorno seguenti:</span><span class="sxs-lookup"><span data-stu-id="15b55-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15b55-106">Numero chiamata</span><span class="sxs-lookup"><span data-stu-id="15b55-106">Call Number</span></span></th>
<th><span data-ttu-id="15b55-107">Tempo di andata e ritorno (millisecondi)</span><span class="sxs-lookup"><span data-stu-id="15b55-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15b55-108">1</span><span class="sxs-lookup"><span data-stu-id="15b55-108">1</span></span></p></td>
<td><p><span data-ttu-id="15b55-109">50</span><span class="sxs-lookup"><span data-stu-id="15b55-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-110">2</span><span class="sxs-lookup"><span data-stu-id="15b55-110">2</span></span></p></td>
<td><p><span data-ttu-id="15b55-111">50</span><span class="sxs-lookup"><span data-stu-id="15b55-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-112">3</span><span class="sxs-lookup"><span data-stu-id="15b55-112">3</span></span></p></td>
<td><p><span data-ttu-id="15b55-113">50</span><span class="sxs-lookup"><span data-stu-id="15b55-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-114">4</span><span class="sxs-lookup"><span data-stu-id="15b55-114">4</span></span></p></td>
<td><p><span data-ttu-id="15b55-115">50</span><span class="sxs-lookup"><span data-stu-id="15b55-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-116">5</span><span class="sxs-lookup"><span data-stu-id="15b55-116">5</span></span></p></td>
<td><p><span data-ttu-id="15b55-117">50</span><span class="sxs-lookup"><span data-stu-id="15b55-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-118">6</span><span class="sxs-lookup"><span data-stu-id="15b55-118">6</span></span></p></td>
<td><p><span data-ttu-id="15b55-119">50</span><span class="sxs-lookup"><span data-stu-id="15b55-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-120">7</span><span class="sxs-lookup"><span data-stu-id="15b55-120">7</span></span></p></td>
<td><p><span data-ttu-id="15b55-121">50</span><span class="sxs-lookup"><span data-stu-id="15b55-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-122">8</span><span class="sxs-lookup"><span data-stu-id="15b55-122">8</span></span></p></td>
<td><p><span data-ttu-id="15b55-123">4550</span><span class="sxs-lookup"><span data-stu-id="15b55-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-124">9</span><span class="sxs-lookup"><span data-stu-id="15b55-124">9</span></span></p></td>
<td><p><span data-ttu-id="15b55-125">50</span><span class="sxs-lookup"><span data-stu-id="15b55-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-126">10</span><span class="sxs-lookup"><span data-stu-id="15b55-126">10</span></span></p></td>
<td><p><span data-ttu-id="15b55-127">50</span><span class="sxs-lookup"><span data-stu-id="15b55-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15b55-128">La media per gli orari di andata e ritorno è di 500 millisecondi (5000 diviso 10).</span><span class="sxs-lookup"><span data-stu-id="15b55-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="15b55-129">500 millisecondi è un tempo di andata e ritorno estremamente grande; di conseguenza, potresti credere di avere un problema serio con la congestione della rete.</span><span class="sxs-lookup"><span data-stu-id="15b55-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="15b55-130">I tempi di andata e ritorno lunghi sono in genere il risultato delle reti di overload.</span><span class="sxs-lookup"><span data-stu-id="15b55-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="15b55-131">In realtà, naturalmente, il 90% delle chiamate ha avuto ottimi tempi di andata e ritorno; è stata semplicemente assegnata una chiamata errata che ha alterato i risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="15b55-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="15b55-132">Se si osserva solo il tempo medio di andata e ritorno, è possibile passare a una conclusione molto sbagliata.</span><span class="sxs-lookup"><span data-stu-id="15b55-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="15b55-133">Il report di distribuzione delle metriche di qualità multimediale consente di evitare di saltare a conclusioni errate mostrando una distribuzione grafica di una metrica specificata, ad esempio il tempo di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="15b55-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="15b55-134">Questi grafici consentono di chiarire che sono state effettuate nove chiamate molto valide e una chiamata molto negativa.</span><span class="sxs-lookup"><span data-stu-id="15b55-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="15b55-135">Certo, potresti voler ancora approfondire l'analisi di una chiamata; Tuttavia, il fatto che 9 delle 10 chiamate siano state molto valide suggerisce che non ci sono motivi per apportare modifiche drastiche alla rete, almeno non in questo momento.</span><span class="sxs-lookup"><span data-stu-id="15b55-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="15b55-136">Filtri</span><span class="sxs-lookup"><span data-stu-id="15b55-136">Filters</span></span>

<span data-ttu-id="15b55-137">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="15b55-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="15b55-138">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di distribuzione delle metriche di qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="15b55-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="15b55-139">Filtri per i report di distribuzione delle metriche di qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="15b55-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15b55-140">Nome</span><span class="sxs-lookup"><span data-stu-id="15b55-140">Name</span></span></th>
<th><span data-ttu-id="15b55-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15b55-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15b55-142"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-143">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="15b55-143">Start date/time for the time range.</span></span> <span data-ttu-id="15b55-144">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="15b55-144">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="15b55-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="15b55-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="15b55-146">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="15b55-146">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="15b55-147">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="15b55-147">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15b55-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="15b55-148">7/7/2012</span></span></p>
<p><span data-ttu-id="15b55-149">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="15b55-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15b55-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="15b55-150">7/3/2012</span></span></p>
<p><span data-ttu-id="15b55-151">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="15b55-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-152"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-153">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="15b55-153">End date/time for the time range.</span></span> <span data-ttu-id="15b55-154">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="15b55-154">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="15b55-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="15b55-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="15b55-156">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="15b55-156">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="15b55-157">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="15b55-157">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15b55-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="15b55-158">7/7/2012</span></span></p>
<p><span data-ttu-id="15b55-159">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="15b55-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15b55-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="15b55-160">7/3/2012</span></span></p>
<p><span data-ttu-id="15b55-161">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="15b55-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-162"><strong>Minimo nell'asse x</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-163">Valore più basso da visualizzare sull'asse X del grafico.</span><span class="sxs-lookup"><span data-stu-id="15b55-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-164"><strong>Massimo nell'asse x</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-165">Valore massimo da visualizzare nell'asse X del grafico.</span><span class="sxs-lookup"><span data-stu-id="15b55-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-166"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-167">Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="15b55-167">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="15b55-168">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15b55-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="15b55-169">Tutti</span><span class="sxs-lookup"><span data-stu-id="15b55-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="15b55-170">Interno</span><span class="sxs-lookup"><span data-stu-id="15b55-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="15b55-171">Esterno</span><span class="sxs-lookup"><span data-stu-id="15b55-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15b55-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-173">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="15b55-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="15b55-174">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15b55-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="15b55-175">Tutti</span><span class="sxs-lookup"><span data-stu-id="15b55-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="15b55-176">VPN</span><span class="sxs-lookup"><span data-stu-id="15b55-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="15b55-177">Non VPN</span><span class="sxs-lookup"><span data-stu-id="15b55-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15b55-178"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="15b55-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="15b55-179">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="15b55-179">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="15b55-180">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15b55-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="15b55-181">Tutti</span><span class="sxs-lookup"><span data-stu-id="15b55-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="15b55-182">Cablata</span><span class="sxs-lookup"><span data-stu-id="15b55-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="15b55-183">Wireless</span><span class="sxs-lookup"><span data-stu-id="15b55-183">Wireless</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

