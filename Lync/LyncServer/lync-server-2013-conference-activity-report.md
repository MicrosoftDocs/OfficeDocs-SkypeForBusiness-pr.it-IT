---
title: 'Lync Server 2013: rapporto attività conferenza'
description: 'Lync Server 2013: report attività conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577652"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="b93a0-103">Report attività conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b93a0-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b93a0-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b93a0-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b93a0-105">Con il Rapporto attività conferenza è semplice rispondere a domande come queste: quante conferenze si tengono ogni giorno e quando hanno luogo?</span><span class="sxs-lookup"><span data-stu-id="b93a0-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="b93a0-106">Informazioni di questo tipo non sono solo utili di per sé, ma anche come strumenti di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="b93a0-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="b93a0-107">Si supponga ad esempio che gli utenti si lamentino del fatto che la rete sia particolarmente lenta a metà giornata.</span><span class="sxs-lookup"><span data-stu-id="b93a0-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="b93a0-108">Un rapido sguardo ai report sulle attività di conferenza potrebbe suggerire un possibile motivo: molte più conferenze vengono pianificate tra le ore 10:00 e 2:00 poi in qualsiasi altro momento.</span><span class="sxs-lookup"><span data-stu-id="b93a0-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="b93a0-109">Se la lentezza della rete crea problemi, è possibile chiedere agli utenti di riprogrammare alcune delle conferenze in orari di minor traffico.</span><span class="sxs-lookup"><span data-stu-id="b93a0-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="b93a0-110">Accesso al Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="b93a0-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="b93a0-111">Il rapporto attività conferenza è accessibile dal [rapporto riepilogativo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93a0-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="b93a0-112">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="b93a0-112">Total conferences</span></span>

  - <span data-ttu-id="b93a0-113">Totale partecipanti</span><span class="sxs-lookup"><span data-stu-id="b93a0-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="b93a0-114">Utilizzo ottimale del Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="b93a0-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="b93a0-p102">Per impostazione predefinita, il Rapporto attività conferenza mostra il numero totale di conferenze per il periodo di tempo specificato (ad esempio il numero totale di conferenze al giorno oppure il numero totale di conferenze all'ora). È tuttavia anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo specificato o il numero totale di minuti partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro, quindi selezionare una delle seguenti opzioni dall'elenco a discesa Rapporto di:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="b93a0-118">Numero partecipanti</span><span class="sxs-lookup"><span data-stu-id="b93a0-118">Participant count</span></span>

  - <span data-ttu-id="b93a0-119">Minuti partecipante</span><span class="sxs-lookup"><span data-stu-id="b93a0-119">Participant minutes</span></span>

  - <span data-ttu-id="b93a0-120">Numero conferenze</span><span class="sxs-lookup"><span data-stu-id="b93a0-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b93a0-121">Filtri</span><span class="sxs-lookup"><span data-stu-id="b93a0-121">Filters</span></span>

<span data-ttu-id="b93a0-p103">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività conferenza.</span><span class="sxs-lookup"><span data-stu-id="b93a0-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="b93a0-124">Filtri per il Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="b93a0-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b93a0-125">Nome</span><span class="sxs-lookup"><span data-stu-id="b93a0-125">Name</span></span></th>
<th><span data-ttu-id="b93a0-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93a0-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-p104">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b93a0-130">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="b93a0-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b93a0-p105">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b93a0-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b93a0-133">7/7/2012</span></span></p>
<p><span data-ttu-id="b93a0-134">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b93a0-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b93a0-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b93a0-135">7/3/2012</span></span></p>
<p><span data-ttu-id="b93a0-136">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="b93a0-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93a0-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-p106">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b93a0-140">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="b93a0-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b93a0-p107">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b93a0-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b93a0-143">7/7/2012</span></span></p>
<p><span data-ttu-id="b93a0-144">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="b93a0-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b93a0-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b93a0-145">7/3/2012</span></span></p>
<p><span data-ttu-id="b93a0-146">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="b93a0-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-147"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-p108">Intervallo di tempo. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b93a0-150">Orario (è possibile visualizzare al massimo 25 ore)</span><span class="sxs-lookup"><span data-stu-id="b93a0-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b93a0-151">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="b93a0-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b93a0-152">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="b93a0-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b93a0-153">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="b93a0-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b93a0-p109">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati relativi ai giorni compresi tra 07/08/2012 12.00 e 07/09/2012 12.00, ovvero i dati relativi a un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="b93a0-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93a0-156"><strong>Rapporto di</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-p110">Indica i valori da utilizzare nel rapporto. È possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93a0-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b93a0-159">Numero partecipanti</span><span class="sxs-lookup"><span data-stu-id="b93a0-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="b93a0-160">Minuti partecipante</span><span class="sxs-lookup"><span data-stu-id="b93a0-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="b93a0-161">Numero conferenze</span><span class="sxs-lookup"><span data-stu-id="b93a0-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="b93a0-162">Metrica delle conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="b93a0-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="b93a0-163">Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="b93a0-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="b93a0-164">Metrica delle conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="b93a0-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b93a0-165">Nome</span><span class="sxs-lookup"><span data-stu-id="b93a0-165">Name</span></span></th>
<th><span data-ttu-id="b93a0-166">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="b93a0-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b93a0-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93a0-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-169">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-169">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-170">Nome del pool di registrazione o del server perimetrale utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="b93a0-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93a0-171"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-172">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-172">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-173">Data e ora in cui è stata tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="b93a0-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-174"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-175">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-175">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-176">Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</span><span class="sxs-lookup"><span data-stu-id="b93a0-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="b93a0-177">Metrica delle conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="b93a0-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="b93a0-178">Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni tipo di server.</span><span class="sxs-lookup"><span data-stu-id="b93a0-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="b93a0-179">Metrica delle conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="b93a0-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b93a0-180">Nome</span><span class="sxs-lookup"><span data-stu-id="b93a0-180">Name</span></span></th>
<th><span data-ttu-id="b93a0-181">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="b93a0-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b93a0-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b93a0-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-183"><strong>Tipo server per conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-184">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-184">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-185">Tipo di server utilizzato nella conferenza, in genere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b93a0-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b93a0-186">Web Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="b93a0-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b93a0-187">IM Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="b93a0-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b93a0-188">Telephony Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="b93a0-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b93a0-189">AV Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="b93a0-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="b93a0-190">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="b93a0-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b93a0-191"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-192">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-192">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-193">Data e ora in cui è stata tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="b93a0-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b93a0-194"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="b93a0-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="b93a0-195">No</span><span class="sxs-lookup"><span data-stu-id="b93a0-195">No</span></span></p></td>
<td><p><span data-ttu-id="b93a0-196">Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</span><span class="sxs-lookup"><span data-stu-id="b93a0-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

