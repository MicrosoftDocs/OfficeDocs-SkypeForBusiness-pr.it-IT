---
title: 'Lync Server 2013: poster: indicatori di integrità chiave'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="c20da-102">Indicatori di integrità chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c20da-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c20da-103">_**Argomento Ultima modifica:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="c20da-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="c20da-104">Questo articolo è un complemento per gli [indicatori di integrità chiave: la base per il mantenimento](http://go.microsoft.com/fwlink/?linkid=391838) di un poster di Lync Server sani, che è possibile scaricare dall'area download.</span><span class="sxs-lookup"><span data-stu-id="c20da-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="c20da-105">![Poster che descrive la risoluzione dei problemi con KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "poster che descrive la risoluzione dei problemi usando i dati di KHI")</span><span class="sxs-lookup"><span data-stu-id="c20da-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="c20da-106">Puoi usare questo poster per informazioni sugli indicatori di integrità chiave (KHIs), sui contatori delle prestazioni con soglie mirate a rivelare i problemi di esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="c20da-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c20da-107">La raccolta dei dati di KHI è in genere il primo passaggio per implementare la metodologia di qualità delle chiamate (CQM), focalizzata sulla garanzia di un'esperienza audio di qualità per gli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c20da-108">In caso di domande su come usare CQM, è possibile inviare le proprie domande a cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c20da-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="c20da-109">Il poster illustra le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="c20da-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="c20da-110">Che cosa sono gli indicatori di integrità chiave?</span><span class="sxs-lookup"><span data-stu-id="c20da-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="c20da-111">Per raccogliere dati di KHI</span><span class="sxs-lookup"><span data-stu-id="c20da-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="c20da-112">Flusso di correzione per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="c20da-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="c20da-113">Glossario</span><span class="sxs-lookup"><span data-stu-id="c20da-113">Glossary</span></span>

  - <span data-ttu-id="c20da-114">Server front-end</span><span class="sxs-lookup"><span data-stu-id="c20da-114">Front-end Servers</span></span>

  - <span data-ttu-id="c20da-115">Server SQL back-end</span><span class="sxs-lookup"><span data-stu-id="c20da-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="c20da-116">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c20da-116">Mediation Servers</span></span>

  - <span data-ttu-id="c20da-117">Edge Server</span><span class="sxs-lookup"><span data-stu-id="c20da-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="c20da-118">Che cosa sono gli indicatori di integrità chiave?</span><span class="sxs-lookup"><span data-stu-id="c20da-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="c20da-119">Gli indicatori di integrità principali sono contatori delle prestazioni con soglie mirate a rivelare i problemi di esperienza utente.</span><span class="sxs-lookup"><span data-stu-id="c20da-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c20da-120">La raccolta dei dati di KHI è in genere il primo passaggio per implementare la metodologia di qualità delle chiamate (CQM), focalizzata sulla garanzia di un'esperienza audio di qualità per gli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c20da-121">KHIs vengono usati in aggiunta alle soluzioni di monitoraggio di Lync standard (ad esempio System Center Operations Manager, transazioni sintetiche, server di monitoraggio) e non al posto di tali soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c20da-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="c20da-122">Raccogliere i contatori delle prestazioni di KHI e popolare il foglio di calcolo di KHI che accompagna la guida alla rete per produrre una scorecard che consentirà di determinare l'integrità del server di una distribuzione Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="c20da-123">Una volta popolato, ti guida a ripristinare l'ambiente e offre ulteriori informazioni ad altri stakeholder.</span><span class="sxs-lookup"><span data-stu-id="c20da-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="c20da-124">Valuta KHIs su base mensile e incorporali nei processi operativi in corso per qualsiasi distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c20da-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="c20da-125">Scaricare la [Guida alla rete Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) per visualizzare l'elenco completo di KHIs e per ottenere i fogli di calcolo correlati.</span><span class="sxs-lookup"><span data-stu-id="c20da-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="c20da-126">Per raccogliere dati di KHI</span><span class="sxs-lookup"><span data-stu-id="c20da-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="c20da-127">Eseguire lo script KHI incluso nella Guida di rete di Lync Server in ogni server Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="c20da-128">Verrà creato un agente di raccolta dati all'interno di performance monitor e denominarlo KHI.</span><span class="sxs-lookup"><span data-stu-id="c20da-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="c20da-129">Per impostazione predefinita, i dati verranno interrogati ogni 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="c20da-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="c20da-130">Prima dell'inizio del giorno lavorativo della società, accedere a ogni server Lync e avviare l'agente di raccolta dati di KHI.</span><span class="sxs-lookup"><span data-stu-id="c20da-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="c20da-131">Alla fine del giorno, arrestare l'agente di raccolta dati KHI e copiare i dati in una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="c20da-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="c20da-132">Dopo aver usato Performance Monitor per compilare il foglio di calcolo di KHI incluso nel download di Lync Server Networking Guide, confrontare i risultati con le destinazioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="c20da-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="c20da-133">Flusso di correzione per tutti i ruoli del server</span><span class="sxs-lookup"><span data-stu-id="c20da-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="c20da-134">Per ogni server nell'implementazione di Lync, iniziare verificando che le prestazioni di integrità e di sistema del componente del server siano pari o superiori al livello desiderato.</span><span class="sxs-lookup"><span data-stu-id="c20da-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="c20da-135">Solo dopo che dovrebbero essere esaminati gli indicatori relativi al ruolo del server nell'implementazione complessiva di Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="c20da-136">Iniziare raccogliendo i dati sulle prestazioni di KHI per tutti i server.</span><span class="sxs-lookup"><span data-stu-id="c20da-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="c20da-137">Per ogni ruolo di sistema (dettagli descritti più avanti in questo documento) determinare se i componenti di sistema di base soddisfano le destinazioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="c20da-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="c20da-138">In caso contrario, correggere le prestazioni del sistema e quindi riraccogliere i dati di KHI e garantire l'integrità del sistema prima di esaminare le metriche specifiche del ruolo del server nell'implementazione di Lync.</span><span class="sxs-lookup"><span data-stu-id="c20da-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="c20da-139">L'integrità dei componenti per tutti i ruoli è definita come segue:</span><span class="sxs-lookup"><span data-stu-id="c20da-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="c20da-140">Utilizzo della CPU \< 80%</span><span class="sxs-lookup"><span data-stu-id="c20da-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="c20da-141">Media scrittura \< disco 10 ms</span><span class="sxs-lookup"><span data-stu-id="c20da-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="c20da-142">Media Disk Read \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="c20da-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="c20da-143">Memoria \>disponibile 20% System Total MB</span><span class="sxs-lookup"><span data-stu-id="c20da-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="c20da-144">Lunghezza \< coda di rete 2</span><span class="sxs-lookup"><span data-stu-id="c20da-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="c20da-145">Pacchetti scartati (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="c20da-146">Glossario</span><span class="sxs-lookup"><span data-stu-id="c20da-146">Glossary</span></span>

<span data-ttu-id="c20da-147">In questo poster vengono usati i termini e gli acronimi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c20da-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="c20da-148">Come MCU = unità di controllo a più punti di condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="c20da-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="c20da-149">MCU AV = MCU audio/video</span><span class="sxs-lookup"><span data-stu-id="c20da-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="c20da-150">MCU IM = MCU di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="c20da-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="c20da-151">UCWA = API Web per comunicazioni unificate</span><span class="sxs-lookup"><span data-stu-id="c20da-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="c20da-152">AV Edge = attraversamento di audio/video tramite Edge</span><span class="sxs-lookup"><span data-stu-id="c20da-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="c20da-153">AV auth = autenticazione audio/video</span><span class="sxs-lookup"><span data-stu-id="c20da-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="c20da-154">SIP stack = contiene l'implementazione SIP di base di Lync</span><span class="sxs-lookup"><span data-stu-id="c20da-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="c20da-155">Proxy dati = usato per i servizi di conferenza Edge</span><span class="sxs-lookup"><span data-stu-id="c20da-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="c20da-156">LySS = servizio di archiviazione Lync</span><span class="sxs-lookup"><span data-stu-id="c20da-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="c20da-157">Server front-end</span><span class="sxs-lookup"><span data-stu-id="c20da-157">Front-end Servers</span></span>

<span data-ttu-id="c20da-158">Le destinazioni di KHI consigliate seguenti sono specifiche per i server front-end oltre all'integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="c20da-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20da-159">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="c20da-159">Functional area</span></span></th>
<th><span data-ttu-id="c20da-160">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="c20da-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20da-161">MCU AS/AV/IM</span><span class="sxs-lookup"><span data-stu-id="c20da-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c20da-162">Stato &lt;integrità MCU 2</span><span class="sxs-lookup"><span data-stu-id="c20da-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20da-163">Componenti Web</span><span class="sxs-lookup"><span data-stu-id="c20da-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="c20da-164">Timeout degli annunci di espansione della &lt;lista di distribuzione 0</span><span class="sxs-lookup"><span data-stu-id="c20da-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="c20da-165">Errori di ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="c20da-166">Errori LIS = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="c20da-167">Errori &lt; di autenticazione 1/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c20da-168">Richieste di ASP.NET v4 rifiutate = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20da-169">Stack SIP</span><span class="sxs-lookup"><span data-stu-id="c20da-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c20da-170">AVG. elaborazione &lt; del messaggio in arrivo 1 sec</span><span class="sxs-lookup"><span data-stu-id="c20da-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c20da-171">Risposte in arrivo cadute &lt; 1/sec richieste in arrivo perse &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c20da-172">Latenza &lt; della coda 100 ms</span><span class="sxs-lookup"><span data-stu-id="c20da-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c20da-173">Latenza &lt; SPROC 100 ms</span><span class="sxs-lookup"><span data-stu-id="c20da-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c20da-174">Richieste strozzate = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="c20da-175">Errori &lt; di autenticazione 1/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c20da-176">Messaggi in arrivo scaduti &lt; 2</span><span class="sxs-lookup"><span data-stu-id="c20da-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="c20da-177">Media messaggio in arrivo in attesa &lt; 1 sec</span><span class="sxs-lookup"><span data-stu-id="c20da-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c20da-178">Connessioni &lt; controllate in flusso 2</span><span class="sxs-lookup"><span data-stu-id="c20da-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="c20da-179">Ritardo &lt; della coda media fuori 2 sec</span><span class="sxs-lookup"><span data-stu-id="c20da-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20da-180">LySS</span><span class="sxs-lookup"><span data-stu-id="c20da-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="c20da-181">% dello spazio usato dal servizio di archiviazione &lt; dB 80</span><span class="sxs-lookup"><span data-stu-id="c20da-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="c20da-182">#degli errori di replica della replica = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="c20da-183">#di eventi di perdita dei dati = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20da-184">SQL</span><span class="sxs-lookup"><span data-stu-id="c20da-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="c20da-185">Speranza di vita della &gt; pagina 300 sec.</span><span class="sxs-lookup"><span data-stu-id="c20da-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c20da-186">Richieste batch/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="c20da-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="c20da-187">Server SQL back-end</span><span class="sxs-lookup"><span data-stu-id="c20da-187">Backend SQL Servers</span></span>

<span data-ttu-id="c20da-188">Le destinazioni di KHI consigliate seguenti sono specifiche dei server SQL oltre all'integrità del componente di base:</span><span class="sxs-lookup"><span data-stu-id="c20da-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20da-189">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="c20da-189">Functional area</span></span></th>
<th><span data-ttu-id="c20da-190">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="c20da-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20da-191">SQL</span><span class="sxs-lookup"><span data-stu-id="c20da-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="c20da-192">Speranza di vita della &gt; pagina 300 sec.</span><span class="sxs-lookup"><span data-stu-id="c20da-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c20da-193">Richieste batch/sec &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="c20da-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="c20da-194">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c20da-194">Mediation Servers</span></span>

<span data-ttu-id="c20da-195">Le destinazioni di KHI consigliate seguenti sono specifiche di Mediation Server oltre a integrità dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="c20da-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20da-196">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="c20da-196">Functional area</span></span></th>
<th><span data-ttu-id="c20da-197">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="c20da-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20da-198">Servizio Mediation Server</span><span class="sxs-lookup"><span data-stu-id="c20da-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="c20da-199">Carica indice di errore chiamata = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="c20da-200">Chiamate non riuscite a &lt;causa del proxy 10</span><span class="sxs-lookup"><span data-stu-id="c20da-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="c20da-201">Chiamate non riuscite a &lt;causa del gateway 10</span><span class="sxs-lookup"><span data-stu-id="c20da-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="c20da-202">Chiamate (dentro o fuori) rifiutate = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="c20da-203">Candidati multimediali mancanti = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="c20da-204">Errori di verifica della connettività multimediale = 0</span><span class="sxs-lookup"><span data-stu-id="c20da-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="c20da-205">Edge Server</span><span class="sxs-lookup"><span data-stu-id="c20da-205">Edge Servers</span></span>

<span data-ttu-id="c20da-206">Le destinazioni di KHI consigliate seguenti sono specifiche per i server Edge oltre alla salute dei componenti di base:</span><span class="sxs-lookup"><span data-stu-id="c20da-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c20da-207">Area funzionale</span><span class="sxs-lookup"><span data-stu-id="c20da-207">Functional area</span></span></th>
<th><span data-ttu-id="c20da-208">Metriche di destinazione</span><span class="sxs-lookup"><span data-stu-id="c20da-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c20da-209">AV auth</span><span class="sxs-lookup"><span data-stu-id="c20da-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="c20da-210">Richieste &lt; errate 20/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20da-211">AV Edge</span><span class="sxs-lookup"><span data-stu-id="c20da-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="c20da-212">Auth. Failures &lt;20/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c20da-213">Errori &lt;di allocazione 20/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c20da-214">Pacchetti eliminati &lt;300/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c20da-215">Proxy dati</span><span class="sxs-lookup"><span data-stu-id="c20da-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="c20da-216">Connessioni &lt; server strozzate 3</span><span class="sxs-lookup"><span data-stu-id="c20da-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="c20da-217">Il sistema sta strozzando &lt;1</span><span class="sxs-lookup"><span data-stu-id="c20da-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c20da-218">Stack SIP</span><span class="sxs-lookup"><span data-stu-id="c20da-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c20da-219">Connessioni oltre il limite &lt; 1</span><span class="sxs-lookup"><span data-stu-id="c20da-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="c20da-220">Invia scaduta &lt;10</span><span class="sxs-lookup"><span data-stu-id="c20da-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="c20da-221">Connessioni &lt;controllate in flusso 100</span><span class="sxs-lookup"><span data-stu-id="c20da-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="c20da-222">Richieste in arrivo perse &lt; 1/sec</span><span class="sxs-lookup"><span data-stu-id="c20da-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c20da-223">Media elaborazione &lt; del messaggio 3 sec</span><span class="sxs-lookup"><span data-stu-id="c20da-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c20da-224">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c20da-224">See Also</span></span>


[<span data-ttu-id="c20da-225">Guida alla rete di Lync Server</span><span class="sxs-lookup"><span data-stu-id="c20da-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="c20da-226">Indicatori di integrità chiave: la base per il mantenimento di server Lync integri</span><span class="sxs-lookup"><span data-stu-id="c20da-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="c20da-227">Metodologia di qualità delle chiamate di Lync</span><span class="sxs-lookup"><span data-stu-id="c20da-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

