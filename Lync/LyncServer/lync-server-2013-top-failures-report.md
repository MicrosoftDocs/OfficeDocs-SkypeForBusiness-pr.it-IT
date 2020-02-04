---
title: 'Lync Server 2013: report errori principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a62dce5d074b19c2bc8958715ced61bb54a4c8e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="404e9-102">Report errori principali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="404e9-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="404e9-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="404e9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="404e9-104">Il report errori principali offre un'occhiata agli errori più comunemente segnalati e alle relative tendenze nel tempo.</span><span class="sxs-lookup"><span data-stu-id="404e9-104">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time.</span></span> <span data-ttu-id="404e9-105">Gli errori si basano su una combinazione delle due metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="404e9-105">Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="404e9-106">**ID diagnostica**.</span><span class="sxs-lookup"><span data-stu-id="404e9-106">**Diagnostic ID**.</span></span> <span data-ttu-id="404e9-107">Identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP.</span><span class="sxs-lookup"><span data-stu-id="404e9-107">Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message.</span></span> <span data-ttu-id="404e9-108">Gli ID di diagnostica contengono informazioni utili per la risoluzione dei problemi relativi alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="404e9-108">Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="404e9-109">**Codice di risposta**.</span><span class="sxs-lookup"><span data-stu-id="404e9-109">**Response code**.</span></span> <span data-ttu-id="404e9-110">I codici di risposta vengono usati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP.</span><span class="sxs-lookup"><span data-stu-id="404e9-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="404e9-111">Ad esempio, supponiamo che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken si chiami Pilar Ackerman).</span><span class="sxs-lookup"><span data-stu-id="404e9-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="404e9-112">Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto.</span><span class="sxs-lookup"><span data-stu-id="404e9-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="404e9-113">Il report errori principali include solo i codici di risposta inviati in risposta a un errore di chiamata. Lync Server non tiene traccia di tutti i codici di risposta emessi durante il corso di una chiamata.</span><span class="sxs-lookup"><span data-stu-id="404e9-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="404e9-114">Le informazioni vengono segnalate non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti interessati dall'errore.</span><span class="sxs-lookup"><span data-stu-id="404e9-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="404e9-115">Accesso al report errori principali</span><span class="sxs-lookup"><span data-stu-id="404e9-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="404e9-116">Il report errori principali si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="404e9-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="404e9-117">Facendo clic sulla metrica delle sessioni segnalate si accede al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span><span class="sxs-lookup"><span data-stu-id="404e9-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="404e9-118">Sfruttare al meglio il report errori principali</span><span class="sxs-lookup"><span data-stu-id="404e9-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="404e9-119">Il report errori principali è inusuale in un aspetto: consente di filtrare fino a un massimo di 5 ID di diagnostica contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="404e9-119">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once.</span></span> <span data-ttu-id="404e9-120">In genere è possibile filtrare solo su un elemento, ad esempio un indirizzo SIP dell'utente, alla volta. Per filtrare su più ID di diagnostica, è sufficiente immettere ogni ID nella casella ID di diagnostica, separandoli con virgole.</span><span class="sxs-lookup"><span data-stu-id="404e9-120">(Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas.</span></span> <span data-ttu-id="404e9-121">Se si vuole, è possibile abbandonare uno spazio vuoto dopo ogni virgola. Per esempio:</span><span class="sxs-lookup"><span data-stu-id="404e9-121">(If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="404e9-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="404e9-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="404e9-123">A tale scopo, verranno visualizzate solo le chiamate non riuscite che segnalano almeno uno di questi cinque ID diagnostici.</span><span class="sxs-lookup"><span data-stu-id="404e9-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="404e9-124">Se si tiene premuto il mouse su un codice di risposta, viene visualizzata una descrizione comando che indica il significato del codice di risposta in questione.</span><span class="sxs-lookup"><span data-stu-id="404e9-124">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means.</span></span> <span data-ttu-id="404e9-125">Ad esempio, se si tiene premuto il puntatore del mouse sul codice di risposta 486, viene visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="404e9-125">For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="404e9-126">Occupato qui.</span><span class="sxs-lookup"><span data-stu-id="404e9-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="404e9-127">Filtri</span><span class="sxs-lookup"><span data-stu-id="404e9-127">Filters</span></span>

<span data-ttu-id="404e9-128">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="404e9-128">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="404e9-129">Il report errori principali, ad esempio, consente di filtrare i dati restituiti in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o il codice di risposta SIP che ha accompagnato la sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="404e9-129">For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session.</span></span> <span data-ttu-id="404e9-130">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="404e9-130">You can also choose how data should be grouped.</span></span> <span data-ttu-id="404e9-131">In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="404e9-131">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="404e9-132">Nella tabella seguente sono elencati i filtri che è possibile usare con il report errori principali.</span><span class="sxs-lookup"><span data-stu-id="404e9-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="404e9-133">Filtri di report errori principali</span><span class="sxs-lookup"><span data-stu-id="404e9-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="404e9-134">Nome</span><span class="sxs-lookup"><span data-stu-id="404e9-134">Name</span></span></th>
<th><span data-ttu-id="404e9-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="404e9-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="404e9-136"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-137">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="404e9-137">Start date/time for the time range.</span></span> <span data-ttu-id="404e9-138">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="404e9-138">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="404e9-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="404e9-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="404e9-140">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="404e9-140">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="404e9-141">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="404e9-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="404e9-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="404e9-142">7/7/2012</span></span></p>
<p><span data-ttu-id="404e9-143">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="404e9-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="404e9-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="404e9-144">7/3/2012</span></span></p>
<p><span data-ttu-id="404e9-145">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="404e9-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-146"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-147">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="404e9-147">End date/time for the time range.</span></span> <span data-ttu-id="404e9-148">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="404e9-148">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="404e9-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="404e9-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="404e9-150">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="404e9-150">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="404e9-151">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="404e9-151">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="404e9-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="404e9-152">7/7/2012</span></span></p>
<p><span data-ttu-id="404e9-153">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="404e9-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="404e9-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="404e9-154">7/3/2012</span></span></p>
<p><span data-ttu-id="404e9-155">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="404e9-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="404e9-156"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-157">Tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="404e9-157">Type of activity.</span></span> <span data-ttu-id="404e9-158">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="404e9-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="404e9-159">Tutti</span><span class="sxs-lookup"><span data-stu-id="404e9-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="404e9-160">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="404e9-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="404e9-161">Conferenza</span><span class="sxs-lookup"><span data-stu-id="404e9-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-162"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-163">In questo momento l'unica opzione disponibile è <strong>[tutti]</strong>.</span><span class="sxs-lookup"><span data-stu-id="404e9-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="404e9-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-165">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="404e9-165">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="404e9-166">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="404e9-166">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="404e9-167">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="404e9-167">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-168"><strong>Categoria</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-169">Tipo di errore sperimentato.</span><span class="sxs-lookup"><span data-stu-id="404e9-169">Type of failure experienced.</span></span> <span data-ttu-id="404e9-170">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="404e9-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="404e9-171">Errore sia previsto che imprevisto</span><span class="sxs-lookup"><span data-stu-id="404e9-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="404e9-172">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="404e9-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="404e9-173">Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="404e9-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="404e9-174">Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="404e9-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="404e9-175">Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="404e9-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="404e9-176">Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="404e9-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="404e9-177">Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="404e9-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="404e9-178"><strong>Codice di risposta</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-179">Codice di risposta SIP inviato quando la conferenza non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="404e9-179">SIP response code sent when the conference failed.</span></span> <span data-ttu-id="404e9-180">Immettere l'intero codice di risposta, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="404e9-180">Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="404e9-181">400</span><span class="sxs-lookup"><span data-stu-id="404e9-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-182"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-183">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="404e9-183">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="404e9-184">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="404e9-184">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="404e9-185">Metriche</span><span class="sxs-lookup"><span data-stu-id="404e9-185">Metrics</span></span>

<span data-ttu-id="404e9-186">Nella tabella seguente sono elencate le informazioni fornite nel report errori principali.</span><span class="sxs-lookup"><span data-stu-id="404e9-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="404e9-187">Principali errori di report sulle metriche</span><span class="sxs-lookup"><span data-stu-id="404e9-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="404e9-188">Nome</span><span class="sxs-lookup"><span data-stu-id="404e9-188">Name</span></span></th>
<th><span data-ttu-id="404e9-189">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="404e9-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="404e9-190">Descrizione</span><span class="sxs-lookup"><span data-stu-id="404e9-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="404e9-191"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-192">Sì</span><span class="sxs-lookup"><span data-stu-id="404e9-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="404e9-193">Rango relativo in base al numero di sessioni segnalate.</span><span class="sxs-lookup"><span data-stu-id="404e9-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-194"><strong>Sessioni segnalate</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-195">Sì</span><span class="sxs-lookup"><span data-stu-id="404e9-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="404e9-196">Numero totale di sessioni non riuscite in base all'ID di diagnostica e al codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="404e9-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="404e9-197"><strong>Utenti interessati</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-198">Sì</span><span class="sxs-lookup"><span data-stu-id="404e9-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="404e9-199">Numero totale di utenti interessati dalla sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="404e9-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="404e9-200"><strong>Informazioni sull'errore</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-201">No</span><span class="sxs-lookup"><span data-stu-id="404e9-201">No</span></span></p></td>
<td><p><span data-ttu-id="404e9-202">Informazioni dettagliate sull'errore, incluso l'ID di diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="404e9-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="404e9-203"><strong>Tendenza in passato</strong></span><span class="sxs-lookup"><span data-stu-id="404e9-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="404e9-204">No</span><span class="sxs-lookup"><span data-stu-id="404e9-204">No</span></span></p></td>
<td><p><span data-ttu-id="404e9-205">Grafico delle sessioni non riuscite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="404e9-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

