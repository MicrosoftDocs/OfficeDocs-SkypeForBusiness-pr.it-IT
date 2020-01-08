---
title: 'Lync Server 2013: report di distribuzione degli errori'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="02b9c-102">Report di distribuzione dell'errore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02b9c-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b9c-103">_**Argomento Ultima modifica:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="02b9c-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="02b9c-104">Il rapporto di distribuzione errori non è in grado di classificare le sessioni non riuscite nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="02b9c-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="02b9c-105">Principali motivi diagnostici</span><span class="sxs-lookup"><span data-stu-id="02b9c-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="02b9c-106">Modalità top</span><span class="sxs-lookup"><span data-stu-id="02b9c-106">Top modalities</span></span>

  - <span data-ttu-id="02b9c-107">Pool principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-107">Top pools</span></span>

  - <span data-ttu-id="02b9c-108">Origini principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-108">Top sources</span></span>

  - <span data-ttu-id="02b9c-109">Componenti principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-109">Top components</span></span>

  - <span data-ttu-id="02b9c-110">Inizio degli utenti</span><span class="sxs-lookup"><span data-stu-id="02b9c-110">Top from users</span></span>

  - <span data-ttu-id="02b9c-111">Inizio per gli utenti</span><span class="sxs-lookup"><span data-stu-id="02b9c-111">Top to users</span></span>

  - <span data-ttu-id="02b9c-112">Inizio da agenti utente</span><span class="sxs-lookup"><span data-stu-id="02b9c-112">Top from user agents</span></span>

<span data-ttu-id="02b9c-113">Puoi usare queste categorie per determinare esattamente dove si verifica un problema e, in alcuni casi, perché il problema si verifica.</span><span class="sxs-lookup"><span data-stu-id="02b9c-113">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="02b9c-114">Ad esempio, si supponga di aver registrato 242 sessioni audio/video non riuscite durante un giorno specifico.</span><span class="sxs-lookup"><span data-stu-id="02b9c-114">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="02b9c-115">Se si esamina il report di distribuzione degli errori, potrebbe essere necessario che 237 di tali sessioni non riuscite sia avvenuto nel pool di Dublino.</span><span class="sxs-lookup"><span data-stu-id="02b9c-115">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="02b9c-116">Questo ti offre un buon punto di partenza per il rilevamento e la diagnosi delle cause che stanno dietro a questi errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-116">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="02b9c-117">Se si fa clic sul pool Dublin nella categoria **Top pools** , verrà visualizzato un report di distribuzione di errore solo per il pool.</span><span class="sxs-lookup"><span data-stu-id="02b9c-117">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="02b9c-118">È quindi possibile iniziare ad analizzare il motivo per cui il pool di Dublino stava vivendo tante difficoltà.</span><span class="sxs-lookup"><span data-stu-id="02b9c-118">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="02b9c-119">Visualizzazione del report di distribuzione degli errori</span><span class="sxs-lookup"><span data-stu-id="02b9c-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="02b9c-120">È possibile accedere al report di distribuzione dell'errore da uno dei report seguenti facendo clic sul **volume di errore previsto** o sulla metrica di **volume errore imprevisto** :</span><span class="sxs-lookup"><span data-stu-id="02b9c-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="02b9c-121">Report errori principali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02b9c-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="02b9c-122">Report di diagnostica per conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02b9c-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="02b9c-123">Report di diagnostica attività peer-to-peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02b9c-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="02b9c-124">Nel report distribuzione errori è possibile fare clic su una delle metriche seguenti per visualizzare il [report elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md):</span><span class="sxs-lookup"><span data-stu-id="02b9c-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="02b9c-125">Principali motivi diagnostici (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="02b9c-126">Modalità top (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="02b9c-127">Pool principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="02b9c-128">Origini principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="02b9c-129">Componenti principali (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-129">Top components (sessions)</span></span>

  - <span data-ttu-id="02b9c-130">Inizio da utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="02b9c-131">Inizio per gli utenti (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="02b9c-132">Inizio da agenti utente (sessioni)</span><span class="sxs-lookup"><span data-stu-id="02b9c-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="02b9c-133">Uso del report distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="02b9c-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="02b9c-134">A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dati visualizzati nel report di distribuzione dell'errore vengano troncati durante la visualizzazione sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="02b9c-134">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="02b9c-135">Questo vale soprattutto per le metriche, ad esempio gli agenti utente, che possono avere etichette molto lunghe.</span><span class="sxs-lookup"><span data-stu-id="02b9c-135">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="02b9c-136">Ad esempio, un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" potrebbe essere visualizzato solo parzialmente sullo schermo:</span><span class="sxs-lookup"><span data-stu-id="02b9c-136">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="02b9c-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft ly...</span><span class="sxs-lookup"><span data-stu-id="02b9c-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="02b9c-138">Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente tenendo il mouse sopra il valore troncato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="02b9c-139">Una metrica interessante in cui è possibile applicare il filtro usando il report distribuzione errori è ID diagnostica.</span><span class="sxs-lookup"><span data-stu-id="02b9c-139">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="02b9c-140">Se viene visualizzato lo stesso ID diagnostica in altri report, è possibile filtrare tale ID nel report distribuzione errori e ottenere un'analisi dettagliata precisamente dove e con quale frequenza è stato segnalato l'ID durante una sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="02b9c-140">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="02b9c-141">Filtri</span><span class="sxs-lookup"><span data-stu-id="02b9c-141">Filters</span></span>

<span data-ttu-id="02b9c-142">I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi.</span><span class="sxs-lookup"><span data-stu-id="02b9c-142">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="02b9c-143">Ad esempio, il report di distribuzione non riuscito consente di filtrare in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o l'ID di diagnostica che ha accompagnato ogni sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="02b9c-143">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="02b9c-144">Nella tabella seguente sono elencati i filtri che è possibile usare con il report di distribuzione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="02b9c-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="02b9c-145">Filtri dei report di distribuzione errori</span><span class="sxs-lookup"><span data-stu-id="02b9c-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-146">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-146">Name</span></span></th>
<th><span data-ttu-id="02b9c-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-148"><strong>Da</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-149">Data/ora di inizio per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="02b9c-149">Start date/time for the time range.</span></span> <span data-ttu-id="02b9c-150">Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02b9c-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="02b9c-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="02b9c-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="02b9c-152">Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="02b9c-153">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="02b9c-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="02b9c-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="02b9c-154">7/7/2012</span></span></p>
<p><span data-ttu-id="02b9c-155">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="02b9c-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="02b9c-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="02b9c-156">7/3/2012</span></span></p>
<p><span data-ttu-id="02b9c-157">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-158"><strong>A</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-159">Data/ora di fine per l'intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="02b9c-159">End date/time for the time range.</span></span> <span data-ttu-id="02b9c-160">Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02b9c-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="02b9c-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="02b9c-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="02b9c-162">Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="02b9c-163">Per visualizzare i dati per giorno, immettere solo la data:</span><span class="sxs-lookup"><span data-stu-id="02b9c-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="02b9c-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="02b9c-164">7/7/2012</span></span></p>
<p><span data-ttu-id="02b9c-165">Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</span><span class="sxs-lookup"><span data-stu-id="02b9c-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="02b9c-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="02b9c-166">7/3/2012</span></span></p>
<p><span data-ttu-id="02b9c-167">Le settimane si eseguono sempre da domenica a sabato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-169">Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="02b9c-169">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="02b9c-170">È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool.</span><span class="sxs-lookup"><span data-stu-id="02b9c-170">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="02b9c-171">Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</span><span class="sxs-lookup"><span data-stu-id="02b9c-171">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-172"><strong>Tipo di attività</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-173">Tipo di attività su cui applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="02b9c-173">Type of activity to filter on.</span></span> <span data-ttu-id="02b9c-174">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02b9c-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="02b9c-175">Tutti</span><span class="sxs-lookup"><span data-stu-id="02b9c-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="02b9c-176">Peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="02b9c-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="02b9c-177">Conferenza</span><span class="sxs-lookup"><span data-stu-id="02b9c-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-178"><strong>Categoria sessione</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-179">Indica se l'attività in questione è riuscita o meno.</span><span class="sxs-lookup"><span data-stu-id="02b9c-179">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="02b9c-180">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02b9c-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="02b9c-181">Tutti</span><span class="sxs-lookup"><span data-stu-id="02b9c-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="02b9c-182">Successo</span><span class="sxs-lookup"><span data-stu-id="02b9c-182">Success</span></span></p></li>
<li><p><span data-ttu-id="02b9c-183">Errore previsto</span><span class="sxs-lookup"><span data-stu-id="02b9c-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="02b9c-184">Errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="02b9c-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="02b9c-185">Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi.</span><span class="sxs-lookup"><span data-stu-id="02b9c-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="02b9c-186">Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="02b9c-187">Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro.</span><span class="sxs-lookup"><span data-stu-id="02b9c-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="02b9c-188">Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa.</span><span class="sxs-lookup"><span data-stu-id="02b9c-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="02b9c-189">Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</span><span class="sxs-lookup"><span data-stu-id="02b9c-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-190"><strong>ID diagnostica</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-191">Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-191">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="02b9c-192">Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</span><span class="sxs-lookup"><span data-stu-id="02b9c-192">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="02b9c-193">Metriche per i principali motivi diagnostici</span><span class="sxs-lookup"><span data-stu-id="02b9c-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="02b9c-194">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base all'ID di diagnostica segnalato più di frequente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="02b9c-195">Metriche per i principali motivi diagnostici</span><span class="sxs-lookup"><span data-stu-id="02b9c-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-196">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-196">Name</span></span></th>
<th><span data-ttu-id="02b9c-197">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-199"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-200">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-200">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-201">Classificazione relativa delle sessioni non riuscite in base agli ID di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="02b9c-201">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="02b9c-202">L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione degli errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-202">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-203"><strong>Principali motivi diagnostici</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-204">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-204">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-205">ID di diagnostica generato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-206"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-207">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-207">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-208">Numero totale di sessioni non riuscite in cui è stato generato l'ID di diagnostica specificato.</span><span class="sxs-lookup"><span data-stu-id="02b9c-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="02b9c-209">Metriche per le modalità top</span><span class="sxs-lookup"><span data-stu-id="02b9c-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="02b9c-210">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base alle modalità di sessione che hanno registrato più errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="02b9c-211">Metriche per le modalità top</span><span class="sxs-lookup"><span data-stu-id="02b9c-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-212">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-212">Name</span></span></th>
<th><span data-ttu-id="02b9c-213">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-214">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-215"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-216">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-216">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-217">Classificazione relativa basata sulla sessione non riuscita in base al tipo di sessione, ad esempio una conferenza audio/video o una sessione di trasferimento di file peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="02b9c-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-218"><strong>Modalità top</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-219">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-219">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-220">Tipo di sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-221"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-222">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-222">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-223">Numero totale di sessioni non riuscite che coinvolgono la modalità specificata.</span><span class="sxs-lookup"><span data-stu-id="02b9c-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="02b9c-224">Metriche per i pool principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-224">Metrics for Top Pools</span></span>

<span data-ttu-id="02b9c-225">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai pool che hanno sperimentato più errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="02b9c-226">Metriche per i pool principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-227">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-227">Name</span></span></th>
<th><span data-ttu-id="02b9c-228">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-229">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-230"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-231">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-231">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-232">Classificazione relativa delle sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-233"><strong>Pool principali</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-234">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-234">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-235">Nome del pool di registrazione o del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="02b9c-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-236"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-237">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-237">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-238">Numero totale di sessioni non riuscite per ogni pool di registrar o Edge Server.</span><span class="sxs-lookup"><span data-stu-id="02b9c-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="02b9c-239">Metriche per le origini principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-239">Metrics for Top Sources</span></span>

<span data-ttu-id="02b9c-240">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai computer con più errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="02b9c-241">Metriche per le origini principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-242">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-242">Name</span></span></th>
<th><span data-ttu-id="02b9c-243">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-244">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-245"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-246">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-246">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-247">Classificazione relativa delle sessioni non riuscite per ogni computer.</span><span class="sxs-lookup"><span data-stu-id="02b9c-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-248"><strong>Origini principali</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-249">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-249">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-250">Nome del computer coinvolto nella sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="02b9c-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-251"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-252">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-252">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-253">Numero totale di sessioni non riuscite per computer.</span><span class="sxs-lookup"><span data-stu-id="02b9c-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="02b9c-254">Metriche per i componenti principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-254">Metrics for Top Components</span></span>

<span data-ttu-id="02b9c-255">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai componenti di Microsoft Lync Server 2010 che hanno sperimentato la maggior parte degli errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="02b9c-256">Metriche per i componenti principali</span><span class="sxs-lookup"><span data-stu-id="02b9c-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-257">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-257">Name</span></span></th>
<th><span data-ttu-id="02b9c-258">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-259">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-260"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-261">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-261">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-262">Classificazione relativa delle sessioni non riuscite in base al componente Lync Server 2010 (ad esempio, ExumRouting, GroupChat o MediationServer).</span><span class="sxs-lookup"><span data-stu-id="02b9c-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-263"><strong>Componenti principali</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-264">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-264">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-265">Nome del componente coinvolto nella sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="02b9c-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-266"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-267">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-267">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-268">Numero totale di sessioni non riuscite per componente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="02b9c-269">Metriche per l'inizio degli utenti</span><span class="sxs-lookup"><span data-stu-id="02b9c-269">Metrics for Top From Users</span></span>

<span data-ttu-id="02b9c-270">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato la maggior parte degli errori quando hanno tentato di chiamare un altro utente (detto "da" utenti).</span><span class="sxs-lookup"><span data-stu-id="02b9c-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="02b9c-271">Metriche per l'inizio degli utenti</span><span class="sxs-lookup"><span data-stu-id="02b9c-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-272">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-272">Name</span></span></th>
<th><span data-ttu-id="02b9c-273">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-274">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-275"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-276">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-276">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-277">Classificazione relativa delle sessioni non riuscite in base all'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-278"><strong>Inizio degli utenti</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-279">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-279">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-280">Indirizzo SIP dell'utente invitato a partecipare alla sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-281"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-282">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-282">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-283">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="02b9c-284">Metriche per i primi utenti</span><span class="sxs-lookup"><span data-stu-id="02b9c-284">Metrics for Top To Users</span></span>

<span data-ttu-id="02b9c-285">Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato più errori quando un altro utente ha provato a chiamarli (detti "a" utenti).</span><span class="sxs-lookup"><span data-stu-id="02b9c-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-286">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-286">Name</span></span></th>
<th><span data-ttu-id="02b9c-287">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-288">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-289"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-290">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-290">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-291">Classificazione relativa delle sessioni non riuscite in base all'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-292"><strong>Inizio per gli utenti</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-293">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-293">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-294">Indirizzo SIP dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-295"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-296">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-296">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-297">Numero totale di sessioni non riuscite per utente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="02b9c-298">Metriche per gli agenti Top User</span><span class="sxs-lookup"><span data-stu-id="02b9c-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="02b9c-299">La tabella seguente elenca le informazioni fornite nel report di distribuzione dell'errore in base al software dell'endpoint che ha riscontrato la maggior parte degli errori.</span><span class="sxs-lookup"><span data-stu-id="02b9c-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="02b9c-300">Metriche per gli agenti Top User</span><span class="sxs-lookup"><span data-stu-id="02b9c-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02b9c-301">Nome</span><span class="sxs-lookup"><span data-stu-id="02b9c-301">Name</span></span></th>
<th><span data-ttu-id="02b9c-302">Si può ordinare su questo elemento?</span><span class="sxs-lookup"><span data-stu-id="02b9c-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="02b9c-303">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02b9c-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-304"><strong>Rango</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-305">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-305">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-306">Classificazione relativa delle sessioni non riuscite in base all'agente utente (software) coinvolto nella sessione.</span><span class="sxs-lookup"><span data-stu-id="02b9c-306">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="02b9c-307">Ad esempio: RTCC/4.0.0.0 routing in ingresso/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="02b9c-307">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02b9c-308"><strong>Agenti utente principali</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-309">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-309">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-310">Nome dell'agente utente coinvolto nella sessione non riuscita.</span><span class="sxs-lookup"><span data-stu-id="02b9c-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02b9c-311"><strong>Sessioni</strong></span><span class="sxs-lookup"><span data-stu-id="02b9c-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="02b9c-312">No</span><span class="sxs-lookup"><span data-stu-id="02b9c-312">No</span></span></p></td>
<td><p><span data-ttu-id="02b9c-313">Numero totale di sessioni non riuscite per agente utente.</span><span class="sxs-lookup"><span data-stu-id="02b9c-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

