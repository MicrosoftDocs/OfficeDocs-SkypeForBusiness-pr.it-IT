---
title: 'Lync Server 2013: rapporto riepilogativo sulla qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="03881-102">Report riepilogativo sulla qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03881-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03881-103">_**Ultimo argomento modificato:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="03881-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="03881-104">Il Rapporto riepilogativo qualità multimediale è probabilmente la risorsa migliore per analizzare la qualità delle chiamate nell'organizzazione: questo rapporto offre metriche QoE (Quality of Experience) dettagliate sulle chiamate, suddivise nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="03881-105">Chiamate peer-to-peer UC (ad esempio una chiamata Microsoft Lync 2013 a Microsoft Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="03881-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="03881-106">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="03881-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="03881-107">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="03881-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="03881-108">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="03881-109">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="03881-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="03881-110">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="03881-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="03881-111">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="03881-111">Other Call Types</span></span>

<span data-ttu-id="03881-112">Quando si apre per la prima volta il rapporto, vengono visualizzate informazioni di riepilogo per ognuna delle categorie.</span><span class="sxs-lookup"><span data-stu-id="03881-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="03881-113">Senza lasciare il report, è possibile espandere ogni categoria per esaminare le sottocategorie, ad esempio le chiamate effettuate da Office Communicator 2007 R2 a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03881-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="03881-114">È quindi possibile eseguire il drill-down in queste sottocategorie per visualizzare dettagli su ogni chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="03881-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="03881-115">In Microsoft Lync Server 2013 il rapporto riepilogativo sulla qualità multimediale suddivide ulteriormente i dati in tre tipi di chiamata: chiamate audio, chiamate video e chiamate di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="03881-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="03881-116">A ogni tipo di chiamata è associata una sezione del rapporto e un set personalizzato di metriche.</span><span class="sxs-lookup"><span data-stu-id="03881-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="03881-117">Il Rapporto riepilogativo qualità multimediale consente inoltre di applicare filtri in base ai quali confrontare la qualità delle chiamate cablate con quella delle chiamate wireless, di quelle interne con quelle esterne e delle chiamate VPN rispetto a quelle non VPN.</span><span class="sxs-lookup"><span data-stu-id="03881-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="03881-118">Accesso al Rapporto riepilogativo qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="03881-119">Il Rapporto riepilogativo qualità multimediale è accessibile dalla home page Rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="03881-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="03881-120">È possibile eseguire il drill-down [nel rapporto elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="03881-121">Volume chiamata</span><span class="sxs-lookup"><span data-stu-id="03881-121">Call volume</span></span>

  - <span data-ttu-id="03881-122">Percentuale chiamate di livello insufficiente</span><span class="sxs-lookup"><span data-stu-id="03881-122">Poor call percentage</span></span>

<span data-ttu-id="03881-123">È inoltre possibile accedere al Rapporto distribuzione metriche di qualità multimediale facendo clic sulle metriche di chiamata audio seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="03881-124">Roundtrip (ms)</span><span class="sxs-lookup"><span data-stu-id="03881-124">Round trip (ms)</span></span>

  - <span data-ttu-id="03881-125">Degradazione (MOS)</span><span class="sxs-lookup"><span data-stu-id="03881-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="03881-126">Perdita di pacchetti</span><span class="sxs-lookup"><span data-stu-id="03881-126">Packet loss</span></span>

  - <span data-ttu-id="03881-127">Instabilità (ms)</span><span class="sxs-lookup"><span data-stu-id="03881-127">Jitter (ms)</span></span>

  - <span data-ttu-id="03881-128">Rapporto campioni nascosti utilità di ripristino</span><span class="sxs-lookup"><span data-stu-id="03881-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="03881-129">Rapporto campioni estesi utilità di ripristino</span><span class="sxs-lookup"><span data-stu-id="03881-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="03881-130">Rapporto campioni compressi utilità di ripristino</span><span class="sxs-lookup"><span data-stu-id="03881-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="03881-131">Filtri</span><span class="sxs-lookup"><span data-stu-id="03881-131">Filters</span></span>

<span data-ttu-id="03881-p104">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Il rapporto riepilogativo sulla qualità multimediale, ad esempio, consente di filtrare i dati restituiti in base a fattori come il tipo di accesso (interno o esterno) o il tipo di connessione di rete (cablata o wireless). È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="03881-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="03881-136">Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo sulla qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="03881-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="03881-137">Filtri per il rapporto riepilogativo sulla qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03881-138">Nome</span><span class="sxs-lookup"><span data-stu-id="03881-138">Name</span></span></th>
<th><span data-ttu-id="03881-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03881-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03881-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="03881-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-p105">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="03881-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="03881-143">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="03881-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03881-p106">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="03881-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03881-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03881-146">7/7/2012</span></span></p>
<p><span data-ttu-id="03881-147">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="03881-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03881-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03881-148">7/3/2012</span></span></p>
<p><span data-ttu-id="03881-149">Le settimane vengono calcolate sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="03881-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="03881-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-p107">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="03881-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="03881-153">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="03881-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="03881-p108">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="03881-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="03881-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="03881-156">7/7/2012</span></span></p>
<p><span data-ttu-id="03881-157">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="03881-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="03881-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="03881-158">7/3/2012</span></span></p>
<p><span data-ttu-id="03881-159">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="03881-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-160"><strong>Tipo di accesso</strong></span><span class="sxs-lookup"><span data-stu-id="03881-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-p109">Indica se al momento dell'esecuzione della chiamata il client era connesso alla rete interna o alla rete esterna. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-163">Tutti</span><span class="sxs-lookup"><span data-stu-id="03881-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="03881-164">Interna</span><span class="sxs-lookup"><span data-stu-id="03881-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="03881-165">Esterna</span><span class="sxs-lookup"><span data-stu-id="03881-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-166"><strong>Tipo di rete</strong></span><span class="sxs-lookup"><span data-stu-id="03881-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-p110">Indica il tipo di rete alla quale era connesso il client quando è stata effettuata la chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-169">Tutti</span><span class="sxs-lookup"><span data-stu-id="03881-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="03881-170">Cablata</span><span class="sxs-lookup"><span data-stu-id="03881-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="03881-171">Wireless</span><span class="sxs-lookup"><span data-stu-id="03881-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="03881-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-p111">Indica se un client esterno stava utilizzando una connessione VPN (Virtual Private Network) al momento della chiamata. Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="03881-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-175">Tutti</span><span class="sxs-lookup"><span data-stu-id="03881-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="03881-176">VPN</span><span class="sxs-lookup"><span data-stu-id="03881-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="03881-177">Non VPN</span><span class="sxs-lookup"><span data-stu-id="03881-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="03881-178">Metriche</span><span class="sxs-lookup"><span data-stu-id="03881-178">Metrics</span></span>

<span data-ttu-id="03881-179">Nella tabella seguente sono elencate le informazioni disponibili nel rapporto riepilogativo sulla qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="03881-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="03881-180">Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate audio</span><span class="sxs-lookup"><span data-stu-id="03881-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03881-181">Nome</span><span class="sxs-lookup"><span data-stu-id="03881-181">Name</span></span></th>
<th><span data-ttu-id="03881-182">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="03881-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03881-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03881-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03881-184"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="03881-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-185">No</span><span class="sxs-lookup"><span data-stu-id="03881-185">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p112">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="03881-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-188">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="03881-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="03881-189">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="03881-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-190">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="03881-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-191">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="03881-192">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="03881-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-193">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="03881-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-194">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="03881-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-195"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="03881-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-196">No</span><span class="sxs-lookup"><span data-stu-id="03881-196">No</span></span></p></td>
<td><p><span data-ttu-id="03881-197">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="03881-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-198"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="03881-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-199">No</span><span class="sxs-lookup"><span data-stu-id="03881-199">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p113">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="03881-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-202"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-203">No</span><span class="sxs-lookup"><span data-stu-id="03881-203">No</span></span></p></td>
<td><p><span data-ttu-id="03881-204">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="03881-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-205"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-206">No</span><span class="sxs-lookup"><span data-stu-id="03881-206">No</span></span></p></td>
<td><p><span data-ttu-id="03881-207">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="03881-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-208"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-209">No</span><span class="sxs-lookup"><span data-stu-id="03881-209">No</span></span></p></td>
<td><p><span data-ttu-id="03881-210">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="03881-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-211"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-212">No</span><span class="sxs-lookup"><span data-stu-id="03881-212">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p114">Tempo medio di roundtrip, in millisecondi, necessario per un pacchetto RTP (Real-Time Transport Protocol) per viaggiare fino a un altro endpoint e tornare indietro. Un roundtrip di 100 millisecondi o meno è considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="03881-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="03881-p115">Valori di roundtrip elevati possono essere causati dal routing di chiamate internazionali, da una configurazione errata del routing o da un server di contenuti multimediali sovraccarico. Tempi di roundtrip elevati generano difficoltà nelle conversazioni audio in tempo reale bidirezionali.</span><span class="sxs-lookup"><span data-stu-id="03881-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-217"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-218">No</span><span class="sxs-lookup"><span data-stu-id="03881-218">No</span></span></p></td>
<td><p><span data-ttu-id="03881-219">Degradazione MOS (Mean Opinion Score) media sperimentata durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="03881-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="03881-220">I valori di degradazione possono essere compresi tra un minimo di 0 e un massimo di 5.</span><span class="sxs-lookup"><span data-stu-id="03881-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="03881-221">Il valore 0,5 o inferiore rappresenta una degradazione accettabile.</span><span class="sxs-lookup"><span data-stu-id="03881-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="03881-222">In passato, i valori MOS venivano calcolati chiedendo agli utenti di valutare la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="03881-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="03881-223">In Lync Server, Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="03881-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="03881-p117">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="03881-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-226"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="03881-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-227">No</span><span class="sxs-lookup"><span data-stu-id="03881-227">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p118">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video in Internet, non raggiungono la destinazione. Valori di perdita alti sono in genere dovuti a congestione, disponibilità di una larghezza di banda troppo ridotta, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="03881-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-231"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-232">No</span><span class="sxs-lookup"><span data-stu-id="03881-232">No</span></span></p></td>
<td><p><span data-ttu-id="03881-233">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="03881-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="03881-234">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="03881-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-235"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="03881-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-236">No</span><span class="sxs-lookup"><span data-stu-id="03881-236">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p120">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="03881-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-239"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="03881-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-240">No</span><span class="sxs-lookup"><span data-stu-id="03881-240">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p121">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="03881-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-243"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="03881-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-244">No</span><span class="sxs-lookup"><span data-stu-id="03881-244">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p122">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. I campioni audio vengono compressi per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="03881-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="03881-247">Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle videochiamate</span><span class="sxs-lookup"><span data-stu-id="03881-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03881-248">Nome</span><span class="sxs-lookup"><span data-stu-id="03881-248">Name</span></span></th>
<th><span data-ttu-id="03881-249">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="03881-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03881-250">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03881-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03881-251"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="03881-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-252">No</span><span class="sxs-lookup"><span data-stu-id="03881-252">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p123">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="03881-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-255">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="03881-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="03881-256">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="03881-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-257">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="03881-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-258">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="03881-259">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="03881-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-260">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="03881-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-261">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="03881-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-262"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="03881-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-263">No</span><span class="sxs-lookup"><span data-stu-id="03881-263">No</span></span></p></td>
<td><p><span data-ttu-id="03881-264">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="03881-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-265"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="03881-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-266">No</span><span class="sxs-lookup"><span data-stu-id="03881-266">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p124">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="03881-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-269"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-270">No</span><span class="sxs-lookup"><span data-stu-id="03881-270">No</span></span></p></td>
<td><p><span data-ttu-id="03881-271">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="03881-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-272"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-273">No</span><span class="sxs-lookup"><span data-stu-id="03881-273">No</span></span></p></td>
<td><p><span data-ttu-id="03881-274">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="03881-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-275"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-276">No</span><span class="sxs-lookup"><span data-stu-id="03881-276">No</span></span></p></td>
<td><p><span data-ttu-id="03881-277">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="03881-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-278"><strong>Velocità media in bit (Kbit/s)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-279">No</span><span class="sxs-lookup"><span data-stu-id="03881-279">No</span></span></p></td>
<td><p><span data-ttu-id="03881-280">Velocità in bit video media (in kilobit al secondo).</span><span class="sxs-lookup"><span data-stu-id="03881-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-281"><strong>Bassa velocità in bit (%)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-282">No</span><span class="sxs-lookup"><span data-stu-id="03881-282">No</span></span></p></td>
<td><p><span data-ttu-id="03881-283">Percentuale della chiamata con velocità in bit bassa.</span><span class="sxs-lookup"><span data-stu-id="03881-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-284"><strong>Perdita di pacchetti in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="03881-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-285">No</span><span class="sxs-lookup"><span data-stu-id="03881-285">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p125">Perdita di pacchetti RTP (Real-Time Transport Protocol) in uscita. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="03881-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-289"><strong>% fotogrammi bloccati</strong></span><span class="sxs-lookup"><span data-stu-id="03881-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-290">No</span><span class="sxs-lookup"><span data-stu-id="03881-290">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p126">Percentuale di fotogrammi “bloccati”. In un fotogramma bloccato, il video smette di avanzare mentre la parte audio della chiamata prosegue.</span><span class="sxs-lookup"><span data-stu-id="03881-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-293"><strong>Frequenza media dei fotogrammi in uscita</strong></span><span class="sxs-lookup"><span data-stu-id="03881-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-294">No</span><span class="sxs-lookup"><span data-stu-id="03881-294">No</span></span></p></td>
<td><p><span data-ttu-id="03881-295">Frequenza media dei fotogrammi per le trasmissioni in uscita durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="03881-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-296"><strong>Frequenza media dei fotogrammi in ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="03881-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-297">No</span><span class="sxs-lookup"><span data-stu-id="03881-297">No</span></span></p></td>
<td><p><span data-ttu-id="03881-298">Frequenza media dei fotogrammi per le trasmissioni in arrivo durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="03881-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-299"><strong>Bassa frequenza dei fotogrammi in ingresso (%)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-300">No</span><span class="sxs-lookup"><span data-stu-id="03881-300">No</span></span></p></td>
<td><p><span data-ttu-id="03881-301">Percentuale della chiamata con velocità in bit bassa per il video in arrivo.</span><span class="sxs-lookup"><span data-stu-id="03881-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-302"><strong>Integrità client (%)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="03881-303">Indica l'integrità relativa del dispositivo client durante la chiamata.</span><span class="sxs-lookup"><span data-stu-id="03881-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="03881-304">Metriche del Rapporto riepilogativo qualità multimediale: riepilogo delle chiamate di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="03881-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03881-305">Nome</span><span class="sxs-lookup"><span data-stu-id="03881-305">Name</span></span></th>
<th><span data-ttu-id="03881-306">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="03881-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="03881-307">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03881-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03881-308"><strong>Tipo di chiamata/Tipo di endpoint </strong></span><span class="sxs-lookup"><span data-stu-id="03881-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-309">No</span><span class="sxs-lookup"><span data-stu-id="03881-309">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p127">Facendo clic su questo elemento è possibile visualizzare informazioni dettagliate sulle chiamate in base al tipo. I tipi di chiamata includono:</span><span class="sxs-lookup"><span data-stu-id="03881-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="03881-312">Chiamate peer-to-peer UC</span><span class="sxs-lookup"><span data-stu-id="03881-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="03881-313">Sessioni conferenza UC</span><span class="sxs-lookup"><span data-stu-id="03881-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-314">Sessioni conferenza PSTN</span><span class="sxs-lookup"><span data-stu-id="03881-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="03881-315">Chiamate PSTN: bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="03881-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="03881-316">Chiamate PSTN (senza bypass): coda UC</span><span class="sxs-lookup"><span data-stu-id="03881-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-317">Chiamate PSTN (senza bypass): coda gateway</span><span class="sxs-lookup"><span data-stu-id="03881-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="03881-318">Altri tipi di chiamata</span><span class="sxs-lookup"><span data-stu-id="03881-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-319"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="03881-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-320">No</span><span class="sxs-lookup"><span data-stu-id="03881-320">No</span></span></p></td>
<td><p><span data-ttu-id="03881-321">Numero totale di chiamate per ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="03881-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-322"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="03881-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-323">No</span><span class="sxs-lookup"><span data-stu-id="03881-323">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p128">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="03881-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-326"><strong>Volume chiamata (chiamata wireless) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-327">No</span><span class="sxs-lookup"><span data-stu-id="03881-327">No</span></span></p></td>
<td><p><span data-ttu-id="03881-328">Numero totale di chiamate eseguite tramite una connessione wireless.</span><span class="sxs-lookup"><span data-stu-id="03881-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-329"><strong>Volume chiamata (chiamata VPN) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-330">No</span><span class="sxs-lookup"><span data-stu-id="03881-330">No</span></span></p></td>
<td><p><span data-ttu-id="03881-331">Numero totale di chiamate eseguite tramite una connessione VPN.</span><span class="sxs-lookup"><span data-stu-id="03881-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-332"><strong>Volume chiamata (chiamata esterna) </strong></span><span class="sxs-lookup"><span data-stu-id="03881-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-333">No</span><span class="sxs-lookup"><span data-stu-id="03881-333">No</span></span></p></td>
<td><p><span data-ttu-id="03881-334">Numero di chiamate eseguite tramite una connessione esterna, ovvero un collegamento fuori dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="03881-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-335"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="03881-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-336">No</span><span class="sxs-lookup"><span data-stu-id="03881-336">No</span></span></p></td>
<td><p><span data-ttu-id="03881-337">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="03881-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="03881-338">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="03881-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-339"><strong>Media unidirezionale relativa</strong></span><span class="sxs-lookup"><span data-stu-id="03881-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-340">No</span><span class="sxs-lookup"><span data-stu-id="03881-340">No</span></span></p></td>
<td><p><span data-ttu-id="03881-p130">Media unidirezionale relativa tra due endpoint multimediali. Si tratta di una misurazione della latenza a singolo hop.</span><span class="sxs-lookup"><span data-stu-id="03881-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03881-343"><strong>Latenza media elaborazione sezioni RDP</strong></span><span class="sxs-lookup"><span data-stu-id="03881-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-344">No</span><span class="sxs-lookup"><span data-stu-id="03881-344">No</span></span></p></td>
<td><p><span data-ttu-id="03881-345">Latenza media dell'elaborazione delle sezioni RDP in AS Conferencing Server per la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="03881-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="03881-346">Una media elevata riflette un ritardo più lungo nell'esperienza di visualizzazione e include la latenza della rete.</span><span class="sxs-lookup"><span data-stu-id="03881-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="03881-347">In un server per conferenze sovraccaricato possono verificarsi ritardi medi maggiori.</span><span class="sxs-lookup"><span data-stu-id="03881-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03881-348"><strong>% totale sezioni danneggiate</strong></span><span class="sxs-lookup"><span data-stu-id="03881-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="03881-349">No</span><span class="sxs-lookup"><span data-stu-id="03881-349">No</span></span></p></td>
<td><p><span data-ttu-id="03881-350">Percentuale totale di sezioni RDP danneggiate.</span><span class="sxs-lookup"><span data-stu-id="03881-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

