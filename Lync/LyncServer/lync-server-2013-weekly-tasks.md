---
title: 'Lync Server 2013: attività settimanali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da6e0eb7c4377941992dfba9dd11312a12ee29a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="0a86a-102">Attività settimanali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a86a-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a86a-103">_**Ultimo argomento modificato:** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="0a86a-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="0a86a-104">Le attività settimanali sono generalmente correlate alla raccolta e all'analisi di registri e report.</span><span class="sxs-lookup"><span data-stu-id="0a86a-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="0a86a-105">Registri eventi di archiviazione</span><span class="sxs-lookup"><span data-stu-id="0a86a-105">Archive event logs</span></span>

<span data-ttu-id="0a86a-106">Se sono configurati in modo che gli eventi registrati vengano sovrascritti in base alle esigenze, i registri eventi devono essere archiviati ed eliminati a intervalli regolari.</span><span class="sxs-lookup"><span data-stu-id="0a86a-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="0a86a-107">Questa azione è particolarmente importante quando si tratta dei registri di protezione, poiché questi potrebbero essere necessari quando si tenta di individuare eventuali tentativi di violazione della protezione.</span><span class="sxs-lookup"><span data-stu-id="0a86a-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="0a86a-108">L'organizzazione dovrà definire i criteri e le procedure per l'archiviazione dei log.</span><span class="sxs-lookup"><span data-stu-id="0a86a-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="0a86a-109">Creazione di rapporti</span><span class="sxs-lookup"><span data-stu-id="0a86a-109">Create reports</span></span>

<span data-ttu-id="0a86a-110">Creare rapporti di stato per facilitare la pianificazione della capacità, le revisioni di SLA e l'analisi delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0a86a-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="0a86a-111">Utilizzare i dati giornalieri del registro eventi e del monitor di sistema per creare report su disco, memoria e utilizzo della CPU.</span><span class="sxs-lookup"><span data-stu-id="0a86a-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="0a86a-112">Utilizzare System Center Operations Manager per generare i rapporti di disponibilità e di uptime.</span><span class="sxs-lookup"><span data-stu-id="0a86a-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="0a86a-113">L'organizzazione dovrà definire i criteri e le procedure per i report sullo stato.</span><span class="sxs-lookup"><span data-stu-id="0a86a-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="0a86a-114">Rapporti operazioni non consentite</span><span class="sxs-lookup"><span data-stu-id="0a86a-114">Incident reports</span></span>

<span data-ttu-id="0a86a-115">Eseguire un controllo settimanale dei rapporti sugli incidenti dell'organizzazione correlati a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a86a-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="0a86a-116">Questo controllo deve includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-116">This audit should include the following:</span></span>

  - <span data-ttu-id="0a86a-117">Gli incidenti principali generati, risolti e in sospeso.</span><span class="sxs-lookup"><span data-stu-id="0a86a-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="0a86a-118">Soluzioni per gli incidenti non risolti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="0a86a-119">Aggiornamento di report per includere nuovi ticket di problemi.</span><span class="sxs-lookup"><span data-stu-id="0a86a-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="0a86a-120">Aggiornamento di un archivio di documenti per la risoluzione dei problemi relativi a guide e post mortem su interruzioni.</span><span class="sxs-lookup"><span data-stu-id="0a86a-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="0a86a-121">Dal momento che il sistema di verifica degli incidenti dell'organizzazione è una scelta indipendente da Lync Server, istruzioni specifiche o puntatori non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="0a86a-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="0a86a-122">Consultare la documentazione per il sistema scelto dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a86a-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="0a86a-123">Controllare i registri e le prestazioni di IIS</span><span class="sxs-lookup"><span data-stu-id="0a86a-123">Check IIS logs and performance</span></span>

<span data-ttu-id="0a86a-124">Eseguire una revisione settimanale dei registri e delle prestazioni di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0a86a-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="0a86a-125">Per ulteriori informazioni su come monitorare i registri e le prestazioni di IIS, vedere [Panoramica della registrazione di eventi di Windows Server 2003 Internet Information Services (IIS)](https://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="0a86a-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="0a86a-126">La revisione deve includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-126">The review should include the following:</span></span>

  - <span data-ttu-id="0a86a-127">Contatori della cache del servizio Web per monitorare la cache del servizio WWW.</span><span class="sxs-lookup"><span data-stu-id="0a86a-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="0a86a-128">Contatori ASP (Active Server Pages) per monitorare le applicazioni eseguite come ASP.</span><span class="sxs-lookup"><span data-stu-id="0a86a-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="0a86a-129">Generare report di database</span><span class="sxs-lookup"><span data-stu-id="0a86a-129">Generate database reports</span></span>

<span data-ttu-id="0a86a-130">**Per generare report nel database SQL**</span><span class="sxs-lookup"><span data-stu-id="0a86a-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="0a86a-131">Aprire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a86a-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="0a86a-132">Nell'albero della console espandere il nodo foresta, espandere **pool Enterprise**e quindi fare clic sul pool per il quale si desidera generare un report di database.</span><span class="sxs-lookup"><span data-stu-id="0a86a-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="0a86a-133">Nel riquadro dei dettagli, fare clic sulla scheda **database** .</span><span class="sxs-lookup"><span data-stu-id="0a86a-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="0a86a-134">Nella scheda **database** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="0a86a-135">Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="0a86a-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="0a86a-136">Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **rapporti di riepilogo degli utenti**, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="0a86a-137">Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="0a86a-138">Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **rapporti di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="0a86a-139">Verificare la disponibilità di aggiornamenti per la sicurezza e Lync Server</span><span class="sxs-lookup"><span data-stu-id="0a86a-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="0a86a-140">Identificare nuovi Service Pack, hotfix o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="0a86a-141">Se necessario, testarli in un laboratorio di testing e utilizzare le procedure di controllo delle modifiche per organizzare la distribuzione nei server di produzione.</span><span class="sxs-lookup"><span data-stu-id="0a86a-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="0a86a-142">Inoltre, gli aggiornamenti dei componenti di Lync Server sono ora disponibili come parte di Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0a86a-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="0a86a-143">Tutti gli aggiornamenti del componente di Lync Server devono essere aggiornati contemporaneamente su tutti i server che eseguono Lync Server per il quale sono applicabili gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="0a86a-144">Eseguire l'analizzatore delle procedure consigliate di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a86a-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="0a86a-145">Lync Server 2013 Best Practices Analyzer Tool è uno strumento di diagnostica che raccoglie le informazioni di configurazione e determina se la configurazione è impostata in base alle procedure consigliate di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0a86a-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="0a86a-146">La documentazione per questo strumento è in [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="0a86a-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="0a86a-147">Lo strumento Confronta i dati di configurazione della distribuzione in base a un set di regole predefinite per Lync Server e segnala potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="0a86a-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="0a86a-148">Per tutti i problemi segnalati, lo strumento fornisce la configurazione corrente nell'ambiente Lync Server e la configurazione consigliata.</span><span class="sxs-lookup"><span data-stu-id="0a86a-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="0a86a-149">Con l'accesso di rete corretto, lo strumento può esaminare i servizi di dominio Active Directory e i server in cui è in esecuzione Lync Server 2013 per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="0a86a-150">Eseguire le verifiche di integrità in modo proattivo, verificando che la configurazione sia impostata in base alle procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="0a86a-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="0a86a-151">Generare un elenco di problemi, ad esempio le impostazioni di configurazione non ottimali o le opzioni non supportate o consigliate</span><span class="sxs-lookup"><span data-stu-id="0a86a-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="0a86a-152">Giudicare l'integrità generale di un sistema</span><span class="sxs-lookup"><span data-stu-id="0a86a-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="0a86a-153">Risoluzione dei problemi specifici</span><span class="sxs-lookup"><span data-stu-id="0a86a-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="0a86a-154">Richiedere di scaricare gli aggiornamenti se disponibili</span><span class="sxs-lookup"><span data-stu-id="0a86a-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="0a86a-155">Fornire documentazione online e locale sui problemi segnalati e includere suggerimenti per la risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0a86a-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="0a86a-156">Generare informazioni di configurazione che possono essere acquisite per la revisione successiva</span><span class="sxs-lookup"><span data-stu-id="0a86a-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="0a86a-157">Verificare che RTCBPA. msi sia installato in tutti i server Lync Server 2013 e generare un rapporto di verifica dell'integrità settimanale.</span><span class="sxs-lookup"><span data-stu-id="0a86a-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="0a86a-158">Prendere nota dei risultati e correggere, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0a86a-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="0a86a-159">Esaminare i dati sulle prestazioni del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="0a86a-159">Review SLA performance figures</span></span>

<span data-ttu-id="0a86a-160">Controllare i dati chiave relativi alle prestazioni per la settimana precedente.</span><span class="sxs-lookup"><span data-stu-id="0a86a-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="0a86a-161">Esaminare le prestazioni in base ai requisiti del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="0a86a-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="0a86a-162">Identificare le tendenze e gli elementi che non hanno soddisfatto gli obiettivi.</span><span class="sxs-lookup"><span data-stu-id="0a86a-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="0a86a-163">Esaminare il Management Pack di System Center Operations Manager e i report sulla qualità dei rapporti di utilizzo</span><span class="sxs-lookup"><span data-stu-id="0a86a-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="0a86a-164">Ottenere e rivedere i report di Lync Server 2013 Management Pack e Quality of Experience.</span><span class="sxs-lookup"><span data-stu-id="0a86a-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="0a86a-165">Generazione e visualizzazione di report di database per pool Enterprise</span><span class="sxs-lookup"><span data-stu-id="0a86a-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="0a86a-166">**Per generare i report del pool**</span><span class="sxs-lookup"><span data-stu-id="0a86a-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="0a86a-167">Aprire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a86a-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="0a86a-168">Nell'albero della console espandere il nodo foresta, espandere **pool Enterprise**e quindi fare clic sul pool per il quale si desidera generare un report di database.</span><span class="sxs-lookup"><span data-stu-id="0a86a-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="0a86a-169">Nel riquadro dei dettagli, fare clic sulla scheda **database** .</span><span class="sxs-lookup"><span data-stu-id="0a86a-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="0a86a-170">Nella scheda **database** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="0a86a-171">Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="0a86a-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="0a86a-172">Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **rapporti di riepilogo degli utenti**, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="0a86a-173">Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="0a86a-174">Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **rapporti di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0a86a-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="0a86a-175">Per ogni pool Enterprise, gli amministratori possono utilizzare la scheda **database** per visualizzare il nome del database e recuperare e visualizzare i report dal database.</span><span class="sxs-lookup"><span data-stu-id="0a86a-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="0a86a-176">Report e descrizioni dei database</span><span class="sxs-lookup"><span data-stu-id="0a86a-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a86a-177">Sezione</span><span class="sxs-lookup"><span data-stu-id="0a86a-177">Section</span></span></th>
<th><span data-ttu-id="0a86a-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a86a-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a86a-179">Rapporti di riepilogo degli utenti</span><span class="sxs-lookup"><span data-stu-id="0a86a-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="0a86a-180">Dbanalyze/v/report: diag [/SqlServer: valore]</span><span class="sxs-lookup"><span data-stu-id="0a86a-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="0a86a-181">In questa sezione vengono visualizzate informazioni di aggregazione sugli utenti in un pool, ad esempio il numero di utenti abilitati, il numero medio di contatti per utente e il numero di utenti per caratteristiche specifiche.</span><span class="sxs-lookup"><span data-stu-id="0a86a-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="0a86a-182">Quando si utilizzano questi rapporti, è possibile che siano utili le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="0a86a-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a86a-183">Un utente abilitato è un utente abilitato per Lync Server 2013 mediante lo snap-in utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a86a-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="0a86a-184">Un utente attivo è un utente che ha eseguito l'accesso o la registrazione.</span><span class="sxs-lookup"><span data-stu-id="0a86a-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="0a86a-185">I rapporti di riepilogo offrono anche una serie di informazioni statistiche sui contatti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="0a86a-186">Queste statistiche sono valide solo per la popolazione di utenti che hanno effettuato l'accesso almeno una volta e che dispongono di almeno un contatto.</span><span class="sxs-lookup"><span data-stu-id="0a86a-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="0a86a-187">Di conseguenza, in genere, non viene visualizzato un numero minimo di contatti pari a 0.</span><span class="sxs-lookup"><span data-stu-id="0a86a-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="0a86a-188">A causa di questo comportamento, se un utente non ha contatti (ma è attivo, in quanto l'utente è registrato), è possibile che &lt;venga&gt; visualizzato: vuoto per alcuni campi di statistiche.</span><span class="sxs-lookup"><span data-stu-id="0a86a-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a86a-189">Report per utente</span><span class="sxs-lookup"><span data-stu-id="0a86a-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="0a86a-190">Dbanalyze/v/report: disco [/SqlServer: valore]</span><span class="sxs-lookup"><span data-stu-id="0a86a-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="0a86a-191">A differenza dei rapporti di riepilogo, che vengono calcolati su un gruppo di utenti, si tratta di report relativi a un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="0a86a-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a86a-192">Rapporti di riepilogo conferenze</span><span class="sxs-lookup"><span data-stu-id="0a86a-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="0a86a-193">Dbanalyze/v/report: conf [/SqlServer: valore]</span><span class="sxs-lookup"><span data-stu-id="0a86a-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="0a86a-194">In questa sezione vengono visualizzate informazioni di aggregazione sulle statistiche di riepilogo delle conferenze per il pool, ad esempio il numero di conferenze attive e il numero totale di partecipanti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="0a86a-195">Esecuzione dell'analizzatore dell'utilizzo della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0a86a-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="0a86a-196">L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che consente di creare report su diverse visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC tra i collegamenti WAN nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="0a86a-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="0a86a-197">Questi report possono essere utilizzati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="0a86a-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="0a86a-198">Inoltre, viene eseguita una iterazione sulla capacità di larghezza di banda assegnata a vari collegamenti.</span><span class="sxs-lookup"><span data-stu-id="0a86a-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="0a86a-199">Questo strumento esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-199">This tool does the following:</span></span>

  - <span data-ttu-id="0a86a-200">Genera relazioni specifiche per l'utilizzo dell'audio tramite la rete</span><span class="sxs-lookup"><span data-stu-id="0a86a-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="0a86a-201">Consente di eseguire una pianificazione e un'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a vari collegamenti</span><span class="sxs-lookup"><span data-stu-id="0a86a-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="0a86a-202">L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche dei rapporti di utilizzo e capacità della larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0a86a-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="0a86a-203">Sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a86a-203">They are as follows:</span></span>

  - <span data-ttu-id="0a86a-204">Tutti i collegamenti WAN nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="0a86a-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="0a86a-205">Filtrato da collegamenti WAN selezionati che sono stati scelti</span><span class="sxs-lookup"><span data-stu-id="0a86a-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="0a86a-206">Filtrato tramite collegamenti WAN che hanno superato la capacità dei collegamenti</span><span class="sxs-lookup"><span data-stu-id="0a86a-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="0a86a-207">Filtrato mediante collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning</span><span class="sxs-lookup"><span data-stu-id="0a86a-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="0a86a-208">Filtrare mediante collegamenti WAN che raggiungevano livelli critici (un utilizzo della larghezza di banda maggiore del 90% della capacità di larghezza di banda del collegamento WAN)</span><span class="sxs-lookup"><span data-stu-id="0a86a-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="0a86a-209">Filtro in base al tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito</span><span class="sxs-lookup"><span data-stu-id="0a86a-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="0a86a-210">Filtrato in base all'area di rete</span><span class="sxs-lookup"><span data-stu-id="0a86a-210">Filtered by network region</span></span>

<span data-ttu-id="0a86a-211">La documentazione per questo strumento è disponibile in [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="0a86a-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a86a-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a86a-212">See Also</span></span>


[<span data-ttu-id="0a86a-213">Elenco di controllo delle attività settimanali</span><span class="sxs-lookup"><span data-stu-id="0a86a-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

