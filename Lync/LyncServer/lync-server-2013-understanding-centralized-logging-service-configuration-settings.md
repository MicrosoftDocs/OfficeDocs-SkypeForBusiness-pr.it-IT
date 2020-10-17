---
title: Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd4403bedbf6fe3b6983e6071a162ce02c16936
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527753"
---
# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3dab6-102">Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dab6-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dab6-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3dab6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3dab6-104">Il servizio di registrazione centralizzato è configurato per definire la modalità di raccolta del servizio di registrazione, il modo in cui verrà raccolta, la raccolta e le impostazioni del registro.</span><span class="sxs-lookup"><span data-stu-id="3dab6-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="3dab6-105">Queste impostazioni vengono definite globalmente, ovvero per l'intera distribuzione, o per un sito, ovvero un sito denominato nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3dab6-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="3dab6-106">Per tutte le attività di registrazione definite verranno utilizzate le impostazioni adatte all'identità utilizzata per i comandi di avvio, interruzione, scaricamento e ricerca dei log.</span><span class="sxs-lookup"><span data-stu-id="3dab6-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="3dab6-107">Per visualizzare la configurazione del servizio di registrazione centralizzata corrente</span><span class="sxs-lookup"><span data-stu-id="3dab6-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="3dab6-108">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3dab6-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3dab6-109">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="3dab6-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="3dab6-110">È possibile limitare o espandere l'ambito delle impostazioni di configurazione restituite definendo <CODE>-Identity</CODE> e un ambito, ad esempio "site: Redmond" per restituire solo CsClsConfiguration per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="3dab6-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="3dab6-111">Se si desiderano informazioni dettagliate su una determinata parte della configurazione, è possibile eseguire il piping dell'output in un altro cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3dab6-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="3dab6-112">Ad esempio, per ottenere informazioni dettagliate sugli scenari definiti nella configurazione per il sito "Redmond", digitare: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="3dab6-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="3dab6-113">![Output di esempio da Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio da Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="3dab6-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="3dab6-114">Il risultato del cmdlet consente di visualizzare la configurazione corrente del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="3dab6-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="3dab6-115">Impostazione di configurazione</span><span class="sxs-lookup"><span data-stu-id="3dab6-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="3dab6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dab6-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-117"><strong>Identità</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p103">Identifica l'ambito e il nome della configurazione corrente. Esistono una sola configurazione a livello globale e una sola per sito.</span><span class="sxs-lookup"><span data-stu-id="3dab6-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-120"><strong>Scenari</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-121">Elenco di tutti gli scenari definiti per questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="3dab6-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-123">Termini di ricerca definiti per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="3dab6-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="3dab6-124">Office 365 o Microsoft 365, non distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="3dab6-124">Office 365 or Microsoft 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-126">Gruppi di sicurezza definiti che controllano gli utenti, ovvero i membri dei gruppi di sicurezza, che possono vedere i computer in base al sito in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="3dab6-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="3dab6-127">Il sito, in questo contesto, è il sito come definito in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3dab6-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-128"><strong>Regioni</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-129">Le aree definite vengono utilizzate per raccogliere i SecurityGroups in un'area, ad esempio EMEA.</span><span class="sxs-lookup"><span data-stu-id="3dab6-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p106">Percorso definito della posizione nei computer in cui vengono scritti i file di log. CLSAgent scrive i file di log e viene eseguito nel contesto del servizio di rete. In tal caso, %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="3dab6-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p107">Il parametro indica le dimensioni massime del file di log prima che venga creato un nuovo file di log traccia eventi (.etl). Viene creato un nuovo file di log quando si raggiungono le dimensioni definite anche se non è stato ancora esaurito il tempo massimo impostato in EtlFileRolloverMinutes.</span><span class="sxs-lookup"><span data-stu-id="3dab6-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p108">Periodo di tempo massimo definito, espresso in minuti, che può trascorrere per un log prima che venga creato un nuovo file con estensione etl. Viene creato un nuovo file di log quando il timer scade anche se non sono ancora state raggiunte le dimensioni massime impostate in EtlFileRolloverSizeMB.</span><span class="sxs-lookup"><span data-stu-id="3dab6-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p109">Posizione in cui cercare i file TMF (Trace Message Format). I file TMF vengono utilizzati per convertire i file binari in un formato leggibile.</span><span class="sxs-lookup"><span data-stu-id="3dab6-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-p110">Percorso definito della posizione nei computer in cui vengono scritti i file di cache. CLSAgent scrive i file di cache e viene eseguito nel contesto del servizio di rete. In questo caso, %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Per impostazione predefinita, i file di cache e di log vengono scritti nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="3dab6-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-149">È possibile definire un percorso UNC (Universal Naming Convention) per ricevere i file di cache durante le operazioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3dab6-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-151">Definito come tempo massimo, espresso in giorni, di mantenimento dei file di cache.</span><span class="sxs-lookup"><span data-stu-id="3dab6-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-153">Definito come percentuale dello spazio su disco che può essere utilizzato dai file di cache.</span><span class="sxs-lookup"><span data-stu-id="3dab6-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-155">Definito come numero massimo di tracce al secondo che un componente può produrre prima che venga attivato il limite di velocità automatico.</span><span class="sxs-lookup"><span data-stu-id="3dab6-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="3dab6-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-157">Numero di volte nell'arco di 60 secondi in cui è possibile superare ComponentThrottleLimit.</span><span class="sxs-lookup"><span data-stu-id="3dab6-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="3dab6-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3dab6-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="3dab6-159">Versione minima di CLSAgent di cui è consentita l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3dab6-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="3dab6-160">Questo elemento è destinato a Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3dab6-160">This element is intended for Office 365 or Microsoft 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3dab6-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dab6-161">See Also</span></span>


[<span data-ttu-id="3dab6-162">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dab6-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="3dab6-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dab6-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="3dab6-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dab6-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="3dab6-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dab6-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="3dab6-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3dab6-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

