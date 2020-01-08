---
title: 'Lync Server 2013: report di riepilogo qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c967c6d6b120c73cb933281d4edb17be1868900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="bb4c7-102">Report di riepilogo qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb4c7-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb4c7-103">_**Argomento Ultima modifica:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="bb4c7-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="bb4c7-104">Il report Riepilogo qualità multimediale è forse la soluzione migliore per analizzare la qualità delle chiamate nell'organizzazione: questo report fornisce le metriche delle chiamate QoE (Quality of Experience) dettagliate suddivise nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="bb4c7-105">Chiamate peer-to-peer UC (ad esempio una chiamata di Microsoft Lync 2013 a Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="bb4c7-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="bb4c7-106">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="bb4c7-107">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="bb4c7-108">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="bb4c7-109">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="bb4c7-110">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="bb4c7-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="bb4c7-111">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-111">Other Call Types</span></span>

<span data-ttu-id="bb4c7-112">Quando si apre il report per la prima volta, vengono visualizzate informazioni di riepilogo per ognuna di queste categorie.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="bb4c7-113">Senza uscire dal report, è possibile espandere ogni categoria per esaminare le sottocategorie, ad esempio le chiamate effettuate da Office Communicator 2007 R2 a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="bb4c7-114">A sua volta, è possibile eseguire il drill-down in queste sottocategorie per visualizzare i dettagli su ogni chiamata effettuata all'interno di tale sottocategoria.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="bb4c7-115">In Microsoft Lync Server 2013 il report Riepilogo qualità multimediale suddivide ulteriormente i dati in tre tipi di chiamata: chiamate audio, videochiamate e chiamate di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="bb4c7-116">Ogni tipo di chiamata ha una propria sezione nel report e un set personalizzato di metriche delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="bb4c7-117">Il report Riepilogo qualità multimediale consente inoltre di applicare filtri che consentono di confrontare la qualità delle chiamate cablate e le chiamate wireless, le chiamate interne e le chiamate esterne e le chiamate VPN e le chiamate non VPN.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="bb4c7-118">Accesso al report di riepilogo qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="bb4c7-119">Il report Riepilogo qualità multimediale è accessibile dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="bb4c7-120">È possibile eseguire il drill-down nel [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="bb4c7-121">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-121">Call volume</span></span>

  - <span data-ttu-id="bb4c7-122">Percentuale di chiamata scadente</span><span class="sxs-lookup"><span data-stu-id="bb4c7-122">Poor call percentage</span></span>

<span data-ttu-id="bb4c7-123">Inoltre, è possibile accedere al report di distribuzione delle metriche di qualità multimediale facendo clic su una delle metriche delle chiamate audio seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="bb4c7-124">Andata e ritorno (MS)</span><span class="sxs-lookup"><span data-stu-id="bb4c7-124">Round trip (ms)</span></span>

  - <span data-ttu-id="bb4c7-125">Degradazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="bb4c7-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="bb4c7-126">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="bb4c7-126">Packet loss</span></span>

  - <span data-ttu-id="bb4c7-127">Jitter (MS)</span><span class="sxs-lookup"><span data-stu-id="bb4c7-127">Jitter (ms)</span></span>

  - <span data-ttu-id="bb4c7-128">Rapporto nascosto del guaritore</span><span class="sxs-lookup"><span data-stu-id="bb4c7-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="bb4c7-129">Rapporto allungato guaritore</span><span class="sxs-lookup"><span data-stu-id="bb4c7-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="bb4c7-130">Rapporto compresso del guaritore</span><span class="sxs-lookup"><span data-stu-id="bb4c7-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bb4c7-131">Filtri</span><span class="sxs-lookup"><span data-stu-id="bb4c7-131">Filters</span></span>

<span data-ttu-id="bb4c7-132">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="bb4c7-133">Ad esempio, il report Riepilogo qualità multimediale consente di filtrare i dati restituiti in base a elementi come il tipo di accesso (ovvero l'accesso a intervalli o l'accesso esterno) o la connessione di rete cablata/wireless.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-133">For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="bb4c7-134">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="bb4c7-135">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-135">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="bb4c7-136">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="bb4c7-137">Filtri report Riepilogo qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4c7-138">Nome</span><span class="sxs-lookup"><span data-stu-id="bb4c7-138">Name</span></span></th>
<th><span data-ttu-id="bb4c7-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb4c7-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-140"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-141">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-141">Start date/time for the time range.</span></span> <span data-ttu-id="bb4c7-142">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-142">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="bb4c7-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bb4c7-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bb4c7-144">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-144">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="bb4c7-145">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bb4c7-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bb4c7-146">7/7/2012</span></span></p>
<p><span data-ttu-id="bb4c7-147">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="bb4c7-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bb4c7-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bb4c7-148">7/3/2012</span></span></p>
<p><span data-ttu-id="bb4c7-149">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-150"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-151">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-151">End date/time for the time range.</span></span> <span data-ttu-id="bb4c7-152">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-152">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="bb4c7-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bb4c7-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bb4c7-154">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-154">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="bb4c7-155">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-155">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bb4c7-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bb4c7-156">7/7/2012</span></span></p>
<p><span data-ttu-id="bb4c7-157">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="bb4c7-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bb4c7-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bb4c7-158">7/3/2012</span></span></p>
<p><span data-ttu-id="bb4c7-159">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-160"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-161">Indica se il client ha effettuato l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-161">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="bb4c7-162">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-162">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-163">Tutti</span><span class="sxs-lookup"><span data-stu-id="bb4c7-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-164">Interno</span><span class="sxs-lookup"><span data-stu-id="bb4c7-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-165">Esterno</span><span class="sxs-lookup"><span data-stu-id="bb4c7-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-166"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-167">Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-167">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="bb4c7-168">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-169">Tutti</span><span class="sxs-lookup"><span data-stu-id="bb4c7-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-170">Cablata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-171">Wireless</span><span class="sxs-lookup"><span data-stu-id="bb4c7-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-173">Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="bb4c7-174">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-175">Tutti</span><span class="sxs-lookup"><span data-stu-id="bb4c7-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-176">VPN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-177">Non VPN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="bb4c7-178">Metriche</span><span class="sxs-lookup"><span data-stu-id="bb4c7-178">Metrics</span></span>

<span data-ttu-id="bb4c7-179">Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="bb4c7-180">Metriche rapporto di riepilogo qualità multimediale: riepilogo delle chiamate audio</span><span class="sxs-lookup"><span data-stu-id="bb4c7-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4c7-181">Nome</span><span class="sxs-lookup"><span data-stu-id="bb4c7-181">Name</span></span></th>
<th><span data-ttu-id="bb4c7-182">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="bb4c7-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bb4c7-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb4c7-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-184"><strong>Tipo di chiamata/tipo di endpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-185">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-185">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-186">Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-186">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="bb4c7-187">I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-187">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-188">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-189">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-190">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-191">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-192">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-193">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="bb4c7-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-194">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-195"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-196">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-196">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-197">Numero totale di chiamate per tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-198"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-199">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-199">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-200">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-200">Total number of calls classified as poor.</span></span> <span data-ttu-id="bb4c7-201">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-201">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-202"><strong>Volume chiamata (chiamata wireless)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-203">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-203">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-204">Numero totale di chiamate che hanno usato una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-205"><strong>Volume chiamata (chiamata VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-206">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-206">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-207">Numero totale di chiamate che hanno usato una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-208"><strong>Volume chiamata (chiamata esterna)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-209">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-209">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-210">Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</span><span class="sxs-lookup"><span data-stu-id="bb4c7-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-211"><strong>Andata e ritorno (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-212">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-212">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-213">Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-213">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="bb4c7-214">I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-214">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="bb4c7-215">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-215">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="bb4c7-216">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-216">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-217"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-218">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-218">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-219">Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="bb4c7-220">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="bb4c7-221">Un valore di 0,5 o meno rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="bb4c7-222">Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="bb4c7-223">In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="bb4c7-224">I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-224">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="bb4c7-225">L'elevata degradazione genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-225">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-226"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-227">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-227">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-228">Tasso medio di perdita di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-228">Average rate of RTP packet loss.</span></span> <span data-ttu-id="bb4c7-229">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-229">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="bb4c7-230">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-230">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-231"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-232">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-232">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-233">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="bb4c7-234">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-235"><strong>Rapporto nascosto del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-236">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-236">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-237">Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-237">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="bb4c7-238">(Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-238">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-239"><strong>Rapporto allungato guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-240">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-240">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-241">Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-241">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="bb4c7-242">(L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-242">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-243"><strong>Rapporto compresso del guaritore</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-244">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-244">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-245">Rapporto medio tra campioni audio compressi e il numero totale di esempi.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-245">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="bb4c7-246">(L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-246">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="bb4c7-247">Metriche rapporto di riepilogo qualità multimediale: riepilogo videochiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4c7-248">Nome</span><span class="sxs-lookup"><span data-stu-id="bb4c7-248">Name</span></span></th>
<th><span data-ttu-id="bb4c7-249">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="bb4c7-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bb4c7-250">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb4c7-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-251"><strong>Tipo di chiamata/tipo di endpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-252">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-252">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-253">Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-253">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="bb4c7-254">I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-254">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-255">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-256">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-257">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-258">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-259">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-260">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="bb4c7-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-261">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-262"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-263">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-263">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-264">Numero totale di chiamate per tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-265"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-266">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-266">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-267">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-267">Total number of calls classified as poor.</span></span> <span data-ttu-id="bb4c7-268">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-268">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-269"><strong>Volume chiamata (chiamata wireless)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-270">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-270">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-271">Numero totale di chiamate che hanno usato una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-272"><strong>Volume chiamata (chiamata VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-273">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-273">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-274">Numero totale di chiamate che hanno usato una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-275"><strong>Volume chiamata (chiamata esterna)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-276">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-276">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-277">Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</span><span class="sxs-lookup"><span data-stu-id="bb4c7-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-278"><strong>Velocità di bit AVG (kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-279">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-279">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-280">Velocità in bit video media (in kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="bb4c7-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-281"><strong>Percentuale di bit bassa</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-282">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-282">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-283">Percentuale della chiamata in cui il bit rate è basso.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-284"><strong>Perdita di pacchetti in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-285">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-285">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-286">Perdita di pacchetti RTP (Real-Time Transport Protocol) per pacchetti in uscita.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-286">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="bb4c7-287">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-287">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="bb4c7-288">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-288">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-289"><strong>Fotogramma congelato%</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-290">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-290">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-291">Percentuale di fotogrammi "bloccati".</span><span class="sxs-lookup"><span data-stu-id="bb4c7-291">Percentage of “frozen” frames.</span></span> <span data-ttu-id="bb4c7-292">In un fotogramma bloccato il video smette di avanzare mentre la parte audio della chiamata continua.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-292">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-293"><strong>Frequenza fotogrammi in uscita AVG</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-294">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-294">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-295">Frequenza fotogrammi media per le trasmissioni in uscita durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-296"><strong>Frequenza fotogrammi in ingresso AVG</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-297">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-297">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-298">Frequenza fotogrammi media per le trasmissioni in arrivo durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-299"><strong>Frequenza fotogrammi ridotta in ingresso%</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-300">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-300">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-301">Percentuale della chiamata in cui la velocità in bit per il video in arrivo è bassa.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-302"><strong>Integrità client%</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bb4c7-303">Indica l'integrità relativa del dispositivo client durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="bb4c7-304">Metriche rapporto di riepilogo qualità multimediale: riepilogo delle chiamate di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="bb4c7-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4c7-305">Nome</span><span class="sxs-lookup"><span data-stu-id="bb4c7-305">Name</span></span></th>
<th><span data-ttu-id="bb4c7-306">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="bb4c7-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bb4c7-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb4c7-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-308"><strong>Tipo di chiamata/tipo di endpoint</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-309">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-309">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-310">Quando si fa clic su questo elemento, nel report vengono visualizzate informazioni dettagliate sulle chiamate basate su tale tipo.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-310">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="bb4c7-311">I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="bb4c7-311">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb4c7-312">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-313">Sessioni di conferenza UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-314">Sessioni di conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="bb4c7-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-315">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="bb4c7-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-316">Chiamate PSTN (non bypass): Leg UC</span><span class="sxs-lookup"><span data-stu-id="bb4c7-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-317">Chiamate PSTN (non bypass): Leg gateway</span><span class="sxs-lookup"><span data-stu-id="bb4c7-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="bb4c7-318">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="bb4c7-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-319"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-320">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-320">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-321">Numero totale di chiamate per tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-322"><strong>Percentuale di chiamata scadente</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-323">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-323">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-324">Numero totale di chiamate classificate come scadenti.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-324">Total number of calls classified as poor.</span></span> <span data-ttu-id="bb4c7-325">Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-325">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-326"><strong>Volume chiamata (chiamata wireless)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-327">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-327">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-328">Numero totale di chiamate che hanno usato una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-329"><strong>Volume chiamata (chiamata VPN)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-330">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-330">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-331">Numero totale di chiamate che hanno usato una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-332"><strong>Volume chiamata (chiamata esterna)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-333">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-333">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-334">Numero di chiamate che hanno usato una connessione esterna (ovvero una connessione esterna alla rete interna).</span><span class="sxs-lookup"><span data-stu-id="bb4c7-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-335"><strong>Jitter (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-336">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-336">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-337">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="bb4c7-338">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-339"><strong>AVG. un modo relativo</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-340">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-340">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-341">Ritardo unidirezionale relativo medio tra due endpoint multimediali.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-341">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="bb4c7-342">Si tratta di una misura di latenza single-hop.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-342">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb4c7-343"><strong>Latenza di elaborazione del riquadro media RDP</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-344">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-344">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-345">La latenza media di elaborazione dei riquadri RDP nel server dei servizi di conferenza durante la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="bb4c7-346">Una media elevata riflette un ritardo maggiore nell'esperienza di visualizzazione e include la latenza della rete.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="bb4c7-347">Un server di conferenza di overload può avere ritardi medi più alti.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb4c7-348"><strong>Totale riquadro viziato%</strong></span><span class="sxs-lookup"><span data-stu-id="bb4c7-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="bb4c7-349">No</span><span class="sxs-lookup"><span data-stu-id="bb4c7-349">No</span></span></p></td>
<td><p><span data-ttu-id="bb4c7-350">Percentuale totale di riquadri RDP viziati.</span><span class="sxs-lookup"><span data-stu-id="bb4c7-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

