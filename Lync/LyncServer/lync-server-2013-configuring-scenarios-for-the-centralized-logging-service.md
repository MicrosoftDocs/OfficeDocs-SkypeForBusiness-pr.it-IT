---
title: 'Lync Server 2013: configurazione degli scenari per il servizio di registrazione centralizzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="48131-102">Configurazione di scenari per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48131-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48131-103">_**Argomento Ultima modifica:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="48131-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="48131-104">Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e i provider da usare nel servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="48131-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="48131-105">Usando gli scenari, puoi abilitare o disabilitare la traccia sui provider, ad esempio S4, SIPStack, IM e Presence.</span><span class="sxs-lookup"><span data-stu-id="48131-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="48131-106">Configurando uno scenario, è possibile raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.</span><span class="sxs-lookup"><span data-stu-id="48131-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="48131-107">Se si scopre che è necessario modificare uno scenario in base alle esigenze di risoluzione dei problemi e alla registrazione, gli strumenti di debug di Lync Server 2013 forniscono un modulo di Windows PowerShell denominato *ClsController. psm1* che contiene una funzione denominata *Edit-CsClsScenario*.</span><span class="sxs-lookup"><span data-stu-id="48131-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="48131-108">Lo scopo del modulo consiste nel modificare le proprietà dello scenario denominato.</span><span class="sxs-lookup"><span data-stu-id="48131-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="48131-109">In questo argomento sono disponibili alcuni esempi di funzionamento di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="48131-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="48131-110">Gli strumenti di debug di Lync Server 2013 vengono scaricati dal collegamento seguente:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="48131-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="48131-111">Per un ambito specifico, ovvero sito, globale, pool o computer, è possibile eseguire un massimo di due scenari in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="48131-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="48131-112">Per determinare gli scenari attualmente in uso, usare Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span><span class="sxs-lookup"><span data-stu-id="48131-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="48131-113">Usando Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, è possibile modificare in modo dinamico gli scenari in uso.</span><span class="sxs-lookup"><span data-stu-id="48131-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="48131-114">È possibile modificare gli scenari in corso durante una sessione di registrazione per modificare o affinare i dati che si stanno raccogliendo e da quali provider.</span><span class="sxs-lookup"><span data-stu-id="48131-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="48131-115">Per eseguire le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="48131-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="48131-116">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati personalmente, eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48131-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="48131-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="48131-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="48131-118">La parte restante di questo argomento illustra come definire uno scenario, modificare uno scenario, recuperare gli scenari in uso, rimuovere uno scenario e specificare lo scenario che contiene per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="48131-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="48131-119">Esistono due modi per emettere comandi di servizio di registrazione centralizzati.</span><span class="sxs-lookup"><span data-stu-id="48131-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="48131-120">Per impostazione predefinita, è possibile usare CLSController. exe nella directory C\\: programmi\\comuni di\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="48131-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="48131-121">In alternativa, puoi usare Lync Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48131-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="48131-122">La distinzione importante è che quando si usa CLSController. exe alla riga di comando è disponibile una selezione limitata di scenari.</span><span class="sxs-lookup"><span data-stu-id="48131-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="48131-123">Quando si usa Windows PowerShell, è possibile definire nuovi scenari da usare nelle sessioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="48131-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="48131-124">Come è stato introdotto in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi di uno scenario sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="48131-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="48131-125">**Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="48131-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="48131-126">I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="48131-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="48131-127">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="48131-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="48131-128">Per informazioni dettagliate sulla configurazione dei provider, vedere [configurazione di provider per il servizio di registrazione centralizzata in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span><span class="sxs-lookup"><span data-stu-id="48131-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="48131-129">**Identity**   il parametro: Identity imposta l'ambito e il nome dello scenario.</span><span class="sxs-lookup"><span data-stu-id="48131-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="48131-130">Ad esempio, puoi impostare un ambito di "globale" e identificare lo scenario con "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="48131-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="48131-131">Quando si combinano i due, si definisce l'identità, ad esempio "Global/LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="48131-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="48131-132">Facoltativamente, è possibile usare i parametri-Name e-Parent.</span><span class="sxs-lookup"><span data-stu-id="48131-132">Optionally, you can use the –Name and –Parent parameters.</span></span> <span data-ttu-id="48131-133">Puoi definire il parametro Name per identificare in modo univoco lo scenario.</span><span class="sxs-lookup"><span data-stu-id="48131-133">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="48131-134">Se si usa nome, è necessario usare anche l'elemento padre per aggiungere lo scenario a globale o a sito.</span><span class="sxs-lookup"><span data-stu-id="48131-134">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48131-135">Se si usano i parametri Name e Parent, non è possibile usare il parametro <STRONG>– Identity</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="48131-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="48131-136">Per creare un nuovo scenario con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="48131-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="48131-137">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-138">Per creare un nuovo scenario per una sessione di registrazione, USA [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e Definisci il nome dello scenario, ovvero il modo in cui verrà identificato in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="48131-138">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="48131-139">Scegliere un tipo di formato di registrazione da WPP (ovvero il preprocessore di traccia del software Windows ed è il valore predefinito), EventLog (ovvero il formato del log eventi di Windows) o IISLog (ovvero file in formato ASCII basato sul formato del file di log di IIS).</span><span class="sxs-lookup"><span data-stu-id="48131-139">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="48131-140">Definire quindi il livello (definito in livelli di registrazione in questo argomento) e i contrassegni (come definito in contrassegni in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="48131-140">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="48131-141">Per questo scenario di esempio, usiamo LyssProvider come variabile di provider di esempio.</span><span class="sxs-lookup"><span data-stu-id="48131-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="48131-142">Per creare uno scenario usando le opzioni definite, digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="48131-143">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="48131-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="48131-144">Formato alternativo con-nome e-padre:</span><span class="sxs-lookup"><span data-stu-id="48131-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="48131-145">Per creare un nuovo scenario con più provider con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="48131-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="48131-146">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-147">Si è limitati a due scenari per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="48131-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="48131-148">Tuttavia, non si è limitati a un determinato numero di provider.</span><span class="sxs-lookup"><span data-stu-id="48131-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="48131-149">In questo esempio, supponiamo di avere creato tre provider e di assegnare tutti e tre allo scenario che stai definendo.</span><span class="sxs-lookup"><span data-stu-id="48131-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="48131-150">I nomi delle variabili del provider sono LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="48131-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="48131-151">Per definire e assegnare più provider a uno scenario, digitare quanto segue in un prompt dei comandi di Lync Server Management Shell o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48131-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48131-152">Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> usando è nota come <EM>splatting</EM>.</span><span class="sxs-lookup"><span data-stu-id="48131-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="48131-153">Per informazioni dettagliate su splatting in Windows PowerShell, <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>vedere.</span><span class="sxs-lookup"><span data-stu-id="48131-153">For details about splatting in Windows PowerShell, see <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="48131-154">Per modificare uno scenario esistente con il cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="48131-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="48131-155">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-156">Si è limitati a due scenari per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="48131-156">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="48131-157">È possibile modificare gli scenari in esecuzione in qualsiasi momento, anche quando è in corso una sessione di acquisizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="48131-157">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="48131-158">Se si ridefiniscono gli scenari in uso, la sessione di registrazione corrente smetterà di usare lo scenario rimosso e quindi inizierà a usare il nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="48131-158">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="48131-159">Tuttavia, le informazioni di registrazione acquisite con lo scenario rimosso restano nei registri acquisiti.</span><span class="sxs-lookup"><span data-stu-id="48131-159">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="48131-160">Per definire un nuovo scenario, eseguire le operazioni seguenti, ad esempio supponendo che l'aggiunta di un provider già definito denominato "S4Provider":</span><span class="sxs-lookup"><span data-stu-id="48131-160">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="48131-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="48131-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="48131-162">Se si vuole sostituire i provider, definire un singolo provider o un elenco di provider separati da virgole per sostituire il set corrente.</span><span class="sxs-lookup"><span data-stu-id="48131-162">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="48131-163">Se si vuole sostituire solo uno di molti provider, aggiungere i provider correnti con i nuovi provider per creare un nuovo set di provider che contiene sia i nuovi provider che i provider esistenti.</span><span class="sxs-lookup"><span data-stu-id="48131-163">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="48131-164">Per sostituire tutti i provider con un nuovo set, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48131-164">To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="48131-165">Ad esempio, per sostituire il set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="48131-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="48131-166">Per sostituire solo il provider $LyssProvider dal set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48131-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="48131-167">Per rimuovere uno scenario esistente con il cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="48131-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="48131-168">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-169">Se si vuole rimuovere uno scenario definito in precedenza, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="48131-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="48131-170">Ad esempio, per rimuovere il sito scenario definito: Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="48131-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="48131-171">Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite sono ancora disponibili nei registri in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="48131-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="48131-172">Per caricare e scaricare il cmdlet Edit-CsClsScenario usando il modulo ClsController. psm1</span><span class="sxs-lookup"><span data-stu-id="48131-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="48131-173">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="48131-174">Il modulo ClsController. psm1 viene fornito come download Web separato.</span><span class="sxs-lookup"><span data-stu-id="48131-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="48131-175">Il modulo fa parte degli strumenti di debug di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48131-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="48131-176">Per impostazione predefinita, gli strumenti di debug sono installati nella directory C:\Program Files\Lync Server 2013 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="48131-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="48131-177">In Windows PowerShell digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="48131-178">Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48131-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="48131-179">Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, <CODE>Get-Help Edit-CsClsScenario</CODE>Digitare.</span><span class="sxs-lookup"><span data-stu-id="48131-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="48131-180">Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="48131-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="48131-181">Per scaricare i moduli, digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="48131-182">Il riuscito scarico del modulo restituisce il prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48131-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="48131-183">Per verificare che il modulo sia scaricato, digitare <CODE>Get-Help Edit-CsClsScenario</CODE>.</span><span class="sxs-lookup"><span data-stu-id="48131-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="48131-184">Windows PowerShell tenterà di individuare la guida per il cmdlet e non riesce.</span><span class="sxs-lookup"><span data-stu-id="48131-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="48131-185">Per rimuovere un provider esistente da uno scenario con il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="48131-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="48131-186">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-187">Per rimuovere un provider dallo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="48131-188">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="48131-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="48131-189">I parametri ScenarioName e ProviderName sono posizionali, ovvero devono essere definiti nella posizione prevista nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="48131-189">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="48131-190">Il nome del parametro non deve essere definito in modo esplicito se il nome dello scenario è nella posizione due e il provider è nella posizione tre, in relazione al nome del cmdlet come posizione uno.</span><span class="sxs-lookup"><span data-stu-id="48131-190">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="48131-191">Usando queste informazioni, il comando precedente verrebbe tipizzato come segue:</span><span class="sxs-lookup"><span data-stu-id="48131-191">Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="48131-192">La posizione di posizionamento dei valori di parametro si applica solo a-scenario e-provider.</span><span class="sxs-lookup"><span data-stu-id="48131-192">The positional placing of the parameter values applies only to –Scenario and –Provider.</span></span> <span data-ttu-id="48131-193">Tutti gli altri parametri devono essere definiti in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="48131-193">All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="48131-194">Per aggiungere un provider a uno scenario con il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="48131-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="48131-195">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="48131-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="48131-196">Per aggiungere un provider allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="48131-197">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="48131-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="48131-198">\-LogLevel può essere di tipo Fatal, Error, Warning, info, Verbose, debug o all.</span><span class="sxs-lookup"><span data-stu-id="48131-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="48131-199">: I contrassegni possono essere uno dei contrassegni supportati dal provider, ad esempio\_TF Component,\_TF diag.</span><span class="sxs-lookup"><span data-stu-id="48131-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="48131-200">-Flags può anche essere di valore ALL</span><span class="sxs-lookup"><span data-stu-id="48131-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="48131-201">L'esempio precedente può anche essere digitato usando la caratteristica posizionali del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="48131-201">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="48131-202">Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="48131-202">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

