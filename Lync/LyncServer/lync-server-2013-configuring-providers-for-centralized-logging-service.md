---
title: 'Lync Server 2013: configurazione dei provider per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="df2d2-102">Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df2d2-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df2d2-103">_**Argomento Ultima modifica:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="df2d2-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="df2d2-104">I concetti e la configurazione dei *provider* in un servizio di registrazione centralizzato è uno dei più importanti da afferrare.</span><span class="sxs-lookup"><span data-stu-id="df2d2-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="df2d2-105">I *provider* sono mappati direttamente ai componenti del ruolo di Lync Server Server nel modello di traccia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df2d2-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="df2d2-106">Il provider definisce i componenti di un Lync Server 2013 che verranno analizzati, il tipo di messaggi (ad esempio, fatale, Error o Warning) da raccogliere e i contrassegni (ad esempio, TF\_Connection o TF\_diag).</span><span class="sxs-lookup"><span data-stu-id="df2d2-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="df2d2-107">I provider sono i componenti rintracciabili in ogni ruolo di server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df2d2-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="df2d2-108">Usando i provider, Definisci il livello e il tipo di traccia sui componenti (ad esempio, S4, SIPStack, IM e Presence).</span><span class="sxs-lookup"><span data-stu-id="df2d2-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="df2d2-109">Il provider definito viene usato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.</span><span class="sxs-lookup"><span data-stu-id="df2d2-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="df2d2-110">Per eseguire le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene una delle opzioni questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="df2d2-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="df2d2-111">Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="df2d2-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="df2d2-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="df2d2-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="df2d2-113">Il resto di questo argomento illustra come definire i provider, modificare un provider e il contenuto di una definizione di provider per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="df2d2-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="df2d2-114">Esistono due modi per emettere comandi di servizio di registrazione centralizzati.</span><span class="sxs-lookup"><span data-stu-id="df2d2-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="df2d2-115">Per impostazione predefinita, è possibile usare CLSController. exe nella directory C\\: programmi\\comuni di\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="df2d2-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="df2d2-116">In alternativa, puoi usare Lync Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df2d2-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="df2d2-117">La distinzione importante è che quando si usa CLSController. exe alla riga di comando è disponibile una selezione limitata di scenari in cui i provider sono già definiti e non sono modificabili, ma è possibile definire il livello di log.</span><span class="sxs-lookup"><span data-stu-id="df2d2-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="df2d2-118">Usando Windows PowerShell puoi definire nuovi provider da usare nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e su quale livello raccolgono i dati.</span><span class="sxs-lookup"><span data-stu-id="df2d2-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="df2d2-119">Come accennato, i provider sono molto potenti.</span><span class="sxs-lookup"><span data-stu-id="df2d2-119">As mentioned, providers are very powerful.</span></span> <span data-ttu-id="df2d2-120">Tuttavia, gli scenari sono più potenti perché contengono l'incorporamento di tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider.</span><span class="sxs-lookup"><span data-stu-id="df2d2-120">However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent.</span></span> <span data-ttu-id="df2d2-121">Con gli scenari che sono una raccolta di provider, questa operazione potrebbe essere confrontata con l'esecuzione di un file batch contenente centinaia di comandi per raccogliere molte informazioni rispetto al rilascio di centinaia di comandi, uno alla volta, nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="df2d2-121">With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="df2d2-122">Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato offre numerosi scenari già definiti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="df2d2-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="df2d2-123">Gli scenari forniti coprono la stragrande maggioranza dei possibili problemi che incontrerai.</span><span class="sxs-lookup"><span data-stu-id="df2d2-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="df2d2-124">In rari casi potrebbe essere necessario creare e definire provider e assegnarli agli scenari.</span><span class="sxs-lookup"><span data-stu-id="df2d2-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="df2d2-125">Ti consigliamo vivamente di acquisire familiarità con ognuno degli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari.</span><span class="sxs-lookup"><span data-stu-id="df2d2-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="df2d2-126">Mentre le informazioni sulla creazione di provider si trovano qui per familiarizzare con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, in questo momento non vengono forniti dettagli sui provider stessi.</span><span class="sxs-lookup"><span data-stu-id="df2d2-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="df2d2-127">Introdotti in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi chiave della definizione di un provider per l'uso in uno scenario sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="df2d2-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="df2d2-128">**Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="df2d2-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="df2d2-129">I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="df2d2-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="df2d2-130">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="df2d2-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="df2d2-131">Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte dell'architettura del servizio di registrazione centralizzata che sta eseguendo la traccia dei componenti definiti nella configurazione di provider.</span><span class="sxs-lookup"><span data-stu-id="df2d2-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="df2d2-132">**Livelli di registrazione**   OCSLogger fornito l'opzione per scegliere un numero di livelli di dettaglio per i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="df2d2-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="df2d2-133">Questa caratteristica è parte integrante del servizio di registrazione centralizzato e degli scenari e viene definita dal parametro **Type** .</span><span class="sxs-lookup"><span data-stu-id="df2d2-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="df2d2-134">È possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="df2d2-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="df2d2-135">**Tutti**   raccoglie i messaggi di traccia di tipo Fatal, Error, Warning e info nel log per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="df2d2-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="df2d2-136">**Fatal**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="df2d2-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="df2d2-137">**Errore**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito, oltre a messaggi irreversibili.</span><span class="sxs-lookup"><span data-stu-id="df2d2-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="df2d2-138">**Avviso**   raccoglie solo i messaggi di traccia che indicano un avviso per il provider definito, oltre a messaggi fatali e di errore.</span><span class="sxs-lookup"><span data-stu-id="df2d2-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="df2d2-139">**Informazioni**   raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi fatali, di errore e di avviso.</span><span class="sxs-lookup"><span data-stu-id="df2d2-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="df2d2-140">**Verbose**   raccoglie tutti i messaggi di traccia di tipo Fatal, Error, Warning e info per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="df2d2-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="df2d2-141">**Flags**   OCSLogger ha fornito l'opzione per scegliere contrassegni per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia.</span><span class="sxs-lookup"><span data-stu-id="df2d2-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="df2d2-142">È possibile scegliere i contrassegni seguenti in base al provider:</span><span class="sxs-lookup"><span data-stu-id="df2d2-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="df2d2-143">**La\_connessione**   TF include voci di log correlate alla connessione.</span><span class="sxs-lookup"><span data-stu-id="df2d2-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="df2d2-144">Questi registri includono informazioni sulle connessioni stabilite da e verso un particolare componente.</span><span class="sxs-lookup"><span data-stu-id="df2d2-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="df2d2-145">Può anche includere informazioni significative a livello di rete, ovvero per i componenti senza il concetto di connessione.</span><span class="sxs-lookup"><span data-stu-id="df2d2-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="df2d2-146">**TF\_Security**   offre tutti gli eventi/voci di log correlate alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="df2d2-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="df2d2-147">Ad esempio, per SipStack, si tratta di eventi di sicurezza come l'errore di convalida del dominio e gli errori di autenticazione client/autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="df2d2-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="df2d2-148">**TF\_diag**   offre eventi di diagnostica che è possibile usare per diagnosticare o risolvere i problemi del componente.</span><span class="sxs-lookup"><span data-stu-id="df2d2-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="df2d2-149">Ad esempio, per SipStack, si tratta di errori di certificato o di avvisi e messaggi DNS.</span><span class="sxs-lookup"><span data-stu-id="df2d2-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="df2d2-150">**Il\_protocollo**   TF fornisce messaggi di protocollo, ad esempio messaggi SIP e combinati di codec community.</span><span class="sxs-lookup"><span data-stu-id="df2d2-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="df2d2-151">**Il\_componente**   TF Abilita la registrazione dei componenti specificati come parte dei provider.</span><span class="sxs-lookup"><span data-stu-id="df2d2-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="df2d2-152">**Tutto**   imposta tutti i contrassegni disponibili per il provider.</span><span class="sxs-lookup"><span data-stu-id="df2d2-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="df2d2-153">Per esaminare le informazioni sui provider di scenari di servizi di registrazione centralizzati esistenti</span><span class="sxs-lookup"><span data-stu-id="df2d2-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="df2d2-154">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2d2-155">Per esaminare la configurazione dei provider esistenti, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df2d2-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="df2d2-156">Ad esempio, per esaminare le informazioni sull'operatore di conferenza globale, digitare:</span><span class="sxs-lookup"><span data-stu-id="df2d2-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="df2d2-157">Il comando Visualizza un elenco di provider con i contrassegni, le impostazioni e i componenti associati.</span><span class="sxs-lookup"><span data-stu-id="df2d2-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="df2d2-158">Se le informazioni visualizzate non sono sufficienti o l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare altre informazioni definendo un metodo di output diverso.</span><span class="sxs-lookup"><span data-stu-id="df2d2-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="df2d2-159">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="df2d2-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="df2d2-160">L'output di questo comando Visualizza ogni provider visualizzato in un formato a cinque righe con il nome del provider, il tipo di registrazione, il livello di registrazione, i contrassegni, il GUID e il ruolo, ognuno in una riga distinta.</span><span class="sxs-lookup"><span data-stu-id="df2d2-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="df2d2-161">Per definire un nuovo provider di scenari del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="df2d2-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="df2d2-162">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2d2-163">Un provider di scenari è costituito da un componente da tracciare, da contrassegni da usare e da un livello di dettaglio da raccogliere.</span><span class="sxs-lookup"><span data-stu-id="df2d2-163">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect.</span></span> <span data-ttu-id="df2d2-164">Per eseguire questa operazione, digitare:</span><span class="sxs-lookup"><span data-stu-id="df2d2-164">You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="df2d2-165">Ad esempio, la definizione di un provider di traccia che definisce cosa raccogliere e il livello di dettaglio del provider Lyss ha l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="df2d2-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="df2d2-166">La raccolta-livello raccoglie messaggi fatali, di errore, di avviso e di informazioni.</span><span class="sxs-lookup"><span data-stu-id="df2d2-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="df2d2-167">I contrassegni usati sono tutti quelli definiti per il provider Lyss e includono la connessione\_TF, TF\_diag e TF\_Protocol.</span><span class="sxs-lookup"><span data-stu-id="df2d2-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="df2d2-168">Dopo aver definito la variabile $LyssProvider, è possibile usarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss.</span><span class="sxs-lookup"><span data-stu-id="df2d2-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="df2d2-169">Per completare la creazione e l'assegnazione del provider in un nuovo scenario, digitare:</span><span class="sxs-lookup"><span data-stu-id="df2d2-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="df2d2-170">Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="df2d2-171">Per modificare un provider di scenario del servizio di registrazione centralizzato esistente</span><span class="sxs-lookup"><span data-stu-id="df2d2-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="df2d2-172">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2d2-173">Per aggiornare o modificare la configurazione di un provider esistente, digitare:</span><span class="sxs-lookup"><span data-stu-id="df2d2-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="df2d2-174">È quindi possibile aggiornare lo scenario per assegnare il provider digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df2d2-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="df2d2-175">Il risultato finale del comando è che il sito scenario: Redmond/RedmondLyssInfo avrà aggiornato i contrassegni e il livello per il provider assegnato.</span><span class="sxs-lookup"><span data-stu-id="df2d2-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="df2d2-176">Puoi visualizzare il nuovo scenario usando Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="df2d2-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="df2d2-177">Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="df2d2-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="df2d2-178"><STRONG>New-ClsCsProvider</STRONG> non controlla per determinare se i contrassegni sono validi.</span><span class="sxs-lookup"><span data-stu-id="df2d2-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="df2d2-179">Verificare che l'ortografia dei contrassegni (ad esempio TF_DIAG o TF_CONNECTION) sia stata digitata correttamente.</span><span class="sxs-lookup"><span data-stu-id="df2d2-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="df2d2-180">Se i contrassegni non vengono digitati correttamente, il provider non potrà restituire le informazioni di log previste.</span><span class="sxs-lookup"><span data-stu-id="df2d2-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="df2d2-181">Se si vogliono aggiungere altri provider a questo scenario, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df2d2-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="df2d2-182">Dove ogni provider definito con la direttiva add è già stato definito tramite il processo **New-CsClsProvider** .</span><span class="sxs-lookup"><span data-stu-id="df2d2-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="df2d2-183">Per rimuovere un provider di scenari</span><span class="sxs-lookup"><span data-stu-id="df2d2-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="df2d2-184">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2d2-185">I cmdlet forniti consentono di aggiornare i provider esistenti e di creare nuovi provider.</span><span class="sxs-lookup"><span data-stu-id="df2d2-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="df2d2-186">Per rimuovere un provider, è necessario usare la direttiva Replace per il parametro provider per **impostare-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="df2d2-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="df2d2-187">L'unico modo per rimuovere completamente un provider è sostituirlo con un provider ridefinito con lo stesso nome e usare la direttiva Update.</span><span class="sxs-lookup"><span data-stu-id="df2d2-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="df2d2-188">Ad esempio, il nostro provider LyssProvider è definito con WPP come tipo di log, Level set to debug e set di contrassegni\_sono connessione TF\_e TF diag.</span><span class="sxs-lookup"><span data-stu-id="df2d2-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="df2d2-189">È necessario modificare i contrassegni in "tutti".</span><span class="sxs-lookup"><span data-stu-id="df2d2-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="df2d2-190">Per cambiare il provider, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df2d2-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="df2d2-191">Se si vuole rimuovere completamente uno scenario e i provider a esso associati, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="df2d2-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="df2d2-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="df2d2-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="df2d2-193">Il cmdlet <STRONG>Remove-CsClsScenario</STRONG> non chiede conferma.</span><span class="sxs-lookup"><span data-stu-id="df2d2-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="df2d2-194">Lo scenario viene eliminato, insieme ai provider assegnati.</span><span class="sxs-lookup"><span data-stu-id="df2d2-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="df2d2-195">Puoi ricreare lo scenario eseguendo nuovamente i comandi usati per crearlo inizialmente.</span><span class="sxs-lookup"><span data-stu-id="df2d2-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="df2d2-196">Non esiste una procedura per recuperare gli scenari o i provider rimossi.</span><span class="sxs-lookup"><span data-stu-id="df2d2-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="df2d2-197">Quando si rimuove uno scenario usando il cmdlet **Remove-CsClsScenario** , si rimuove completamente lo scenario dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="df2d2-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="df2d2-198">Per usare gli scenari creati e i provider che facevano parte dello scenario, è possibile creare nuovi provider e assegnarli a un nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="df2d2-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df2d2-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df2d2-199">See Also</span></span>


[<span data-ttu-id="df2d2-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="df2d2-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="df2d2-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="df2d2-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="df2d2-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="df2d2-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="df2d2-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="df2d2-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="df2d2-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="df2d2-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

