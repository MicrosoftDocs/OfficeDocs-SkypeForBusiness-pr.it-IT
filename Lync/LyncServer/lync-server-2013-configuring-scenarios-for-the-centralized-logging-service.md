---
title: 'Lync Server 2013: configurazione degli scenari per il servizio di registrazione centralizzato'
description: 'Lync Server 2013: configurazione degli scenari per il servizio di registrazione centralizzato.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf3f569ae8d2596f735851ae3d5d6c55f022b09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575862"
---
# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="d2a22-103">Configurazione degli scenari per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2a22-103">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2a22-104">_**Ultimo argomento modificato:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d2a22-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d2a22-105">Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e quali provider utilizzare nel servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="d2a22-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="d2a22-106">Attraverso gli scenari si attivano o disattivano le tracce per i provider (ad esempio, S4, SIPStack, messaggistica immediata e presenza).</span><span class="sxs-lookup"><span data-stu-id="d2a22-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="d2a22-107">Attraverso la configurazione di uno scenario, è possibile raggruppare tutti i provider per una data raccolta logica relativa a un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="d2a22-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="d2a22-108">Se si rileva che è necessario modificare uno scenario per soddisfare la risoluzione dei problemi e le esigenze di registrazione, gli strumenti di debug di Lync Server 2013 forniscono un modulo di Windows PowerShell denominato *ClsController. psm1* che contiene una funzione denominata *Edit-CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="d2a22-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="d2a22-109">Il modulo consente di modificare le proprietà dello scenario.</span><span class="sxs-lookup"><span data-stu-id="d2a22-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="d2a22-110">In questo argomento sono forniti esempi di funzionamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="d2a22-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="d2a22-111">Gli strumenti di debug di Lync Server 2013 vengono scaricati dal collegamento seguente: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="d2a22-111">The Lync Server 2013 Debug Tools are downloaded from the following link: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d2a22-112">Per un determinato ambito (sito, globale, pool o computer), è possibile eseguire un massimo di due scenari alla volta.</span><span class="sxs-lookup"><span data-stu-id="d2a22-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="d2a22-113">Per determinare gli scenari attualmente in esecuzione, utilizzare Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="d2a22-113">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="d2a22-114">Utilizzando Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, è possibile modificare in modo dinamico gli scenari in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d2a22-114">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="d2a22-115">È possibile modificare gli scenari durante una sessione di registrazione, al fine di regolare o rifinire i dati che vengono raccolti, nonché i provider.</span><span class="sxs-lookup"><span data-stu-id="d2a22-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="d2a22-116">Per eseguire le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="d2a22-116">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d2a22-117">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati dall'utente, eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d2a22-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="d2a22-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2a22-118">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="d2a22-119">Questo argomento si concentra sulle modalità di definizione di uno scenario, modifica di uno scenario, recupero degli scenari in esecuzione, rimozione di uno scenario e specificazione del contenuto di uno scenario, per l'ottimizzazione della risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="d2a22-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="d2a22-120">Esistono due modi per emettere comandi del servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="d2a22-120">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="d2a22-121">È possibile utilizzare l'CLSController.exe che si trova, per impostazione predefinita, nella directory C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="d2a22-121">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="d2a22-122">In alternativa, è possibile utilizzare Lync Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2a22-122">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="d2a22-123">Quando si utilizza CLSController.exe, nella riga di comando esiste una selezione di scenari disponibili finita.</span><span class="sxs-lookup"><span data-stu-id="d2a22-123">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="d2a22-124">Quando si utilizza Windows PowerShell, è possibile definire nuovi scenari per l'utilizzo nelle sessioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d2a22-124">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="d2a22-125">Come descritto in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi di uno scenario sono:</span><span class="sxs-lookup"><span data-stu-id="d2a22-125">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="d2a22-126">**Provider**     Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger cosa dovrebbe raccogliere i log dal motore di traccia.</span><span class="sxs-lookup"><span data-stu-id="d2a22-126">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="d2a22-127">I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="d2a22-127">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="d2a22-128">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server in cui il servizio di registrazione centralizzato può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="d2a22-128">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="d2a22-129">Per informazioni dettagliate sulla configurazione dei provider, vedere [configurazione di provider per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="d2a22-129">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="d2a22-130">**Identità**     Il parametro – Identity consente di impostare l'ambito e il nome dello scenario.</span><span class="sxs-lookup"><span data-stu-id="d2a22-130">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="d2a22-131">Ad esempio, è possibile impostare un ambito “globale” e identificare lo scenario con “LyssServiceScenario”.</span><span class="sxs-lookup"><span data-stu-id="d2a22-131">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="d2a22-132">Quando si combinano le due cose, si definisce il parametro Identity (ad esempio, “global/LyssServiceScenario”).</span><span class="sxs-lookup"><span data-stu-id="d2a22-132">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="d2a22-p107">Facoltativamente è possibile utilizzare i parametri –Name and –Parent. Il parametro Name identifica lo scenario in maniera univoca. Se si utilizza il parametro Name, è necessario utilizzare anche il parametro Parent per aggiungere lo scenario all'ambito globale o sito.</span><span class="sxs-lookup"><span data-stu-id="d2a22-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2a22-136">Se si utilizzano i parametri Name e Parent, non è possibile utilizzare il parametro <STRONG>–Identity</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d2a22-136">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d2a22-137">Per creare un nuovo scenario con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d2a22-137">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d2a22-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-139">Per creare un nuovo scenario per una sessione di registrazione, utilizzare [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e definire il nome dello scenario (ovvero, un'identificazione univoca).</span><span class="sxs-lookup"><span data-stu-id="d2a22-139">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="d2a22-140">Scegliere un tipo di formato di registrazione da WPP (ovvero, Windows software trace preprocessor e predefinito), EventLog (ovvero, il formato del registro eventi di Windows) o IISLog (ovvero, il file formato ASCII basato sul formato dei file di registro IIS).</span><span class="sxs-lookup"><span data-stu-id="d2a22-140">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="d2a22-141">Definire quindi il livello (Secondo la definizione dei livelli di registrazione in questo argomento) e i contrassergni (secondo la definizione dei contrassegni in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="d2a22-141">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="d2a22-142">In questo scenario di esempio, utilizzeremo LyssProvider come provider variabile di esempio.</span><span class="sxs-lookup"><span data-stu-id="d2a22-142">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="d2a22-143">Per creare uno scenario utilizzando le opzioni definite, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-143">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="d2a22-144">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2a22-144">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="d2a22-145">Il formato alternativo, –Name e –Parent:</span><span class="sxs-lookup"><span data-stu-id="d2a22-145">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="d2a22-146">Per creare un nuovo scenario con provider multipli con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d2a22-146">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d2a22-147">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-148">Esiste un limite di due scenari per ambito.</span><span class="sxs-lookup"><span data-stu-id="d2a22-148">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="d2a22-149">Non esiste, tuttavia, un limite fisso di provider.</span><span class="sxs-lookup"><span data-stu-id="d2a22-149">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="d2a22-150">In questo esempio, si supponga di aver creato tre provider, e di volerli assegnare tutti a uno scenario che si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="d2a22-150">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="d2a22-151">I nomi variabili dei provider sono LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="d2a22-151">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="d2a22-152">Per definire e assegnare più provider a uno scenario, digitare il comando seguente in un prompt dei comandi di Lync Server Management Shell o di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d2a22-152">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2a22-153">Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori utilizzando <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> è nota come <EM>splatting</EM>.</span><span class="sxs-lookup"><span data-stu-id="d2a22-153">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="d2a22-154">Per informazioni dettagliate su splatting in Windows PowerShell, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A> .</span><span class="sxs-lookup"><span data-stu-id="d2a22-154">For details about splatting in Windows PowerShell, see <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="d2a22-155">Per modificare uno scenario esistente tramite il cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d2a22-155">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d2a22-156">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-156">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-p111">Esiste un limite di due scenari per ambito. È possibile cambiare in qualunque momento lo scenario eseguito, anche quando è in esecuzione una sessione di raccolta di registri. Se si definisce nuovamente lo scenario in esecuzione, la sessione di raccolta smetterà di utilizzare lo scenario rimosso, e inizierà ad utilizzare il nuovo scenario. Tuttavia, le informazioni raccolte con lo scenario rimosso rimarranno nei registri. Per definire un nuovo scenario, eseguire le operazioni seguenti (supponiamo che è stato aggiunto un nome di provider già definito, chiamato “S4Provider”):</span><span class="sxs-lookup"><span data-stu-id="d2a22-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="d2a22-162">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2a22-162">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="d2a22-p112">Per sostituire un provider, definire un provider singolo o un elenco di provider separati da virgola a sostituzione dell'insieme esistente. Se si desidera sostituire uno dei molti provider, aggiungere i nuovi provider a quelli esistenti, per creare un insieme di provider contenente sia i provider esistenti che quelli nuovi. Per sostituire tutti i provider con un nuovo insieme, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="d2a22-166">Ad esempio, per sostituire l'insieme esistente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="d2a22-166">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="d2a22-167">Per sostituire soltanto il provider $LyssProvider dall'insieme corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-167">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="d2a22-168">Per rimuovere uno scenario esistente tramite il cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="d2a22-168">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="d2a22-169">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-170">Per rimuovere uno scenario precedentemente definito, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-170">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="d2a22-171">Ad esempio, per rimuovere lo scenario definito:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="d2a22-171">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="d2a22-172">Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite restano disponibili nei registri per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d2a22-172">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="d2a22-173">Per caricare e scaricare il cmdlet Edit-CsClsScenario attraverso il modulo ClsController.psm1</span><span class="sxs-lookup"><span data-stu-id="d2a22-173">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="d2a22-174">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-174">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2a22-175">Il modulo ClsController.psm1 è fornito come download Web separato.</span><span class="sxs-lookup"><span data-stu-id="d2a22-175">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="d2a22-176">Il modulo fa parte degli strumenti di debug di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2a22-176">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="d2a22-177">Per impostazione predefinita, gli strumenti di debug sono installati nella cartella C:\Program Files\Lync Server 2013\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="d2a22-177">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="d2a22-178">Da Windows PowerShell, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-178">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d2a22-179">Il corretto caricamento del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2a22-179">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d2a22-180">Per verificare che il modulo sia caricato e che Edit-CsClsScenario sia disponibile, digitare <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="d2a22-180">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="d2a22-181">Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="d2a22-181">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="d2a22-182">Per scaricare i moduli, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-182">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d2a22-183">Lo scaricamento riuscito del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2a22-183">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="d2a22-184">Per verificare che il modulo sia scaricato, digitare <CODE>Get-Help Edit-CsClsScenario</CODE> .</span><span class="sxs-lookup"><span data-stu-id="d2a22-184">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="d2a22-185">Windows PowerShell tenterà di individuare la guida per il cmdlet e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d2a22-185">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d2a22-186">Per rimuovere un provider esistente da uno scenario attraverso il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d2a22-186">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="d2a22-187">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-187">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-188">Per rimuovere un provider dallo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-188">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="d2a22-189">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2a22-189">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="d2a22-p116">I parametri ScenarioName e ProviderName sono parametri relativi alla posizione, ovvero devono essere definiti nella posizione della riga di comando attesa. Il nome del parametro non deve essere definito esplicitamente se il nome dello scenario si trova in posizione due e il provider in posizione tre, in relazione al nome del cmdlet in posizione uno. Attraverso queste informazioni, il comando precedente verrebbe digitato come:</span><span class="sxs-lookup"><span data-stu-id="d2a22-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="d2a22-p117">Questo tipo di posizionamento del valore del parametro si applica soltanto ai parametri –Scenario e –Provider. Tutti gli altri parametri devono essere definiti esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="d2a22-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="d2a22-195">Per aggiungere un provider esistente a uno scenario attraverso il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="d2a22-195">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="d2a22-196">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2a22-196">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2a22-197">Per aggiungere un provider allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-197">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="d2a22-198">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d2a22-198">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="d2a22-199">\-LogLevel può essere di tipo fatale, Error, Warning, info, Verbose, debug o all.</span><span class="sxs-lookup"><span data-stu-id="d2a22-199">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="d2a22-200">: I flag possono corrispondere a qualsiasi flag supportato dal provider, ad esempio TF \_ \_ diag.</span><span class="sxs-lookup"><span data-stu-id="d2a22-200">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="d2a22-201">–Il valore dei contrassegni, inoltre, può essere ALL</span><span class="sxs-lookup"><span data-stu-id="d2a22-201">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="d2a22-p119">L'esempio precedente può essere digitato anche attraverso la caratteristiche di posizione del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="d2a22-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

