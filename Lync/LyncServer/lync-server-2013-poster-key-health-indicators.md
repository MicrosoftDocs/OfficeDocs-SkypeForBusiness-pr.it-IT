---
title: 'Lync Server 2013: poster: indicatori di integrità chiave'
description: 'Lync Server 2013: poster: indicatori di integrità chiave.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566342"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="6f516-103">Indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f516-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f516-104">_**Ultimo argomento modificato:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="6f516-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="6f516-105">Questo articolo è una compagna degli [indicatori di integrità principali: la base per il mantenimento di un poster integro di Lync Server](https://go.microsoft.com/fwlink/?linkid=391838) , che è possibile scaricare dall'area download.</span><span class="sxs-lookup"><span data-stu-id="6f516-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="6f516-106">![Poster che descrive la risoluzione dei problemi utilizzando i dati di KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster che descrive la risoluzione dei problemi utilizzando i dati di KHI")</span><span class="sxs-lookup"><span data-stu-id="6f516-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="6f516-107">È possibile utilizzare questo poster per informazioni sugli indicatori di integrità chiave (KHIs), sui contatori delle prestazioni con soglie volte a rivelare i problemi relativi all'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="6f516-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="6f516-108">La raccolta dei dati di KHI è in genere il primo passaggio per l'implementazione della metodologia della qualità delle chiamate (CQM), che si concentra sul garantire un'esperienza audio di qualità per gli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="6f516-109">In caso di domande sull'utilizzo di CQM, è possibile inoltrare le proprie domande a cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6f516-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="6f516-110">Nel poster vengono illustrate le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f516-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="6f516-111">Che cosa sono gli indicatori di integrità principali?</span><span class="sxs-lookup"><span data-stu-id="6f516-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="6f516-112">Per raccogliere i dati di KHI</span><span class="sxs-lookup"><span data-stu-id="6f516-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="6f516-113">Flusso di correzione per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="6f516-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="6f516-114">Glossario</span><span class="sxs-lookup"><span data-stu-id="6f516-114">Glossary</span></span>

  - <span data-ttu-id="6f516-115">Server front-end</span><span class="sxs-lookup"><span data-stu-id="6f516-115">Front-end Servers</span></span>

  - <span data-ttu-id="6f516-116">Server SQL back-end</span><span class="sxs-lookup"><span data-stu-id="6f516-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="6f516-117">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="6f516-117">Mediation Servers</span></span>

  - <span data-ttu-id="6f516-118">server perimetrali</span><span class="sxs-lookup"><span data-stu-id="6f516-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="6f516-119">Che cosa sono gli indicatori di integrità principali?</span><span class="sxs-lookup"><span data-stu-id="6f516-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="6f516-120">Gli indicatori di integrità principali sono contatori delle prestazioni con soglie volte a rivelare i problemi relativi all'esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="6f516-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="6f516-121">La raccolta dei dati di KHI è in genere il primo passaggio per l'implementazione della metodologia della qualità delle chiamate (CQM), che si concentra sul garantire un'esperienza audio di qualità per gli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="6f516-122">KHIs vengono utilizzati oltre alle soluzioni di monitoraggio di Lync standard (ad esempio System Center Operations Manager, transazioni sintetiche, Monitoring Server) e non invece di tali soluzioni.</span><span class="sxs-lookup"><span data-stu-id="6f516-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="6f516-123">Raccogliere i contatori delle prestazioni di KHI e popolare il foglio di calcolo di KHI che accompagna la guida alla rete per produrre una scorecard che consenta di determinare l'integrità del server di una distribuzione di Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="6f516-124">Una volta popolata, viene fornita una guida per la riparazione dell'ambiente e per informazioni aggiuntive su altre parti interessate.</span><span class="sxs-lookup"><span data-stu-id="6f516-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="6f516-125">Valutare KHIs su base mensile e inserirli nei processi operativi in continua distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6f516-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="6f516-126">Scaricare la [Guida alla rete di Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) per visualizzare l'elenco completo di KHIs e per ottenere i fogli di calcolo correlati.</span><span class="sxs-lookup"><span data-stu-id="6f516-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="6f516-127">Per raccogliere i dati di KHI</span><span class="sxs-lookup"><span data-stu-id="6f516-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="6f516-128">Eseguire lo script KHI incluso nella Guida alla rete di Lync Server in ogni server Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="6f516-129">In questo modo verrà creato un agente di raccolta dati all'interno di performance monitor e il nome KHI.</span><span class="sxs-lookup"><span data-stu-id="6f516-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="6f516-130">Per impostazione predefinita, i dati verranno sottoposti a polling ogni 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="6f516-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="6f516-131">Prima dell'inizio della giornata lavorativa della società, passare a ogni server Lync e avviare l'agente di raccolta dati di KHI.</span><span class="sxs-lookup"><span data-stu-id="6f516-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="6f516-132">Alla fine di quel giorno, arrestare l'agente di raccolta dati di KHI e copiare i dati in una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="6f516-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="6f516-133">Dopo aver utilizzato Performance Monitor per compilare il foglio di calcolo di KHI incluso nel download della Guida alla rete di Lync Server, confrontare i risultati con gli obiettivi consigliati.</span><span class="sxs-lookup"><span data-stu-id="6f516-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="6f516-134">Flusso di correzione per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="6f516-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="6f516-135">Per ogni server dell'implementazione di Lync, iniziare verificando che le prestazioni del sistema e dell'integrità del componente del server siano pari o superiori al livello desiderato.</span><span class="sxs-lookup"><span data-stu-id="6f516-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="6f516-136">Solo dopo, è necessario esaminare gli indicatori relativi al ruolo del server nell'implementazione complessiva di Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="6f516-137">Iniziare raccogliendo i dati sulle prestazioni di KHI per tutti i server.</span><span class="sxs-lookup"><span data-stu-id="6f516-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="6f516-138">Per ogni ruolo di sistema (dettagli descritti più avanti in questo documento) determinare se i componenti di sistema di base soddisfano le destinazioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="6f516-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="6f516-139">In caso contrario, correggere le prestazioni del sistema e quindi raccogliere di nuovo i dati di KHI e garantire l'integrità del sistema prima di esaminare le metriche specifiche del ruolo del server nell'implementazione di Lync.</span><span class="sxs-lookup"><span data-stu-id="6f516-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="6f516-140">L'integrità dei componenti per tutti i ruoli è definita come segue:</span><span class="sxs-lookup"><span data-stu-id="6f516-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="6f516-141">Utilizzo della CPU \< 80%</span><span class="sxs-lookup"><span data-stu-id="6f516-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="6f516-142">AVG. Disk Write \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="6f516-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="6f516-143">AVG. Disk Read \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="6f516-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="6f516-144">Memoria disponibile \> 20% System Total MB</span><span class="sxs-lookup"><span data-stu-id="6f516-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="6f516-145">Lunghezza coda di rete \< 2</span><span class="sxs-lookup"><span data-stu-id="6f516-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="6f516-146">Pacchetti scartati (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="6f516-147">Glossario</span><span class="sxs-lookup"><span data-stu-id="6f516-147">Glossary</span></span>

<span data-ttu-id="6f516-148">In questo poster vengono utilizzati i termini e gli acronimi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f516-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="6f516-149">Come MCU = unità di controllo a più punti di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="6f516-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="6f516-150">MCU AV = MCU audio/video</span><span class="sxs-lookup"><span data-stu-id="6f516-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="6f516-151">MCU IM = MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="6f516-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="6f516-152">UCWA = API Web per le comunicazioni unificate</span><span class="sxs-lookup"><span data-stu-id="6f516-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="6f516-153">AV Edge = attraversamento di audio/video tramite Edge</span><span class="sxs-lookup"><span data-stu-id="6f516-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="6f516-154">AV auth = autenticazione audio/video</span><span class="sxs-lookup"><span data-stu-id="6f516-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="6f516-155">SIP stack = contiene l'implementazione SIP di base di Lync</span><span class="sxs-lookup"><span data-stu-id="6f516-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="6f516-156">Proxy di dati = utilizzato per le conferenze Edge</span><span class="sxs-lookup"><span data-stu-id="6f516-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="6f516-157">LySS = servizio di archiviazione di Lync</span><span class="sxs-lookup"><span data-stu-id="6f516-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="6f516-158">Server front-end</span><span class="sxs-lookup"><span data-stu-id="6f516-158">Front-end Servers</span></span>

<span data-ttu-id="6f516-159">Le seguenti destinazioni KHI consigliate sono specifiche per i server front-end oltre all'integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="6f516-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f516-160">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="6f516-160">Functional area</span></span></th>
<th><span data-ttu-id="6f516-161">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="6f516-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f516-162">MCU AS/AV/IM</span><span class="sxs-lookup"><span data-stu-id="6f516-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="6f516-163">Stato di integrità MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="6f516-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f516-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="6f516-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="6f516-165">Timeout di espansione della lista di distribuzione- &lt; 0</span><span class="sxs-lookup"><span data-stu-id="6f516-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="6f516-166">Errori di ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="6f516-167">Errori LIS = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="6f516-168">Errori di autenticazione &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="6f516-169">Richieste di ASP.NET v4 rifiutate = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f516-170">Stack SIP</span><span class="sxs-lookup"><span data-stu-id="6f516-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="6f516-171">Elaborazione dei messaggi in arrivo &lt; 1 secondo</span><span class="sxs-lookup"><span data-stu-id="6f516-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="6f516-172">Risposte in ingresso rilasciate &lt; 1/sec le richieste in arrivo sono state perse &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="6f516-173">Latenza coda &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="6f516-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="6f516-174">Latenza SPROC &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="6f516-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="6f516-175">Richieste limitate = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="6f516-176">Errori di autenticazione &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="6f516-177">Timeout dei messaggi in arrivo &lt; 2</span><span class="sxs-lookup"><span data-stu-id="6f516-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="6f516-178">AVG. messaggio in arrivo in attesa &lt; 1 secondo</span><span class="sxs-lookup"><span data-stu-id="6f516-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="6f516-179">Connessioni controllate dal flusso &lt; 2</span><span class="sxs-lookup"><span data-stu-id="6f516-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="6f516-180">Ritardo della coda di AVG. out &lt; 2 sec</span><span class="sxs-lookup"><span data-stu-id="6f516-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f516-181">LySS</span><span class="sxs-lookup"><span data-stu-id="6f516-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="6f516-182">% dello spazio utilizzato dal servizio di archiviazione DB &lt; 80</span><span class="sxs-lookup"><span data-stu-id="6f516-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="6f516-183"># degli errori di replica di replica = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="6f516-184"># degli eventi di perdita di dati = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f516-185">SQL</span><span class="sxs-lookup"><span data-stu-id="6f516-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="6f516-186">Durata della pagina &gt; 300 sec.</span><span class="sxs-lookup"><span data-stu-id="6f516-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="6f516-187">Richieste batch/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="6f516-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="6f516-188">Server SQL back-end</span><span class="sxs-lookup"><span data-stu-id="6f516-188">Backend SQL Servers</span></span>

<span data-ttu-id="6f516-189">Le seguenti destinazioni KHI consigliate sono specifiche per i server SQL oltre che per l'integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="6f516-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f516-190">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="6f516-190">Functional area</span></span></th>
<th><span data-ttu-id="6f516-191">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="6f516-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f516-192">SQL</span><span class="sxs-lookup"><span data-stu-id="6f516-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="6f516-193">Durata della pagina &gt; 300 sec.</span><span class="sxs-lookup"><span data-stu-id="6f516-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="6f516-194">Richieste batch/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="6f516-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="6f516-195">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="6f516-195">Mediation Servers</span></span>

<span data-ttu-id="6f516-196">Le seguenti destinazioni KHI consigliate sono specifiche per i Mediation Server oltre all'integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="6f516-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f516-197">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="6f516-197">Functional area</span></span></th>
<th><span data-ttu-id="6f516-198">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="6f516-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f516-199">Servizio Mediation Server</span><span class="sxs-lookup"><span data-stu-id="6f516-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="6f516-200">Indice di errore di chiamata di carico = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="6f516-201">Chiamate non riuscite a causa del proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="6f516-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="6f516-202">Chiamate non riuscite a causa del gateway &lt; 10</span><span class="sxs-lookup"><span data-stu-id="6f516-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="6f516-203">Chiamate (dentro o fuori) rifiutate = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="6f516-204">Candidati ai media mancanti = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="6f516-205">Errori di controllo della connettività multimediale = 0</span><span class="sxs-lookup"><span data-stu-id="6f516-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="6f516-206">server perimetrali</span><span class="sxs-lookup"><span data-stu-id="6f516-206">Edge Servers</span></span>

<span data-ttu-id="6f516-207">Le seguenti destinazioni KHI consigliate sono specifiche per i server perimetrali oltre all'integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="6f516-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f516-208">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="6f516-208">Functional area</span></span></th>
<th><span data-ttu-id="6f516-209">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="6f516-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f516-210">Autenticazione AV</span><span class="sxs-lookup"><span data-stu-id="6f516-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="6f516-211">Richieste non valide &lt; 20/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f516-212">AV Edge</span><span class="sxs-lookup"><span data-stu-id="6f516-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="6f516-213">Auth. Failures &lt; 20/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="6f516-214">Errori di allocazione &lt; 20/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="6f516-215">Pacchetti rilasciati &lt; 300/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f516-216">Proxy di dati</span><span class="sxs-lookup"><span data-stu-id="6f516-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="6f516-217">Connessioni server limitate &lt; 3</span><span class="sxs-lookup"><span data-stu-id="6f516-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="6f516-218">Il sistema ha la limitazione &lt; 1</span><span class="sxs-lookup"><span data-stu-id="6f516-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f516-219">Stack SIP</span><span class="sxs-lookup"><span data-stu-id="6f516-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="6f516-220">Connessioni su limite eliminato &lt; 1</span><span class="sxs-lookup"><span data-stu-id="6f516-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="6f516-221">Invia scaduta &lt; 10</span><span class="sxs-lookup"><span data-stu-id="6f516-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="6f516-222">Connessioni controllate dal flusso &lt; 100</span><span class="sxs-lookup"><span data-stu-id="6f516-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="6f516-223">Richieste in ingresso interrotte &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="6f516-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="6f516-224">Elaborazione media dei messaggi &lt; 3 sec</span><span class="sxs-lookup"><span data-stu-id="6f516-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f516-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f516-225">See Also</span></span>


[<span data-ttu-id="6f516-226">Guida alla rete di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f516-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="6f516-227">Indicatori di integrità chiave: la base per la gestione dei server Lync integri</span><span class="sxs-lookup"><span data-stu-id="6f516-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="6f516-228">Metodologia qualità chiamata Lync</span><span class="sxs-lookup"><span data-stu-id="6f516-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

