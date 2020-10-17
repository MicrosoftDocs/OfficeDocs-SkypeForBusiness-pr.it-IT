---
title: 'Lync Server 2013: rapporto di distribuzione delle metriche sulla qualità multimediale'
description: 'Lync Server 2013: rapporto di distribuzione delle metriche sulla qualità multimediale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548152"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="f5f10-103">Il rapporto distribuzione metriche di qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5f10-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f10-104">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f5f10-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f5f10-105">Il rapporto distribuzione metriche di qualità multimediale consente di visualizzare un grafico che mostra i valori di distribuzione per una metrica di qualità di esperienza, ad esempio instabilità o perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="f5f10-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="f5f10-106">Si supponga, ad esempio, che gli utenti effettuino un totale di 10 chiamate telefoniche; tali 10 chiamate segnalano i seguenti tempi di andata e ritorno:</span><span class="sxs-lookup"><span data-stu-id="f5f10-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f10-107">Numero di chiamata</span><span class="sxs-lookup"><span data-stu-id="f5f10-107">Call Number</span></span></th>
<th><span data-ttu-id="f5f10-108">Tempo di andata e ritorno (millisecondi)</span><span class="sxs-lookup"><span data-stu-id="f5f10-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-109">1 </span><span class="sxs-lookup"><span data-stu-id="f5f10-109">1</span></span></p></td>
<td><p><span data-ttu-id="f5f10-110">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-111">2</span><span class="sxs-lookup"><span data-stu-id="f5f10-111">2</span></span></p></td>
<td><p><span data-ttu-id="f5f10-112">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-113">3</span><span class="sxs-lookup"><span data-stu-id="f5f10-113">3</span></span></p></td>
<td><p><span data-ttu-id="f5f10-114">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-115">4 </span><span class="sxs-lookup"><span data-stu-id="f5f10-115">4</span></span></p></td>
<td><p><span data-ttu-id="f5f10-116">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-117">5 </span><span class="sxs-lookup"><span data-stu-id="f5f10-117">5</span></span></p></td>
<td><p><span data-ttu-id="f5f10-118">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-119">6 </span><span class="sxs-lookup"><span data-stu-id="f5f10-119">6</span></span></p></td>
<td><p><span data-ttu-id="f5f10-120">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-121">7 </span><span class="sxs-lookup"><span data-stu-id="f5f10-121">7</span></span></p></td>
<td><p><span data-ttu-id="f5f10-122">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-123">8 </span><span class="sxs-lookup"><span data-stu-id="f5f10-123">8</span></span></p></td>
<td><p><span data-ttu-id="f5f10-124">4550</span><span class="sxs-lookup"><span data-stu-id="f5f10-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-125">9 </span><span class="sxs-lookup"><span data-stu-id="f5f10-125">9</span></span></p></td>
<td><p><span data-ttu-id="f5f10-126">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-127">10  </span><span class="sxs-lookup"><span data-stu-id="f5f10-127">10</span></span></p></td>
<td><p><span data-ttu-id="f5f10-128">50</span><span class="sxs-lookup"><span data-stu-id="f5f10-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5f10-129">La media per i tempi di andata e ritorno è di 500 millisecondi (5000 diviso 10).</span><span class="sxs-lookup"><span data-stu-id="f5f10-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="f5f10-130">500 millisecondi è un tempo di andata e ritorno estremamente elevato; di conseguenza, è possibile che si verifichi un problema serio con la congestione della rete.</span><span class="sxs-lookup"><span data-stu-id="f5f10-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="f5f10-131">(I tempi di andata e ritorno lunghi sono in genere il risultato delle reti di overload).</span><span class="sxs-lookup"><span data-stu-id="f5f10-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="f5f10-132">In realtà, ovviamente, il 90% delle chiamate ha avuto tempi di andata e ritorno eccellenti; si è avuta solo una cattiva chiamata che ha alterato i risultati complessivi.</span><span class="sxs-lookup"><span data-stu-id="f5f10-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="f5f10-133">Se si esamina solo il tempo medio di andata e ritorno, è possibile passare a una conclusione molto sbagliata.</span><span class="sxs-lookup"><span data-stu-id="f5f10-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="f5f10-134">Il rapporto distribuzione metriche di qualità multimediale consente di evitare di saltare a conclusioni errate mostrando una distribuzione grafica di una metrica specificata, ad esempio il tempo di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="f5f10-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="f5f10-135">Questi grafici possono essere utili per chiarire che sono state riportate nove chiamate molto valide e una pessima chiamata.</span><span class="sxs-lookup"><span data-stu-id="f5f10-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="f5f10-136">È possibile che si desideri continuare a indagare su una chiamata. Tuttavia, il fatto che 9 chiamate su 10 siano state molto valide suggerisce che non vi è alcun motivo per apportare modifiche drastiche alla rete, almeno non a questo punto nel tempo.</span><span class="sxs-lookup"><span data-stu-id="f5f10-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="f5f10-137">Filtri</span><span class="sxs-lookup"><span data-stu-id="f5f10-137">Filters</span></span>

<span data-ttu-id="f5f10-138">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="f5f10-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="f5f10-139">Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto distribuzione metriche di qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="f5f10-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="f5f10-140">Filtri del rapporto distribuzione metriche di qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="f5f10-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f10-141">Nome</span><span class="sxs-lookup"><span data-stu-id="f5f10-141">Name</span></span></th>
<th><span data-ttu-id="f5f10-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5f10-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-p106">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f5f10-146">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="f5f10-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f5f10-p107">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f5f10-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f5f10-149">7/7/2012</span></span></p>
<p><span data-ttu-id="f5f10-150">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="f5f10-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f5f10-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f5f10-151">7/3/2012</span></span></p>
<p><span data-ttu-id="f5f10-152">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="f5f10-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-p108">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f5f10-156">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="f5f10-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f5f10-p109">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f5f10-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f5f10-159">7/7/2012</span></span></p>
<p><span data-ttu-id="f5f10-160">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="f5f10-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f5f10-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f5f10-161">7/3/2012</span></span></p>
<p><span data-ttu-id="f5f10-162">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="f5f10-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-163"><strong>Minimo nell'asse x</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-164">Valore più basso da visualizzare sull'asse X del grafico.</span><span class="sxs-lookup"><span data-stu-id="f5f10-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-165"><strong>Massimo nell'asse x</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-166">Valore massimo da visualizzare sull'asse X del grafico.</span><span class="sxs-lookup"><span data-stu-id="f5f10-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-167"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-p110">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f5f10-170">Tutti</span><span class="sxs-lookup"><span data-stu-id="f5f10-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="f5f10-171">Interno</span><span class="sxs-lookup"><span data-stu-id="f5f10-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="f5f10-172">Esterno</span><span class="sxs-lookup"><span data-stu-id="f5f10-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f10-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-p111">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f5f10-176">Tutti</span><span class="sxs-lookup"><span data-stu-id="f5f10-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="f5f10-177">VPN</span><span class="sxs-lookup"><span data-stu-id="f5f10-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="f5f10-178">Non VPN</span><span class="sxs-lookup"><span data-stu-id="f5f10-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f10-179"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="f5f10-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f10-p112">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5f10-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f5f10-182">Tutti</span><span class="sxs-lookup"><span data-stu-id="f5f10-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="f5f10-183">Cablata</span><span class="sxs-lookup"><span data-stu-id="f5f10-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="f5f10-184">Wireless</span><span class="sxs-lookup"><span data-stu-id="f5f10-184">Wireless</span></span></p></li>
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

