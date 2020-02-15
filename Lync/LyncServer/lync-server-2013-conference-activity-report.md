---
title: 'Lync Server 2013: rapporto attività conferenza'
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
ms.openlocfilehash: f8992d4a8e6dc0933449c4ab4be4602d9707f1d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="99c47-102">Report attività conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99c47-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99c47-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="99c47-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="99c47-104">Con il Rapporto attività conferenza è semplice rispondere a domande come queste: quante conferenze si tengono ogni giorno e quando hanno luogo?</span><span class="sxs-lookup"><span data-stu-id="99c47-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="99c47-105">Informazioni di questo tipo non sono solo utili di per sé, ma anche come strumenti di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="99c47-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="99c47-106">Si supponga ad esempio che gli utenti si lamentino del fatto che la rete sia particolarmente lenta a metà giornata.</span><span class="sxs-lookup"><span data-stu-id="99c47-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="99c47-107">Un rapido sguardo ai report sulle attività di conferenza potrebbe suggerire un possibile motivo: molte più conferenze vengono pianificate tra le ore 10:00 e 2:00 poi in qualsiasi altro momento.</span><span class="sxs-lookup"><span data-stu-id="99c47-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="99c47-108">Se la lentezza della rete crea problemi, è possibile chiedere agli utenti di riprogrammare alcune delle conferenze in orari di minor traffico.</span><span class="sxs-lookup"><span data-stu-id="99c47-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="99c47-109">Accesso al Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="99c47-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="99c47-110">Il rapporto attività conferenza è accessibile dal [rapporto riepilogativo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c47-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="99c47-111">Totale conferenze</span><span class="sxs-lookup"><span data-stu-id="99c47-111">Total conferences</span></span>

  - <span data-ttu-id="99c47-112">Totale partecipanti</span><span class="sxs-lookup"><span data-stu-id="99c47-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="99c47-113">Utilizzo ottimale del Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="99c47-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="99c47-p102">Per impostazione predefinita, il Rapporto attività conferenza mostra il numero totale di conferenze per il periodo di tempo specificato (ad esempio il numero totale di conferenze al giorno oppure il numero totale di conferenze all'ora). È tuttavia anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo specificato o il numero totale di minuti partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro, quindi selezionare una delle seguenti opzioni dall'elenco a discesa Rapporto di:</span><span class="sxs-lookup"><span data-stu-id="99c47-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="99c47-117">Numero partecipanti</span><span class="sxs-lookup"><span data-stu-id="99c47-117">Participant count</span></span>

  - <span data-ttu-id="99c47-118">Minuti partecipante</span><span class="sxs-lookup"><span data-stu-id="99c47-118">Participant minutes</span></span>

  - <span data-ttu-id="99c47-119">Numero conferenze</span><span class="sxs-lookup"><span data-stu-id="99c47-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="99c47-120">Filtri</span><span class="sxs-lookup"><span data-stu-id="99c47-120">Filters</span></span>

<span data-ttu-id="99c47-p103">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività conferenza.</span><span class="sxs-lookup"><span data-stu-id="99c47-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="99c47-123">Filtri per il Rapporto attività conferenza</span><span class="sxs-lookup"><span data-stu-id="99c47-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99c47-124">Nome</span><span class="sxs-lookup"><span data-stu-id="99c47-124">Name</span></span></th>
<th><span data-ttu-id="99c47-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c47-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99c47-126"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-p104">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="99c47-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="99c47-129">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="99c47-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="99c47-p105">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="99c47-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="99c47-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="99c47-132">7/7/2012</span></span></p>
<p><span data-ttu-id="99c47-133">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="99c47-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="99c47-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="99c47-134">7/3/2012</span></span></p>
<p><span data-ttu-id="99c47-135">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="99c47-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c47-136"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-p106">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="99c47-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="99c47-139">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="99c47-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="99c47-p107">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="99c47-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="99c47-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="99c47-142">7/7/2012</span></span></p>
<p><span data-ttu-id="99c47-143">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="99c47-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="99c47-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="99c47-144">7/3/2012</span></span></p>
<p><span data-ttu-id="99c47-145">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="99c47-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c47-146"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-p108">Intervallo di tempo. Selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c47-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="99c47-149">Orario (è possibile visualizzare al massimo 25 ore)</span><span class="sxs-lookup"><span data-stu-id="99c47-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="99c47-150">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="99c47-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="99c47-151">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="99c47-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="99c47-152">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="99c47-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="99c47-p109">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati relativi ai giorni compresi tra 07/08/2012 12.00 e 07/09/2012 12.00, ovvero i dati relativi a un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="99c47-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c47-155"><strong>Rapporto di</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-p110">Indica i valori da utilizzare nel rapporto. È possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c47-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="99c47-158">Numero partecipanti</span><span class="sxs-lookup"><span data-stu-id="99c47-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="99c47-159">Minuti partecipante</span><span class="sxs-lookup"><span data-stu-id="99c47-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="99c47-160">Numero conferenze</span><span class="sxs-lookup"><span data-stu-id="99c47-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="99c47-161">Metrica delle conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="99c47-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="99c47-162">Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni pool.</span><span class="sxs-lookup"><span data-stu-id="99c47-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="99c47-163">Metrica delle conferenze per pool</span><span class="sxs-lookup"><span data-stu-id="99c47-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99c47-164">Nome</span><span class="sxs-lookup"><span data-stu-id="99c47-164">Name</span></span></th>
<th><span data-ttu-id="99c47-165">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="99c47-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="99c47-166">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c47-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99c47-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-168">No</span><span class="sxs-lookup"><span data-stu-id="99c47-168">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-169">Nome del pool di registrazione o del server perimetrale utilizzato nella conferenza.</span><span class="sxs-lookup"><span data-stu-id="99c47-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c47-170"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-171">No</span><span class="sxs-lookup"><span data-stu-id="99c47-171">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-172">Data e ora in cui è stata tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="99c47-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c47-173"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-174">No</span><span class="sxs-lookup"><span data-stu-id="99c47-174">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-175">Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</span><span class="sxs-lookup"><span data-stu-id="99c47-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="99c47-176">Metrica delle conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="99c47-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="99c47-177">Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni tipo di server.</span><span class="sxs-lookup"><span data-stu-id="99c47-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="99c47-178">Metrica delle conferenze per tipo di server</span><span class="sxs-lookup"><span data-stu-id="99c47-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99c47-179">Nome</span><span class="sxs-lookup"><span data-stu-id="99c47-179">Name</span></span></th>
<th><span data-ttu-id="99c47-180">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="99c47-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="99c47-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99c47-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99c47-182"><strong>Tipo server per conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-183">No</span><span class="sxs-lookup"><span data-stu-id="99c47-183">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-184">Tipo di server utilizzato nella conferenza, in genere uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="99c47-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="99c47-185">Web Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="99c47-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="99c47-186">IM Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="99c47-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="99c47-187">Telephony Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="99c47-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="99c47-188">AV Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="99c47-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="99c47-189">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="99c47-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99c47-190"><strong>Data/ora</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-191">No</span><span class="sxs-lookup"><span data-stu-id="99c47-191">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-192">Data e ora in cui è stata tenuta la conferenza.</span><span class="sxs-lookup"><span data-stu-id="99c47-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99c47-193"><strong>Totale</strong></span><span class="sxs-lookup"><span data-stu-id="99c47-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="99c47-194">No</span><span class="sxs-lookup"><span data-stu-id="99c47-194">No</span></span></p></td>
<td><p><span data-ttu-id="99c47-195">Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</span><span class="sxs-lookup"><span data-stu-id="99c47-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

