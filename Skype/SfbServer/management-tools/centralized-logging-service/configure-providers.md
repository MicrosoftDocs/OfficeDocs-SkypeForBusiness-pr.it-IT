---
title: Configurare i provider per il servizio di registrazione centralizzata in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: cd0364d6497aa53d258b5346090d6cdd7c338cc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098852"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="1e6d5-103">Configurare i provider per il servizio di registrazione centralizzata in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e6d5-103">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1e6d5-104">**Riepilogo:** Informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-104">**Summary:** Learn how to configure scenario providers for the Centralized Logging Service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1e6d5-105">I concetti e la configurazione dei provider nel servizio di registrazione centralizzata sono tra i più importanti da comprendere.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-105">The concepts and configuration of providers in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="1e6d5-106">I provider vengono mappati direttamente ai componenti del ruolo del server Skype for Business Server nel modello di traccia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-106">Theproviders map directly to Skype for Business Server server role components in the Skype for Business Server tracing model.</span></span> <span data-ttu-id="1e6d5-107">Il provider definisce i componenti di Skype for Business Server 2015 che verranno tracciati, il tipo di messaggi (ad esempio, irreversibile, errore o avviso) da raccogliere e i flag (ad esempio, TF_Connection o TF_Diag).</span><span class="sxs-lookup"><span data-stu-id="1e6d5-107">The provider defines the components of a Skype for Business Server 2015 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF_Connection or TF_Diag).</span></span> <span data-ttu-id="1e6d5-108">I provider sono i componenti tracciabili in ogni ruolo del server Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-108">Providers are the traceable components in each Skype for Business Server server role.</span></span> <span data-ttu-id="1e6d5-109">Tramite i provider vengono definiti il livello e il tipo di traccia per i componenti (ad esempio, S4, SIPStack, messaggistica istantanea e presenza).</span><span class="sxs-lookup"><span data-stu-id="1e6d5-109">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="1e6d5-110">Il provider definito viene utilizzato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica riferita a una condizione problematica specifica.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-110">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>
  
<span data-ttu-id="1e6d5-111">Per eseguire le funzioni del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator basati sui ruoli o un ruolo RBAC personalizzato contenente uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-111">To run the Centralized Logging Service functions using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="1e6d5-112">Per restituire un elenco di tutti i ruoli RBAC (Role-Based Access Control) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati dall'utente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-112">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="1e6d5-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-113">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="1e6d5-114">Nella parte restante di questo argomento viene illustrato come definire provider, modificare un provider e cosa contiene una definizione di provider per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-114">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="1e6d5-115">Esistono due modi per emettere comandi del servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-115">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="1e6d5-116">Puoi usare il CLSController.exe che si trova, per impostazione predefinita, nella directory C:\Programmi\File comuni\Skype for Business Server 2015\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-116">You can use the CLSController.exe that is located, by default, in the directory C:\Program Files\Common Files\Skype for Business Server 2015\CLSAgent.</span></span> <span data-ttu-id="1e6d5-117">In caso contrario, è possibile utilizzare Skype for Business Server Management Shell per emettere Windows PowerShell comandi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-117">Or, you can use the Skype for Business Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="1e6d5-118">Utilizzando Windows PowerShell, è possibile definire nuovi provider da utilizzare nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e a quale livello raccolgono i dati.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e6d5-p104">Come già accennato, i provider sono uno strumento dalle grandi potenzialità. Gli scenari, tuttavia, sono ancora più efficaci perché incorporano tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Dato che gli scenari sono in effetti una raccolta di provider, possono essere paragonati all'esecuzione di un file batch contenente centinaia di comandi per raccogliere grandi quantità di informazioni anziché eseguire centinaia di comandi, uno alla volta, dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span> 
  
<span data-ttu-id="1e6d5-122">Invece di richiedere un'approfondita ricerca nei dettagli dei provider, il servizio di registrazione centralizzata offre una serie di scenari già definiti.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="1e6d5-123">Gli scenari forniti riguardano la maggior parte dei possibili problemi che si verificano.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="1e6d5-124">In rari casi, potrebbe essere necessario creare e definire provider e assegnarli agli scenari.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="1e6d5-125">È consigliabile acquisire familiarità con ognuno degli scenari forniti prima di analizzare la necessità di creare nuovi provider e scenari.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="1e6d5-126">Sebbene le informazioni sulla creazione di provider siano disponibili qui per acquisire familiarità con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, al momento non vengono forniti dettagli sui provider stessi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span> 
  
<span data-ttu-id="1e6d5-127">Introdotto in [Centralized Logging Service in Skype for Business 2015,](centralized-logging-service.md)gli elementi chiave della definizione di un provider da utilizzare in uno scenario sono:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-127">Introduced in [Centralized Logging Service in Skype for Business 2015](centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>
  
- <span data-ttu-id="1e6d5-128">**Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti che si sceglie di indicare a OCSLogger da quale motore di traccia raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-128">**Providers** If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="1e6d5-129">I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="1e6d5-130">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server da cui il servizio di registrazione centralizzata può raccogliere i registri.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="1e6d5-131">Nel caso del servizio di registrazione centralizzata, CLSAgent è la parte architetturale del servizio di registrazione centralizzata che esegue la traccia dei componenti definiti nella configurazione dei provider.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>
    
- <span data-ttu-id="1e6d5-132">**Livelli di registrazione** OCSLogger ha fornito la possibilità di scegliere un numero di livelli di dettaglio per i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-132">**Logging levels** OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="1e6d5-133">Questa funzionalità è parte integrante del servizio di registrazione centralizzata e degli scenari ed è definita dal **parametro Type.**</span><span class="sxs-lookup"><span data-stu-id="1e6d5-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="1e6d5-134">È possibile scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-134">You can choose from the following:</span></span>
    
  - <span data-ttu-id="1e6d5-135">**All** Raccoglie nel registro per il provider definito i messaggi di traccia di tipo irreversibile, errore, avviso, dettagliato e debug.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-135">**All** Collects trace messages of type fatal, error, warning, verbose, and debug info to the log for the defined provider.</span></span>
    
  - <span data-ttu-id="1e6d5-136">**Fatale** Raccoglie solo i messaggi di traccia definiti come "Fatale".</span><span class="sxs-lookup"><span data-stu-id="1e6d5-136">**Fatal** Collects only the trace messages defined as "Fatal."</span></span>
    
  - <span data-ttu-id="1e6d5-137">**Errore** Raccoglie solo i messaggi di traccia definiti come "Errore" o "Fatale".</span><span class="sxs-lookup"><span data-stu-id="1e6d5-137">**Error** Collects only the trace messages defined as "Error" or "Fatal."</span></span>
    
  - <span data-ttu-id="1e6d5-138">**Avviso** Raccoglie solo i messaggi di traccia di tipo "Avviso", "Errore" e "Irreversibile".</span><span class="sxs-lookup"><span data-stu-id="1e6d5-138">**Warning** Collects only the trace messages of type "Warning," "Error" and "Fatal."</span></span>
    
  - <span data-ttu-id="1e6d5-139">**Info** Raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre ai messaggi di errore irreversibile, di errore e di avviso.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-139">**Info** Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
  - <span data-ttu-id="1e6d5-140">**Verbose** Raccoglie tutti i messaggi di traccia di tipo irreversibile, errore, avviso e dettagliato per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-140">**Verbose** Collects all trace messages of type fatal, error, warning and verbose for the defined provider.</span></span>
    
  - <span data-ttu-id="1e6d5-141">**Il** debug è essenzialmente un equivalente di 'All': raccoglie tracce di tipo Fatal, Error, Warning, Info, Verbose e Debug per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-141">**Debug** this is essentially an equivalent of 'All' - collects traces of type Fatal, Error, Warning, Info, Verbose and Debug for the defined provider.</span></span>
    
- <span data-ttu-id="1e6d5-142">**Flag** OCSLogger ha fornito la possibilità di scegliere i flag per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-142">**Flags** OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="1e6d5-143">È possibile scegliere tra i flag seguenti, in base al provider:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-143">You can chose the following flags, based on the provider:</span></span>
    
  - <span data-ttu-id="1e6d5-144">**TF_Connection** Fornisce voci di registro correlate alla connessione.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-144">**TF_Connection** Provides connection-related log entries.</span></span> <span data-ttu-id="1e6d5-145">Questi log includono informazioni sulle connessioni stabilite con e da un particolare componente.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-145">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="1e6d5-146">Potrebbero essere anche incluse informazioni significative a livello di rete, ovvero per componenti non correlati al concetto di connessione.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-146">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
  - <span data-ttu-id="1e6d5-147">**TF_Security** Fornisce tutti gli eventi/voci di registro relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-147">**TF_Security** Provides all events/log entries related to security.</span></span> <span data-ttu-id="1e6d5-148">Per SipStack, ad esempio, si tratta degli eventi di sicurezza come errori di convalida del dominio ed errori di autenticazione/autorizzazione dei client.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-148">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
  - <span data-ttu-id="1e6d5-149">**TF_Diag** Fornisce eventi di diagnostica che è possibile utilizzare per diagnosticare o risolvere i problemi del componente.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-149">**TF_Diag** Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="1e6d5-150">Per SipStack, ad esempio, si tratta di errori dei certificati oppure di avvisi/errori DNS.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-150">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
  - <span data-ttu-id="1e6d5-151">**TF_Protocol** Fornisce messaggi di protocollo quali i messaggi SIP e Combined Community Codec Pack.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-151">**TF_Protocol** Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
  - <span data-ttu-id="1e6d5-152">**TF_Component** Abilita la registrazione dei componenti specificati come parte dei provider.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-152">**TF_Component** Enables logging on the components specified as part of the providers.</span></span>
    
  - <span data-ttu-id="1e6d5-153">**All** Imposta tutti i flag disponibili disponibili per il provider.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-153">**All** Sets all available flags available for the provider.</span></span>
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="1e6d5-154">Per esaminare le informazioni sui provider di scenari esistenti del servizio di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="1e6d5-154">To review information about existing Centralized Logging Service scenario providers</span></span>

1. <span data-ttu-id="1e6d5-155">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1e6d5-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e6d5-156">Per esaminare la configurazione dei provider esistenti, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-156">To review the configuration of existing providers, type the following:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    <span data-ttu-id="1e6d5-157">Per visualizzare informazioni sull'operatore conferenza globale, ad esempio, digitare:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-157">For example, to review information about the global conferencing attendant, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    <span data-ttu-id="1e6d5-158">Il comando visualizza un elenco dei provider con i flag, le impostazioni e i componenti associati.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-158">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="1e6d5-159">Se le informazioni visualizzate non sono sufficienti o se l'elenco è troppo lungo per il formato di elenco Windows PowerShell predefinito, è possibile visualizzare ulteriori informazioni definendo un metodo di output diverso.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-159">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="1e6d5-160">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-160">To do this, type:</span></span>
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    <span data-ttu-id="1e6d5-161">Nell'output di questo comando, le informazioni su ogni provider sono visualizzate su cinque righe separate che includono nome del provider, tipo di registrazione, livello di registrazione, flag, GUID e ruolo.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-161">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span> 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="1e6d5-162">Per definire un nuovo provider di scenari del servizio di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="1e6d5-162">To define a new Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="1e6d5-163">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1e6d5-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e6d5-p113">Un provider di scenari è costituito dal componente da tracciare, i flag da utilizzare e il livello di dettaglio per la raccolta dei dati. Per definire questi elementi, digitare:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    <span data-ttu-id="1e6d5-166">La definizione di un provider di traccia per specificare quali dati raccogliere e con quale livello di dettaglio dal provider Lyss, ad esempio, è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-166">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

<span data-ttu-id="1e6d5-167">-Level raccoglie messaggi irreversibili, di errore, di avviso e di informazioni.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-167">The -Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="1e6d5-168">I flag utilizzati sono tutti quelli definiti per il provider Lyss e includono TF_Connection, TF_Diag e TF_Protocol.Dopo aver definito la variabile $LyssProvider, è possibile utilizzarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-168">The flags used are all of those defined for the Lyss provider, and include TF_Connection, TF_Diag and TF_Protocol.After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="1e6d5-169">Per completare la creazione e l'assegnazione del provider a un nuovo scenario, digitare:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

<span data-ttu-id="1e6d5-170">Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="1e6d5-171">Per modificare un provider di scenari del servizio di registrazione centralizzata esistente</span><span class="sxs-lookup"><span data-stu-id="1e6d5-171">To change an existing Centralized Logging Service scenario provider</span></span>

1. <span data-ttu-id="1e6d5-172">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1e6d5-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e6d5-173">Per aggiornare o modificare la configurazione di un provider esistente, digitare:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-173">To update or change the configuration of an existing provider, type:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    <span data-ttu-id="1e6d5-174">Aggiornare quindi lo scenario per assegnare il provider digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

<span data-ttu-id="1e6d5-175">Il risultato finale del comando è l'aggiornamento dei flag per lo scenario site:Redmond/RedmondLyssInfo e l'assegnazione del livello per il provider.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="1e6d5-176">Per visualizzare il nuovo scenario, utilizzare Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="1e6d5-177">Per informazioni dettagliate, vedere [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1e6d5-177">For details, see [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).</span></span>
> [!CAUTION]
> <span data-ttu-id="1e6d5-178">**New-ClsCsProvider** non esegue un controllo per stabilire se i flag sono validi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-178">**New-ClsCsProvider** does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="1e6d5-179">Assicurarsi di digitare correttamente i flag, ad esempio TF_DIAG o TF_CONNECTION.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="1e6d5-180">Se il nome dei flag non è corretto, il provider non potrà restituire le informazioni di log previste.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>
  
<span data-ttu-id="1e6d5-181">Se si desidera aggiungere ulteriori provider a questo scenario, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-181">If you want to add additional providers to this scenario, type the following:</span></span>

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

<span data-ttu-id="1e6d5-182">In cui ogni provider definito con la direttiva Add è già stato definito tramite il processo **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>
### <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="1e6d5-183">Per rimuovere un provider di scenari</span><span class="sxs-lookup"><span data-stu-id="1e6d5-183">To remove a scenario provider</span></span>

1. <span data-ttu-id="1e6d5-184">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1e6d5-184">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1e6d5-185">I cmdlet indicati consentono di aggiornare i provider esistenti e di crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="1e6d5-186">Per rimuovere un provider, è necessario utilizzare la direttiva Replace per il parametro Provider in **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="1e6d5-187">L'unico modo per rimuovere completamente un provider consiste nel sostituirlo con un provider ridefinito con lo stesso nome e poi utilizzare la direttiva Update.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="1e6d5-188">Il provider LyssProvider utilizzato negli esempi precedenti, ad esempio, è definito con il tipo di log WPP, il livello di registrazione Debug e i flag TF_CONNECTION e TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF_CONNECTION and TF_DIAG.</span></span> <span data-ttu-id="1e6d5-189">È necessario modificare i flag in "All".</span><span class="sxs-lookup"><span data-stu-id="1e6d5-189">You need to change the flags to "All".</span></span> <span data-ttu-id="1e6d5-190">per modificare il provider digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-190">To change the provider, type the following:</span></span>
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. <span data-ttu-id="1e6d5-191">Se si desidera rimuovere completamente uno scenario e i provider associati, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    <span data-ttu-id="1e6d5-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1e6d5-192">For example:</span></span>
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > <span data-ttu-id="1e6d5-193">Il cmdlet **Remove-CsClsScenario** non richiede alcuna conferma.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-193">The cmdlet **Remove-CsClsScenario** does not prompt you for confirmation.</span></span> <span data-ttu-id="1e6d5-194">Lo scenario viene eliminato insieme ai provider assegnati.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="1e6d5-195">È possibile ricreare lo scenario rieseguendo i comandi utilizzati inizialmente per crearlo.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="1e6d5-196">Non esiste una procedura per il ripristino di scenari o provider rimossi.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-196">There is no procedure to recover removed scenarios or providers.</span></span>
  
<span data-ttu-id="1e6d5-197">Quando si rimuove uno scenario tramite il cmdlet **Remove-CsClsScenario**, si rimuove completamente lo scenario dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="1e6d5-198">Per utilizzare gli scenari creati e i provider che facevano parte dello scenario, creare nuovi provider e assegnarli a un nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="1e6d5-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>
## <a name="see-also"></a><span data-ttu-id="1e6d5-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e6d5-199">See also</span></span>

[<span data-ttu-id="1e6d5-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="1e6d5-200">Get-CsClsScenario</span></span>](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="1e6d5-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="1e6d5-201">New-CsClsScenario</span></span>](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="1e6d5-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="1e6d5-202">Remove-CsClsScenario</span></span>](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="1e6d5-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="1e6d5-203">Set-CsClsScenario</span></span>](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[<span data-ttu-id="1e6d5-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="1e6d5-204">New-CsClsProvider</span></span>](/powershell/module/skype/new-csclsprovider?view=skype-ps)