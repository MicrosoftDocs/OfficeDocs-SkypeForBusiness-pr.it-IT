---
title: Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015
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
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Riepilogo: informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 89aa0c37dfb13f7614067b64e37ee9c9fb376331
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186818"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="968f8-103">Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="968f8-103">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="968f8-104">**Riepilogo:** Informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="968f8-104">**Summary:** Learn how to create, modify, and remove scenarios for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="968f8-105">Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e i provider da usare nel servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="968f8-105">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="968f8-106">Usando gli scenari, puoi abilitare o disabilitare la traccia sui provider, ad esempio S4, SIPStack, IM e Presence.</span><span class="sxs-lookup"><span data-stu-id="968f8-106">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="968f8-107">Configurando uno scenario, è possibile raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.</span><span class="sxs-lookup"><span data-stu-id="968f8-107">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="968f8-108">Se si scopre che è necessario modificare uno scenario per soddisfare le esigenze di risoluzione dei problemi e registrazione, gli strumenti di debug di Skype for Business Server 2015 forniscono un modulo di Windows PowerShell denominato ClsScenarioEdit. psm1 che contiene una funzione namedEdit-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-108">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Skype for Business Server 2015 Debug Tools provides you a Windows PowerShell module named ClsScenarioEdit.psm1 that contains a function namedEdit-CsClsScenario.</span></span> <span data-ttu-id="968f8-109">Lo scopo del modulo consiste nel modificare le proprietà dello scenario denominato.</span><span class="sxs-lookup"><span data-stu-id="968f8-109">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="968f8-110">In questo argomento sono disponibili alcuni esempi di funzionamento di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="968f8-110">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="968f8-111">Scaricare gli [strumenti di debug](https://go.microsoft.com/fwlink/p/?LinkId=285257) di Skype for Business Server 2015 prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="968f8-111">Download the Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) before going any further.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="968f8-112">Per un ambito specifico, ovvero sito, globale, pool o computer, è possibile eseguire un massimo di due scenari in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="968f8-112">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="968f8-113">Per determinare gli scenari attualmente in uso, usare Windows PowerShell e [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="968f8-113">To determine which scenarios are currently running, use Windows PowerShell and [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span> <span data-ttu-id="968f8-114">Usando Windows PowerShell e [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), è possibile modificare in modo dinamico gli scenari in uso.</span><span class="sxs-lookup"><span data-stu-id="968f8-114">By using Windows PowerShell and [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="968f8-115">È possibile modificare gli scenari in corso durante una sessione di registrazione per modificare o affinare i dati che si stanno raccogliendo e da quali provider.</span><span class="sxs-lookup"><span data-stu-id="968f8-115">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span> 
  
<span data-ttu-id="968f8-116">Per eseguire le funzioni del servizio di registrazione centralizzato usando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="968f8-116">To run the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="968f8-117">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati personalmente, eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="968f8-117">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="968f8-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="968f8-118">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="968f8-119">La parte restante di questo argomento illustra come definire uno scenario, modificare uno scenario, recuperare gli scenari in uso, rimuovere uno scenario e specificare lo scenario che contiene per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="968f8-119">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="968f8-120">Puoi usare Skype for Business Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="968f8-120">You can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="968f8-121">Quando si usa Windows PowerShell, è possibile definire nuovi scenari da usare nelle sessioni di registrazione.</span><span class="sxs-lookup"><span data-stu-id="968f8-121">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>
  
<span data-ttu-id="968f8-122">Come è stato introdotto in [servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md), gli elementi di uno scenario sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="968f8-122">As introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the elements of a scenario are:</span></span>
  
- <span data-ttu-id="968f8-123">**Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="968f8-123">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="968f8-124">I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="968f8-124">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="968f8-125">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="968f8-125">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="968f8-126">Per informazioni dettagliate sulla configurazione dei provider, vedere [configurare i provider per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-providers.md).</span><span class="sxs-lookup"><span data-stu-id="968f8-126">For details about the configuration of providers, see [Configure providers for Centralized Logging Service in Skype for Business Server 2015](configure-providers.md).</span></span>
    
- <span data-ttu-id="968f8-127">**Identità** Il parametro-Identity imposta l'ambito e il nome dello scenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-127">**Identity** The parameter -Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="968f8-128">Ad esempio, puoi impostare un ambito di "globale" e identificare lo scenario con "LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="968f8-128">For example, you could set a scope of "global" and identify the scenario with "LyssServiceScenario".</span></span> <span data-ttu-id="968f8-129">Quando si combinano i due, si definisce l'identità, ad esempio "Global/LyssServiceScenario".</span><span class="sxs-lookup"><span data-stu-id="968f8-129">When you combine the two, you define the Identity (for example, "global/LyssServiceScenario").</span></span>
    
    <span data-ttu-id="968f8-130">Facoltativamente, è possibile usare i parametri-Name e-Parent.</span><span class="sxs-lookup"><span data-stu-id="968f8-130">Optionally, you can use the -Name and -Parent parameters.</span></span> <span data-ttu-id="968f8-131">Puoi definire il parametro Name per identificare in modo univoco lo scenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-131">You define the Name parameter to uniquely identify the scenario.</span></span> <span data-ttu-id="968f8-132">Se si usa nome, è necessario usare anche l'elemento padre per aggiungere lo scenario a globale o a sito.</span><span class="sxs-lookup"><span data-stu-id="968f8-132">If you use Name, you must also use Parent to add the scenario to either global or site.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="968f8-133">Se si usano i parametri Name e Parent, non è possibile usare il parametro **-Identity** .</span><span class="sxs-lookup"><span data-stu-id="968f8-133">If you use the Name and Parent parameters, you cannot use the **-Identity** parameter.</span></span>
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="968f8-134">Per creare un nuovo scenario con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="968f8-134">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="968f8-135">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-135">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-136">Per creare un nuovo scenario per una sessione di registrazione, USA [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) e Definisci il nome dello scenario, ovvero il modo in cui verrà identificato in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="968f8-136">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) and define the name of the scenario (that is, how it will be uniquely identified).</span></span> <span data-ttu-id="968f8-137">Scegliere un tipo di formato di registrazione da WPP (ovvero il preprocessore di traccia del software Windows ed è il valore predefinito), EventLog (ovvero il formato del log eventi di Windows) o IISLog (ovvero file in formato ASCII basato sul formato del file di log di IIS).</span><span class="sxs-lookup"><span data-stu-id="968f8-137">Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format).</span></span> <span data-ttu-id="968f8-138">Definire quindi il livello (definito in livelli di registrazione in questo argomento) e i contrassegni (come definito in contrassegni in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="968f8-138">Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="968f8-139">Per questo scenario di esempio, usiamo LyssProvider come variabile di provider di esempio.</span><span class="sxs-lookup"><span data-stu-id="968f8-139">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="968f8-140">Per creare uno scenario usando le opzioni definite, digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-140">To create a scenario using the options defined, type:</span></span>
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    <span data-ttu-id="968f8-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="968f8-141">For example:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    <span data-ttu-id="968f8-142">Il formato alternativo using-Name e-Parent:</span><span class="sxs-lookup"><span data-stu-id="968f8-142">The alternate format using -Name and -Parent:</span></span>
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="968f8-143">Per creare un nuovo scenario con più provider con il cmdlet New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="968f8-143">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="968f8-144">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-145">Si è limitati a due scenari per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="968f8-145">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="968f8-146">Tuttavia, non si è limitati a un determinato numero di provider.</span><span class="sxs-lookup"><span data-stu-id="968f8-146">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="968f8-147">In questo esempio, supponiamo di avere creato tre provider e di assegnare tutti e tre allo scenario che stai definendo.</span><span class="sxs-lookup"><span data-stu-id="968f8-147">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="968f8-148">I nomi delle variabili del provider sono LyssProvider, ABServerProvider e SIPStackProvider.</span><span class="sxs-lookup"><span data-stu-id="968f8-148">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="968f8-149">Per definire e assegnare più provider a uno scenario, digitare quanto segue in un prompt dei comandi di Skype for Business Server Management Shell o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="968f8-149">To define and assign multiple providers to a scenario, type the following at a Skype for Business Server Management Shell or Windows PowerShell command prompt:</span></span>
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > <span data-ttu-id="968f8-150">Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori `@{<variable>=<value1>, <value2>, <value>…}` usando è nota assplatting.</span><span class="sxs-lookup"><span data-stu-id="968f8-150">As it is known in Windows PowerShell, the convention for creating a hash table of values using  `@{<variable>=<value1>, <value2>, <value>…}` is known assplatting.</span></span> <span data-ttu-id="968f8-151">Per informazioni dettagliate su splatting in Windows PowerShell, [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)vedere.</span><span class="sxs-lookup"><span data-stu-id="968f8-151">For details about splatting in Windows PowerShell, see [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760).</span></span> 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="968f8-152">Per modificare uno scenario esistente con il cmdlet Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="968f8-152">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="968f8-153">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-153">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-154">Si è limitati a due scenari per ogni ambito.</span><span class="sxs-lookup"><span data-stu-id="968f8-154">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="968f8-155">È possibile modificare gli scenari in esecuzione in qualsiasi momento, anche quando è in corso una sessione di acquisizione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="968f8-155">You can change which scenarios are running at any time, even when a logging capture session is in process.</span></span> <span data-ttu-id="968f8-156">Se si ridefiniscono gli scenari in uso, la sessione di registrazione corrente smetterà di usare lo scenario rimosso e quindi inizierà a usare il nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-156">If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario.</span></span> <span data-ttu-id="968f8-157">Tuttavia, le informazioni di registrazione acquisite con lo scenario rimosso restano nei registri acquisiti.</span><span class="sxs-lookup"><span data-stu-id="968f8-157">However, the logging information that was captured with the removed scenario remains in the captured logs.</span></span> <span data-ttu-id="968f8-158">Per definire un nuovo scenario, eseguire le operazioni seguenti, ad esempio supponendo che l'aggiunta di un provider già definito denominato "S4Provider":</span><span class="sxs-lookup"><span data-stu-id="968f8-158">To define a new scenario, do the following (that is, assuming the addition of an already defined provider named "S4Provider"):</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    <span data-ttu-id="968f8-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="968f8-159">For example:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    <span data-ttu-id="968f8-160">Se si vuole sostituire i provider, definire un singolo provider o un elenco di provider separati da virgole per sostituire il set corrente.</span><span class="sxs-lookup"><span data-stu-id="968f8-160">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set.</span></span> <span data-ttu-id="968f8-161">Se si vuole sostituire solo uno di molti provider, aggiungere i provider correnti con i nuovi provider per creare un nuovo set di provider che contiene sia i nuovi provider che i provider esistenti.</span><span class="sxs-lookup"><span data-stu-id="968f8-161">If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers.</span></span> <span data-ttu-id="968f8-162">Per sostituire tutti i provider con un nuovo set, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="968f8-162">To replace all providers with a new set, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    <span data-ttu-id="968f8-163">Ad esempio, per sostituire il set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:</span><span class="sxs-lookup"><span data-stu-id="968f8-163">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    <span data-ttu-id="968f8-164">Per sostituire solo il provider $LyssProvider dal set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="968f8-164">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="968f8-165">Per rimuovere uno scenario esistente con il cmdlet Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="968f8-165">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1. <span data-ttu-id="968f8-166">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-166">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-167">Se si vuole rimuovere uno scenario definito in precedenza, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="968f8-167">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    <span data-ttu-id="968f8-168">Ad esempio, per rimuovere il sito scenario definito: Redmond/LyssServiceScenario:</span><span class="sxs-lookup"><span data-stu-id="968f8-168">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

<span data-ttu-id="968f8-169">Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite sono ancora disponibili nei registri in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="968f8-169">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a><span data-ttu-id="968f8-170">Per caricare e scaricare il cmdlet Edit-CsClsScenario usando il modulo ClsScenarioEdit. psm1</span><span class="sxs-lookup"><span data-stu-id="968f8-170">To load and unload the Edit-CsClsScenario cmdlet using the ClsScenarioEdit.psm1 module</span></span>

1. <span data-ttu-id="968f8-171">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-171">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="968f8-172">Il modulo ClsScenarioEdit. psm1 viene fornito come download Web separato.</span><span class="sxs-lookup"><span data-stu-id="968f8-172">The ClsScenarioEdit.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="968f8-173">Il modulo fa parte degli strumenti di debug di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="968f8-173">The module is part of the Skype for Business Server 2015 Debugging tools.</span></span> <span data-ttu-id="968f8-174">Per impostazione predefinita, gli strumenti di debug sono installati nella directory C:\Program Skype for Business Server 2015 \ Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="968f8-174">By default, the debugging tools are installed in the directory C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> 
  
2. <span data-ttu-id="968f8-175">In Windows PowerShell digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-175">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="968f8-176">Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="968f8-176">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="968f8-177">Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, `Get-Help Edit-CsClsScenario`Digitare.</span><span class="sxs-lookup"><span data-stu-id="968f8-177">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="968f8-178">Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-178">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="968f8-179">Per scaricare i moduli, digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-179">To unload the modules, type:</span></span>
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > <span data-ttu-id="968f8-180">Il riuscito scarico del modulo restituisce il prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="968f8-180">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="968f8-181">Per verificare che il modulo sia scaricato, digitare `Get-Help Edit-CsClsScenario`.</span><span class="sxs-lookup"><span data-stu-id="968f8-181">To confirm that the module is unloaded, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="968f8-182">Windows PowerShell tenterà di individuare la guida per il cmdlet e non riesce.</span><span class="sxs-lookup"><span data-stu-id="968f8-182">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span> 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="968f8-183">Per rimuovere un provider esistente da uno scenario con il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="968f8-183">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="968f8-184">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-185">In Windows PowerShell digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-185">From the Windows PowerShell, type:</span></span>
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > <span data-ttu-id="968f8-186">Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="968f8-186">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="968f8-187">Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, `Get-Help Edit-CsClsScenario`Digitare.</span><span class="sxs-lookup"><span data-stu-id="968f8-187">To confirm that the module is loaded and that Edit-CsClsScenario is available, type  `Get-Help Edit-CsClsScenario`.</span></span> <span data-ttu-id="968f8-188">Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="968f8-188">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span> 
  
3. <span data-ttu-id="968f8-189">Per rimuovere un provider dallo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-189">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   <span data-ttu-id="968f8-190">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="968f8-190">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   <span data-ttu-id="968f8-191">I parametri ScenarioName e ProviderName sono posizionali, ovvero devono essere definiti nella posizione prevista nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="968f8-191">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters.</span></span> <span data-ttu-id="968f8-192">Il nome del parametro non deve essere definito in modo esplicito se il nome dello scenario è nella posizione due e il provider è nella posizione tre, in relazione al nome del cmdlet come posizione uno.</span><span class="sxs-lookup"><span data-stu-id="968f8-192">The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one.</span></span> <span data-ttu-id="968f8-193">Usando queste informazioni, il comando precedente verrebbe tipizzato come segue:</span><span class="sxs-lookup"><span data-stu-id="968f8-193">Using this information, the previous command would be typed as:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   <span data-ttu-id="968f8-194">La posizione di posizionamento dei valori di parametro si applica solo a-scenario e-provider.</span><span class="sxs-lookup"><span data-stu-id="968f8-194">The positional placing of the parameter values applies only to -Scenario and -Provider.</span></span> <span data-ttu-id="968f8-195">Tutti gli altri parametri devono essere definiti in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="968f8-195">All other parameters must be explicitly defined.</span></span>
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="968f8-196">Per aggiungere un provider a uno scenario con il modulo Edit-ClsController</span><span class="sxs-lookup"><span data-stu-id="968f8-196">To add a provider to a scenario with the Edit-ClsController module</span></span>

1. <span data-ttu-id="968f8-197">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="968f8-197">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="968f8-198">Per aggiungere un provider allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-198">To add a provider to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    <span data-ttu-id="968f8-199">Per esempio:</span><span class="sxs-lookup"><span data-stu-id="968f8-199">For Example:</span></span>
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    <span data-ttu-id="968f8-200">-LogLevel può essere di tipo Fatal, Error, Warning, info, Verbose, debug o all.</span><span class="sxs-lookup"><span data-stu-id="968f8-200">-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="968f8-201">-I flag possono essere uno dei contrassegni supportati dal provider, ad esempio TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="968f8-201">-Flags can be any of the flags that the provider supports, such as TF_COMPONENT, TF_DIAG.</span></span> <span data-ttu-id="968f8-202">-Flags può anche essere di valore ALL</span><span class="sxs-lookup"><span data-stu-id="968f8-202">-Flags can also be of value ALL</span></span>
    
   <span data-ttu-id="968f8-203">L'esempio precedente può anche essere digitato usando la caratteristica posizionali del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="968f8-203">The previous example can also be typed using the positional feature of the cmdlet.</span></span> <span data-ttu-id="968f8-204">Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:</span><span class="sxs-lookup"><span data-stu-id="968f8-204">For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
