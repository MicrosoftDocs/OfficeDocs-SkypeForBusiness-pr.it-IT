---
title: Configurazione del servizio di registrazione centralizzata del computer, del sito e globale
description: Gestione dei computer, del sito e della configurazione del servizio di registrazione centralizzata globale.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dee125d69e17664fddd0c32feb3048ffcf91b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570382"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="e9c56-103">Gestione del computer, del sito e della configurazione del servizio di registrazione centralizzata globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c56-103">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9c56-104">_**Ultimo argomento modificato:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="e9c56-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="e9c56-105">Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer, un pool di computer, in un ambito di sito, ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, oppure in un ambito globale (ovvero tutti i computer e i pool della distribuzione).</span><span class="sxs-lookup"><span data-stu-id="e9c56-105">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="e9c56-106">Per configurare l'ambito del servizio di registrazione centralizzato mediante Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="e9c56-106">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="e9c56-107">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e9c56-107">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="e9c56-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e9c56-108">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="e9c56-109">Windows PowerShell offre altre opzioni e altre opzioni di configurazione che non sono disponibili tramite CLSController.exe.</span><span class="sxs-lookup"><span data-stu-id="e9c56-109">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="e9c56-110">CLSController offre un metodo rapido e sintetico per eseguire i comandi, tuttavia è limitato al set di comandi disponibili per CLSController.</span><span class="sxs-lookup"><span data-stu-id="e9c56-110">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="e9c56-111">Windows PowerShell non è limitato solo al comando disponibile per il processore dei comandi di CLSController e fornisce un insieme più ampio di comandi e un insieme più ricco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="e9c56-111">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="e9c56-112">Ad esempio, CLSController.exe offre opzioni sull'ambito, ovvero computer e pool.</span><span class="sxs-lookup"><span data-stu-id="e9c56-112">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="e9c56-113">Con Windows PowerShell, è possibile indicare i computer o i pool nella maggior parte dei comandi e quando si definiscono nuovi scenari (CLSController dispone di un numero finito di scenari che non sono modificabili dall'utente) è possibile definire un sito o un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="e9c56-113">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="e9c56-114">Questa potente funzionalità di Windows PowerShell consente di definire uno scenario a un sito o a un ambito globale, ma limitare la registrazione effettiva a un computer o a un pool.</span><span class="sxs-lookup"><span data-stu-id="e9c56-114">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="e9c56-115">Sono presenti differenze fondamentali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="e9c56-115">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="e9c56-116">Windows PowerShell fornisce un metodo RTF per la configurazione e la definizione degli scenari e per riutilizzare tali scenari in modo significativo per gli scenari di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e9c56-116">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="e9c56-117">Mentre CLSController non offre un modo rapido ed efficiente per eseguire comandi e ottenere risultati, il set di comandi di CLSController è limitato dal numero finito di comandi disponibili dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e9c56-117">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="e9c56-118">A differenza dei cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire gli ambiti a livello di sito o globale e molte altre limitazioni di un set di comandi finiti che non può essere configurato dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="e9c56-118">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="e9c56-119">Mentre CLSController fornisce un mezzo per l'esecuzione rapida, Windows PowerShell fornisce un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.</span><span class="sxs-lookup"><span data-stu-id="e9c56-119">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="e9c56-120">È possibile definire un singolo ambito del computer durante l'esecuzione di un comando [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) tramite il parametro – Computers.</span><span class="sxs-lookup"><span data-stu-id="e9c56-120">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="e9c56-121">Il parametro –Computers accetta un elenco con valori separati da virgole di nomi di dominio completi dei computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e9c56-121">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="e9c56-122">È inoltre possibile definire –Pools e un elenco di valori separati da virgole di pool in cui si desidera eseguire i comandi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e9c56-122">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="e9c56-123">I siti e gli ambiti globali sono definiti nei cmdlet **New-**, **set-** e **Remove-** centralizzated Logging Service.</span><span class="sxs-lookup"><span data-stu-id="e9c56-123">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="e9c56-124">Negli esempi seguenti viene illustrato come impostare un ambito a livello di sito o globale.</span><span class="sxs-lookup"><span data-stu-id="e9c56-124">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e9c56-125">I comandi illustrati possono contenere i parametri e concetti trattati in altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="e9c56-125">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="e9c56-126">I comandi di esempio servono a illustrare l'uso del parametro <STRONG>–Identity</STRONG> per definire l'ambito e gli altri parametri sono inclusi per completezza e per specificare l'ambito.</span><span class="sxs-lookup"><span data-stu-id="e9c56-126">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="e9c56-127">Per dettagli sui cmdlet <STRONG>Set-CsClsConfiguration</STRONG>, vedere <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> nella documentazione sulle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e9c56-127">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="e9c56-128">Per recuperare la configurazione del servizio di registrazione centralizzata corrente</span><span class="sxs-lookup"><span data-stu-id="e9c56-128">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e9c56-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-130">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-130">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="e9c56-131">Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornarne una esistente.</span><span class="sxs-lookup"><span data-stu-id="e9c56-131">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="e9c56-132">Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni analoghe alla schermata seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:</span><span class="sxs-lookup"><span data-stu-id="e9c56-132">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="e9c56-133">![Output di esempio da Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio da Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="e9c56-133">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="e9c56-134">Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer</span><span class="sxs-lookup"><span data-stu-id="e9c56-134">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="e9c56-135">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-136">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-136">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="e9c56-137">Quando si utilizza il primo esempio in cui **Get-CsClsConfiguration** non specifica alcun parametro, il comando fa riferimento all'archivio di gestione centrale per i dati.</span><span class="sxs-lookup"><span data-stu-id="e9c56-137">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="e9c56-138">Se si specifica il parametro – LocalStore, il comando fa riferimento al computer LocalStore anziché all'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="e9c56-138">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="e9c56-139">Per recuperare un elenco di scenari attualmente definiti</span><span class="sxs-lookup"><span data-stu-id="e9c56-139">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="e9c56-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-141">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-141">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="e9c56-142">Ad esempio, per recuperare gli scenari definiti nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="e9c56-142">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="e9c56-143">Il cmdlet **Get-CsClsConfiguration** visualizza sempre gli scenari che fanno parte della configurazione di un determinato ambito.</span><span class="sxs-lookup"><span data-stu-id="e9c56-143">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="e9c56-144">Nella maggior parte dei casi, non sono visualizzati tutti gli scenari e sono presenti troncamenti.</span><span class="sxs-lookup"><span data-stu-id="e9c56-144">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="e9c56-145">Il comando usato in questo caso elenca tutti gli scenari e informazioni parziali sui provider, le impostazioni e i flag in uso.</span><span class="sxs-lookup"><span data-stu-id="e9c56-145">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e9c56-146">Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9c56-146">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e9c56-147">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-148">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-148">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="e9c56-149">Esempio:</span><span class="sxs-lookup"><span data-stu-id="e9c56-149">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="e9c56-p109">Il comando indica al CLSAgent in ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. Il comando si applica a tutti i computer e i pool in tutti i siti e imposta il valore di rollover del log di traccia configurato su 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="e9c56-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="e9c56-152">Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9c56-152">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="e9c56-153">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-154">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-154">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="e9c56-155">Esempio:</span><span class="sxs-lookup"><span data-stu-id="e9c56-155">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e9c56-p110">Come si nota nell'esempio, il percorso predefinito dei file di log è %TEMP%\Tracing. Tuttavia, poiché il file viene in effetti scritto da CLSAgent il quale viene eseguito con l'account Servizio di rete, la variabile %TEMP% si espande in %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="e9c56-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="e9c56-p111">Il comando indica al CLSAgent in ogni computer e pool del sito Redmond di impostare le dimensioni del valore di rollover per il file di traccia su 40 megabyte. I computer e i pool in altri siti non verranno modificati dal comando e continueranno a usare il valore di rollover del log di traccia definito per impostazione predefinita (20 megabyte) o durante l'avvio della sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e9c56-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="e9c56-160">Per creare una nuova configurazione del servizio di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="e9c56-160">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e9c56-161">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-161">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-162">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-162">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e9c56-163">New-CsClsConfiguration offre accesso a numerose impostazioni di configurazione facoltative.</span><span class="sxs-lookup"><span data-stu-id="e9c56-163">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="e9c56-164">Per informazioni dettagliate sulle opzioni di configurazione, vedere <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9c56-164">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="e9c56-165">Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per tali file, occorre digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e9c56-165">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="e9c56-166">È consigliabile pianificare attentamente la creazione di nuove configurazioni e la modalità di definizione di nuove proprietà per il servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="e9c56-166">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="e9c56-167">È anche opportuno prestare attenzione alle modifiche che vi si apportano accertandosi di comprenderne l'impatto sulla capacità di registrare correttamente gli scenari dei problemi.</span><span class="sxs-lookup"><span data-stu-id="e9c56-167">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="e9c56-168">È consigliabile apportare alla configurazione modifiche in grado di migliorare la gestione dei log con dimensioni e periodi di rollover che consentano di risolvere i problemi quando si verificano.</span><span class="sxs-lookup"><span data-stu-id="e9c56-168">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="e9c56-169">Per rimuovere una configurazione del servizio di registrazione centralizzata esistente</span><span class="sxs-lookup"><span data-stu-id="e9c56-169">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="e9c56-170">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e9c56-170">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e9c56-171">Digitare quanto segue al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e9c56-171">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="e9c56-172">Ad esempio, per rimuovere una configurazione del servizio di registrazione centralizzata creata per aumentare il tempo di rollover dei file di registro, aumentare le dimensioni del file di registro di rollover e impostare il percorso della cache dei file di registro su una condivisione di rete, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e9c56-172">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e9c56-173">Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".</span><span class="sxs-lookup"><span data-stu-id="e9c56-173">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="e9c56-174">Se si sceglie di rimuovere una configurazione a livello di sito, il sito userà le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="e9c56-174">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9c56-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9c56-175">See Also</span></span>


[<span data-ttu-id="e9c56-176">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c56-176">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="e9c56-177">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9c56-177">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="e9c56-178">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e9c56-178">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="e9c56-179">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e9c56-179">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="e9c56-180">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e9c56-180">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="e9c56-181">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e9c56-181">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

