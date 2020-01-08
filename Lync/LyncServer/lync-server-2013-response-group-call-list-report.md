---
title: 'Lync Server 2013: report elenco chiamate di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf2c45167b5e5c437a3ff755115aa54d34c74a87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="be493-102">Report elenco chiamate di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be493-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be493-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="be493-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="be493-104">L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le telefonate in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande.</span><span class="sxs-lookup"><span data-stu-id="be493-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="be493-105">In genere, le chiamate di Response Group non vengono instradate a una singola persona, ma vengono invece indirizzate a un team di persone denominato gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="be493-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="be493-106">Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Lync Server 2013 può automaticamente indirizzare la chiamata al primo agente del supporto tecnico disponibile.</span><span class="sxs-lookup"><span data-stu-id="be493-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="be493-107">In alternativa, Lync Server può porre una serie di domande ("premere 1 se si verificano problemi hardware.</span><span class="sxs-lookup"><span data-stu-id="be493-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="be493-108">Premere 2 Se si verificano problemi di software.</span><span class="sxs-lookup"><span data-stu-id="be493-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="be493-109">Premere 3 Se si verificano problemi di rete. ") quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.</span><span class="sxs-lookup"><span data-stu-id="be493-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="be493-110">Il report elenco delle chiamate di Response Group rappresenta una raccolta di chiamate effettuate per un determinato periodo di tempo e per un determinato tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="be493-110">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="be493-111">Il report sull'utilizzo dei gruppi di risposte (che deve essere aperto per primo prima di poter aprire il report di elenco delle chiamate di Response Group) riconosce i tipi di chiamata seguenti:</span><span class="sxs-lookup"><span data-stu-id="be493-111">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="be493-112">**Chiamate ricevute**.</span><span class="sxs-lookup"><span data-stu-id="be493-112">**Received calls**.</span></span> <span data-ttu-id="be493-113">Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="be493-114">**Chiamate di successo**.</span><span class="sxs-lookup"><span data-stu-id="be493-114">**Successful calls**.</span></span> <span data-ttu-id="be493-115">Numero totale di chiamate rilevate dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="be493-116">**Chiamate offerte**.</span><span class="sxs-lookup"><span data-stu-id="be493-116">**Offered calls**.</span></span> <span data-ttu-id="be493-117">Numero totale di chiamate trasferite a un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="be493-118">**Chiamate con risposta**.</span><span class="sxs-lookup"><span data-stu-id="be493-118">**Answered calls**.</span></span> <span data-ttu-id="be493-119">Numero totale di chiamate effettivamente risolte da un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="be493-120">Percentuale di chiamate abbandonate.</span><span class="sxs-lookup"><span data-stu-id="be493-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="be493-121">Percentuale di chiamate ricevute dall'applicazione Response Group, ma non è stata mai risolta da un agente.</span><span class="sxs-lookup"><span data-stu-id="be493-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="be493-122">Questo valore viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute.</span><span class="sxs-lookup"><span data-stu-id="be493-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="be493-123">Ad esempio, se sono state ricevute 10 chiamate e 7 sono state risolte, è necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="be493-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="be493-124">Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.</span><span class="sxs-lookup"><span data-stu-id="be493-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="be493-125">**Chiamate trasferite**.</span><span class="sxs-lookup"><span data-stu-id="be493-125">**Transferred calls**.</span></span> <span data-ttu-id="be493-126">Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="be493-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="be493-127">Accesso al report elenco chiamate di Response Group</span><span class="sxs-lookup"><span data-stu-id="be493-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="be493-128">È possibile accedere al report elenco delle chiamate di Response Group solo facendo clic su una delle metriche seguenti disponibili nel [report sull'utilizzo dei gruppi di risposte in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="be493-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="be493-129">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="be493-129">Received calls</span></span>

  - <span data-ttu-id="be493-130">Chiamate di successo</span><span class="sxs-lookup"><span data-stu-id="be493-130">Successful calls</span></span>

  - <span data-ttu-id="be493-131">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="be493-131">Offered calls</span></span>

  - <span data-ttu-id="be493-132">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="be493-132">Answered calls</span></span>

  - <span data-ttu-id="be493-133">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="be493-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="be493-134">Sfruttare al meglio il report elenco chiamate di Response Group</span><span class="sxs-lookup"><span data-stu-id="be493-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="be493-135">Il report elenco delle chiamate di Response Group consente di limitare i dati visualizzati alle chiamate che coinvolgono un determinato flusso di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-135">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="be493-136">A questo scopo, devi immettere l'URI del flusso di lavoro (l'indirizzo SIP del flusso di lavoro) nella casella URI flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="be493-136">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="be493-137">Prima di poterlo fare, tuttavia, devi essere effettivamente in grado di vedere la casella URI flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="be493-137">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="be493-138">Per visualizzare le opzioni di filtro per il report elenco chiamate di Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del report.</span><span class="sxs-lookup"><span data-stu-id="be493-138">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="be493-139">Tieni presente che l'elenco delle chiamate di gruppo di risposta non Visualizza le informazioni sul codice di risposta o sull'ID di diagnostica se tieni premuto il mouse su una di queste metriche.</span><span class="sxs-lookup"><span data-stu-id="be493-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="be493-140">Se sono necessarie altre informazioni, è possibile notare il codice di risposta e/o l'ID di diagnostica e quindi cercare tali valori nel [report errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="be493-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="be493-141">una domanda simile alla seguente: "quale singolo flusso di lavoro ha ricevuto la maggior parte delle chiamate?", è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="be493-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="be493-142">Nel report sull'utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica chiamate ricevute.</span><span class="sxs-lookup"><span data-stu-id="be493-142">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="be493-143">Che aprirà il report elenco delle chiamate di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-143">That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="be493-144">Esportare i dati visualizzati nel report elenco chiamate di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-144">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="be493-145">Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi usare Excel per convertire i dati in un file con valori separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="be493-145">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="be493-146">Eseguire le analisi con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be493-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="be493-147">Ad esempio, se i dati sono stati salvati in un file denominato C:\\elenco\\\_chiamate\_\_di\_gruppo risposta dati. csv, è possibile usare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel report:</span><span class="sxs-lookup"><span data-stu-id="be493-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="be493-148">In questo modo le informazioni sono simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="be493-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="be493-149">Filtri</span><span class="sxs-lookup"><span data-stu-id="be493-149">Filters</span></span>

<span data-ttu-id="be493-150">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="be493-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="be493-151">Nella tabella seguente sono elencati i filtri che è possibile usare con il report elenco chiamate di Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-151">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="be493-152">Filtri dei report elenco chiamate di Response Group</span><span class="sxs-lookup"><span data-stu-id="be493-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be493-153">Nome</span><span class="sxs-lookup"><span data-stu-id="be493-153">Name</span></span></th>
<th><span data-ttu-id="be493-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be493-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be493-155"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="be493-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-156">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="be493-156">Start date/time for the time range.</span></span> <span data-ttu-id="be493-157">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="be493-157">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="be493-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="be493-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="be493-159">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="be493-159">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="be493-160">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="be493-160">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="be493-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="be493-161">7/7/2012</span></span></p>
<p><span data-ttu-id="be493-162">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="be493-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="be493-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="be493-163">7/3/2012</span></span></p>
<p><span data-ttu-id="be493-164">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="be493-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be493-165"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="be493-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-166">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="be493-166">End date/time for the time range.</span></span> <span data-ttu-id="be493-167">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="be493-167">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="be493-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="be493-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="be493-169">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="be493-169">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="be493-170">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="be493-170">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="be493-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="be493-171">7/7/2012</span></span></p>
<p><span data-ttu-id="be493-172">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="be493-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="be493-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="be493-173">7/3/2012</span></span></p>
<p><span data-ttu-id="be493-174">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="be493-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be493-175"><strong>URI del flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="be493-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-176">Consente di limitare i dati restituiti al flusso di lavoro del gruppo di risposte specificato.</span><span class="sxs-lookup"><span data-stu-id="be493-176">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="be493-177">Per usare questo filtro, immettere l'indirizzo SIP del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="be493-177">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="be493-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="be493-178">For example:</span></span></p>
<p><span data-ttu-id="be493-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be493-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be493-180"><strong>Chiamate</strong></span><span class="sxs-lookup"><span data-stu-id="be493-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-181">Puoi selezionare uno dei tipi di chiamata seguenti:</span><span class="sxs-lookup"><span data-stu-id="be493-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="be493-182">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="be493-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="be493-183">Chiamate di successo</span><span class="sxs-lookup"><span data-stu-id="be493-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="be493-184">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="be493-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="be493-185">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="be493-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="be493-186">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="be493-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="be493-187">Metriche</span><span class="sxs-lookup"><span data-stu-id="be493-187">Metrics</span></span>

<span data-ttu-id="be493-188">Nella tabella seguente sono elencate le informazioni fornite nel report di elenco delle chiamate di Response Group per ogni chiamata ricevuta dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="be493-189">Metriche del report elenco chiamate di Response Group</span><span class="sxs-lookup"><span data-stu-id="be493-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be493-190">Nome</span><span class="sxs-lookup"><span data-stu-id="be493-190">Name</span></span></th>
<th><span data-ttu-id="be493-191">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="be493-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="be493-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be493-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be493-193"><strong>Chiamante</strong></span><span class="sxs-lookup"><span data-stu-id="be493-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-194">No</span><span class="sxs-lookup"><span data-stu-id="be493-194">No</span></span></p></td>
<td><p><span data-ttu-id="be493-195">Indirizzo SIP del chiamante.</span><span class="sxs-lookup"><span data-stu-id="be493-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be493-196"><strong>Flusso</strong></span><span class="sxs-lookup"><span data-stu-id="be493-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-197">No</span><span class="sxs-lookup"><span data-stu-id="be493-197">No</span></span></p></td>
<td><p><span data-ttu-id="be493-198">Indirizzo SIP del flusso di lavoro Response Group.</span><span class="sxs-lookup"><span data-stu-id="be493-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be493-199"><strong>Ora di inizio</strong></span><span class="sxs-lookup"><span data-stu-id="be493-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-200">No</span><span class="sxs-lookup"><span data-stu-id="be493-200">No</span></span></p></td>
<td><p><span data-ttu-id="be493-201">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="be493-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be493-202"><strong>Ora di fine</strong></span><span class="sxs-lookup"><span data-stu-id="be493-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-203">No</span><span class="sxs-lookup"><span data-stu-id="be493-203">No</span></span></p></td>
<td><p><span data-ttu-id="be493-204">Data e ora di fine della chiamata.</span><span class="sxs-lookup"><span data-stu-id="be493-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be493-205"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="be493-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-206">No</span><span class="sxs-lookup"><span data-stu-id="be493-206">No</span></span></p></td>
<td><p><span data-ttu-id="be493-207">Codice di risposta SIP inviato quando la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="be493-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be493-208"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="be493-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="be493-209">No</span><span class="sxs-lookup"><span data-stu-id="be493-209">No</span></span></p></td>
<td><p><span data-ttu-id="be493-210">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="be493-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

