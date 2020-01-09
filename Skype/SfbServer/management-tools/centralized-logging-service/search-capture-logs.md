---
title: Cercare i log di acquisizione creati dal servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Riepilogo: informazioni su come cercare e leggere i registri di acquisizione dei servizi di registrazione centralizzati in Skype for Business Server 2015.'
ms.openlocfilehash: 563f2c5e08da0830c3bd03e562d0d94052fa359b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991451"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="09873-103">Cercare i log di acquisizione creati dal servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="09873-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09873-104">**Riepilogo:** Informazioni su come cercare e leggere i registri di acquisizione dei servizi di registrazione centralizzati in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="09873-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="09873-105">Le funzionalità di ricerca nel servizio di registrazione centralizzata sono utili e potenti per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="09873-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="09873-106">Le ricerche e i risultati vengono eseguiti in un singolo computer, un pool, un sito o un ambito globale, in base ai criteri definiti.</span><span class="sxs-lookup"><span data-stu-id="09873-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="09873-107">Le ricerche possono essere inizialmente ampie e quindi limitate a criteri più mirati, ad esempio ora, componente o computer.</span><span class="sxs-lookup"><span data-stu-id="09873-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="09873-108">Si esegue una ricerca in base agli stessi registri e non è necessario eseguire di nuovo una sessione di registrazione quando cambia il criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="09873-109">I risultati della ricerca vengono raccolti da tutti i computer e i pool nell'ambito, raccolti e aggregati in un singolo file di output che rappresenta tutti i risultati dei criteri di ricerca (limitati agli scenari in uso e ai dati acquisiti dall' scenari).</span><span class="sxs-lookup"><span data-stu-id="09873-109">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios).</span></span> <span data-ttu-id="09873-110">Si usano strumenti noti come **Snooper** o **notepad** per leggere il file di output e i messaggi di analisi provenienti da tutta la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09873-110">You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="09873-111">Il CLSAgent in ogni singolo computer crea i registri in base allo scenario o agli scenari (due scenari per ogni computer possono essere eseguiti in qualsiasi momento).</span><span class="sxs-lookup"><span data-stu-id="09873-111">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time).</span></span> <span data-ttu-id="09873-112">I log e i file di indice e cache associati vengono gestiti da CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="09873-112">The logs and their associated index and cache files are managed by the CLSAgent.</span></span> <span data-ttu-id="09873-113">Quando si definisce ed esegue una ricerca, il comando Cerca indica a CLSAgent le informazioni che devono essere recuperate.</span><span class="sxs-lookup"><span data-stu-id="09873-113">When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved.</span></span> <span data-ttu-id="09873-114">CLSAgent esegue la query in base ai file di log, ai file di cache e ai file di indice e restituisce i risultati della ricerca al CLSContoller.</span><span class="sxs-lookup"><span data-stu-id="09873-114">The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller.</span></span> <span data-ttu-id="09873-115">CLSController riceve i risultati della ricerca da tutti i computer e i pool nell'ambito della ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-115">The CLSController receives the search results from all computers and pools in the scope of the search.</span></span> <span data-ttu-id="09873-116">Il CLSController quindi aggrega i registri e li inserisce nell'ordine di Delta temporale, la prima voce più antica e procede in tempo fino all'ultima voce più recente.</span><span class="sxs-lookup"><span data-stu-id="09873-116">The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="09873-117">Dopo ogni ricerca, il cmdlet **Sync-CsClsLogging** viene eseguito e svuota la cache usata dalle ricerche (da non confondere con i file di cache gestiti da CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="09873-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="09873-118">La cancellazione della cache consente di verificare che il buffer di acquisizione di file e traccia puliti sia pulito in CLSController per la successiva operazione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="09873-119">Per trarre il massimo vantaggio dal servizio di registrazione centralizzato, è necessario avere una buona conoscenza della configurazione della ricerca per restituire solo i messaggi di traccia dal computer e i registri del pool rilevanti per il problema che si sta ricercando.</span><span class="sxs-lookup"><span data-stu-id="09873-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="09873-120">problemi</span><span class="sxs-lookup"><span data-stu-id="09873-120">issues</span></span>
  
<span data-ttu-id="09873-121">Per eseguire le funzioni di ricerca del servizio di registrazione centralizzata usando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="09873-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="09873-122">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="09873-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="09873-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="09873-124">Il resto di questo argomento illustra come definire una ricerca per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="09873-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="09873-125">Per eseguire una ricerca di base tramite il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="09873-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="09873-126">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="09873-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="09873-127">Verificare di avere lo scenario AlwaysOn in uso nella distribuzione in ambito globale e quindi digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="09873-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="09873-128">Per impostazione predefinita, la ricerca-CsClsLogging invia i risultati della ricerca alla console.</span><span class="sxs-lookup"><span data-stu-id="09873-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="09873-129">Se si vogliono salvare i risultati della ricerca in un file, usare il _ \<percorso\>di file_completo di stringa outputFilePath.</span><span class="sxs-lookup"><span data-stu-id="09873-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="09873-130">Per definire il parametro-OutputFilePath, specificare un percorso e un nome di file come parte del parametro in un formato stringa racchiuso tra virgolette, ad esempio. C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="09873-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="09873-131">In questo esempio, devi assicurarti che la directory C:\LogFiles esista e che tu abbia le autorizzazioni per la lettura e la scrittura dei file (autorizzazione NTFS Modify) nella cartella.</span><span class="sxs-lookup"><span data-stu-id="09873-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="09873-132">L'output viene accodato e non viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="09873-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="09873-133">Se hai bisogno di file separati, definisci un nome di file distinto per ogni ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="09873-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="09873-135">Per eseguire una ricerca di base in un pool o un computer usando il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="09873-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="09873-136">Per limitare la ricerca a un pool o un computer specifico, usare il parametro-computers con il computer definito da un nome completo del computer, racchiuso tra virgolette e separato da una virgola come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="09873-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="09873-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="09873-138">Per eseguire ricerche in più computer, digitare più nomi di computer racchiusi tra virgolette e separati da virgole, ad esempio i seguenti:</span><span class="sxs-lookup"><span data-stu-id="09873-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="09873-139">Se è necessario eseguire ricerche in un intero pool anziché in un singolo computer, cambiare il parametro-computer in pool, rimuovere il nome del computer e sostituirlo con il pool o i pool tra virgolette separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="09873-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="09873-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="09873-141">Quando si usano i comandi di ricerca, i pool possono essere qualsiasi pool nella distribuzione, ad esempio pool Front-End, pool di bordi, pool di server di chat permanenti o altri che sono definiti come pool nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="09873-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="09873-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="09873-143">Per eseguire una ricerca usando i parametri di ora</span><span class="sxs-lookup"><span data-stu-id="09873-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="09873-144">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="09873-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="09873-145">Per impostazione predefinita, l'ora di inizio per i parametri specifici del tempo di una ricerca è di 25 minuti prima di cinque minuti dopo il momento in cui si avvia la ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="09873-146">In altre parole, se si cerca in 4:00:00 PM, l'ora di inizio della ricerca verrà visualizzata come 3:35:00 PM to 4:05:00 PM.</span><span class="sxs-lookup"><span data-stu-id="09873-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="09873-147">Se è necessario cercare 60 minuti o 3 ore prima dell'ora corrente, usare il parametro-StartTime e impostare la stringa di data e ora per indicare l'ora in cui si vuole che venga avviata la ricerca.</span><span class="sxs-lookup"><span data-stu-id="09873-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="09873-148">Ad esempio, usando-StartTime e-EndTime per definire un intervallo di data e ora, è possibile definire una ricerca tra le 8.00 e le 09:00 in 11/20/2012 nel pool.</span><span class="sxs-lookup"><span data-stu-id="09873-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="09873-149">È possibile impostare il percorso di output per scrivere i risultati in un file denominato c:\logfile.txt come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="09873-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="09873-150">La stringa di data e ora specificata può essere "data/ora" o "data di scadenza".</span><span class="sxs-lookup"><span data-stu-id="09873-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="09873-151">"Il comando analizzerà la stringa e utilizzerà i valori appropriati per la data e l'ora e le impostazioni locali e della lingua nel computer in cui è in esecuzione cmdlet.</span><span class="sxs-lookup"><span data-stu-id="09873-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="09873-152">Se si vogliono recuperare i log a partire da 11:00:00 AM su 11/20/2012, è possibile definire il-StartTime.</span><span class="sxs-lookup"><span data-stu-id="09873-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="09873-153">L'intervallo di tempo predefinito per la ricerca è di 30 minuti a meno che non si definisca un specifico-EndTime.</span><span class="sxs-lookup"><span data-stu-id="09873-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="09873-154">La ricerca risultante restituirà i log dal computer o dai pool definiti da 11:00:00 AM a 11:30:00 AM.</span><span class="sxs-lookup"><span data-stu-id="09873-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="09873-155">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="09873-156">Per eseguire una ricerca di log in un determinato periodo di tempo, Definisci a-StartTime e an-EndTime.</span><span class="sxs-lookup"><span data-stu-id="09873-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="09873-157">È necessario eseguire il log dalle 1 PM alle 2:45 PM nel computer edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="09873-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="09873-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="09873-159">Per eseguire una ricerca avanzata usando altri criteri e le opzioni di corrispondenza</span><span class="sxs-lookup"><span data-stu-id="09873-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="09873-160">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="09873-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="09873-161">Per eseguire un comando per raccogliere tracce per componenti specifici, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="09873-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="09873-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09873-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="09873-163">La ricerca risultante restituisce tutte le voci di log con componenti di traccia per SIPStack, S4 e UserServices in tutti i computer e i pool della distribuzione per i 30 minuti scorsi.</span><span class="sxs-lookup"><span data-stu-id="09873-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="09873-164">Per limitare la ricerca con gli stessi componenti solo al pool Front-End denominato pool01.contoso.net, digitare:</span><span class="sxs-lookup"><span data-stu-id="09873-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="09873-165">La logica di ricerca predefinita per i comandi con più parametri consiste nell'usare il valore logico o con ognuno dei parametri definiti.</span><span class="sxs-lookup"><span data-stu-id="09873-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="09873-166">Puoi modificare questo comportamento specificando il parametro **-MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="09873-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="09873-167">A tale scopo, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="09873-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="09873-168">Se gli scenari sono impostati per l'esecuzione costante, ad esempio AlwaysOn, oppure è stato definito un log dello scenario a esecuzione prolungata, è possibile che il computer locale venga disattivato nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="09873-168">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="09873-169">Puoi definire la condivisione di file usando il parametro CacheFileNetworkFolder usando New-CsClsConfiguration per creare una nuova configurazione o modificare una configurazione esistente con Set-CsClsConfiguration.</span><span class="sxs-lookup"><span data-stu-id="09873-169">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="09873-170">Se non si vuole che la ricerca includa la condivisione file nella raccolta di log in cui eseguire la ricerca, usare il parametro SkipNetworkLogs nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="09873-170">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="09873-171">Leggere i registri di acquisizione dal servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="09873-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="09873-172">Dopo aver eseguito la ricerca, è possibile realizzare il vero vantaggio del servizio di registrazione centralizzato e si ha un file che può essere usato per rintracciare un problema segnalato.</span><span class="sxs-lookup"><span data-stu-id="09873-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="09873-173">È possibile leggere il file in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="09873-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="09873-174">Il file di output è in formato testo standard ed è possibile usare Notepad. exe o qualsiasi altra applicazione che consentirà di aprire e leggere un file di testo.</span><span class="sxs-lookup"><span data-stu-id="09873-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="09873-175">Per i file più grandi e i problemi più complessi, puoi usare uno strumento come Snooper. exe progettato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="09873-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="09873-176">Snooper è incluso negli strumenti di debug disponibili come download separato.</span><span class="sxs-lookup"><span data-stu-id="09873-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="09873-177">È possibile scaricare gli strumenti di debug qui [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257):.</span><span class="sxs-lookup"><span data-stu-id="09873-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="09873-178">Quando si installano gli strumenti di debug, non vengono creati scorciatoie e voci di menu.</span><span class="sxs-lookup"><span data-stu-id="09873-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="09873-179">Dopo aver installato gli strumenti di debug, aprire Esplora risorse, una finestra della riga di comando o Skype for Business Server Management Shell e accedere alla directory (posizione predefinita) C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="09873-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="09873-180">Fare doppio clic su Snooper. exe o digitare Snooper. exe, quindi premere INVIO se si usa la riga di comando o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="09873-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="09873-181">Lo scopo di questo argomento non è dettagliare e discutere le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="09873-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="09873-182">La risoluzione dei problemi e i processi che la circondano sono un argomento complesso.</span><span class="sxs-lookup"><span data-stu-id="09873-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="09873-183">Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere il [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)manuale del Resource Kit di Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="09873-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="09873-184">I processi e le procedure si applicano ancora a Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="09873-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="09873-185">Per aprire un file di log in Snooper</span><span class="sxs-lookup"><span data-stu-id="09873-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="09873-186">Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log.</span><span class="sxs-lookup"><span data-stu-id="09873-186">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="09873-187">Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="09873-187">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="09873-188">Dopo l'installazione degli strumenti di debug (LyncDebugTools. msi), cambiare directory nella posizione di Snooper. exe usando Esplora risorse o dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="09873-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="09873-189">Per impostazione predefinita, gli strumenti di debug si trovano in C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="09873-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="09873-190">Fare doppio clic su o eseguire Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="09873-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="09873-191">Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di log, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="09873-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="09873-192">I messaggi di **traccia** del file di log vengono visualizzati nella scheda **traccia** . fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.</span><span class="sxs-lookup"><span data-stu-id="09873-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="09873-193">Per visualizzare un diagramma di flusso delle chiamate</span><span class="sxs-lookup"><span data-stu-id="09873-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="09873-194">Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log.</span><span class="sxs-lookup"><span data-stu-id="09873-194">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="09873-195">Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="09873-195">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="09873-196">Aprire un file di log e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi o selezionare un componente di traccia nella scheda **traccia** .</span><span class="sxs-lookup"><span data-stu-id="09873-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="09873-197">Fare clic su **flusso di chiamata**.</span><span class="sxs-lookup"><span data-stu-id="09873-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="09873-198">Se si fa clic su un messaggio o una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow".</span><span class="sxs-lookup"><span data-stu-id="09873-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="09873-199">Scegliere un altro messaggio o traccia e il flusso di chiamata viene visualizzato se il messaggio o la traccia fa parte di un flusso di chiamata.</span><span class="sxs-lookup"><span data-stu-id="09873-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="09873-200">Spostarsi tra i messaggi o le linee di traccia e notare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.</span><span class="sxs-lookup"><span data-stu-id="09873-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="09873-201">Posizionare il puntatore del mouse sugli elementi per ottenere informazioni su messaggi di chiamata, endpoint e altri componenti.</span><span class="sxs-lookup"><span data-stu-id="09873-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
