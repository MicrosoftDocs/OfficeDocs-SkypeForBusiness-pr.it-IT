---
title: "Lync Server 2013: report sull'utilizzo di Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702ab291955ef7c8ec992e3607de581dff52b6a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="6a0ba-102">Report sull'utilizzo di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a0ba-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a0ba-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="6a0ba-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="6a0ba-104">L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le telefonate in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="6a0ba-105">In genere, le chiamate di Response Group non vengono instradate a una singola persona, ma vengono invece indirizzate a un team di persone denominato gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="6a0ba-106">Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Lync Server 2013 può automaticamente indirizzare la chiamata al primo agente del supporto tecnico disponibile.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="6a0ba-107">In alternativa, Lync Server può porre una serie di domande ("premere 1 se si verificano problemi hardware.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="6a0ba-108">Premere 2 Se si verificano problemi di software.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="6a0ba-109">Premere 3 Se si verificano problemi di rete. ") quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="6a0ba-110">Il report sull'utilizzo dei gruppi di risposta fornisce un'occhiata dettagliata al numero di telefonate ricevute da tutti i flussi di lavoro di Response Group, quindi suddivide le chiamate in categorie più finite, ad esempio le chiamate offerte, le chiamate e le chiamate interrotte.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="6a0ba-111">La chiave per l'uso del report sull'utilizzo del gruppo di risposte consiste nel comprendere la differenza tra i tipi di chiamata segnalati:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="6a0ba-112">**Chiamate ricevute**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-112">**Received calls**.</span></span> <span data-ttu-id="6a0ba-113">Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="6a0ba-114">**Chiamate di successo**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-114">**Successful calls**.</span></span> <span data-ttu-id="6a0ba-115">Numero totale di chiamate rilevate dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="6a0ba-116">**Chiamate offerte**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-116">**Offered calls**.</span></span> <span data-ttu-id="6a0ba-117">Numero totale di chiamate trasferite a un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="6a0ba-118">**Chiamate con risposta**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-118">**Answered calls**.</span></span> <span data-ttu-id="6a0ba-119">Numero totale di chiamate effettivamente risolte da un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="6a0ba-120">**Percentuale di chiamate abbandonate**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-120">**Percentage of abandoned calls**.</span></span> <span data-ttu-id="6a0ba-121">Percentuale di chiamate ricevute dall'applicazione Response Group, ma non è stata mai risolta da un agente.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="6a0ba-122">Questo valore viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="6a0ba-123">Ad esempio, se sono state ricevute 10 chiamate e 7 sono state risolte, è necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="6a0ba-124">Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="6a0ba-125">**Chiamate trasferite**.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-125">**Transferred calls**.</span></span> <span data-ttu-id="6a0ba-126">Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="6a0ba-127">Se si sta esaminando il report sull'utilizzo di Response Group e non si riesce a ricordare la definizione per uno di questi tipi di chiamata, è sufficiente posizionare il puntatore del mouse sull'etichetta appropriata per il tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-127">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label.</span></span> <span data-ttu-id="6a0ba-128">Verrà visualizzata una descrizione comando che offre una breve descrizione del tipo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-128">A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="6a0ba-129">Il report sull'utilizzo di Response Group consente di filtrare in base a un URI del flusso di lavoro (l'indirizzo SIP associato al flusso di lavoro).</span><span class="sxs-lookup"><span data-stu-id="6a0ba-129">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow).</span></span> <span data-ttu-id="6a0ba-130">Tuttavia, gli URI del flusso di lavoro non vengono effettivamente visualizzati nel report stesso.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-130">However, workflow URIs do not actually appear on the report itself.</span></span> <span data-ttu-id="6a0ba-131">Se si vuole sapere quali sono i flussi di lavoro che rispondono alla maggior parte delle chiamate o i flussi di lavoro in cui si verificano le chiamate più trasferite, fare clic sulla metrica appropriata per aprire il report di elenco delle chiamate di Response Group per il periodo di tempo indicato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-131">If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period.</span></span> <span data-ttu-id="6a0ba-132">Questi report elencano gli URI del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-132">That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="6a0ba-133">Accesso al report sull'utilizzo dei gruppi di risposte</span><span class="sxs-lookup"><span data-stu-id="6a0ba-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="6a0ba-134">Il report sull'utilizzo dei gruppi di risposte si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="6a0ba-135">È possibile eseguire il drill-down nel [report elenco delle chiamate di Response Group in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="6a0ba-136">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="6a0ba-136">Received calls</span></span>

  - <span data-ttu-id="6a0ba-137">Chiamate di successo</span><span class="sxs-lookup"><span data-stu-id="6a0ba-137">Successful calls</span></span>

  - <span data-ttu-id="6a0ba-138">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="6a0ba-138">Offered calls</span></span>

  - <span data-ttu-id="6a0ba-139">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="6a0ba-139">Answered calls</span></span>

  - <span data-ttu-id="6a0ba-140">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="6a0ba-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="6a0ba-141">Uso ottimale del report sull'utilizzo dei gruppi di risposte</span><span class="sxs-lookup"><span data-stu-id="6a0ba-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="6a0ba-142">Uno degli usi più interessanti del report sull'utilizzo dei gruppi di risposte potrebbe non essere evidente: la possibilità di recuperare le informazioni sull'utilizzo per un singolo flusso di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6a0ba-143">Un flusso di lavoro di Response Group è fondamentalmente un set di istruzioni che determina il funzionamento di Lync Server quando un utente compone un determinato numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="6a0ba-144">A questo scopo, ogni flusso di lavoro è associato in modo univoco a un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="6a0ba-145">Quando qualcuno chiama tale numero, il flusso di lavoro determina il modo in cui verrà gestita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="6a0ba-146">Ad esempio, il flusso di lavoro può causare la instradamento della chiamata a una serie di domande IVR (Interactive Voice Response) che richiedono al chiamante di immettere altre informazioni ("premere 1 per il supporto hardware.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="6a0ba-147">Premere 2 per il supporto del software. ").</span><span class="sxs-lookup"><span data-stu-id="6a0ba-147">Press 2 for software support.").</span></span> <span data-ttu-id="6a0ba-148">In alternativa, il flusso di lavoro potrebbe causare la chiamata a essere inserita in una coda, con il chiamante messo in attesa finché non è disponibile un agente per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="6a0ba-149">La disponibilità degli agenti per rispondere alle chiamate viene dettata anche dal flusso di lavoro: i flussi di lavoro vengono usati per configurare sia gli orari di ufficio (i giorni della settimana che gli orari in cui gli agenti sono disponibili per rispondere alle chiamate) e le festività (giorni in cui non sono disponibili agenti per rispondere chiamate).</span><span class="sxs-lookup"><span data-stu-id="6a0ba-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="6a0ba-150">Ogni volta che si digita un numero di telefono che appartiene all'applicazione Response Group si sta essenzialmente chiamando un flusso di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="6a0ba-151">Anche se gli URI del flusso di lavoro non vengono visualizzati nel report sull'utilizzo dei gruppi di risposte, è comunque possibile visualizzare le statistiche di utilizzo per un singolo flusso di lavoro, un aspetto spesso estremamente utile.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-151">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful.</span></span> <span data-ttu-id="6a0ba-152">Supponi, ad esempio, che tu abbia recentemente svelato una nuova campagna pubblicitaria e che sia curioso sapere se le persone stanno chiamando per chiedere informazioni sul prodotto.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-152">For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product.</span></span> <span data-ttu-id="6a0ba-153">Se è stato associato un flusso di lavoro di Response Group con il numero di telefono indicato nella campagna pubblicitaria, è possibile verificare facilmente quante persone (se presenti) chiamano tale numero.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-153">If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="6a0ba-154">Potresti anche usare un approccio simile per valutare il numero di chiamate gestite dall'help desk interno o dal reparto assistenza clienti.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="6a0ba-155">Per rivedere le statistiche sull'utilizzo per un determinato flusso di lavoro, immettere l'URI del flusso di lavoro nella casella URI flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="6a0ba-156">Naturalmente, come indicato, gli URI del flusso di lavoro (l'indirizzo SIP associato a un flusso di lavoro) non vengono visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="6a0ba-157">Questo significa che devi trovare un altro modo per determinare l'URI di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="6a0ba-158">Un modo per eseguire questa operazione consiste nell'usare Windows PowerShell e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="6a0ba-159">Ad esempio, questo comando restituisce gli URI per tutti i flussi di lavoro di Response Group:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="6a0ba-160">Che restituirà dati simili a questi:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="6a0ba-161">Questo comando restituisce le informazioni per un singolo flusso di lavoro, quello con la campagna nuovo annuncio nome:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6a0ba-162">Filtri</span><span class="sxs-lookup"><span data-stu-id="6a0ba-162">Filters</span></span>

<span data-ttu-id="6a0ba-163">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-163">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="6a0ba-164">Ad esempio, il report sull'utilizzo di Response Group consente di visualizzare i dati per tutti i flussi di lavoro di Response Group o di visualizzare i dati per un singolo flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-164">For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow.</span></span> <span data-ttu-id="6a0ba-165">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-165">You can also choose how data should be grouped.</span></span> <span data-ttu-id="6a0ba-166">In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-166">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="6a0ba-167">Nella tabella seguente sono elencati i filtri che è possibile usare con il report sull'utilizzo di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="6a0ba-168">Filtri di report sull'utilizzo dei gruppi di risposta</span><span class="sxs-lookup"><span data-stu-id="6a0ba-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a0ba-169">Nome</span><span class="sxs-lookup"><span data-stu-id="6a0ba-169">Name</span></span></th>
<th><span data-ttu-id="6a0ba-170">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a0ba-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-171"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-172">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-172">Start date/time for the time range.</span></span> <span data-ttu-id="6a0ba-173">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-173">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6a0ba-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6a0ba-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6a0ba-175">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-175">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="6a0ba-176">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-176">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6a0ba-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6a0ba-177">7/7/2012</span></span></p>
<p><span data-ttu-id="6a0ba-178">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="6a0ba-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6a0ba-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6a0ba-179">7/3/2012</span></span></p>
<p><span data-ttu-id="6a0ba-180">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-181"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-182">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-182">End date/time for the time range.</span></span> <span data-ttu-id="6a0ba-183">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-183">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6a0ba-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="6a0ba-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6a0ba-185">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-185">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="6a0ba-186">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6a0ba-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6a0ba-187">7/7/2012</span></span></p>
<p><span data-ttu-id="6a0ba-188">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="6a0ba-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6a0ba-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6a0ba-189">7/3/2012</span></span></p>
<p><span data-ttu-id="6a0ba-190">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-191"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-192">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-192">Time interval.</span></span> <span data-ttu-id="6a0ba-193">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-193">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6a0ba-194">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="6a0ba-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6a0ba-195">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="6a0ba-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6a0ba-196">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="6a0ba-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6a0ba-197">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="6a0ba-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6a0ba-198">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="6a0ba-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="6a0ba-199">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-200"><strong>URI del flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-201">Consente di limitare i dati restituiti al flusso di lavoro del gruppo di risposte specificato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-201">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="6a0ba-202">Per usare questo filtro, immettere l'indirizzo SIP del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-202">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="6a0ba-203">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-203">For example:</span></span></p>
<p><span data-ttu-id="6a0ba-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6a0ba-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6a0ba-205">Metriche</span><span class="sxs-lookup"><span data-stu-id="6a0ba-205">Metrics</span></span>

<span data-ttu-id="6a0ba-206">Nella tabella seguente sono elencate le informazioni fornite nel report sull'utilizzo di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="6a0ba-207">Metriche del report sull'utilizzo di Response Group</span><span class="sxs-lookup"><span data-stu-id="6a0ba-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6a0ba-208">Nome</span><span class="sxs-lookup"><span data-stu-id="6a0ba-208">Name</span></span></th>
<th><span data-ttu-id="6a0ba-209">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="6a0ba-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6a0ba-210">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a0ba-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-211"><strong>Oraria</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="6a0ba-212"><strong>Quotidiana</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="6a0ba-213"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="6a0ba-214"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-215">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-215">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-216">Indica l'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-216">Indicates the selected time interval.</span></span> <span data-ttu-id="6a0ba-217">Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="6a0ba-218">Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-219"><strong>Chiamate ricevute</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-220">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-220">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-221">Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-221">Total number of calls received by all instances of the Response Group application.</span></span> <span data-ttu-id="6a0ba-222">Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-222">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-223"><strong>Chiamate di successo</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-224">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-224">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-225">Numero totale di chiamate raccolte nell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-225">Total number of calls that were picked up the Response Group application.</span></span> <span data-ttu-id="6a0ba-226">Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-226">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-227"><strong>Chiamate offerte</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-228">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-228">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-229">Numero totale di chiamate trasferite a un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-229">Total number of calls that were transferred to a Response Group agent.</span></span> <span data-ttu-id="6a0ba-230">Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-230">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-231"><strong>Chiamate con risposta</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-232">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-232">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-233">Numero totale di chiamate effettivamente risolte da un agente di Response Group.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-233">Total number of calls that were actually answered by a Response Group agent.</span></span> <span data-ttu-id="6a0ba-234">Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-234">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-235"><strong>Percentuale di chiamate abbandonate</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-236">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-236">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-237">Numero totale di chiamate ricevute dall'applicazione Response Group, ma non sono mai state risposte da un agente.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-237">Total number of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="6a0ba-238">Ciò viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-238">This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls.</span></span> <span data-ttu-id="6a0ba-239">Ad esempio, se hai 10 chiamate ricevute e sette hanno ricevuto una risposta, devi sottrarre sette da 10, lasciando tre chiamate senza risposta.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-239">For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls.</span></span> <span data-ttu-id="6a0ba-240">Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-240">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6a0ba-241"><strong>Minuti di chiamata media per agente</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-242">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-242">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-243">Intervallo di tempo medio di un agente del gruppo di risposte speso per una chiamata.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6a0ba-244"><strong>Chiamate trasferite</strong></span><span class="sxs-lookup"><span data-stu-id="6a0ba-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="6a0ba-245">No</span><span class="sxs-lookup"><span data-stu-id="6a0ba-245">No</span></span></p></td>
<td><p><span data-ttu-id="6a0ba-246">Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-246">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span> <span data-ttu-id="6a0ba-247">Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-247">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

