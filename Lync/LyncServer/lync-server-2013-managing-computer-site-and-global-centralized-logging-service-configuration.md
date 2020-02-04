---
title: Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globali
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
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="53674-102">Gestione della configurazione del servizio di registrazione centralizzata di computer, siti e globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53674-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53674-103">_**Argomento Ultima modifica:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="53674-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="53674-104">Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer, un pool di computer, in un ambito del sito, ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione, o in un ambito globale (ovvero , tutti i computer e i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="53674-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="53674-105">Per configurare l'ambito del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="53674-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="53674-106">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="53674-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="53674-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="53674-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="53674-108">Windows PowerShell offre altre opzioni e opzioni di configurazione aggiuntive che non sono disponibili con CLSController. exe.</span><span class="sxs-lookup"><span data-stu-id="53674-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="53674-109">CLSController offre un metodo rapido e conciso per eseguire comandi, ma è limitato al set di comandi disponibili per CLSController.</span><span class="sxs-lookup"><span data-stu-id="53674-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="53674-110">Windows PowerShell non si limita solo al comando disponibile per il processore di comandi di CLSController e fornisce un set di comandi più ampio e un set di opzioni più completo.</span><span class="sxs-lookup"><span data-stu-id="53674-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="53674-111">Ad esempio, CLSController. exe offre una delle opzioni di ambito per-computer e-pool.</span><span class="sxs-lookup"><span data-stu-id="53674-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="53674-112">Con Windows PowerShell puoi indicare i computer o i pool nella maggior parte dei comandi e quando Definisci nuovi scenari (CLSController ha un numero limitato di scenari che non sono modificabili dall'utente) puoi definire un sito o un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="53674-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="53674-113">Questa potente funzionalità di Windows PowerShell consente di definire uno scenario di un sito o di un ambito globale, ma limita la registrazione effettiva a un computer o a un pool.</span><span class="sxs-lookup"><span data-stu-id="53674-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="53674-114">Esistono differenze sostanziali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="53674-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="53674-115">Windows PowerShell offre un metodo RTF per configurare e definire scenari e per riutilizzare questi scenari in modo significativo per gli scenari di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="53674-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="53674-116">Mentre CLSController offre un modo rapido ed efficiente per emettere comandi e ottenere risultati, il set di comandi per CLSController è limitato dai comandi finiti disponibili dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="53674-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="53674-117">Diversamente dai cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire l'ambito a livello di sito o globale e molte altre limitazioni di un set di comandi finito che non può essere configurato in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="53674-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="53674-118">Mentre CLSController offre un mezzo per l'esecuzione veloce, Windows PowerShell offre un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.</span><span class="sxs-lookup"><span data-stu-id="53674-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="53674-119">Un singolo ambito del computer può essere definito durante l'esecuzione di un comando [Cerca-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) usando il parametro – Computers.</span><span class="sxs-lookup"><span data-stu-id="53674-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="53674-120">Il parametro – Computers accetta un elenco delimitato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53674-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="53674-121">È anche possibile definire i pool e un elenco di pool separati da virgole per cui si vogliono eseguire i comandi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="53674-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="53674-122">Il sito e gli ambiti globali sono definiti nei cmdlet **nuovo-**, **set-** e **Rimuovi-** servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="53674-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="53674-123">Gli esempi seguenti illustrano come impostare un sito e un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="53674-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="53674-124">I comandi visualizzati possono contenere parametri e concetti trattati in altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="53674-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="53674-125">I comandi di esempio hanno lo scopo di dimostrare l'uso del parametro <STRONG>– Identity</STRONG> per definire l'ambito e gli altri parametri sono inclusi per la completezza e per specificare l'ambito.</span><span class="sxs-lookup"><span data-stu-id="53674-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="53674-126">Per informazioni dettagliate sui cmdlet <STRONG>Set-CsClsConfiguration</STRONG> , vedere <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="53674-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="53674-127">Per recuperare la configurazione del servizio di registrazione centralizzata corrente</span><span class="sxs-lookup"><span data-stu-id="53674-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="53674-128">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-129">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="53674-130">Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornare una configurazione esistente.</span><span class="sxs-lookup"><span data-stu-id="53674-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="53674-131">Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni simili allo screenshot seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:</span><span class="sxs-lookup"><span data-stu-id="53674-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="53674-132">![Output di esempio di Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Output di esempio di Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="53674-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="53674-133">Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer</span><span class="sxs-lookup"><span data-stu-id="53674-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="53674-134">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-135">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="53674-136">Quando si usa il primo esempio in cui **Get-CsClsConfiguration** non specifica parametri, il comando fa riferimento all'Central Management store per i dati.</span><span class="sxs-lookup"><span data-stu-id="53674-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="53674-137">Se specifichi il parametro-LocalStore, il comando fa riferimento al computer LocalStore invece che a Central Management store.</span><span class="sxs-lookup"><span data-stu-id="53674-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="53674-138">Per recuperare un elenco di scenari attualmente definiti</span><span class="sxs-lookup"><span data-stu-id="53674-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="53674-139">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-140">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="53674-141">Ad esempio, per recuperare gli scenari definiti nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="53674-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="53674-142">Il cmdlet **Get-CsClsConfiguration** Visualizza sempre gli scenari che fanno parte di una determinata configurazione dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="53674-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="53674-143">Nella maggior parte dei casi, tutti gli scenari non vengono visualizzati e vengono troncati.</span><span class="sxs-lookup"><span data-stu-id="53674-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="53674-144">Il comando usato qui elenca tutti gli scenari e le informazioni parziali sui provider, le impostazioni e i contrassegni usati.</span><span class="sxs-lookup"><span data-stu-id="53674-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="53674-145">Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53674-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="53674-146">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-147">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="53674-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="53674-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="53674-149">Il comando indica a CLSAgent su ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="53674-149">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="53674-150">I computer e i pool in tutti i siti sono interessati dal comando e impostano il valore di rollover del log di traccia configurato su 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="53674-150">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="53674-151">Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53674-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="53674-152">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-153">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="53674-154">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="53674-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="53674-155">Come indicato nell'esempio, la posizione predefinita dei file di log è%TEMP%\Tracing.</span><span class="sxs-lookup"><span data-stu-id="53674-155">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="53674-156">Tuttavia, poiché in realtà è CLSAgent che sta scrivendo il file e CSLAgent viene eseguito come servizio di rete, la variabile% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="53674-156">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="53674-157">Il comando indica a CLSAgent su ogni computer e pool nel sito Redmond di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="53674-157">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="53674-158">I computer e i pool in altri siti non saranno interessati dal comando e continueranno a usare il valore di rollover del log di traccia attualmente configurato per impostazione predefinita (20 megabyte) o durante l'inizio della sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="53674-158">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="53674-159">Per creare una nuova configurazione del servizio di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="53674-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="53674-160">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-161">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="53674-162">New-CsClsConfiguration offre l'accesso a un numero elevato di impostazioni di configurazione facoltative.</span><span class="sxs-lookup"><span data-stu-id="53674-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="53674-163">Per informazioni dettagliate sulle opzioni di configurazione, vedere <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53674-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="53674-164">Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per i file di log, digitare:</span><span class="sxs-lookup"><span data-stu-id="53674-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="53674-165">È consigliabile pianificare con attenzione la creazione di nuove configurazioni e come definire nuove proprietà per il servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="53674-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="53674-166">È necessario prestare attenzione a apportare modifiche e verificare che sia possibile comprendere l'impatto sulla possibilità di registrare correttamente gli scenari di problemi.</span><span class="sxs-lookup"><span data-stu-id="53674-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="53674-167">È necessario apportare modifiche alla configurazione che rafforzerà la possibilità di gestire i log in una dimensione e un periodo di rollover che consentiranno di risolvere i problemi quando si presenta.</span><span class="sxs-lookup"><span data-stu-id="53674-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="53674-168">Per rimuovere una configurazione del servizio di registrazione centralizzata esistente</span><span class="sxs-lookup"><span data-stu-id="53674-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="53674-169">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53674-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="53674-170">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="53674-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="53674-171">Ad esempio, per rimuovere una configurazione centralizzata del servizio di registrazione creata per aumentare il tempo di rollover del file di log, aumentare le dimensioni del file di log di rollover e impostare la posizione della cache del file di log su una condivisione di rete come segue:</span><span class="sxs-lookup"><span data-stu-id="53674-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="53674-172">Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".</span><span class="sxs-lookup"><span data-stu-id="53674-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="53674-173">Se si sceglie di rimuovere una configurazione a livello di sito, il sito utilizzerà le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="53674-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53674-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53674-174">See Also</span></span>


[<span data-ttu-id="53674-175">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53674-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="53674-176">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53674-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="53674-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="53674-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="53674-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="53674-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="53674-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="53674-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="53674-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="53674-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

