---
title: Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015
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
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Riepilogo: informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 8778530826cdbd0c3ecc5128385644f2191a858e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835186"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="8a52d-103">Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a52d-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a52d-104">**Riepilogo:** Informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a52d-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8a52d-105">Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e quali provider utilizzare nel servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="8a52d-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="8a52d-106">Attraverso gli scenari si attivano o disattivano le tracce per i provider (ad esempio, S4, SIPStack, messaggistica immediata e presenza).</span><span class="sxs-lookup"><span data-stu-id="8a52d-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="8a52d-107">Attraverso la configurazione di uno scenario, è possibile raggruppare tutti i provider per una data raccolta logica relativa a un problema specifico.</span><span class="sxs-lookup"><span data-stu-id="8a52d-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="8a52d-108">Se si rileva che è necessario modificare uno scenario per soddisfare le esigenze di registrazione e risoluzione dei problemi, gli strumenti di debug di Skype for Business Server 2015 forniscono un modulo di Windows PowerShell denominato ClsScenarioEdit. psm1 che contiene una funzione namedEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="8a52d-109">Il modulo consente di modificare le proprietà dello scenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="8a52d-110">In questo argomento sono forniti esempi di funzionamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="8a52d-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="8a52d-111">Scaricare gli [strumenti di debug](https://go.microsoft.com/fwlink/p/?LinkId=285257) di Skype for Business Server 2015 prima di proseguire.</span><span class="sxs-lookup"><span data-stu-id="8a52d-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8a52d-112">Per un determinato ambito (sito, globale, pool o computer), è possibile eseguire un massimo di due scenari alla volta.</span><span class="sxs-lookup"><span data-stu-id="8a52d-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="8a52d-113">Per determinare gli scenari attualmente in esecuzione, utilizzare Windows PowerShell e [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8a52d-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="8a52d-114">Utilizzando Windows PowerShell e [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), è possibile modificare in modo dinamico gli scenari in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8a52d-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="8a52d-115">È possibile modificare gli scenari durante una sessione di registrazione, al fine di regolare o rifinire i dati che vengono raccolti, nonché i provider.</span><span class="sxs-lookup"><span data-stu-id="8a52d-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="8a52d-116">Per eseguire le funzioni del servizio di registrazione centralizzato utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o del controllo di accesso basato sui ruoli di CsServerAdministrator oppure di un ruolo RBAC personalizzato che contenga uno dei due gruppi.</span><span class="sxs-lookup"><span data-stu-id="8a52d-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="8a52d-117">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi gli eventuali ruoli RBAC personalizzati creati dall'utente, eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a52d-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="8a52d-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a52d-118">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="8a52d-119">Questo argomento si concentra sulle modalità di definizione di uno scenario, modifica di uno scenario, recupero degli scenari in esecuzione, rimozione di uno scenario e specificazione del contenuto di uno scenario, per l'ottimizzazione della risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="8a52d-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="8a52d-120">È possibile utilizzare la shell di gestione di Skype for Business Server per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a52d-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="8a52d-121">Quando si utilizza Windows PowerShell, è possibile definire nuovi scenari per l'utilizzo nelle sessioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8a52d-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="8a52d-122">Come introdotti nel [servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md), gli elementi di uno scenario sono:</span><span class="sxs-lookup"><span data-stu-id="8a52d-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="8a52d-123">**Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger cosa dovrebbe raccogliere i log dal motore di traccia.</span><span class="sxs-lookup"><span data-stu-id="8a52d-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="8a52d-124">I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="8a52d-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="8a52d-125">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server in cui il servizio di registrazione centralizzato può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="8a52d-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="8a52d-126">Per informazioni dettagliate sulla configurazione dei provider, vedere [configurare i provider per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="8a52d-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="8a52d-127">**Identità** Il parametro-Identity consente di impostare l'ambito e il nome dello scenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="8a52d-128">Ad esempio, è possibile impostare un ambito di "globale" e identificare lo scenario con "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="8a52d-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="8a52d-129">Quando si combinano le due, si definisce l'identità (ad esempio, "Global/LyssServiceScenario").</span><span class="sxs-lookup"><span data-stu-id="8a52d-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="8a52d-130">Facoltativamente, è possibile utilizzare i parametri-Name e-Parent.</span><span class="sxs-lookup"><span data-stu-id="8a52d-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="8a52d-131">Il parametro Name identifica lo scenario in maniera univoca.</span><span class="sxs-lookup"><span data-stu-id="8a52d-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="8a52d-132">Se si utilizza il parametro Name, è necessario utilizzare anche il parametro Parent per aggiungere lo scenario all'ambito globale o sito.</span><span class="sxs-lookup"><span data-stu-id="8a52d-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a52d-133">Se si utilizzano i parametri Name e Parent, non è possibile utilizzare il parametro **-Identity** .</span><span class="sxs-lookup"><span data-stu-id="8a52d-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8a52d-134">Per creare un nuovo scenario con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8a52d-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8a52d-135">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-136">Per creare un nuovo scenario per una sessione di registrazione, utilizzare [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) e definire il nome dello scenario (ovvero, un'identificazione univoca).</span><span class="sxs-lookup"><span data-stu-id="8a52d-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="8a52d-137">Scegliere un tipo di formato di registrazione da WPP (ovvero, Windows software trace preprocessor e predefinito), EventLog (ovvero, il formato del registro eventi di Windows) o IISLog (ovvero, il file formato ASCII basato sul formato dei file di registro IIS).</span><span class="sxs-lookup"><span data-stu-id="8a52d-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="8a52d-138">Definire quindi il livello (Secondo la definizione dei livelli di registrazione in questo argomento) e i contrassergni (secondo la definizione dei contrassegni in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="8a52d-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="8a52d-139">In questo scenario di esempio, utilizzeremo LyssProvider come provider variabile di esempio.</span><span class="sxs-lookup"><span data-stu-id="8a52d-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="8a52d-140">Per creare uno scenario utilizzando le opzioni definite, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-140">To create a scenario using the options defined, type:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="8a52d-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a52d-141">For example:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="8a52d-142">Il formato alternativo using-Name e-Parent:</span><span class="sxs-lookup"><span data-stu-id="8a52d-142">The alternate format using -Name and -Parent:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="8a52d-143">Per creare un nuovo scenario con provider multipli con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8a52d-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8a52d-144">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-145">Esiste un limite di due scenari per ambito.</span><span class="sxs-lookup"><span data-stu-id="8a52d-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8a52d-146">Non esiste, tuttavia, un limite fisso di provider.</span><span class="sxs-lookup"><span data-stu-id="8a52d-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="8a52d-147">In questo esempio, si supponga di aver creato tre provider, e di volerli assegnare tutti a uno scenario che si sta definendo.</span><span class="sxs-lookup"><span data-stu-id="8a52d-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="8a52d-148">I nomi variabili dei provider sono LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="8a52d-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="8a52d-149">Per definire e assegnare più provider a uno scenario, digitare il comando seguente in un prompt dei comandi di Skype for Business Server Management Shell o di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a52d-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="8a52d-150">Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash dei valori utilizzando  `@{<variable>=<value1>, <value2>, <value>…}` è nota come assplatting.</span><span class="sxs-lookup"><span data-stu-id="8a52d-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="8a52d-151">Per informazioni dettagliate su splatting in Windows PowerShell, vedere [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760) .</span><span class="sxs-lookup"><span data-stu-id="8a52d-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="8a52d-152">Per modificare uno scenario esistente tramite il cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8a52d-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8a52d-153">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-154">Esiste un limite di due scenari per ambito.</span><span class="sxs-lookup"><span data-stu-id="8a52d-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="8a52d-155">È possibile cambiare in qualunque momento lo scenario eseguito, anche quando è in esecuzione una sessione di raccolta di registri.</span><span class="sxs-lookup"><span data-stu-id="8a52d-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="8a52d-156">Se si definisce nuovamente lo scenario in esecuzione, la sessione di raccolta smetterà di utilizzare lo scenario rimosso, e inizierà ad utilizzare il nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="8a52d-157">Tuttavia, le informazioni raccolte con lo scenario rimosso rimarranno nei registri.</span><span class="sxs-lookup"><span data-stu-id="8a52d-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="8a52d-158">Per definire un nuovo scenario, eseguire le operazioni seguenti (ovvero, presupponendo che l'aggiunta di un provider già definito denominato "S4Provider"):</span><span class="sxs-lookup"><span data-stu-id="8a52d-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="8a52d-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a52d-159">For example:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="8a52d-p112">Per sostituire un provider, definire un provider singolo o un elenco di provider separati da virgola a sostituzione dell'insieme esistente. Se si desidera sostituire uno dei molti provider, aggiungere i nuovi provider a quelli esistenti, per creare un insieme di provider contenente sia i provider esistenti che quelli nuovi. Per sostituire tutti i provider con un nuovo insieme, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="8a52d-163">Ad esempio, per sostituire l'insieme esistente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="8a52d-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="8a52d-164">Per sostituire soltanto il provider $LyssProvider dall'insieme corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="8a52d-165">Per rimuovere uno scenario esistente tramite il cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="8a52d-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="8a52d-166">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-167">Per rimuovere uno scenario precedentemente definito, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="8a52d-168">Ad esempio, per rimuovere lo scenario definito:Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="8a52d-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="8a52d-169">Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite restano disponibili nei registri per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a52d-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="8a52d-170">Per caricare e scaricare il cmdlet Edit-CsClsScenario tramite il modulo ClsScenarioEdit. psm1</span><span class="sxs-lookup"><span data-stu-id="8a52d-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="8a52d-171">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8a52d-172">Il modulo ClsScenarioEdit. psm1 viene fornito come download Web separato.</span><span class="sxs-lookup"><span data-stu-id="8a52d-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="8a52d-173">Il modulo fa parte degli strumenti di debug di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8a52d-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="8a52d-174">Per impostazione predefinita, gli strumenti di debug sono installati nella directory C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="8a52d-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="8a52d-175">Da Windows PowerShell, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-175">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="8a52d-176">Il corretto caricamento del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a52d-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8a52d-177">Per verificare che il modulo sia caricato e che Edit-CsClsScenario sia disponibile, digitare  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8a52d-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8a52d-178">Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8a52d-179">Per scaricare i moduli, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-179">To unload the modules, type:</span></span>
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="8a52d-180">Lo scaricamento riuscito del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a52d-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8a52d-181">Per verificare che il modulo sia scaricato, digitare  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8a52d-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8a52d-182">Windows PowerShell tenterà di individuare la guida per il cmdlet e avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8a52d-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8a52d-183">Per rimuovere un provider esistente da uno scenario attraverso il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8a52d-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8a52d-184">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-185">Da Windows PowerShell, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-185">From the Windows PowerShell, type:</span></span>
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="8a52d-186">Il corretto caricamento del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a52d-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="8a52d-187">Per verificare che il modulo sia caricato e che Edit-CsClsScenario sia disponibile, digitare  `Get-Help Edit-CsClsScenario` .</span><span class="sxs-lookup"><span data-stu-id="8a52d-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="8a52d-188">Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="8a52d-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="8a52d-189">Per rimuovere un provider dallo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="8a52d-190">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a52d-190">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="8a52d-p117">I parametri ScenarioName e ProviderName sono parametri relativi alla posizione, ovvero devono essere definiti nella posizione della riga di comando attesa. Il nome del parametro non deve essere definito esplicitamente se il nome dello scenario si trova in posizione due e il provider in posizione tre, in relazione al nome del cmdlet in posizione uno. Attraverso queste informazioni, il comando precedente verrebbe digitato come:</span><span class="sxs-lookup"><span data-stu-id="8a52d-p117">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="8a52d-194">La disposizione posizionale dei valori di parametro si applica solo a-scenario e-provider.</span><span class="sxs-lookup"><span data-stu-id="8a52d-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="8a52d-195">Tutti gli altri parametri devono essere definiti esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="8a52d-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="8a52d-196">Per aggiungere un provider esistente a uno scenario attraverso il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="8a52d-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="8a52d-197">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8a52d-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8a52d-198">Per aggiungere un provider allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="8a52d-199">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8a52d-199">For Example:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="8a52d-200">-Loglevel può essere di tipo Fatal, Error, Warning, Info, Verbose, Debug o All.</span><span class="sxs-lookup"><span data-stu-id="8a52d-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="8a52d-201">-I flag possono corrispondere a qualsiasi flag supportato dal provider, ad esempio TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="8a52d-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="8a52d-202">-Flags può anche essere di valore ALL</span><span class="sxs-lookup"><span data-stu-id="8a52d-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="8a52d-p120">L'esempio precedente può essere digitato anche attraverso la caratteristiche di posizione del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="8a52d-p120">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
