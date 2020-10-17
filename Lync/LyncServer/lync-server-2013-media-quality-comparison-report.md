---
title: 'Lync Server 2013: rapporto di confronto qualità multimediale'
description: 'Lync Server 2013: rapporto di confronto qualità multimediale.'
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
ms.openlocfilehash: b2c4c5c948d167ce5210f9814c4e0625ffaa9152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548232"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="07f86-103">Rapporto di confronto qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07f86-103">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07f86-104">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="07f86-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="07f86-105">Il Rapporto di confronto qualità multimediale consente di confrontare i valori di qualità delle chiamate per diversi tipi di chiamate audio, ad esempio le chiamate effettuate su rete wireless rispetto alle chiamate effettuate su connessione cablata.</span><span class="sxs-lookup"><span data-stu-id="07f86-105">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="07f86-106">Accesso al Rapporto di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="07f86-106">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="07f86-107">È possibile accedere al Rapporto di confronto qualità multimediale dalla home page dei rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="07f86-107">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="07f86-108">Filtri</span><span class="sxs-lookup"><span data-stu-id="07f86-108">Filters</span></span>

<span data-ttu-id="07f86-p101">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto di confronto qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="07f86-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="07f86-111">Filtri del Rapporto di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="07f86-111">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f86-112">Nome</span><span class="sxs-lookup"><span data-stu-id="07f86-112">Name</span></span></th>
<th><span data-ttu-id="07f86-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07f86-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f86-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-p102">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="07f86-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="07f86-117">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="07f86-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07f86-p103">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="07f86-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07f86-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07f86-120">7/7/2012</span></span></p>
<p><span data-ttu-id="07f86-121">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="07f86-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07f86-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07f86-122">7/3/2012</span></span></p>
<p><span data-ttu-id="07f86-123">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="07f86-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-p104">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="07f86-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="07f86-127">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="07f86-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07f86-p105">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="07f86-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07f86-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07f86-130">7/7/2012</span></span></p>
<p><span data-ttu-id="07f86-131">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="07f86-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07f86-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07f86-132">7/3/2012</span></span></p>
<p><span data-ttu-id="07f86-133">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="07f86-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-134"><strong>Chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-134"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-p106">Tipo di chiamata da utilizzare come elemento principale del confronto. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="07f86-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="07f86-137">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f86-137">[All]</span></span></p></li>
<li><p><span data-ttu-id="07f86-138">Esterno</span><span class="sxs-lookup"><span data-stu-id="07f86-138">External</span></span></p></li>
<li><p><span data-ttu-id="07f86-139">Interno</span><span class="sxs-lookup"><span data-stu-id="07f86-139">Internal</span></span></p></li>
<li><p><span data-ttu-id="07f86-140">VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-140">VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-141">Non VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-141">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-142">Cablata</span><span class="sxs-lookup"><span data-stu-id="07f86-142">Wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-143">Wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-143">Wireless</span></span></p></li>
<li><p><span data-ttu-id="07f86-144">Esterne e cablate</span><span class="sxs-lookup"><span data-stu-id="07f86-144">External and wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-145">Esterne e wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-145">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="07f86-146">Esterne e VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-146">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-147">Esterne e non VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-147">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-148">Interne e cablate</span><span class="sxs-lookup"><span data-stu-id="07f86-148">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-149">Interne e wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-149">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-150"><strong>Confronto con le chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-150"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-p107">Tipo di chiamata da utilizzare come elemento secondario del confronto. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="07f86-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="07f86-153">Tutti</span><span class="sxs-lookup"><span data-stu-id="07f86-153">[All]</span></span></p></li>
<li><p><span data-ttu-id="07f86-154">Esterno</span><span class="sxs-lookup"><span data-stu-id="07f86-154">External</span></span></p></li>
<li><p><span data-ttu-id="07f86-155">Interno</span><span class="sxs-lookup"><span data-stu-id="07f86-155">Internal</span></span></p></li>
<li><p><span data-ttu-id="07f86-156">VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-157">Non VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-157">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-158">Cablata</span><span class="sxs-lookup"><span data-stu-id="07f86-158">Wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-159">Wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-159">Wireless</span></span></p></li>
<li><p><span data-ttu-id="07f86-160">Esterne e cablate</span><span class="sxs-lookup"><span data-stu-id="07f86-160">External and wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-161">Esterne e wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-161">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="07f86-162">Esterne e VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-162">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-163">Esterne e non VPN</span><span class="sxs-lookup"><span data-stu-id="07f86-163">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="07f86-164">Interne e cablate</span><span class="sxs-lookup"><span data-stu-id="07f86-164">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="07f86-165">Interne e wireless</span><span class="sxs-lookup"><span data-stu-id="07f86-165">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-166"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-166"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-p108">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f86-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="07f86-169">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="07f86-169">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="07f86-170">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="07f86-170">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="07f86-171">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="07f86-171">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="07f86-p109">Se per le date di inizio e di fine si immette un numero di valori superiore al massimo consentito per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo Giornaliero con la data di inizio 07.07.12 e la data di fine 28.02.12, verranno visualizzati i dati relativi ai giorni da 07.08.12 alle 00.00 a 07.09.12 alle 00.00, ovvero per un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="07f86-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="07f86-174">Metriche</span><span class="sxs-lookup"><span data-stu-id="07f86-174">Metrics</span></span>

<span data-ttu-id="07f86-175">Nella tabella seguente sono elencate le informazioni disponibili nel Rapporto di confronto qualità multimediale.</span><span class="sxs-lookup"><span data-stu-id="07f86-175">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="07f86-176">Metriche del Rapporto di confronto qualità multimediale</span><span class="sxs-lookup"><span data-stu-id="07f86-176">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07f86-177">Nome</span><span class="sxs-lookup"><span data-stu-id="07f86-177">Name</span></span></th>
<th><span data-ttu-id="07f86-178">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="07f86-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="07f86-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07f86-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07f86-180"><strong>Volume chiamata</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-180"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-181">No</span><span class="sxs-lookup"><span data-stu-id="07f86-181">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-182">Numero totale di chiamate</span><span class="sxs-lookup"><span data-stu-id="07f86-182">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-183"><strong>Degradazione (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-184">No</span><span class="sxs-lookup"><span data-stu-id="07f86-184">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-185">Quantità media di degradazione MOS (media Opinion Score) con esperienza durante una chiamata.</span><span class="sxs-lookup"><span data-stu-id="07f86-185">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="07f86-186">I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore pari a 0,5 o meno rappresenta un calo accettabile.</span><span class="sxs-lookup"><span data-stu-id="07f86-186">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="07f86-187">Storicamente, i punteggi del parere medio sono stati calcolati con gli utenti che valutano la qualità di una chiamata su una scala da 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="07f86-187">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="07f86-188">Lync Server utilizza un set di algoritmi per stimare il modo in cui gli utenti avrebbero valutato una chiamata.</span><span class="sxs-lookup"><span data-stu-id="07f86-188">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="07f86-p111">Valori di degradazione elevati possono essere causati da congestione, mancanza di larghezza di banda, interferenze o congestione della rete wireless o da un endpoint o un server di contenuti multimediali sovraccarico. Una degradazione elevata genera audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="07f86-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-191"><strong>Percentuale chiamate di livello insufficiente</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-191"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-192">No</span><span class="sxs-lookup"><span data-stu-id="07f86-192">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p112">Numero totale di chiamate classificate come di livello insufficiente. In una chiama di livello insufficiente almeno una delle metriche misurate supera il valore consentito, ad esempio viene rilevato un livello di instabilità eccessivo.</span><span class="sxs-lookup"><span data-stu-id="07f86-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-195"><strong>Roundtrip (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-195"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-196">No</span><span class="sxs-lookup"><span data-stu-id="07f86-196">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p113">Tempo medio di roundtrip (in millisecondi) necessario a un pacchetto RTP (Real-Time Transport Protocol) per raggiungere un altro endpoint e quindi tornare indietro. I roundtrip pari o inferiori a 200 millisecondi vengono considerati accettabili.</span><span class="sxs-lookup"><span data-stu-id="07f86-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="07f86-p114">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="07f86-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-201"><strong>Perdita di pacchetti</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-201"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-202">No</span><span class="sxs-lookup"><span data-stu-id="07f86-202">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p115">Frequenza media di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori alti di perdita sono in genere dovuti a congestione, superamento della larghezza di banda disponibile, congestione/interferenze wireless o sovraccarico del server dei contenuti multimediali con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="07f86-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-206"><strong>Instabilità (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-206"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-207">No</span><span class="sxs-lookup"><span data-stu-id="07f86-207">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-208">Instabilità media rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="07f86-208">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="07f86-209">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="07f86-209">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-210"><strong>Rapporto campioni nascosti utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-210"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-211">No</span><span class="sxs-lookup"><span data-stu-id="07f86-211">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p117">Rapporto medio tra i campioni audio nascosti e il numero totale di campioni. Un campione audio nascosto è una tecnica utilizzata per mitigare le transazioni improvvise generalmente causate dall'eliminazione di pacchetti di rete. Valori elevati indicano l'applicazione di livelli significativi di soppressione della perdita applicata dovuti a perdita di pacchetti o instabilità, con conseguente audio distorto o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="07f86-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07f86-214"><strong>Rapporto campioni estesi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-214"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-215">No</span><span class="sxs-lookup"><span data-stu-id="07f86-215">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p118">Rapporto medio tra i campioni audio estesi e il numero totale di campioni. Con audio esteso si intende l'audio che è stato espanso per garantire la qualità delle chiamate quando viene rilevato un pacchetto di rete eliminato. Valori elevati indicano livelli significativi di estensione dei campioni dovuti a instabilità, con conseguente riproduzione di audio robotico o distorto.</span><span class="sxs-lookup"><span data-stu-id="07f86-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07f86-218"><strong>Rapporto campioni compressi utilità di ripristino</strong></span><span class="sxs-lookup"><span data-stu-id="07f86-218"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="07f86-219">No</span><span class="sxs-lookup"><span data-stu-id="07f86-219">No</span></span></p></td>
<td><p><span data-ttu-id="07f86-p119">Rapporto medio tra i campioni audio compressi e il numero totale di campioni. L'audio compresso è audio che è stato compresso per mantenere la qualità della chiamata quando è stato rilevato un pacchetto di rete eliminato. Valori alti indicano livelli significativi di compressione dei campioni dovuti a instabilità con conseguente riproduzione di audio accelerato o distorto.</span><span class="sxs-lookup"><span data-stu-id="07f86-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

