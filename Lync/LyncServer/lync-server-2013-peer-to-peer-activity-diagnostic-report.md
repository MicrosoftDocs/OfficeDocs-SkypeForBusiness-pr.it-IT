---
title: 'Lync Server 2013: report di diagnostica attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="640e5-102">Report di diagnostica attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640e5-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="640e5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="640e5-104">Il report di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo e negativo delle sessioni di comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="640e5-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="640e5-105">Si noti che Microsoft Lync Server 2013 distingue diversi tipi di errore:</span><span class="sxs-lookup"><span data-stu-id="640e5-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="640e5-106">**Errore previsto**.</span><span class="sxs-lookup"><span data-stu-id="640e5-106">**Expected failure**.</span></span> <span data-ttu-id="640e5-107">Un errore previsto è in genere un errore solo in senso più tecnico.</span><span class="sxs-lookup"><span data-stu-id="640e5-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="640e5-108">Ad esempio, supponiamo che tu chiami qualcuno, ma che sia fuori sede e che non sia in grado di rispondere al telefono.</span><span class="sxs-lookup"><span data-stu-id="640e5-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="640e5-109">Dato che la chiamata non è stata risolta, la chiamata è tecnicamente considerata un errore.</span><span class="sxs-lookup"><span data-stu-id="640e5-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="640e5-110">In compenso, si è verificato un errore previsto: Microsoft Lync Server 2013 non si aspetta di rispondere al telefono se non si è disponibili per rispondere al telefono.</span><span class="sxs-lookup"><span data-stu-id="640e5-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="640e5-111">Allo stesso modo, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline oppure si accede solo a un telefono che non supporta la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="640e5-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="640e5-112">**Errore imprevisto**.</span><span class="sxs-lookup"><span data-stu-id="640e5-112">**Unexpected failure**.</span></span> <span data-ttu-id="640e5-113">Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi.</span><span class="sxs-lookup"><span data-stu-id="640e5-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="640e5-114">Ad esempio, supponiamo che tu chiami qualcuno e che la persona sia disponibile per rispondere alla chiamata; Tuttavia, quando Lync Server 2013 prova a instradare la chiamata alla segreteria telefonica, la chiamata non riesce perché la connettività alla messaggistica unificata di Exchange è stata persa.</span><span class="sxs-lookup"><span data-stu-id="640e5-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="640e5-115">Si tratta di un errore imprevisto: ci si aspetterebbe che le chiamate vengano sempre indirizzate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="640e5-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="640e5-116">Come regola generale, gli errori imprevisti sono errori reali: si tratta di problemi che probabilmente non possono essere risolti tramite l'istruzione degli utenti o misure simili.</span><span class="sxs-lookup"><span data-stu-id="640e5-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="640e5-117">Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="640e5-117">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="640e5-118">Nella figura precedente, ad esempio, sono presenti i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="640e5-118">For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640e5-119">Successi</span><span class="sxs-lookup"><span data-stu-id="640e5-119">Successes</span></span></th>
<th><span data-ttu-id="640e5-120">Errori previsti</span><span class="sxs-lookup"><span data-stu-id="640e5-120">Expected failures</span></span></th>
<th><span data-ttu-id="640e5-121">Errori imprevisti</span><span class="sxs-lookup"><span data-stu-id="640e5-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="640e5-122">Totale sessioni</span><span class="sxs-lookup"><span data-stu-id="640e5-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640e5-123">2024</span><span class="sxs-lookup"><span data-stu-id="640e5-123">2024</span></span></p></td>
<td><p><span data-ttu-id="640e5-124">469</span><span class="sxs-lookup"><span data-stu-id="640e5-124">469</span></span></p></td>
<td><p><span data-ttu-id="640e5-125">16</span><span class="sxs-lookup"><span data-stu-id="640e5-125">16</span></span></p></td>
<td><p><span data-ttu-id="640e5-126">2521</span><span class="sxs-lookup"><span data-stu-id="640e5-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="640e5-127">Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni.</span><span class="sxs-lookup"><span data-stu-id="640e5-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="640e5-128">Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito.</span><span class="sxs-lookup"><span data-stu-id="640e5-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="640e5-129">A volte succede quando un prodotto di terze parti introduce un nuovo codice diagnostico sconosciuto a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="640e5-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="640e5-130">In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="640e5-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="640e5-131">Accesso al report di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="640e5-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="640e5-132">Il report di diagnostica peer-to-peer si accede dalla Home page dei report di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="640e5-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="640e5-133">È possibile accedere al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:</span><span class="sxs-lookup"><span data-stu-id="640e5-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="640e5-134">Volume di errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="640e5-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="640e5-135">Volume di errore previsto</span><span class="sxs-lookup"><span data-stu-id="640e5-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="640e5-136">Sfruttare al meglio il rapporto di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="640e5-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="640e5-137">Esistono diversi modi per filtrare il report di diagnostica attività peer-to-peer ma, per impostazione predefinita, le opzioni di filtro sono nascoste dalla visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="640e5-137">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view.</span></span> <span data-ttu-id="640e5-138">Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo in alto a destra della finestra del report.</span><span class="sxs-lookup"><span data-stu-id="640e5-138">To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window.</span></span> <span data-ttu-id="640e5-139">Dopo aver eseguito l'operazione, le opzioni di filtro saranno disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="640e5-139">Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="640e5-140">Filtri</span><span class="sxs-lookup"><span data-stu-id="640e5-140">Filters</span></span>

<span data-ttu-id="640e5-141">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="640e5-141">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="640e5-142">Il report di diagnostica attività peer-to-peer, ad esempio, consente di filtrare in base alla modalità di sessione, ad esempio la messaggistica istantanea, il trasferimento di file o la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="640e5-142">For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing).</span></span> <span data-ttu-id="640e5-143">È anche possibile scegliere la modalità di raggruppamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="640e5-143">You can also choose how data should be grouped.</span></span> <span data-ttu-id="640e5-144">In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.</span><span class="sxs-lookup"><span data-stu-id="640e5-144">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="640e5-145">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica attività peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="640e5-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="640e5-146">Filtri di report di diagnostica attività peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="640e5-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640e5-147">Nome</span><span class="sxs-lookup"><span data-stu-id="640e5-147">Name</span></span></th>
<th><span data-ttu-id="640e5-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640e5-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640e5-149"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-150">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="640e5-150">Start date/time for the time range.</span></span> <span data-ttu-id="640e5-151">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="640e5-151">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="640e5-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="640e5-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="640e5-153">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="640e5-153">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="640e5-154">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="640e5-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="640e5-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="640e5-155">7/7/2012</span></span></p>
<p><span data-ttu-id="640e5-156">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="640e5-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="640e5-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="640e5-157">7/3/2012</span></span></p>
<p><span data-ttu-id="640e5-158">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="640e5-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-159"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-160">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="640e5-160">End date/time for the time range.</span></span> <span data-ttu-id="640e5-161">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="640e5-161">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="640e5-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="640e5-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="640e5-163">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="640e5-163">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="640e5-164">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="640e5-164">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="640e5-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="640e5-165">7/7/2012</span></span></p>
<p><span data-ttu-id="640e5-166">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="640e5-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="640e5-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="640e5-167">7/3/2012</span></span></p>
<p><span data-ttu-id="640e5-168">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="640e5-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-169"><strong>Intervallo</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-170">Intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="640e5-170">Time interval.</span></span> <span data-ttu-id="640e5-171">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="640e5-171">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="640e5-172">Ogni ora (può essere visualizzato un massimo di 25 ore)</span><span class="sxs-lookup"><span data-stu-id="640e5-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="640e5-173">Giornaliera (è possibile visualizzare un massimo di 31 giorni)</span><span class="sxs-lookup"><span data-stu-id="640e5-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="640e5-174">Settimanale (può essere visualizzato un massimo di 12 settimane)</span><span class="sxs-lookup"><span data-stu-id="640e5-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="640e5-175">Mensile (può essere visualizzato un massimo di 12 mesi)</span><span class="sxs-lookup"><span data-stu-id="640e5-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="640e5-176">Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio).</span><span class="sxs-lookup"><span data-stu-id="640e5-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="640e5-177">Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="640e5-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-178"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-179">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="640e5-179">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="640e5-180">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="640e5-180">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="640e5-181">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="640e5-181">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-182"><strong>Modalità</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-183">Indica il tipo di attività di comunicazione che ha avuto luogo.</span><span class="sxs-lookup"><span data-stu-id="640e5-183">Indicates the type of communication activity that took place.</span></span> <span data-ttu-id="640e5-184">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="640e5-184">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="640e5-185">Tutti</span><span class="sxs-lookup"><span data-stu-id="640e5-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="640e5-186">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="640e5-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="640e5-187">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="640e5-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="640e5-188">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="640e5-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="640e5-189">Audio</span><span class="sxs-lookup"><span data-stu-id="640e5-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="640e5-190">Video</span><span class="sxs-lookup"><span data-stu-id="640e5-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="640e5-191">Metriche (per modalità)</span><span class="sxs-lookup"><span data-stu-id="640e5-191">Metrics (per modality)</span></span>

<span data-ttu-id="640e5-192">Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica attività peer-to-peer per ogni modalità.</span><span class="sxs-lookup"><span data-stu-id="640e5-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="640e5-193">Metriche (per modalità)</span><span class="sxs-lookup"><span data-stu-id="640e5-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640e5-194">Nome</span><span class="sxs-lookup"><span data-stu-id="640e5-194">Name</span></span></th>
<th><span data-ttu-id="640e5-195">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="640e5-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="640e5-196">Descrizione</span><span class="sxs-lookup"><span data-stu-id="640e5-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640e5-197"><strong>Volume di successo</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-198">No</span><span class="sxs-lookup"><span data-stu-id="640e5-198">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-199">Numero totale di sessioni peer-to-peer di successo.</span><span class="sxs-lookup"><span data-stu-id="640e5-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-200"><strong>Percentuale di successo</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-201">No</span><span class="sxs-lookup"><span data-stu-id="640e5-201">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-202">Percentuale di sessioni peer-to-peer completate da problemi significativi.</span><span class="sxs-lookup"><span data-stu-id="640e5-202">Percentage of peer-to-peer sessions that completed with significant problems.</span></span> <span data-ttu-id="640e5-203">Calcolata dividendo il volume di successo per il totale delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="640e5-203">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-204"><strong>Volume di errore previsto</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-205">No</span><span class="sxs-lookup"><span data-stu-id="640e5-205">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-206">Numero totale di sessioni in cui &quot;si è&quot; verificato un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="640e5-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="640e5-207">Un errore previsto è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="640e5-207">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="640e5-208">Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="640e5-208">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-209"><strong>Percentuale di errore prevista</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-210">No</span><span class="sxs-lookup"><span data-stu-id="640e5-210">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-211">Percentuale di sessioni peer-to-peer che hanno avuto un errore previsto.</span><span class="sxs-lookup"><span data-stu-id="640e5-211">Percentage of peer-to-peer sessions that experienced an expected error.</span></span> <span data-ttu-id="640e5-212">Calcolata dividendo il volume di errore previsto per le sessioni totali.</span><span class="sxs-lookup"><span data-stu-id="640e5-212">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-213"><strong>Volume di errore imprevisto</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-214">No</span><span class="sxs-lookup"><span data-stu-id="640e5-214">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-215">Numero totale di sessioni in cui &quot;si è&quot; verificato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="640e5-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="640e5-216">Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="640e5-216">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="640e5-217">Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="640e5-217">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="640e5-218">Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="640e5-218">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-219"><strong>Percentuale di errore imprevisto</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-220">No</span><span class="sxs-lookup"><span data-stu-id="640e5-220">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-221">Percentuale di sessioni peer-to-peer che hanno registrato un errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="640e5-221">Percentage of peer-to-peer sessions that experienced an unexpected error.</span></span> <span data-ttu-id="640e5-222">Calcolata dividendo il volume di errore imprevisto per le sessioni totali.</span><span class="sxs-lookup"><span data-stu-id="640e5-222">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-223"><strong>Totale sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="640e5-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="640e5-224">No</span><span class="sxs-lookup"><span data-stu-id="640e5-224">No</span></span></p></td>
<td><p><span data-ttu-id="640e5-225">Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.</span><span class="sxs-lookup"><span data-stu-id="640e5-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

