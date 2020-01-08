---
title: Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7d94d-102">Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d94d-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d94d-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7d94d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7d94d-104">Il servizio di registrazione centralizzato è configurato per definire il modo in cui il servizio di registrazione è destinato a raccogliere, come raccoglie, da dove raccoglierà e quali sono le impostazioni del log.</span><span class="sxs-lookup"><span data-stu-id="7d94d-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="7d94d-105">Puoi definire queste impostazioni a livello globale (ovvero, per l'intera distribuzione) o per un sito (ovvero un sito denominato nella distribuzione).</span><span class="sxs-lookup"><span data-stu-id="7d94d-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="7d94d-106">Tutte le registrazioni definitive utilizzeranno le impostazioni appropriate per l'identità usata per i comandi per avviare, arrestare, svuotare e cercare i registri.</span><span class="sxs-lookup"><span data-stu-id="7d94d-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="7d94d-107">Per visualizzare la configurazione del servizio di registrazione centralizzata corrente</span><span class="sxs-lookup"><span data-stu-id="7d94d-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="7d94d-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7d94d-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7d94d-109">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="7d94d-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="7d94d-110">È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo <CODE>-Identity</CODE> e un ambito, ad esempio "site: Redmond", per restituire solo il CsClsConfiguration per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="7d94d-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="7d94d-111">Per informazioni dettagliate su una determinata parte della configurazione, è possibile reindirizzare l'output in un altro cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d94d-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="7d94d-112">Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="7d94d-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="7d94d-113">![Esempio di output di Get-CsClsConfiguration.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Esempio di output di Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="7d94d-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="7d94d-114">Il risultato del cmdlet Visualizza la configurazione corrente del servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="7d94d-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7d94d-115">Impostazione di configurazione</span><span class="sxs-lookup"><span data-stu-id="7d94d-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="7d94d-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d94d-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-117"><strong>Identity</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-118">Identifica l'ambito e il nome per questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d94d-118">Identifies the scope and name for this configuration.</span></span> <span data-ttu-id="7d94d-119">Esiste una sola configurazione globale e una configurazione per ogni sito.</span><span class="sxs-lookup"><span data-stu-id="7d94d-119">There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-120"><strong>Scenari</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-121">Elenco di tutti gli scenari definiti per questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d94d-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-123">Termini di ricerca definiti per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="7d94d-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="7d94d-124">Office 365, non distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="7d94d-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-126">I gruppi di sicurezza definiti che controllano chi, ovvero i membri dei gruppi di sicurezza, possono vedere i computer in base al sito in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="7d94d-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="7d94d-127">Il sito, in questo contesto, è il sito definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7d94d-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-128"><strong>Aree geografiche</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-129">Le aree definite vengono usate per raccogliere SecurityGroups in un'area geografica, ad esempio EMEA.</span><span class="sxs-lookup"><span data-stu-id="7d94d-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-131">Percorso definito nella posizione in cui vengono scritti i file di log nei computer.</span><span class="sxs-lookup"><span data-stu-id="7d94d-131">Defined path to the location where log files are written on computers.</span></span> <span data-ttu-id="7d94d-132">CLSAgent scrive i file di log e viene eseguito nel contesto del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="7d94d-132">CLSAgent writes the log files and runs under the context of the Network Service.</span></span> <span data-ttu-id="7d94d-133">In questo caso,% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="7d94d-133">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-135">Il parametro indica la dimensione massima del file di log prima che venga creato un nuovo file di log di traccia eventi (ETL).</span><span class="sxs-lookup"><span data-stu-id="7d94d-135">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created.</span></span> <span data-ttu-id="7d94d-136">Viene creato un nuovo file di log quando viene raggiunta la dimensione definita anche se il tempo massimo impostato in EtlFileRolloverMinutes non è ancora stato raggiunto.</span><span class="sxs-lookup"><span data-stu-id="7d94d-136">A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-138">Intervallo di tempo massimo definito, in minuti, che un log può trascorrere prima che venga creato un nuovo file con estensione ETL.</span><span class="sxs-lookup"><span data-stu-id="7d94d-138">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created.</span></span> <span data-ttu-id="7d94d-139">Viene creato un nuovo file di log quando il timer scade anche se la dimensione massima impostata in EtlFileRolloverSizeMB non è ancora stata raggiunta.</span><span class="sxs-lookup"><span data-stu-id="7d94d-139">A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-141">Posizione in cui cercare i file di formato del messaggio di traccia.</span><span class="sxs-lookup"><span data-stu-id="7d94d-141">Location to search for the trace message format files.</span></span> <span data-ttu-id="7d94d-142">I file di formato del messaggio di traccia vengono usati per convertire i file binari in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="7d94d-142">The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-144">Percorso definito nella posizione in cui vengono scritti i file di cache nei computer.</span><span class="sxs-lookup"><span data-stu-id="7d94d-144">Defined path to the location where cache files are written on computers.</span></span> <span data-ttu-id="7d94d-145">CLSAgent scrive i file della cache ed è in esecuzione nel contesto del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="7d94d-145">CLSAgent writes the cache files and runs under the context of the Network Service.</span></span> <span data-ttu-id="7d94d-146">In questo caso,% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="7d94d-146">In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span> <span data-ttu-id="7d94d-147">Per impostazione predefinita, i file di cache e i file di log vengono scritti nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="7d94d-147">By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-149">Puoi definire un percorso UNC (Universal Naming Convention) per ricevere i file della cache durante le operazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7d94d-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-151">Definito come il tempo massimo, in giorni, in cui vengono conservati i file della cache.</span><span class="sxs-lookup"><span data-stu-id="7d94d-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-153">Definita come percentuale di spazio su disco che può essere usata dai file di cache.</span><span class="sxs-lookup"><span data-stu-id="7d94d-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-155">Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limitatore automatico della valvola a farfalla.</span><span class="sxs-lookup"><span data-stu-id="7d94d-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7d94d-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-157">Numero di volte in 60 secondi che il ComponentThrottleLimit può essere superato.</span><span class="sxs-lookup"><span data-stu-id="7d94d-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7d94d-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7d94d-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="7d94d-159">La versione minima di CLSAgent è consentita per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7d94d-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="7d94d-160">Questo elemento è destinato a Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d94d-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d94d-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d94d-161">See Also</span></span>


[<span data-ttu-id="7d94d-162">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d94d-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="7d94d-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7d94d-163">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="7d94d-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7d94d-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="7d94d-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7d94d-165">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="7d94d-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7d94d-166">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

