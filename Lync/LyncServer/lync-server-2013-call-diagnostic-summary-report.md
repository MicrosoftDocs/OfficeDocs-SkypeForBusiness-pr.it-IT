---
title: 'Lync Server 2013: rapporto riepilogativo di diagnostica chiamate'
description: 'Lync Server 2013: rapporto riepilogativo di diagnostica chiamate.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b444a176c06974a9eb9827006e078c17b54047a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561702"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="23eaa-103">Rapporto riepilogativo di diagnostica chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23eaa-103">Call Diagnostic Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23eaa-104">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="23eaa-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="23eaa-p101">Il Rapporto riepilogativo di diagnostica chiamate offre un quadro generale delle sessioni di conferenza e peer-to-peer non riuscite. Il rapporto illustra la percentuale generale degli errori per entrambi i tipi di sessioni e ulteriori dettagli sui problemi in base al tipo di modalità della sessione:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="23eaa-107">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="23eaa-107">Instant messaging</span></span>

  - <span data-ttu-id="23eaa-108">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="23eaa-108">Application sharing</span></span>

  - <span data-ttu-id="23eaa-109">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="23eaa-109">File transfer</span></span>

  - <span data-ttu-id="23eaa-110">Audio</span><span class="sxs-lookup"><span data-stu-id="23eaa-110">Audio</span></span>

  - <span data-ttu-id="23eaa-111">Video</span><span class="sxs-lookup"><span data-stu-id="23eaa-111">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="23eaa-112">Accesso al Rapporto riepilogativo di diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="23eaa-112">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="23eaa-113">Il Rapporto riepilogativo di diagnostica chiamate è accessibile dalla home page Rapporti di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="23eaa-113">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="23eaa-114">Dal rapporto riepilogativo di diagnostica chiamate è possibile accedere al [rapporto di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) facendo clic sulla metrica di frequenza di errore nella sezione peer-to-peer Session summary del report.</span><span class="sxs-lookup"><span data-stu-id="23eaa-114">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="23eaa-115">È inoltre possibile accedere al [rapporto di diagnostica conferenze in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) facendo clic su una delle metriche di conferenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="23eaa-115">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="23eaa-116">Frequenza generale errori sessione</span><span class="sxs-lookup"><span data-stu-id="23eaa-116">Overall session failure rate</span></span>

  - <span data-ttu-id="23eaa-117">Frequenza errori Focus</span><span class="sxs-lookup"><span data-stu-id="23eaa-117">Focus failure rate</span></span>

  - <span data-ttu-id="23eaa-118">Frequenza errori MCU</span><span class="sxs-lookup"><span data-stu-id="23eaa-118">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="23eaa-119">Uso ottimale del Rapporto riepilogativo di diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="23eaa-119">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="23eaa-120">Il rapporto riepilogativo di diagnostica chiamata include grafici che confrontano le percentuali di errori per le varie modalità utilizzate in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23eaa-120">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="23eaa-121">Le colonne di questi grafici sono in realtà hotlinks; ad esempio, se si fa clic sulla colonna messaggistica immediata per le sessioni peer-to-peer, verrà illustrato come eseguire il drill-down in un'istanza del [rapporto di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un report che fornisce ulteriori dettagli su tutte le sessioni di messaggistica istantanea incluse nel rapporto riepilogativo di diagnostica chiamate.</span><span class="sxs-lookup"><span data-stu-id="23eaa-121">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="23eaa-122">Filtri</span><span class="sxs-lookup"><span data-stu-id="23eaa-122">Filters</span></span>

<span data-ttu-id="23eaa-p104">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il rapporto riepilogativo di diagnostica chiamate consente di filtrare in base al pool di registrazione o al server perimetrale utilizzato nella sessione. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le chiamate sono raggruppabili per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="23eaa-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="23eaa-127">Nella tabella seguente sono elencati i filtri applicabili al rapporto riepilogativo di diagnostica chiamate.</span><span class="sxs-lookup"><span data-stu-id="23eaa-127">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="23eaa-128">Filtri del Rapporto riepilogativo di diagnostica chiamate</span><span class="sxs-lookup"><span data-stu-id="23eaa-128">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23eaa-129">Nome</span><span class="sxs-lookup"><span data-stu-id="23eaa-129">Name</span></span></th>
<th><span data-ttu-id="23eaa-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23eaa-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-131"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-131"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-p105">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="23eaa-134">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="23eaa-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="23eaa-p106">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="23eaa-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="23eaa-137">7/7/2012</span></span></p>
<p><span data-ttu-id="23eaa-138">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="23eaa-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="23eaa-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="23eaa-139">7/3/2012</span></span></p>
<p><span data-ttu-id="23eaa-140">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="23eaa-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-141"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-141"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-p107">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="23eaa-144">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="23eaa-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="23eaa-p108">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="23eaa-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="23eaa-147">7/7/2012</span></span></p>
<p><span data-ttu-id="23eaa-148">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="23eaa-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="23eaa-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="23eaa-149">7/3/2012</span></span></p>
<p><span data-ttu-id="23eaa-150">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="23eaa-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-151"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-151"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-p109">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="23eaa-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="23eaa-154">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="23eaa-154">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="23eaa-155">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="23eaa-155">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="23eaa-156">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="23eaa-156">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="23eaa-157">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="23eaa-157">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="23eaa-p110">Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</span><span class="sxs-lookup"><span data-stu-id="23eaa-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-p111">Nome di dominio completo del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="23eaa-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="23eaa-164">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="23eaa-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="23eaa-165">La tabella seguente elenca le informazioni disponibili nel Rapporto riepilogativo di diagnostica chiamate per le sessioni peer-to-peer di conferenza, ovvero le sessioni che coinvolgono solo due partecipanti.</span><span class="sxs-lookup"><span data-stu-id="23eaa-165">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="23eaa-166">Metriche per le sessioni peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="23eaa-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23eaa-167">Nome</span><span class="sxs-lookup"><span data-stu-id="23eaa-167">Name</span></span></th>
<th><span data-ttu-id="23eaa-168">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="23eaa-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="23eaa-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23eaa-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-170"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-170"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-171">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-171">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-172">Numero totale di sessioni peer-to-peer condotte.</span><span class="sxs-lookup"><span data-stu-id="23eaa-172">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-173"><strong>Frequenza errori</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-173"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-174">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-174">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-p112">Percentuale delle sessioni peer-to-peer non riuscite. Facendo clic su questo elemento verrà visualizzato il Rapporto di diagnostica attività peer-to-peer, che mostra informazioni più dettagliate sulle sessioni peer-to-peer non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="23eaa-177">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="23eaa-177">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="23eaa-178">La tabella seguente elenca le informazioni disponibili nel rapporto di diagnostica chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="23eaa-178">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="23eaa-179">Metriche per le sessioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="23eaa-179">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23eaa-180">Nome</span><span class="sxs-lookup"><span data-stu-id="23eaa-180">Name</span></span></th>
<th><span data-ttu-id="23eaa-181">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="23eaa-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="23eaa-182">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23eaa-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-183"><strong>Totale conferenze</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-183"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-184">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-184">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-185">Numero totale di conferenze condotte.</span><span class="sxs-lookup"><span data-stu-id="23eaa-185">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-186"><strong>Totale sessioni conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-186"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-187">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-187">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-188">Numero totale di sessioni di conferenza condotte.</span><span class="sxs-lookup"><span data-stu-id="23eaa-188">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-189"><strong>Frequenza generale errori sessione</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-189"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-190">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-190">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-191">Percentuale del totale di sessioni di conferenza non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-191">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-192"><strong>Sessioni Focus</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-192"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-193">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-193">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-194">Numero totale di sessioni di conferenza basate su Focus non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-194">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-195"><strong>Frequenza errori Focus</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-195"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-196">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-196">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-197">Percentuale delle sessioni di conferenza basate su Focus non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-197">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23eaa-198"><strong>Sessioni MCU</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-198"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-199">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-199">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-200">Numero totale di conferenze basate su server per conferenze (in precedenza MCU, Multipoint Control Unit) non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-200">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23eaa-201"><strong>Frequenza errori MCU</strong></span><span class="sxs-lookup"><span data-stu-id="23eaa-201"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="23eaa-202">No</span><span class="sxs-lookup"><span data-stu-id="23eaa-202">No</span></span></p></td>
<td><p><span data-ttu-id="23eaa-203">Percentuale di totale di conferenze basate su server per conferenze (in precedenza MCU, Multipoint Control Unit) non riuscite.</span><span class="sxs-lookup"><span data-stu-id="23eaa-203">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

