---
title: Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Riepilogo: informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: e2c633dabf30ffbc42fa90066bf469e10dc25fb6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816605"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="f61bd-103">Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="f61bd-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f61bd-104">**Riepilogo:** Informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f61bd-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f61bd-105">I concetti e la configurazione dei provider in un servizio di registrazione centralizzato è uno dei più importanti da afferrare.</span><span class="sxs-lookup"><span data-stu-id="f61bd-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="f61bd-106">Theproviders mappa direttamente ai componenti del ruolo del server Skype for Business Server nel modello di traccia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f61bd-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="f61bd-107">Il provider definisce i componenti di un server Skype for business 2015 che verrà tracciato, il tipo di messaggi (ad esempio, fatale, errore o avviso) da raccogliere e i contrassegni (ad esempio TF_Connection o TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="f61bd-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="f61bd-108">I provider sono i componenti rintracciabili in ogni ruolo del server Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f61bd-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="f61bd-109">Usando i provider, Definisci il livello e il tipo di traccia sui componenti (ad esempio, S4, SIPStack, IM e Presence).</span><span class="sxs-lookup"><span data-stu-id="f61bd-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="f61bd-110">Il provider definito viene usato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.</span><span class="sxs-lookup"><span data-stu-id="f61bd-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="f61bd-111">Per eseguire le funzioni di servizio di registrazione centralizzata con Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="f61bd-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="f61bd-112">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o Windows PowerShell prompt</span><span class="sxs-lookup"><span data-stu-id="f61bd-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="f61bd-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f61bd-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="f61bd-114">Il resto di questo argomento illustra come definire i provider, modificare un provider e il contenuto di una definizione di provider per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="f61bd-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="f61bd-115">Esistono due modi per emettere comandi di servizio di registrazione centralizzati.</span><span class="sxs-lookup"><span data-stu-id="f61bd-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="f61bd-116">Per impostazione predefinita, è possibile usare CLSController. exe nella directory c:\Programmi\File Skype for Business Server 2015 \ CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="f61bd-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="f61bd-117">In alternativa, puoi usare Skype for Business Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f61bd-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="f61bd-118">Usando Windows PowerShell puoi definire nuovi provider da usare nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e su quale livello raccolgono i dati.</span><span class="sxs-lookup"><span data-stu-id="f61bd-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f61bd-119">Come accennato, i provider sono molto potenti.</span><span class="sxs-lookup"><span data-stu-id="f61bd-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="f61bd-120">Tuttavia, gli scenari sono più potenti perché contengono l'incorporamento di tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider.</span><span class="sxs-lookup"><span data-stu-id="f61bd-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="f61bd-121">Con gli scenari che sono una raccolta di provider, questa operazione potrebbe essere confrontata con l'esecuzione di un file batch contenente centinaia di comandi per raccogliere molte informazioni rispetto al rilascio di centinaia di comandi, uno alla volta, nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f61bd-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="f61bd-122">Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato offre numerosi scenari già definiti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f61bd-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="f61bd-123">Gli scenari forniti coprono la stragrande maggioranza dei possibili problemi che incontrerai.</span><span class="sxs-lookup"><span data-stu-id="f61bd-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="f61bd-124">In rari casi potrebbe essere necessario creare e definire provider e assegnarli agli scenari.</span><span class="sxs-lookup"><span data-stu-id="f61bd-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="f61bd-125">Ti consigliamo vivamente di acquisire familiarità con ognuno degli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari.</span><span class="sxs-lookup"><span data-stu-id="f61bd-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="f61bd-126">Mentre le informazioni sulla creazione di provider si trovano qui per familiarizzare con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, in questo momento non vengono forniti dettagli sui provider stessi.</span><span class="sxs-lookup"><span data-stu-id="f61bd-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="f61bd-127">Introdotti in [servizi di registrazione centralizzati in Skype for Business 2015](centralized-logging-service.md), gli elementi chiave della definizione di un provider per l'uso in uno scenario sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f61bd-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="f61bd-128">**Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="f61bd-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="f61bd-129">I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="f61bd-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="f61bd-130">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="f61bd-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="f61bd-131">Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte dell'architettura del servizio di registrazione centralizzata che sta eseguendo la traccia dei componenti definiti nella configurazione di provider.</span><span class="sxs-lookup"><span data-stu-id="f61bd-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="f61bd-132">**Livelli di registrazione** OCSLogger ha fornito l'opzione per scegliere un numero di livelli di dettaglio per i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="f61bd-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="f61bd-133">Questa caratteristica è parte integrante del servizio di registrazione centralizzato e degli scenari e viene definita dal parametro **Type** .</span><span class="sxs-lookup"><span data-stu-id="f61bd-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="f61bd-134">È possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f61bd-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="f61bd-135">**Tutti i** Raccoglie i messaggi di traccia di tipo Fatal, Error, Warning, verbose e info di debug nel log per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="f61bd-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="f61bd-136">**Fatal** Raccoglie solo i messaggi di traccia definiti come "fatali".</span><span class="sxs-lookup"><span data-stu-id="f61bd-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="f61bd-137">**Errore** Raccoglie solo i messaggi di traccia definiti come "errore" o "fatale".</span><span class="sxs-lookup"><span data-stu-id="f61bd-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="f61bd-138">**Avviso** Raccoglie solo i messaggi di traccia di tipo "avviso", "errore" e "fatale".</span><span class="sxs-lookup"><span data-stu-id="f61bd-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="f61bd-139">**Informazioni** Raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi irreversibili, di errore e di avviso.</span><span class="sxs-lookup"><span data-stu-id="f61bd-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="f61bd-140">**Verbose** Raccoglie tutti i messaggi di traccia di tipo Fatal, Error, Warning e Verbose per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="f61bd-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="f61bd-141">Il **debug** è essenzialmente un equivalente di ' all'-raccoglie tracce di tipo fatale, Error, Warning, info, verbose e debug per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="f61bd-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="f61bd-142">**Contrassegni** OCSLogger ha fornito l'opzione per scegliere contrassegni per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia.</span><span class="sxs-lookup"><span data-stu-id="f61bd-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="f61bd-143">È possibile scegliere i contrassegni seguenti in base al provider:</span><span class="sxs-lookup"><span data-stu-id="f61bd-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="f61bd-144">**TF_Connection** Fornisce voci di log correlate alla connessione.</span><span class="sxs-lookup"><span data-stu-id="f61bd-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="f61bd-145">Questi registri includono informazioni sulle connessioni stabilite da e verso un particolare componente.</span><span class="sxs-lookup"><span data-stu-id="f61bd-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="f61bd-146">Può anche includere informazioni significative a livello di rete, ovvero per i componenti senza il concetto di connessione.</span><span class="sxs-lookup"><span data-stu-id="f61bd-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="f61bd-147">**TF_Security** Fornisce tutti gli eventi/voci di log correlate alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f61bd-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="f61bd-148">Ad esempio, per SipStack, si tratta di eventi di sicurezza come l'errore di convalida del dominio e gli errori di autenticazione client/autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="f61bd-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="f61bd-149">**TF_Diag** Fornisce gli eventi di diagnostica che è possibile usare per diagnosticare o risolvere i problemi del componente.</span><span class="sxs-lookup"><span data-stu-id="f61bd-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="f61bd-150">Ad esempio, per SipStack, si tratta di errori di certificato o di avvisi e messaggi DNS.</span><span class="sxs-lookup"><span data-stu-id="f61bd-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="f61bd-151">**TF_Protocol** Fornisce messaggi di protocollo come i messaggi SIP e i pacchetti di codec community combinati.</span><span class="sxs-lookup"><span data-stu-id="f61bd-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="f61bd-152">**TF_Component** Abilita la registrazione dei componenti specificati come parte dei provider.</span><span class="sxs-lookup"><span data-stu-id="f61bd-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="f61bd-153">**Tutti i** Imposta tutti i contrassegni disponibili per il provider.</span><span class="sxs-lookup"><span data-stu-id="f61bd-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="f61bd-154">Per esaminare le informazioni sui provider di scenari di servizi di registrazione centralizzati esistenti</span><span class="sxs-lookup"><span data-stu-id="f61bd-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="f61bd-155">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61bd-156">Per esaminare la configurazione dei provider esistenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f61bd-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="f61bd-157">Ad esempio, per esaminare le informazioni sull'operatore di conferenza globale, digitare:</span><span class="sxs-lookup"><span data-stu-id="f61bd-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="f61bd-158">Il comando Visualizza un elenco di provider con i contrassegni, le impostazioni e i componenti associati.</span><span class="sxs-lookup"><span data-stu-id="f61bd-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="f61bd-159">Se le informazioni visualizzate non sono sufficienti o l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare altre informazioni definendo un metodo di output diverso.</span><span class="sxs-lookup"><span data-stu-id="f61bd-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="f61bd-160">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="f61bd-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="f61bd-161">L'output di questo comando Visualizza ogni provider visualizzato in un formato a cinque righe con il nome del provider, il tipo di registrazione, il livello di registrazione, i contrassegni, il GUID e il ruolo, ognuno in una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="f61bd-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="f61bd-162">Per definire un nuovo provider di scenari del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="f61bd-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="f61bd-163">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61bd-164">Un provider di scenari è costituito da un componente da tracciare, da contrassegni da usare e da un livello di dettaglio da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="f61bd-164">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="f61bd-165">Per eseguire questa operazione, digitare:</span><span class="sxs-lookup"><span data-stu-id="f61bd-165">You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="f61bd-166">Ad esempio, la definizione di un provider di traccia che definisce cosa raccogliere e il livello di dettaglio del provider Lyss ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="f61bd-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="f61bd-167">Il livello raccoglie messaggi fatali, di errore, di avviso e di informazioni.</span><span class="sxs-lookup"><span data-stu-id="f61bd-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="f61bd-168">I contrassegni usati sono tutti quelli definiti per il provider Lyss e includono TF_Connection, TF_Diag e TF_Protocol. dopo aver definito la variabile $LyssProvider, è possibile usarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss.</span><span class="sxs-lookup"><span data-stu-id="f61bd-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="f61bd-169">Per completare la creazione e l'assegnazione del provider in un nuovo scenario, digitare:</span><span class="sxs-lookup"><span data-stu-id="f61bd-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="f61bd-170">Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="f61bd-171">Per modificare un provider di scenario del servizio di registrazione centralizzato esistente</span><span class="sxs-lookup"><span data-stu-id="f61bd-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="f61bd-172">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61bd-173">Per aggiornare o modificare la configurazione di un provider esistente, digitare:</span><span class="sxs-lookup"><span data-stu-id="f61bd-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="f61bd-174">È quindi possibile aggiornare lo scenario per assegnare il provider digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f61bd-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="f61bd-175">Il risultato finale del comando è che il sito scenario: Redmond/RedmondLyssInfo avrà aggiornato i contrassegni e il livello per il provider assegnato.</span><span class="sxs-lookup"><span data-stu-id="f61bd-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="f61bd-176">Puoi visualizzare il nuovo scenario usando Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="f61bd-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="f61bd-177">Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f61bd-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="f61bd-178">**New-ClsCsProvider** non controlla per determinare se i contrassegni sono validi.</span><span class="sxs-lookup"><span data-stu-id="f61bd-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="f61bd-179">Verificare che l'ortografia dei contrassegni (ad esempio TF_DIAG o TF_CONNECTION) sia stata digitata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f61bd-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="f61bd-180">Se i contrassegni non vengono digitati correttamente, il provider non potrà restituire le informazioni di log previste.</span><span class="sxs-lookup"><span data-stu-id="f61bd-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="f61bd-181">Se si vogliono aggiungere altri provider a questo scenario, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f61bd-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="f61bd-182">Dove ogni provider definito con la direttiva add è già stato definito tramite il processo **New-CsClsProvider** .</span><span class="sxs-lookup"><span data-stu-id="f61bd-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="f61bd-183">Per rimuovere un provider di scenari</span><span class="sxs-lookup"><span data-stu-id="f61bd-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="f61bd-184">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f61bd-185">I cmdlet forniti consentono di aggiornare i provider esistenti e di creare nuovi provider.</span><span class="sxs-lookup"><span data-stu-id="f61bd-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="f61bd-186">Per rimuovere un provider, è necessario usare la direttiva Replace per il parametro provider per **impostare-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="f61bd-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="f61bd-187">L'unico modo per rimuovere completamente un provider è sostituirlo con un provider ridefinito con lo stesso nome e usare la direttiva Update.</span><span class="sxs-lookup"><span data-stu-id="f61bd-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="f61bd-188">Ad esempio, il nostro provider LyssProvider è definito con WPP come tipo di log, Level set to debug e flags set sono TF_CONNECTION e TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="f61bd-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="f61bd-189">È necessario modificare i contrassegni in "tutti".</span><span class="sxs-lookup"><span data-stu-id="f61bd-189">You need to change the flags to "All".</span></span> <span data-ttu-id="f61bd-190">Per cambiare il provider, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f61bd-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="f61bd-191">Se si vuole rimuovere completamente uno scenario e i provider a esso associati, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f61bd-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="f61bd-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f61bd-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="f61bd-193">Il cmdlet **Remove-CsClsScenario** non chiede conferma.</span><span class="sxs-lookup"><span data-stu-id="f61bd-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="f61bd-194">Lo scenario viene eliminato, insieme ai provider assegnati.</span><span class="sxs-lookup"><span data-stu-id="f61bd-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="f61bd-195">Puoi ricreare lo scenario eseguendo nuovamente i comandi usati per crearlo inizialmente.</span><span class="sxs-lookup"><span data-stu-id="f61bd-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="f61bd-196">Non esiste una procedura per recuperare gli scenari o i provider rimossi.</span><span class="sxs-lookup"><span data-stu-id="f61bd-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="f61bd-197">Quando si rimuove uno scenario usando il cmdlet **Remove-CsClsScenario** , si rimuove completamente lo scenario dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="f61bd-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="f61bd-198">Per usare gli scenari creati e i provider che facevano parte dello scenario, è possibile creare nuovi provider e assegnarli a un nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="f61bd-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="f61bd-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f61bd-199">See also</span></span>

[<span data-ttu-id="f61bd-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f61bd-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="f61bd-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f61bd-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="f61bd-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f61bd-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="f61bd-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="f61bd-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="f61bd-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="f61bd-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
