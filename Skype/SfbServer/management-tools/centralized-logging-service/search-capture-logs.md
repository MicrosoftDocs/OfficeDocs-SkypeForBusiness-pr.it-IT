---
title: Registri di acquisizione della ricerca creati dal servizio di registrazione centralizzato in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Riepilogo: informazioni su come eseguire la ricerca e la lettura dei log di acquisizione del servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835126"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="721c2-103">Registri di acquisizione della ricerca creati dal servizio di registrazione centralizzato in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="721c2-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="721c2-104">**Riepilogo:** Informazioni su come eseguire la ricerca e la lettura dei log di acquisizione del servizio di registrazione centralizzato in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="721c2-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="721c2-105">Le funzionalità di ricerca nel servizio di registrazione centralizzato sono utili e potenti per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="721c2-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="721c2-106">Le ricerche e i risultati vengono eseguiti su un unico computer, un pool, un sito o un ambito globale in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="721c2-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="721c2-107">Inizialmente è possibile eseguire ricerche ad ampio spettro e successivamente restringerle adottando criteri più mirati, ad esempio un'ora, un componente o un computer.</span><span class="sxs-lookup"><span data-stu-id="721c2-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="721c2-108">Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="721c2-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="721c2-p102">I risultati di ricerca prelevati da tutti i computer e i pool compresi nell'ambito vengono raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca, limitatamente agli scenari eseguiti e ai dati acquisiti. È possibile utilizzare strumenti noti come **Snooper** o **Blocco note** per leggere il file di output e i messaggi di traccia di tutta la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="721c2-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="721c2-p103">In ogni singolo computer il componente Agente del servizio di registrazione centralizzato (CLSAgent) crea i registri in base allo scenario o agli scenari in esecuzione (è possibile eseguire due scenari per computer in un dato momento). I log e i file di indice e cache associati sono gestiti da CLSAgent. Quando si definisce ed esegue una ricerca, il comando di ricerca indica a CLSAgent quali informazioni recuperare. CLSAgent esegue la query nei file di log, cache e indice e restituisce i risultati della ricerca al Controller servizio di registrazione centralizzato (CLSContoller). Quest'ultimo riceve i risultati di ricerca da tutti i computer e pool compresi nell'ambito della ricerca. Quindi aggrega (combina) i log e li ordina in base a un intervallo di tempo, dalla voce meno recente alla più recente.</span><span class="sxs-lookup"><span data-stu-id="721c2-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="721c2-117">Al termine di ogni ricerca viene eseguito il cmdlet **Sync-CsClsLogging**, che scarica la cache utilizzata per le ricerche (da non confondere con i file cache gestiti da CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="721c2-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="721c2-118">Lo scaricamento della cache aiuta a garantire la presenza di un buffer di acquisizione del log e del file di traccia vuoto in CLSController per la successiva operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="721c2-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="721c2-119">Per ottenere il massimo vantaggio dal servizio di registrazione centralizzato, è necessaria una buona conoscenza di come configurare la ricerca per restituire solo i messaggi di traccia provenienti dai registri del computer e del pool rilevanti per il problema che si sta ricercando.</span><span class="sxs-lookup"><span data-stu-id="721c2-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="721c2-120">problemi</span><span class="sxs-lookup"><span data-stu-id="721c2-120">issues</span></span>
  
<span data-ttu-id="721c2-121">Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o del controllo di accesso basato sui ruoli di CsServerAdministrator oppure di un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="721c2-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="721c2-122">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="721c2-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="721c2-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="721c2-124">Nel resto di questo argomento viene illustrato come definire una ricerca per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="721c2-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="721c2-125">Per eseguire una ricerca di base utilizzando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="721c2-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="721c2-126">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="721c2-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="721c2-127">Verificare che nella distribuzione presso l'ambito globale sia in esecuzione lo scenario AlwaysOn e digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="721c2-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="721c2-128">Per impostazione predefinita, Search-CsClsLogging invia i risultati della ricerca alla console.</span><span class="sxs-lookup"><span data-stu-id="721c2-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="721c2-129">Se si desidera salvare i risultati della ricerca in un file, utilizzare-OutputFilePath  _\<string fully qualified file path\>_ .</span><span class="sxs-lookup"><span data-stu-id="721c2-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="721c2-130">Per definire il parametro-OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette (ad esempio, C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="721c2-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="721c2-131">Nell'esempio fornito è necessario verificare che la directory C:\LogFiles esista e di disporre delle autorizzazioni di lettura e scrittura (autorizzazione NTFS Modifica) dei file nella cartella.</span><span class="sxs-lookup"><span data-stu-id="721c2-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="721c2-132">L'output viene aggiunto e non sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="721c2-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="721c2-133">Se sono necessari singoli file, definire un nome di file per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="721c2-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="721c2-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="721c2-135">Per eseguire una ricerca di base in un pool o in un computer utilizzando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="721c2-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="721c2-136">Per limitare la ricerca a un pool o a un computer specifico, utilizzare il parametro-computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="721c2-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="721c2-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="721c2-138">Per eseguire la ricerca in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, come l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="721c2-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="721c2-139">Se è necessario eseguire una ricerca in un intero pool anziché in un singolo computer, modificare il parametro-computer con i pool, rimuovere il nome del computer e sostituirlo con il pool o i pool racchiusi tra virgolette separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="721c2-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="721c2-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="721c2-141">Quando si utilizzano i comandi di ricerca, i pool possono essere tutti i pool della distribuzione, ad esempio i pool Front End, i pool di server perimetrali, i pool di Persistent Chat o altri che sono definiti come pool nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="721c2-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="721c2-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="721c2-143">Per eseguire una ricerca utilizzando parametri temporali</span><span class="sxs-lookup"><span data-stu-id="721c2-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="721c2-144">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="721c2-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="721c2-145">Per impostazione predefinita, l'ora di inizio dei parametri specifici per il tempo di una ricerca è di 25 minuti prima di cinque minuti dopo la data di avvio della ricerca.</span><span class="sxs-lookup"><span data-stu-id="721c2-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="721c2-146">In altre parole, se si cerca a 4:00:00 PM, l'ora di inizio della ricerca mostrerà come 3:35:00 PM a 4:05:00 PM.</span><span class="sxs-lookup"><span data-stu-id="721c2-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="721c2-147">Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, utilizzare il parametro-StartTime e impostare la stringa di data e ora per indicare l'ora in cui si desidera che venga avviata la ricerca.</span><span class="sxs-lookup"><span data-stu-id="721c2-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="721c2-148">Ad esempio, utilizzando-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 9.00 del 11/20/2012 sul pool.</span><span class="sxs-lookup"><span data-stu-id="721c2-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="721c2-149">È possibile impostare il percorso di output in modo da scrivere i risultati in un file denominato c:\logfile.txt come segue:</span><span class="sxs-lookup"><span data-stu-id="721c2-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="721c2-150">La stringa di data e ora specificata può essere "data ora" o "data ora.</span><span class="sxs-lookup"><span data-stu-id="721c2-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="721c2-151">"Il comando analizzerà la stringa e utilizzerà i valori corretti per la data e l'ora e le impostazioni locali e della lingua nel computer in cui si esegue il cmdlet.</span><span class="sxs-lookup"><span data-stu-id="721c2-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="721c2-152">Se si desidera recuperare i log a partire da 11:00:00 su 11/20/2012, è possibile definire il-StartTime.</span><span class="sxs-lookup"><span data-stu-id="721c2-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="721c2-153">L'intervallo di tempo predefinito per la ricerca è di 30 minuti, a meno che non si definisca una specifica-EndTime.</span><span class="sxs-lookup"><span data-stu-id="721c2-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="721c2-154">La ricerca risultante restituirà i log dal computer o dai pool definiti dalle 11:00:00 alle 11:30:00.</span><span class="sxs-lookup"><span data-stu-id="721c2-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="721c2-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="721c2-156">Per eseguire una ricerca dei log entro un determinato periodo di tempo, definire a-StartTime e an-EndTime.</span><span class="sxs-lookup"><span data-stu-id="721c2-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="721c2-157">Vengono cercati i log dalle 13.00 alle 14.45 del computer edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="721c2-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="721c2-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="721c2-159">Per eseguire una ricerca avanzata utilizzando altri criteri e opzioni di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="721c2-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="721c2-160">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="721c2-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="721c2-161">Per eseguire un comando per raccogliere le tracce di specifici componenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="721c2-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="721c2-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="721c2-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="721c2-163">Vengono restituite tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e pool della distribuzione negli ultimi 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="721c2-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="721c2-164">Per limitare la ricerca agli stessi componenti solo per il pool Front End denominato pool01.contoso.net, digitare:</span><span class="sxs-lookup"><span data-stu-id="721c2-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="721c2-165">La logica di ricerca predefinita per i comandi che dispongono di più parametri consiste nell'utilizzo dell'operatore logico OR con ogni parametro definito.</span><span class="sxs-lookup"><span data-stu-id="721c2-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="721c2-166">È possibile modificare questo comportamento specificando il parametro **-MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="721c2-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="721c2-167">A tal fine, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="721c2-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="721c2-p114">Se è stata impostata l'esecuzione costante degli scenari, come AlwaysOn, o è stato definito uno scenario di lunga durata, è possibile riportare i log del computer locale nella condivisione file. È possibile definire la condivisione file utilizzando il parametro CacheFileNetworkFolder con New-CsClsConfiguration per creare una nuova configurazione e con Set-CsClsConfiguration per modificarne una esistente. Se non si desidera includere la condivisione file nella raccolta dei log per la ricerca, utilizzare il parametro SkipNetworkLogs come segue:</span><span class="sxs-lookup"><span data-stu-id="721c2-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="721c2-171">Leggere i registri di acquisizione dal servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="721c2-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="721c2-172">Si rende conto del vantaggio reale del servizio di registrazione centralizzato dopo aver eseguito la ricerca e si dispone di un file che è possibile utilizzare per individuare un problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="721c2-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="721c2-173">È possibile leggere il file in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="721c2-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="721c2-174">Il file di output è in formato testo standard ed è possibile utilizzare Notepad.exe o qualsiasi altro programma che consenta l'apertura e la lettura di un file di testo.</span><span class="sxs-lookup"><span data-stu-id="721c2-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="721c2-175">Per i file più grandi e i problemi più complessi, è possibile utilizzare uno strumento come Snooper.exe che è stato creato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="721c2-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="721c2-176">Snooper è incluso negli strumenti di debug che sono disponibili come download separato.</span><span class="sxs-lookup"><span data-stu-id="721c2-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="721c2-177">È possibile scaricare gli strumenti di debug qui: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) .</span><span class="sxs-lookup"><span data-stu-id="721c2-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="721c2-178">Quando si installano gli strumenti di debug, non vengono creati scorciatoie e voci di menu.</span><span class="sxs-lookup"><span data-stu-id="721c2-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="721c2-179">Dopo aver installato gli strumenti di debug, aprire Esplora risorse, una finestra della riga di comando o Skype for Business Server Management Shell e passare alla directory (posizione predefinita) C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="721c2-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="721c2-180">Fare doppio clic su Snooper.exe o digitare Snooper.exe, quindi premere INVIO se si utilizza la riga di comando o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="721c2-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="721c2-181">Lo scopo di questo argomento non è quello di illustrare le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="721c2-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="721c2-182">La risoluzione dei problemi e i processi attorno a esso sono un argomento complesso.</span><span class="sxs-lookup"><span data-stu-id="721c2-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="721c2-183">Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) .</span><span class="sxs-lookup"><span data-stu-id="721c2-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="721c2-184">I processi e le procedure si applicano ancora a Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="721c2-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="721c2-185">Per aprire un file di registro in Snooper</span><span class="sxs-lookup"><span data-stu-id="721c2-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="721c2-186">Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro.</span><span class="sxs-lookup"><span data-stu-id="721c2-186">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="721c2-187">Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="721c2-187">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="721c2-188">Dopo l'installazione degli strumenti di debug (LyncDebugTools.msi), cambiare directory nel percorso di Snooper.exe tramite Esplora risorse o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="721c2-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="721c2-189">Per impostazione predefinita, gli strumenti di debug sono disponibili in C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="721c2-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="721c2-190">Fare doppio clic o eseguire Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="721c2-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="721c2-191">Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di registro, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="721c2-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="721c2-192">I messaggi di **traccia** dei file di registro vengono visualizzati nella scheda **traccia** . Fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.</span><span class="sxs-lookup"><span data-stu-id="721c2-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="721c2-193">Per visualizzare un diagramma del flusso di chiamata</span><span class="sxs-lookup"><span data-stu-id="721c2-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="721c2-194">Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro.</span><span class="sxs-lookup"><span data-stu-id="721c2-194">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="721c2-195">Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="721c2-195">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="721c2-196">Aprire un file di registro e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi oppure selezionare un componente di traccia nella scheda **traccia** .</span><span class="sxs-lookup"><span data-stu-id="721c2-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="721c2-197">Fare clic su **flusso di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="721c2-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="721c2-198">Se si fa clic su un messaggio o su una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow".</span><span class="sxs-lookup"><span data-stu-id="721c2-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="721c2-199">Scegliere un altro messaggio o traccia e il flusso di chiamata verrà visualizzato se il messaggio o la traccia è parte di un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="721c2-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="721c2-200">Spostarsi tra i messaggi o le righe di traccia e osservare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.</span><span class="sxs-lookup"><span data-stu-id="721c2-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="721c2-201">Posizionare il puntatore del mouse sugli elementi per ottenere informazioni sui messaggi di chiamata, gli endpoint e altri componenti.</span><span class="sxs-lookup"><span data-stu-id="721c2-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
