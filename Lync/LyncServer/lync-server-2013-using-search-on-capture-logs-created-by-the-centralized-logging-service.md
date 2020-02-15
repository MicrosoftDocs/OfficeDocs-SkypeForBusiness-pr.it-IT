---
title: Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f9571f2efe08eb13091c3d3660e7760a8e805c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="e7244-102">Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7244-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7244-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e7244-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e7244-104">Le funzionalità di ricerca nel servizio di registrazione centralizzato sono utili e potenti per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7244-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="e7244-105">Le ricerche e i risultati vengono eseguiti su un unico computer, un pool, un sito o un ambito globale in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="e7244-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="e7244-p101">Inizialmente è possibile eseguire ricerche ad ampio spettro e successivamente restringerle adottando criteri più mirati, ad esempio un'ora, un componente o un computer. Le ricerche vengono eseguite negli stessi log e quando i criteri di ricerca cambiano non è necessario effettuare di nuovo una sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e7244-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="e7244-p102">I risultati di ricerca prelevati da tutti i computer e i pool compresi nell'ambito vengono raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca, limitatamente agli scenari eseguiti e ai dati acquisiti. È possibile utilizzare strumenti noti come **Snooper** o **Blocco note** per leggere il file di output e i messaggi di traccia di tutta la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7244-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="e7244-p103">In ogni singolo computer il componente Agente del servizio di registrazione centralizzato (CLSAgent) crea i registri in base allo scenario o agli scenari in esecuzione (è possibile eseguire due scenari per computer in un dato momento). I log e i file di indice e cache associati sono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando di ricerca indica a CLSAgent quali informazioni recuperare. CLSAgent esegue la query nei file di log, cache e indice e restituisce i risultati della ricerca al Controller servizio di registrazione centralizzato (CLSContoller). Quest'ultimo riceve i risultati di ricerca da tutti i computer e pool compresi nell'ambito della ricerca. Quindi aggrega (combina) i log e li ordina in base a un intervallo di tempo, dalla voce meno recente alla più recente.</span><span class="sxs-lookup"><span data-stu-id="e7244-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="e7244-116">Al termine di ogni ricerca viene eseguito il cmdlet **Sync-CsClsLogging**, che scarica la cache utilizzata per le ricerche (da non confondere con i file cache gestiti da CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="e7244-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="e7244-117">Lo scaricamento della cache aiuta a garantire la presenza di un buffer di acquisizione del log e del file di traccia vuoto in CLSController per la successiva operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e7244-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="e7244-118">Per ottenere il massimo vantaggio dal servizio di registrazione centralizzato, è necessaria una buona conoscenza di come configurare la ricerca per restituire solo i messaggi di traccia provenienti dai registri del computer e del pool rilevanti per il problema che si sta ricercando.</span><span class="sxs-lookup"><span data-stu-id="e7244-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="e7244-119">problemi</span><span class="sxs-lookup"><span data-stu-id="e7244-119">issues</span></span>

<span data-ttu-id="e7244-120">Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o del controllo di accesso basato sui ruoli di CsServerAdministrator oppure di un ruolo RBAC personalizzato contenente uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="e7244-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e7244-121">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7244-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="e7244-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="e7244-123">Nel resto di questo argomento viene illustrato come definire una ricerca per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e7244-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="e7244-124">Per eseguire una ricerca di base utilizzando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="e7244-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="e7244-125">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e7244-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7244-126">Verificare che nella distribuzione presso l'ambito globale sia in esecuzione lo scenario AlwaysOn e digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e7244-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7244-127">Per impostazione predefinita, Search-CsClsLogging invia i risultati della ricerca alla console.</span><span class="sxs-lookup"><span data-stu-id="e7244-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="e7244-128">Se si desidera salvare i risultati della ricerca in un file, utilizzare – OutputFilePath &lt;String fully qualified file path&gt;.</span><span class="sxs-lookup"><span data-stu-id="e7244-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="e7244-129">Per definire il parametro –OutputFilePath, specificare un percorso e un nome file come parte del parametro in un formato stringa tra virgolette, ad esempio C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="e7244-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="e7244-130">Nell'esempio fornito è necessario verificare che la directory C:\LogFiles esista e di disporre delle autorizzazioni di lettura e scrittura (autorizzazione NTFS Modifica) dei file nella cartella.</span><span class="sxs-lookup"><span data-stu-id="e7244-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="e7244-131">L'output viene aggiunto e non sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="e7244-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="e7244-132">Se sono necessari singoli file, definire un nome di file per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="e7244-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="e7244-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="e7244-134">Per eseguire una ricerca di base in un pool o in un computer utilizzando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="e7244-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="e7244-135">Per limitare la ricerca a uno specifico pool o computer, utilizzare il parametro –Computers con il computer definito da un nome completo tra virgolette e separato da una virgola come segue:</span><span class="sxs-lookup"><span data-stu-id="e7244-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="e7244-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="e7244-137">Per eseguire la ricerca in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, come l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e7244-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="e7244-138">Se è necessario eseguire la ricerca in un intero pool, anziché in un singolo computer, modificare il parametro –Computers in –Pools, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e7244-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="e7244-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="e7244-140">Quando si utilizzano i comandi di ricerca, i pool possono essere tutti i pool della distribuzione, ad esempio i pool Front End, i pool di server perimetrali, i pool di Persistent Chat o altri che sono definiti come pool nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e7244-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="e7244-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="e7244-142">Per eseguire una ricerca utilizzando parametri temporali</span><span class="sxs-lookup"><span data-stu-id="e7244-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="e7244-143">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e7244-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7244-p108">Per impostazione predefinita, l'ora di inizio dei parametri di tempo per una ricerca precede di 30 minuti l'ora di avvio della ricerca. In altre parole, se una ricerca viene avviata alle 16.00.00, nei log dei computer e dei pool definiti la ricerca sarà eseguita dalle 15.30.00 alle 16.00.00. Qualora sia necessario effettuare la ricerca 60 minuti o 3 ore prima dell'ora attuale, utilizzare il parametro –StartTime e impostare la stringa di data e ora per indicare l'ora in cui si desidera avviare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="e7244-p108">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search. In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM. If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="e7244-147">Ad esempio, impostando un intervallo di data e ora con i parametri –StartTime ed –EndTime, è possibile definire che nel pool venga effettuata una ricerca tra le 08.00 e le 09.00 del 20 novembre 2012.</span><span class="sxs-lookup"><span data-stu-id="e7244-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="e7244-148">È possibile impostare il percorso di output in modo che i risultati vengano scritti in un\\file denominato c: logfile. txt, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e7244-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e7244-149">La stringa di data e ora specificata può essere "data ora" o "data ora.</span><span class="sxs-lookup"><span data-stu-id="e7244-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="e7244-150">"Il comando analizzerà la stringa e utilizzerà i valori corretti per la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="e7244-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="e7244-p111">Se si desidera recuperare i log che iniziano alle 11.00.00 del 20 novembre 2012, definire il parametro –StartTime. Se non viene specificato il parametro –EndTime, l'intervallo di tempo predefinito per la ricerca è pari a 30 minuti e vengono pertanto restituiti i log dei computer o pool specificati dalle 11.00.00 alle 11.30.00.</span><span class="sxs-lookup"><span data-stu-id="e7244-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="e7244-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="e7244-p112">Per cercare i log all'interno di uno specifico periodo, definire i parametri –StartTime ed –EndTime. Vengono cercati i log dalle 13.00 alle 14.45 del computer edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="e7244-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="e7244-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="e7244-158">Per eseguire una ricerca avanzata utilizzando altri criteri e opzioni di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="e7244-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="e7244-159">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e7244-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7244-160">Per eseguire un comando per raccogliere le tracce di specifici componenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e7244-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="e7244-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e7244-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="e7244-162">Vengono restituite tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e pool della distribuzione negli ultimi 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="e7244-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="e7244-163">Per limitare la ricerca agli stessi componenti solo per il pool Front End denominato pool01.contoso.net, digitare:</span><span class="sxs-lookup"><span data-stu-id="e7244-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="e7244-p113">La logica di ricerca predefinita per i comandi che dispongono di più parametri consiste nell'utilizzo dell'operatore logico OR con ogni parametro definito. Questo comportamento può essere modificato specificando il parametro **–MatchAll**. A tal fine, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e7244-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="e7244-p114">Se è stata impostata l'esecuzione costante degli scenari, come AlwaysOn, o è stato definito uno scenario di lunga durata, è possibile riportare i log del computer locale nella condivisione file. È possibile definire la condivisione file utilizzando il parametro CacheFileNetworkFolder con New-CsClsConfiguration per creare una nuova configurazione e con Set-CsClsConfiguration per modificarne una esistente. Se non si desidera includere la condivisione file nella raccolta dei log per la ricerca, utilizzare il parametro SkipNetworkLogs come segue:</span><span class="sxs-lookup"><span data-stu-id="e7244-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

