---
title: Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato
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
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="cf929-102">Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf929-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf929-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cf929-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cf929-104">Le funzionalità di ricerca nel servizio di registrazione centralizzata sono utili e potenti per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf929-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="cf929-105">Le ricerche e i risultati vengono eseguiti in un singolo computer, un pool, un sito o un ambito globale, in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="cf929-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="cf929-106">Le ricerche possono essere inizialmente ampie e quindi limitate a criteri più mirati, ad esempio ora, componente o computer.</span><span class="sxs-lookup"><span data-stu-id="cf929-106">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="cf929-107">Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-107">You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="cf929-108">I risultati della ricerca vengono raccolti da tutti i computer e i pool nell'ambito, raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca (limitati agli scenari in uso e ai dati acquisiti dall' scenari).</span><span class="sxs-lookup"><span data-stu-id="cf929-108">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios).</span></span> <span data-ttu-id="cf929-109">Si usano strumenti noti come **Snooper** o **notepad** per leggere il file di output e i messaggi di analisi provenienti da tutta la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf929-109">You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="cf929-110">Il CLSAgent in ogni singolo computer crea i registri in base allo scenario o agli scenari (due scenari per ogni computer possono essere eseguiti in qualsiasi momento).</span><span class="sxs-lookup"><span data-stu-id="cf929-110">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time).</span></span> <span data-ttu-id="cf929-111">I log e i file di indice e cache associati vengono gestiti da CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="cf929-111">The logs and their associated index and cache files are managed by the CLSAgent.</span></span> <span data-ttu-id="cf929-112">Quando si definisce ed esegue una ricerca, il comando Cerca indica a CLSAgent le informazioni che devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="cf929-112">When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved.</span></span> <span data-ttu-id="cf929-113">CLSAgent esegue la query in base ai file di log, ai file di cache e ai file di indice e restituisce i risultati della ricerca al CLSContoller.</span><span class="sxs-lookup"><span data-stu-id="cf929-113">The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller.</span></span> <span data-ttu-id="cf929-114">CLSController riceve i risultati della ricerca da tutti i computer e i pool nell'ambito della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-114">The CLSController receives the search results from all computers and pools in the scope of the search.</span></span> <span data-ttu-id="cf929-115">Il CLSController quindi aggrega i registri e li inserisce nell'ordine di Delta temporale, la prima voce più antica e procede in tempo fino all'ultima voce più recente.</span><span class="sxs-lookup"><span data-stu-id="cf929-115">The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="cf929-116">Dopo ogni ricerca, il cmdlet **Sync-CsClsLogging** viene eseguito e svuota la cache usata dalle ricerche (da non confondere con i file di cache gestiti da CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="cf929-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="cf929-117">La cancellazione della cache consente di verificare che il buffer di acquisizione di file e traccia puliti sia pulito in CLSController per la successiva operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="cf929-118">Per trarre il massimo vantaggio dal servizio di registrazione centralizzato, è necessario avere una buona conoscenza della configurazione della ricerca per restituire solo i messaggi di traccia dal computer e i registri del pool rilevanti per il problema che si sta ricercando.</span><span class="sxs-lookup"><span data-stu-id="cf929-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="cf929-119">problemi</span><span class="sxs-lookup"><span data-stu-id="cf929-119">issues</span></span>

<span data-ttu-id="cf929-120">Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="cf929-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="cf929-121">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf929-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="cf929-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="cf929-123">Il resto di questo argomento illustra come definire una ricerca per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cf929-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="cf929-124">Per eseguire una ricerca di base tramite il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="cf929-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="cf929-125">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cf929-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cf929-126">Verificare di avere lo scenario AlwaysOn in uso nella distribuzione in ambito globale e quindi digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="cf929-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cf929-127">Per impostazione predefinita, la ricerca-CsClsLogging invia i risultati della ricerca alla console.</span><span class="sxs-lookup"><span data-stu-id="cf929-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="cf929-128">Se si vogliono salvare i risultati della ricerca in un file, usare il percorso &lt;&gt;di file completo della stringa outputFilePath.</span><span class="sxs-lookup"><span data-stu-id="cf929-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="cf929-129">Per definire il parametro – OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette (ad esempio; C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="cf929-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="cf929-130">In questo esempio, devi assicurarti che la directory C:\LogFiles esista e che tu abbia le autorizzazioni per la lettura e la scrittura dei file (autorizzazione NTFS Modify) nella cartella.</span><span class="sxs-lookup"><span data-stu-id="cf929-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="cf929-131">L'output viene accodato e non viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="cf929-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="cf929-132">Se hai bisogno di file separati, definisci un nome di file distinto per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="cf929-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="cf929-134">Per eseguire una ricerca di base in un pool o un computer usando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="cf929-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="cf929-135">Per limitare la ricerca a un pool o un computer specifico, usare il parametro – computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf929-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="cf929-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="cf929-137">Per eseguire ricerche in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, ad esempio i seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf929-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="cf929-138">Se è necessario eseguire la ricerca in un intero pool anziché in un singolo computer, modificare il parametro-computer in-pools, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="cf929-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="cf929-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="cf929-140">Quando si usano i comandi di ricerca, i pool possono essere qualsiasi pool nella distribuzione, ad esempio pool Front-End, pool di bordi, pool di server di chat permanenti o altri che sono definiti come pool nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cf929-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="cf929-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="cf929-142">Per eseguire una ricerca usando i parametri di ora</span><span class="sxs-lookup"><span data-stu-id="cf929-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="cf929-143">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cf929-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cf929-144">Per impostazione predefinita, l'ora di inizio per i parametri specifici del tempo di una ricerca è di 30 minuti prima della data di avvio della ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-144">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search.</span></span> <span data-ttu-id="cf929-145">In altre parole, se si avvia la ricerca alle 4:00:00 PM, la ricerca cercherà i registri per i computer e i pool definiti dalle 3:30:00 alle 4:00:00 PM.</span><span class="sxs-lookup"><span data-stu-id="cf929-145">In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM.</span></span> <span data-ttu-id="cf929-146">Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, usare il parametro – StartTime e impostare la stringa di data e ora per indicare l'ora in cui si vuole che venga avviata la ricerca.</span><span class="sxs-lookup"><span data-stu-id="cf929-146">If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="cf929-147">Usando, ad esempio,-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 09:00 in 11/20/2012 nel pool.</span><span class="sxs-lookup"><span data-stu-id="cf929-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="cf929-148">È possibile impostare il percorso di output per scrivere i risultati in un file denominato c\\: logfile. txt come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cf929-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cf929-149">La stringa di data e ora specificata può essere "data/ora" o "data di scadenza".</span><span class="sxs-lookup"><span data-stu-id="cf929-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="cf929-150">"Il comando analizzerà la stringa e utilizzerà i valori appropriati per la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="cf929-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="cf929-151">Se si vogliono recuperare i log a partire da 11:00:00 AM su 11/20/2012, è necessario definire il-StartTime.</span><span class="sxs-lookup"><span data-stu-id="cf929-151">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime.</span></span> <span data-ttu-id="cf929-152">L'intervallo di tempo predefinito per la ricerca è di 30 minuti a meno che non si definisca uno specifico-EndTime.</span><span class="sxs-lookup"><span data-stu-id="cf929-152">The default time range for the search is 30 minutes unless you define a specific –EndTime.</span></span> <span data-ttu-id="cf929-153">La ricerca risultante restituirà i log dal computer o dai pool definiti da 11:00:00 AM a 11:30:00 AM.</span><span class="sxs-lookup"><span data-stu-id="cf929-153">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="cf929-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="cf929-155">Per eseguire una ricerca di log in un determinato periodo di tempo, definire a-StartTime e an-EndTime.</span><span class="sxs-lookup"><span data-stu-id="cf929-155">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime.</span></span> <span data-ttu-id="cf929-156">È necessario eseguire il log dalle 1 PM alle 2:45 PM nel computer edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="cf929-156">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="cf929-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="cf929-158">Per eseguire una ricerca avanzata usando altri criteri e le opzioni di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="cf929-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="cf929-159">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cf929-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cf929-160">Per eseguire un comando per raccogliere tracce per componenti specifici, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf929-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="cf929-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cf929-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="cf929-162">La ricerca risultante restituisce tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e i pool della distribuzione per i 30 minuti scorsi.</span><span class="sxs-lookup"><span data-stu-id="cf929-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="cf929-163">Per limitare la ricerca con gli stessi componenti solo al pool Front-End denominato pool01.contoso.net, digitare:</span><span class="sxs-lookup"><span data-stu-id="cf929-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="cf929-164">La logica di ricerca predefinita per i comandi con più parametri consiste nell'usare il valore logico o con ognuno dei parametri definiti.</span><span class="sxs-lookup"><span data-stu-id="cf929-164">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="cf929-165">Puoi modificare questo comportamento specificando il parametro **– MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="cf929-165">You can change this behavior by specifying the **–MatchAll** parameter.</span></span> <span data-ttu-id="cf929-166">A tale scopo, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cf929-166">To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="cf929-167">Se gli scenari sono impostati per l'esecuzione costante, ad esempio AlwaysOn, oppure è stato definito un log dello scenario a esecuzione prolungata, è possibile che il computer locale venga disattivato nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="cf929-167">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="cf929-168">Puoi definire la condivisione di file usando il parametro CacheFileNetworkFolder usando New-CsClsConfiguration per creare una nuova configurazione o modificare una configurazione esistente con Set-CsClsConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cf929-168">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="cf929-169">Se non si vuole che la ricerca includa la condivisione file nella raccolta di log in cui eseguire la ricerca, usare il parametro SkipNetworkLogs nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="cf929-169">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

