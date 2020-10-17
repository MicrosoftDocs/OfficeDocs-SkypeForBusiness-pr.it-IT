---
title: 'Lync Server 2013: rapporto elenco chiamate Response Group'
description: 'Lync Server 2013: rapporto elenco chiamate Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ffe4b62534d4849b4f0cdade9aeef8be5d69178
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560882"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="44950-103">Rapporto elenco chiamate Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44950-103">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44950-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="44950-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="44950-105">L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le chiamate telefoniche in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande.</span><span class="sxs-lookup"><span data-stu-id="44950-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="44950-106">In genere, le chiamate a Response Group non vengono instradate a una singola persona ma piuttosto a un team di persone definito gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="44950-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="44950-107">Ad esempio, se un utente chiama il numero di telefono per il supporto tecnico, Lync Server 2013 può instradare automaticamente la chiamata al primo agente del supporto tecnico disponibile.</span><span class="sxs-lookup"><span data-stu-id="44950-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="44950-108">In alternativa, è possibile che Lync Server chieda una serie di domande ("premere 1 se si riscontrano problemi hardware.</span><span class="sxs-lookup"><span data-stu-id="44950-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="44950-109">Premere 2 in caso di problemi software.</span><span class="sxs-lookup"><span data-stu-id="44950-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="44950-110">Premere 3 Se si verificano problemi di rete. " e quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.</span><span class="sxs-lookup"><span data-stu-id="44950-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="44950-p102">Il Rapporto Elenco chiamate Response Group è una raccolta di chiamate di un determinato tipo effettuate per un determinato periodo di tempo. Il Rapporto di utilizzo di Response Group, che deve essere aperto prima di poter aprire il Rapporto Elemento chiamate Response Group, riconosce i tipi di chiamate seguenti:</span><span class="sxs-lookup"><span data-stu-id="44950-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="44950-p103">**Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="44950-115">**Chiamate riuscite**.</span><span class="sxs-lookup"><span data-stu-id="44950-115">**Successful calls**.</span></span> <span data-ttu-id="44950-116">Numero totale di chiamate ritirate dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="44950-p105">**Chiamate offerte**. Numero totale di chiamate trasferite a un agente Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="44950-p106">**Chiamate con risposta**. Numero totale di chiamate che hanno effettivamente ricevuto una risposta da un agente Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="44950-121">Percentuale di chiamate interrotte.</span><span class="sxs-lookup"><span data-stu-id="44950-121">Percentage of abandoned calls.</span></span> <span data-ttu-id="44950-122">Percentuale di chiamate ricevute dall'applicazione Response Group alle quali però non è stata mai fornita risposta da un agente.</span><span class="sxs-lookup"><span data-stu-id="44950-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="44950-123">Questo valore viene calcolato sottraendo il valore di Chiamate con risposta dal valore di Chiamate ricevute e quindi dividendo tale valore per il numero di Chiamate ricevute.</span><span class="sxs-lookup"><span data-stu-id="44950-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="44950-124">Se ad esempio si ricevono 10 chiamate, di cui 7 con risposta, sarà necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="44950-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="44950-125">Tale valore verrà poi diviso per 10 e si otterrà una percentuale di chiamate interrotte pari al 30%.</span><span class="sxs-lookup"><span data-stu-id="44950-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="44950-p108">**Chiamate trasferite**. Numero totale di chiamate di Response Group trasferite a causa del timeout o dell'overflow di una coda.</span><span class="sxs-lookup"><span data-stu-id="44950-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="44950-128">Accesso al Rapporto Elenco chiamate Response Group</span><span class="sxs-lookup"><span data-stu-id="44950-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="44950-129">È possibile accedere al rapporto elenco chiamate Response Group solo facendo clic su una delle metriche riportate di seguito riportate nel [report sull'utilizzo di Response Group in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="44950-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="44950-130">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="44950-130">Received calls</span></span>

  - <span data-ttu-id="44950-131">Chiamate riuscite</span><span class="sxs-lookup"><span data-stu-id="44950-131">Successful calls</span></span>

  - <span data-ttu-id="44950-132">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="44950-132">Offered calls</span></span>

  - <span data-ttu-id="44950-133">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="44950-133">Answered calls</span></span>

  - <span data-ttu-id="44950-134">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="44950-134">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="44950-135">Utilizzo ottimale del Rapporto Elenco chiamate Response Group</span><span class="sxs-lookup"><span data-stu-id="44950-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="44950-p109">Il Rapporto Elenco chiamate Response Group consente di limitare i dati visualizzati alle chiamate che interessano un particolare flusso di lavoro di Response Group. A tale scopo, è necessario immettere l'URI del flusso di lavoro, ovvero l'indirizzo SIP del flusso di lavoro, nella casella URI flusso di lavoro. Prima di poter immettere tali informazioni, è tuttavia necessario che la casella URI flusso di lavoro sia visibile. Per visualizzare le opzioni di filtro per il Rapporto Elenco chiamate Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del rapporto.</span><span class="sxs-lookup"><span data-stu-id="44950-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="44950-140">Si noti che nell'elenco chiamate Response Group non vengono visualizzate informazioni relative al codice di risposta o all'ID diagnostica posizionando il puntatore del mouse su una di queste metriche.</span><span class="sxs-lookup"><span data-stu-id="44950-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="44950-141">Se sono necessarie ulteriori informazioni, è possibile prendere nota del codice di risposta e/o dell'ID di diagnostica e quindi cercare tali valori nel [rapporto errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="44950-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="44950-142">Per sapere ad esempio quale singolo flusso di lavoro ha ricevuto il maggior numero di chiamate, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44950-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="44950-p111">Nel Rapporto di utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica Chiamate ricevute. Verrà aperto il Rapporto Elenco chiamate Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="44950-p112">Esportare i dati visualizzati nel Rapporto Elenco chiamate Response Group. Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi utilizzare Excel per convertire tali dati in un file con valori delimitati da virgole.</span><span class="sxs-lookup"><span data-stu-id="44950-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="44950-147">Eseguire le analisi utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44950-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="44950-148">Ad esempio, se i dati sono stati salvati in un file denominato C: \\ data \\ Response \_ Group \_ Call \_ List \_Report.csv, è possibile utilizzare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel rapporto:</span><span class="sxs-lookup"><span data-stu-id="44950-148">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="44950-149">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="44950-149">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="44950-150">Filtri</span><span class="sxs-lookup"><span data-stu-id="44950-150">Filters</span></span>

<span data-ttu-id="44950-p113">I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri applicabili al rapporto Elenco chiamate Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="44950-153">Filtri rapporto Elenco chiamate Response Group</span><span class="sxs-lookup"><span data-stu-id="44950-153">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44950-154">Nome</span><span class="sxs-lookup"><span data-stu-id="44950-154">Name</span></span></th>
<th><span data-ttu-id="44950-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44950-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44950-156"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="44950-156"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-p114">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="44950-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="44950-159">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="44950-159">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44950-p115">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="44950-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44950-162">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44950-162">7/7/2012</span></span></p>
<p><span data-ttu-id="44950-163">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="44950-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44950-164">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44950-164">7/3/2012</span></span></p>
<p><span data-ttu-id="44950-165">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="44950-165">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44950-166"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="44950-166"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-p116">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="44950-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="44950-169">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="44950-169">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44950-p117">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="44950-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44950-172">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44950-172">7/7/2012</span></span></p>
<p><span data-ttu-id="44950-173">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="44950-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44950-174">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44950-174">7/3/2012</span></span></p>
<p><span data-ttu-id="44950-175">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="44950-175">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44950-176"><strong>URI flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="44950-176"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-p118">Consente di limitare i dati restituiti al flusso di lavoro di Response Group specificato. Per utilizzare questo filtro, immettere l'indirizzo SIP del flusso di lavoro, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="44950-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="44950-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="44950-180">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44950-181"><strong>Chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="44950-181"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-182">È possibile selezionare uno dei tipi di chiamata seguenti:</span><span class="sxs-lookup"><span data-stu-id="44950-182">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="44950-183">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="44950-183">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="44950-184">Chiamate completate</span><span class="sxs-lookup"><span data-stu-id="44950-184">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="44950-185">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="44950-185">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="44950-186">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="44950-186">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="44950-187">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="44950-187">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="44950-188">Metriche</span><span class="sxs-lookup"><span data-stu-id="44950-188">Metrics</span></span>

<span data-ttu-id="44950-189">Nella tabella seguente sono elencate le informazioni fornite nel rapporto Elenco chiamate Response Group Call per ogni chiamata ricevuta dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="44950-190">Metriche del rapporto Elenco chiamate Response Group</span><span class="sxs-lookup"><span data-stu-id="44950-190">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44950-191">Nome</span><span class="sxs-lookup"><span data-stu-id="44950-191">Name</span></span></th>
<th><span data-ttu-id="44950-192">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="44950-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="44950-193">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44950-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44950-194"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="44950-194"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-195">No</span><span class="sxs-lookup"><span data-stu-id="44950-195">No</span></span></p></td>
<td><p><span data-ttu-id="44950-196">Indirizzo SIP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="44950-196">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44950-197"><strong>Flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="44950-197"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-198">No</span><span class="sxs-lookup"><span data-stu-id="44950-198">No</span></span></p></td>
<td><p><span data-ttu-id="44950-199">Indirizzo SIP del flusso di lavoro Response Group.</span><span class="sxs-lookup"><span data-stu-id="44950-199">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44950-200"><strong>Ora inizio</strong></span><span class="sxs-lookup"><span data-stu-id="44950-200"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-201">No</span><span class="sxs-lookup"><span data-stu-id="44950-201">No</span></span></p></td>
<td><p><span data-ttu-id="44950-202">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="44950-202">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44950-203"><strong>Ora fine</strong></span><span class="sxs-lookup"><span data-stu-id="44950-203"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-204">No</span><span class="sxs-lookup"><span data-stu-id="44950-204">No</span></span></p></td>
<td><p><span data-ttu-id="44950-205">Data e ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="44950-205">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44950-206"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="44950-206"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-207">No</span><span class="sxs-lookup"><span data-stu-id="44950-207">No</span></span></p></td>
<td><p><span data-ttu-id="44950-208">Codice di risposta SIP inviato per la sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="44950-208">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44950-209"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="44950-209"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="44950-210">No</span><span class="sxs-lookup"><span data-stu-id="44950-210">No</span></span></p></td>
<td><p><span data-ttu-id="44950-211">Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</span><span class="sxs-lookup"><span data-stu-id="44950-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

