---
title: "Lync Server 2013: report sull'utilizzo di Response Group"
description: "Lync Server 2013: report sull'utilizzo di Response Group."
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
ms.openlocfilehash: e541a618e8578debc84630037d530c96f4e39ea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553062"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="075d2-103">Report sull'utilizzo di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="075d2-103">Response Group Usage Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="075d2-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="075d2-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="075d2-105">L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le chiamate telefoniche in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande.</span><span class="sxs-lookup"><span data-stu-id="075d2-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="075d2-106">In genere, le chiamate a Response Group non vengono instradate a una singola persona ma piuttosto a un team di persone definito gruppo di agenti.</span><span class="sxs-lookup"><span data-stu-id="075d2-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="075d2-107">Ad esempio, se un utente chiama il numero di telefono per il supporto tecnico, Lync Server 2013 può instradare automaticamente la chiamata al primo agente del supporto tecnico disponibile.</span><span class="sxs-lookup"><span data-stu-id="075d2-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="075d2-108">In alternativa, è possibile che Lync Server chieda una serie di domande ("premere 1 se si riscontrano problemi hardware.</span><span class="sxs-lookup"><span data-stu-id="075d2-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="075d2-109">Premere 2 in caso di problemi software.</span><span class="sxs-lookup"><span data-stu-id="075d2-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="075d2-110">Premere 3 Se si verificano problemi di rete. " e quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.</span><span class="sxs-lookup"><span data-stu-id="075d2-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="075d2-111">Il Rapporto di utilizzo dei Response Group fornisce una specifica dettagliata del numero di chiamate telefoniche ricevute da tutti i flussi di lavoro di Response Group e quindi suddivide tali chiamate in categorie più limitate, ad esempio Chiamate offerte, Chiamate con risposta e Chiamate interrotte.</span><span class="sxs-lookup"><span data-stu-id="075d2-111">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="075d2-112">Per lavorare con il Rapporto di utilizzo di Response Group è fondamentale comprendere la differenza tra i tipi di chiamate segnalate:</span><span class="sxs-lookup"><span data-stu-id="075d2-112">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="075d2-p102">**Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="075d2-115">**Chiamate riuscite**.</span><span class="sxs-lookup"><span data-stu-id="075d2-115">**Successful calls**.</span></span> <span data-ttu-id="075d2-116">Numero totale di chiamate ritirate dall'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="075d2-p104">**Chiamate offerte**. Numero totale di chiamate trasferite a un agente Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="075d2-p105">**Chiamate con risposta**. Numero totale di chiamate che hanno effettivamente ricevuto una risposta da un agente Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="075d2-p106">**Percentuale di chiamate interrotte**. Percentuale delle chiamate ricevute dall'applicazione Response Group ma che non hanno ricevuto risposta da un agente. Questo valore viene calcolato sottraendo le Chiamate con risposta dalle Chiamate ricevute e quindi dividendo tale valore per il numero di Chiamate ricevute. Se, ad esempio, sono state ricevute 10 chiamate di cui 7 con risposta, è necessario sottrarre 7 a 10. Il risultato sarà 3 chiamate senza risposta. Tale valore deve essere quindi diviso per 10, in modo da ottenere una percentuale di chiamate interrotte pari al 30%.</span><span class="sxs-lookup"><span data-stu-id="075d2-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="075d2-p107">**Chiamate trasferite**. Numero totale di chiamate a Response Group che sono state trasferite a causa di un timeout o di un overflow della coda.</span><span class="sxs-lookup"><span data-stu-id="075d2-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="075d2-p108">Se osservando il Rapporto di utilizzo di Response Group non si ricorda la definizione di uno di questi tipi di chiamate, è sufficiente posizionare il mouse sull'etichetta del tipo di chiamata appropriata per visualizzare una descrizione comandi con una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="075d2-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="075d2-p109">Il Rapporto di utilizzo di Response Group consente di applicare un filtro a un URI di un flusso di lavoro (l'indirizzo SIP associato a tale flusso di lavoro). Gli URI dei flussi di lavoro, tuttavia, non vengono visualizzati nel rapporto. Se si desidera sapere, ad esempio, quali flussi di lavoro stanno rispondendo al maggior numero di chiamate o quali flussi di lavoro stanno registrando il maggior numero di chiamate trasferite, fare clic sulla metrica appropriata per aprire il rapporto Elenco chiamate di Response Group relativo al tale periodo di tempo. Nel rapporto saranno elencati gli URI dei flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="075d2-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="075d2-134">Accesso al Rapporto di utilizzo di Response Group</span><span class="sxs-lookup"><span data-stu-id="075d2-134">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="075d2-135">L'accesso al Rapporto di utilizzo di Response Group può essere effettuato dalla home page di Relazioni monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="075d2-135">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="075d2-136">È possibile eseguire il drill-down nel [rapporto elenco chiamate Response Group in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="075d2-136">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="075d2-137">Chiamate ricevute</span><span class="sxs-lookup"><span data-stu-id="075d2-137">Received calls</span></span>

  - <span data-ttu-id="075d2-138">Chiamate riuscite</span><span class="sxs-lookup"><span data-stu-id="075d2-138">Successful calls</span></span>

  - <span data-ttu-id="075d2-139">Chiamate offerte</span><span class="sxs-lookup"><span data-stu-id="075d2-139">Offered calls</span></span>

  - <span data-ttu-id="075d2-140">Chiamate con risposta</span><span class="sxs-lookup"><span data-stu-id="075d2-140">Answered calls</span></span>

  - <span data-ttu-id="075d2-141">Chiamate trasferite</span><span class="sxs-lookup"><span data-stu-id="075d2-141">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="075d2-142">Uso ottimale del Rapporto di utilizzo di Response Group</span><span class="sxs-lookup"><span data-stu-id="075d2-142">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="075d2-143">Uno degli usi più interessanti del Rapporto di utilizzo di Response Group potrebbe non essere immediatamente evidente, ovvero la capacità di recuperare informazioni sull'utilizzo per un singolo flusso di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-143">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="075d2-144">Un flusso di lavoro di Response Group è fondamentalmente un insieme di istruzioni che determina ciò che Lync Server esegue quando un utente compone un numero di telefono specifico.</span><span class="sxs-lookup"><span data-stu-id="075d2-144">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="075d2-145">A tale scopo, ogni flusso di lavoro è associato in modo univoco a un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="075d2-145">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="075d2-146">Quando un utente chiama tale numero, il flusso di lavoro determina la modalità di gestione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="075d2-146">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="075d2-147">Ad esempio, il flusso di lavoro potrebbe causare l'instradamento della chiamata a una serie di domande IVR (Interactive Voice Response) che richiedono al chiamante di immettere informazioni aggiuntive ("Premere 1 per il supporto hardware.</span><span class="sxs-lookup"><span data-stu-id="075d2-147">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="075d2-148">Premere 2 per il supporto software.").</span><span class="sxs-lookup"><span data-stu-id="075d2-148">Press 2 for software support.").</span></span> <span data-ttu-id="075d2-149">In alternativa, il flusso di lavoro potrebbe causare l'inserimento della chiamata in una coda e mettere in attesa il chiamante finché un agente non sarà disponibile per rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="075d2-149">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="075d2-150">La disponibilità degli agenti per la risposta alle chiamate dipende anche dal flusso di lavoro: i flussi di lavoro vengono usati per configurare sia l'orario di ufficio (i giorni della settimana e le ore del giorno in cui gli agenti sono disponibili per rispondere alle chiamate) che le festività (i giorni in cui non vi sono agenti disponibili per rispondere alle chiamate).</span><span class="sxs-lookup"><span data-stu-id="075d2-150">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="075d2-151">Ogni volta che si compone un numero di telefono appartenente all'applicazione Response Group, si chiama essenzialmente un flusso di lavoro di Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-151">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="075d2-p112">Sebbene gli URI dei flussi di lavoro non vengano visualizzati nel Rapporto di utilizzo di Response Group, è comunque possibile visualizzare le statistiche di utilizzo per un singolo flusso di lavoro, operazione che è spesso molto utile. Si supponga, ad esempio, di aver lanciato di recente una nuova campagna pubblicitaria e di essere curioso di sapere se gli utenti stanno chiamando per chiedere informazioni sul prodotto in questione. Se un flusso di lavoro di Response Group è stato associato al numero di telefono indicato per la campagna pubblicitaria, è possibile verificare facilmente se e quante persone stanno componendo tale numero.</span><span class="sxs-lookup"><span data-stu-id="075d2-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="075d2-155">È possibile adottare un approccio simile anche per misurare il numero di chiamate gestite dall'helpdesk interno o dal Servizio clienti.</span><span class="sxs-lookup"><span data-stu-id="075d2-155">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="075d2-156">Per esaminare le statistiche sull'utilizzo di un flusso di lavoro specifico, immettere l'URI del flusso di lavoro nella casella URI del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="075d2-156">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="075d2-157">Naturalmente, come indicato, gli URI del flusso di lavoro (l'indirizzo SIP associato a un flusso di lavoro) non vengono visualizzati nel report.</span><span class="sxs-lookup"><span data-stu-id="075d2-157">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="075d2-158">Questo significa che è necessario trovare un altro modo per determinare l'URI di un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="075d2-158">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="075d2-159">A tale scopo, è possibile utilizzare Windows PowerShell e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="075d2-159">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="075d2-160">Ad esempio, questo comando restituisce gli URI per tutti i flussi di lavoro di Response Group:</span><span class="sxs-lookup"><span data-stu-id="075d2-160">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="075d2-161">I dati restituiti saranno simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="075d2-161">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="075d2-162">Questo comando restituisce informazioni relative a un singolo flusso di lavoro, ovvero "New Ad Campaign":</span><span class="sxs-lookup"><span data-stu-id="075d2-162">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="075d2-163">Filtri</span><span class="sxs-lookup"><span data-stu-id="075d2-163">Filters</span></span>

<span data-ttu-id="075d2-p114">I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto di utilizzo di Response Group ad esempio consente di visualizzare i dati di tutti i flussi di lavoro di Response Group o di un singolo flusso di lavoro. È inoltre possibile scegliere come raggruppare i dati. In questo caso, gli utilizzi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="075d2-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="075d2-168">Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto di utilizzo di Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-168">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="075d2-169">Filtri del Rapporto di utilizzo di Response Group</span><span class="sxs-lookup"><span data-stu-id="075d2-169">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="075d2-170">Nome</span><span class="sxs-lookup"><span data-stu-id="075d2-170">Name</span></span></th>
<th><span data-ttu-id="075d2-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="075d2-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="075d2-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-p115">Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</span><span class="sxs-lookup"><span data-stu-id="075d2-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="075d2-175">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="075d2-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="075d2-p116">Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="075d2-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="075d2-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="075d2-178">7/7/2012</span></span></p>
<p><span data-ttu-id="075d2-179">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="075d2-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="075d2-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="075d2-180">7/3/2012</span></span></p>
<p><span data-ttu-id="075d2-181">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="075d2-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-p117">Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</span><span class="sxs-lookup"><span data-stu-id="075d2-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="075d2-185">07/07/2012 13.00</span><span class="sxs-lookup"><span data-stu-id="075d2-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="075d2-p118">Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="075d2-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="075d2-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="075d2-188">7/7/2012</span></span></p>
<p><span data-ttu-id="075d2-189">Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="075d2-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="075d2-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="075d2-190">7/3/2012</span></span></p>
<p><span data-ttu-id="075d2-191">Le settimane vanno sempre dal lunedì alla domenica.</span><span class="sxs-lookup"><span data-stu-id="075d2-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="075d2-192"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-p119">Selezionare uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="075d2-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="075d2-195">Orario (è possibile visualizzare un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="075d2-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="075d2-196">Giornaliero (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="075d2-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="075d2-197">Settimanale (è possibile visualizzare un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="075d2-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="075d2-198">Mensile (è possibile visualizzare un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="075d2-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="075d2-p120">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati relativi ai giorni compresi tra 08/07/2012 12.00 e 08/09/2012 12.00, ovvero i dati relativi a un totale di 31 giorni.</span><span class="sxs-lookup"><span data-stu-id="075d2-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-201"><strong>URI flusso di lavoro</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-201"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-p121">Consente di limitare i dati restituiti al flusso di lavoro di Response Group specificato. Per utilizzare questo filtro, immettere l'indirizzo SIP del flusso di lavoro, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="075d2-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="075d2-205">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="075d2-205">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="075d2-206">Metriche</span><span class="sxs-lookup"><span data-stu-id="075d2-206">Metrics</span></span>

<span data-ttu-id="075d2-207">Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto di utilizzo di Response Group.</span><span class="sxs-lookup"><span data-stu-id="075d2-207">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="075d2-208">Metrica del Rapporto di utilizzo di Response Group</span><span class="sxs-lookup"><span data-stu-id="075d2-208">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="075d2-209">Nome</span><span class="sxs-lookup"><span data-stu-id="075d2-209">Name</span></span></th>
<th><span data-ttu-id="075d2-210">Elemento utilizzabile per eseguire l'ordinamento?</span><span class="sxs-lookup"><span data-stu-id="075d2-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="075d2-211">Descrizione</span><span class="sxs-lookup"><span data-stu-id="075d2-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="075d2-212"><strong>Orario</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="075d2-213"><strong>Giornaliero</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="075d2-214"><strong>Settimanale</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="075d2-215"><strong>Mensile</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-216">No</span><span class="sxs-lookup"><span data-stu-id="075d2-216">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p122">Indica l'intervallo di tempo selezionato. Nei casi in cui è previsto, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate relative a tale intervallo di tempo. Se ad esempio si usa l'intervallo Giornaliero e si fa clic su 07/07/2012, verrà visualizzata una suddivisione oraria dell'attività di registrazione dell'utente per tale data.</span><span class="sxs-lookup"><span data-stu-id="075d2-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-220"><strong>Chiamate ricevute</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-220"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-221">No</span><span class="sxs-lookup"><span data-stu-id="075d2-221">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p123">Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="075d2-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="075d2-224"><strong>Chiamate riuscite</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-224"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-225">No</span><span class="sxs-lookup"><span data-stu-id="075d2-225">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p124">Numero totale di chiamate che hanno ricevuto riposta dall'applicazione Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="075d2-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-228"><strong>Chiamate offerte</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-228"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-229">No</span><span class="sxs-lookup"><span data-stu-id="075d2-229">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p125">Numero totale di chiamate trasferite a un agente di Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="075d2-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="075d2-232"><strong>Chiamate con risposta</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-232"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-233">No</span><span class="sxs-lookup"><span data-stu-id="075d2-233">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p126">Numero totale di chiamate a cui effettivamente è stata fornita una risposta da un agente di Response Group. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="075d2-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-236"><strong>Percentuale di chiamate interrotte</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-236"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-237">No</span><span class="sxs-lookup"><span data-stu-id="075d2-237">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p127">Numero totale di chiamate ricevute dall'applicazione Response Group ma alle quali non è stata mai fornita risposta da un agente. Questo valore viene calcolato sottraendo il valore di Chiamate con risposta dal valore di Chiamate ricevute e quindi dividendo tale valore per il numero di chiamate ricevute. Se ad esempio sono state ricevute 10 chiamate, di cui sette con risposta, sarà necessario sottrarre sette da 10, lasciando tre chiamate senza risposta. Tale valore verrà poi diviso per 10 e si otterrà una percentuale di chiamate interrotte pari al 30%.</span><span class="sxs-lookup"><span data-stu-id="075d2-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="075d2-242"><strong>Media minuti chiamata per agente</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-242"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-243">No</span><span class="sxs-lookup"><span data-stu-id="075d2-243">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-244">Quantità media di tempo dedicata da una gente di Response Group per chiamata.</span><span class="sxs-lookup"><span data-stu-id="075d2-244">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="075d2-245"><strong>Chiamate trasferite</strong></span><span class="sxs-lookup"><span data-stu-id="075d2-245"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="075d2-246">No</span><span class="sxs-lookup"><span data-stu-id="075d2-246">No</span></span></p></td>
<td><p><span data-ttu-id="075d2-p128">Numero totale di chiamate di Response Group trasferite a causa del timeout o dell'overflow di una coda. Quando si fa clic su questo elemento, viene visualizzato il Rapporto Elenco chiamate Response Group relativo all'intervallo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="075d2-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

