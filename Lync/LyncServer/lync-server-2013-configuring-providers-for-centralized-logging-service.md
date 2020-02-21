---
title: 'Lync Server 2013: configurazione dei provider per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bc8ad2f5372ee9b434a1236e9d0cbba0f34a5de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="c6e04-102">Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6e04-102">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6e04-103">_**Ultimo argomento modificato:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="c6e04-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="c6e04-104">I concetti e la configurazione dei *provider* nel servizio di registrazione centralizzato è uno dei più importanti da afferrare.</span><span class="sxs-lookup"><span data-stu-id="c6e04-104">The concepts and configuration of *providers* in Centralized Logging Service is one of the most important to grasp.</span></span> <span data-ttu-id="c6e04-105">I *provider* vengono mappati direttamente ai componenti del ruolo del server Lync Server nel modello di traccia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6e04-105">The *providers* map directly to Lync Server server role components in the Lync Server tracing model.</span></span> <span data-ttu-id="c6e04-106">Il provider definisce i componenti di un Lync Server 2013 che verranno rintracciati, il tipo di messaggi (ad esempio, fatale, errore o avviso) da raccogliere e i flag, ad esempio la connessione TF\_o TF\_diag.</span><span class="sxs-lookup"><span data-stu-id="c6e04-106">The provider defines the components of a Lync Server 2013 that will be traced, the type of messages (for example, fatal, error, or warning) to collect, and the flags (for example, TF\_Connection or TF\_Diag).</span></span> <span data-ttu-id="c6e04-107">I provider sono i componenti tracciabili in ogni ruolo del server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6e04-107">Providers are the traceable components in each Lync Server server role.</span></span> <span data-ttu-id="c6e04-108">Tramite i provider vengono definiti il livello e il tipo di traccia per i componenti (ad esempio, S4, SIPStack, messaggistica istantanea e presenza).</span><span class="sxs-lookup"><span data-stu-id="c6e04-108">By using providers, you define the level and type of tracing on components (for example, S4, SIPStack, IM and Presence).</span></span> <span data-ttu-id="c6e04-109">Il provider definito viene utilizzato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica riferita a una condizione problematica specifica.</span><span class="sxs-lookup"><span data-stu-id="c6e04-109">The defined provider is used in a scenario to group all of the providers for a given logical collection that address a specific problem condition.</span></span>

<span data-ttu-id="c6e04-110">Per eseguire le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="c6e04-110">To run the Centralized Logging Service functions using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="c6e04-111">Per restituire un elenco di tutti i ruoli RBAC (Role-Based Access Control) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c6e04-111">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="c6e04-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c6e04-112">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="c6e04-113">La parte restante di questo argomento è incentrata su come definire i provider, modificare un provider e la definizione di un provider che contiene per ottimizzare la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c6e04-113">The remainder of this topic focuses on how to define providers, modify a provider and what a provider definition contains to optimize your troubleshooting.</span></span> <span data-ttu-id="c6e04-114">Esistono due modi per emettere comandi del servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="c6e04-114">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="c6e04-115">È possibile\\utilizzare CLSController. exe che si trova, per impostazione predefinita, nella directory C: Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent.</span><span class="sxs-lookup"><span data-stu-id="c6e04-115">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="c6e04-116">In alternativa, è possibile utilizzare Lync Server Management Shell per emettere comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6e04-116">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="c6e04-117">La distinzione importante è che quando si utilizza CLSController. exe nella riga di comando è disponibile una selezione limitata di scenari in cui i provider sono già definiti e non sono modificabili, ma è possibile definire il livello di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c6e04-117">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available in which the providers are already defined and are not changeable, but you can define the log level.</span></span> <span data-ttu-id="c6e04-118">Utilizzando Windows PowerShell, è possibile definire nuovi provider per l'utilizzo nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e sul livello di raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="c6e04-118">By using Windows PowerShell, you can define new providers for use in your logging sessions, and have complete control over their creation, what they collect, and at what level they collect data.</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c6e04-p104">Come già accennato, i provider sono uno strumento dalle grandi potenzialità. Gli scenari, tuttavia, sono ancora più efficaci perché incorporano tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Dato che gli scenari sono in effetti una raccolta di provider, possono essere paragonati all'esecuzione di un file batch contenente centinaia di comandi per raccogliere grandi quantità di informazioni anziché eseguire centinaia di comandi, uno alla volta, dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c6e04-p104">As mentioned, providers are very powerful. However, scenarios are more powerful because they contain the embodiment of all information needed to set and execute tracing on the components that the providers represent. With scenarios being a collection of providers, this could be loosely compared to running a batch file containing hundreds of commands to collect a lot of information versus issuing hundreds of commands, one at a time, at the command line.</span></span><BR><span data-ttu-id="c6e04-122">Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato fornisce una serie di scenari già definiti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="c6e04-122">Instead of requiring you to dig deeply into the details of providers, the Centralized Logging Service provides a number of scenarios that are already defined for you.</span></span> <span data-ttu-id="c6e04-123">Gli scenari forniti coprono la maggior parte dei possibili problemi che verranno riscontrati.</span><span class="sxs-lookup"><span data-stu-id="c6e04-123">The provided scenarios cover the vast majority of possible issues that you will encounter.</span></span> <span data-ttu-id="c6e04-124">In rari casi, potrebbe essere necessario creare e definire provider e assegnarli a scenari.</span><span class="sxs-lookup"><span data-stu-id="c6e04-124">In rare cases, you may need to create and define providers and assign them to scenarios.</span></span> <span data-ttu-id="c6e04-125">È consigliabile acquisire familiarità con tutti gli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari.</span><span class="sxs-lookup"><span data-stu-id="c6e04-125">We strongly recommend that you become familiar with each of the scenarios provided before you investigate the need to create new providers and scenarios.</span></span> <span data-ttu-id="c6e04-126">Anche se le informazioni sulla creazione di provider sono disponibili in questo articolo per familiarizzare con la modalità di utilizzo degli elementi provider per raccogliere informazioni di traccia, i dettagli sui provider stessi non vengono forniti in questo momento.</span><span class="sxs-lookup"><span data-stu-id="c6e04-126">While information about creating providers is found here to familiarize you with how the scenarios use the provider elements to collect trace information, details on the providers themselves are not provided at this time.</span></span>



</div>

<span data-ttu-id="c6e04-127">Introdotti in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi principali per la definizione di un provider per l'utilizzo in uno scenario sono:</span><span class="sxs-lookup"><span data-stu-id="c6e04-127">Introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the key elements of defining a provider for use in a scenario are:</span></span>

  - <span data-ttu-id="c6e04-128">**Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger cosa dovrebbe raccogliere i log dal motore di traccia.</span><span class="sxs-lookup"><span data-stu-id="c6e04-128">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="c6e04-129">I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="c6e04-129">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="c6e04-130">Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server in cui il servizio di registrazione centralizzato può raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="c6e04-130">If you are not familiar with OCSLogger, providers are server-role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="c6e04-131">Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte architettonica del servizio di registrazione centralizzato che esegue la traccia dei componenti definiti nella configurazione di provider.</span><span class="sxs-lookup"><span data-stu-id="c6e04-131">In the case of the Centralized Logging Service, the CLSAgent is the architectural part of the Centralized Logging Service that is doing the tracing of the components that you define in the providers configuration.</span></span>

  - <span data-ttu-id="c6e04-132">**Livelli di registrazione**   OCSLogger è stata fornita la possibilità di scegliere un certo numero di livelli di dettaglio per i dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="c6e04-132">**Logging levels**   OCSLogger provided the option to choose a number of levels of detail for the data collected.</span></span> <span data-ttu-id="c6e04-133">Questa funzionalità è parte integrante del servizio di registrazione centralizzato e degli scenari ed è definita dal parametro **Type** .</span><span class="sxs-lookup"><span data-stu-id="c6e04-133">This feature is an integral part of the Centralized Logging Service and scenarios, and is defined by the **Type** parameter.</span></span> <span data-ttu-id="c6e04-134">È possibile scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="c6e04-134">You can choose from the following:</span></span>
    
      - <span data-ttu-id="c6e04-135">**Tutti**   i messaggi di traccia di tipo fatale, errore, avviso e informazioni vengono raccolti nel registro per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="c6e04-135">**All**   Collects trace messages of type fatal, error, warning, and info to the log for the defined provider.</span></span>
    
      - <span data-ttu-id="c6e04-136">**Fatal**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="c6e04-136">**Fatal**   Collects only the trace messages that indicate a failure for the defined provider.</span></span>
    
      - <span data-ttu-id="c6e04-137">**L'errore**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito, oltre ai messaggi irreversibili.</span><span class="sxs-lookup"><span data-stu-id="c6e04-137">**Error**   Collects only the trace messages that indicate an error for the defined provider, plus fatal messages.</span></span>
    
      - <span data-ttu-id="c6e04-138">**Avviso**   raccoglie solo i messaggi di traccia che indicano un avviso per il provider definito, oltre a messaggi fatali e di errore.</span><span class="sxs-lookup"><span data-stu-id="c6e04-138">**Warning**   Collects only the trace messages that indicate a warning for the defined provider, plus fatal and error messages.</span></span>
    
      - <span data-ttu-id="c6e04-139">**Info**   raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi fatali, di errore e di avviso.</span><span class="sxs-lookup"><span data-stu-id="c6e04-139">**Info**   Collects only the trace messages that indicate an informational message for the defined provider, plus fatal, error, and warning messages.</span></span>
    
      - <span data-ttu-id="c6e04-140">**Verbose**   raccoglie tutti i messaggi di traccia di tipo fatale, Error, Warning e info per il provider definito.</span><span class="sxs-lookup"><span data-stu-id="c6e04-140">**Verbose**   Collects all trace messages of type fatal, error, warning and info for the defined provider.</span></span>

  - <span data-ttu-id="c6e04-141">**Flags**   OCSLogger è stata fornita la possibilità di scegliere flag per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia.</span><span class="sxs-lookup"><span data-stu-id="c6e04-141">**Flags**   OCSLogger provided the option to choose flags for each provider that defined what type of information you could retrieve from the trace files.</span></span> <span data-ttu-id="c6e04-142">È possibile scegliere tra i flag seguenti, in base al provider:</span><span class="sxs-lookup"><span data-stu-id="c6e04-142">You can chose the following flags, based on the provider:</span></span>
    
      - <span data-ttu-id="c6e04-143">**La\_connessione**   TF fornisce le voci di registro correlate alla connessione.</span><span class="sxs-lookup"><span data-stu-id="c6e04-143">**TF\_Connection**   Provides connection-related log entries.</span></span> <span data-ttu-id="c6e04-144">Questi log includono informazioni sulle connessioni stabilite con e da un particolare componente.</span><span class="sxs-lookup"><span data-stu-id="c6e04-144">These logs include information about connections established to and from a particular component.</span></span> <span data-ttu-id="c6e04-145">Potrebbero essere anche incluse informazioni significative a livello di rete, ovvero per componenti non correlati al concetto di connessione.</span><span class="sxs-lookup"><span data-stu-id="c6e04-145">This may also include significant network-level information (that is, for components without the concept of a connection).</span></span>
    
      - <span data-ttu-id="c6e04-146">**La\_sicurezza**   TF fornisce tutti gli eventi e le voci di registro relative alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c6e04-146">**TF\_Security**   Provides all events/log entries related to security.</span></span> <span data-ttu-id="c6e04-147">Per SipStack, ad esempio, si tratta degli eventi di sicurezza come errori di convalida del dominio ed errori di autenticazione/autorizzazione dei client.</span><span class="sxs-lookup"><span data-stu-id="c6e04-147">For example, for SipStack, these are security events such as domain validation failure, and client authentication/authorization failures.</span></span>
    
      - <span data-ttu-id="c6e04-148">**TF\_diag**   fornisce gli eventi di diagnostica che è possibile utilizzare per diagnosticare o risolvere i problemi del componente.</span><span class="sxs-lookup"><span data-stu-id="c6e04-148">**TF\_Diag**   Provides diagnostics events that you can use to diagnose or troubleshoot the component.</span></span> <span data-ttu-id="c6e04-149">Per SipStack, ad esempio, si tratta di errori dei certificati oppure di avvisi/errori DNS.</span><span class="sxs-lookup"><span data-stu-id="c6e04-149">For example, for SipStack, these are certificate failures, or DNS warnings/errors.</span></span>
    
      - <span data-ttu-id="c6e04-150">**TF\_Protocol**   fornisce messaggi di protocollo, ad esempio messaggi SIP e combinati di codec community.</span><span class="sxs-lookup"><span data-stu-id="c6e04-150">**TF\_Protocol**   Provides protocol messages such as SIP and Combined Community Codec Pack messages.</span></span>
    
      - <span data-ttu-id="c6e04-151">**Il\_componente**   TF consente di abilitare la registrazione sui componenti specificati come parte dei provider.</span><span class="sxs-lookup"><span data-stu-id="c6e04-151">**TF\_Component**   Enables logging on the components specified as part of the providers.</span></span>
    
      - <span data-ttu-id="c6e04-152">**All**   consente di impostare tutti i flag disponibili per il provider.</span><span class="sxs-lookup"><span data-stu-id="c6e04-152">**All**   Sets all available flags available for the provider.</span></span>

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a><span data-ttu-id="c6e04-153">Per esaminare le informazioni sui provider di scenari del servizio di registrazione centralizzato esistenti</span><span class="sxs-lookup"><span data-stu-id="c6e04-153">To review information about existing Centralized Logging Service scenario providers</span></span>

1.  <span data-ttu-id="c6e04-154">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c6e04-155">Per esaminare la configurazione dei provider esistenti, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-155">To review the configuration of existing providers, type the following:</span></span>
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    <span data-ttu-id="c6e04-156">Per visualizzare informazioni sull'operatore conferenza globale, ad esempio, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6e04-156">For example, to review information about the global conferencing attendant, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA"
    
    <span data-ttu-id="c6e04-157">Il comando visualizza un elenco dei provider con i flag, le impostazioni e i componenti associati.</span><span class="sxs-lookup"><span data-stu-id="c6e04-157">The command displays a list of providers with the associated flags, settings, and components.</span></span> <span data-ttu-id="c6e04-158">Se le informazioni visualizzate non sono sufficienti o se l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare ulteriori informazioni definendo un metodo di output diverso.</span><span class="sxs-lookup"><span data-stu-id="c6e04-158">If the information displayed is not enough or the list is too long for the default Windows PowerShell list format, you can display additional information by defining a different output method.</span></span> <span data-ttu-id="c6e04-159">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6e04-159">To do this, type:</span></span>
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    <span data-ttu-id="c6e04-160">Nell'output di questo comando, le informazioni su ogni provider sono visualizzate su cinque righe separate che includono nome del provider, tipo di registrazione, livello di registrazione, flag, GUID e ruolo.</span><span class="sxs-lookup"><span data-stu-id="c6e04-160">The output of this command displays each provider displayed in a five line format with the provider name, type of logging, logging level, flags, GUID, and role, each one on a separate line.</span></span>

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a><span data-ttu-id="c6e04-161">Per definire un nuovo provider di scenari per il servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="c6e04-161">To define a new Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="c6e04-162">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c6e04-p113">Un provider di scenari è costituito dal componente da tracciare, i flag da utilizzare e il livello di dettaglio per la raccolta dei dati. Per definire questi elementi, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6e04-p113">A scenario provider consists of a component to trace, flags to use, and a level of detail to collect. You do this by typing:</span></span>
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    <span data-ttu-id="c6e04-165">La definizione di un provider di traccia per specificare quali dati raccogliere e con quale livello di dettaglio dal provider Lyss, ad esempio, è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-165">For example, a trace provider definition that defines what to collect and to what level of detail from the Lyss provider looks like the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

<span data-ttu-id="c6e04-166">Il parametro –Level consente di specificare se raccogliere i messaggi relativi a errori irreversibili, errori, avvisi e informazioni.</span><span class="sxs-lookup"><span data-stu-id="c6e04-166">The –Level collects fatal, error, warning, and information messages.</span></span> <span data-ttu-id="c6e04-167">I flag utilizzati sono tutti quelli definiti per il provider Lyss e includono la connessione TF\_, TF\_diag e il protocollo\_TF.</span><span class="sxs-lookup"><span data-stu-id="c6e04-167">The flags used are all of those defined for the Lyss provider, and include TF\_Connection, TF\_Diag and TF\_Protocol.</span></span>

<span data-ttu-id="c6e04-168">Dopo aver definito la variabile $LyssProvider è possibile utilizzarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss.</span><span class="sxs-lookup"><span data-stu-id="c6e04-168">After the variable $LyssProvider is defined, you can use it with the **New-CsClsScenario** cmdlet to collect traces from the Lyss provider.</span></span> <span data-ttu-id="c6e04-169">Per completare la creazione e l'assegnazione del provider a un nuovo scenario, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6e04-169">To complete the creation and assignment of the provider to a new scenario, type:</span></span>

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="c6e04-170">Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-170">Where $LyssProvider is the variable containing the defined scenario created with **New-CsClsProvider**.</span></span>

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a><span data-ttu-id="c6e04-171">Per modificare un provider di scenari del servizio di registrazione centralizzato esistente</span><span class="sxs-lookup"><span data-stu-id="c6e04-171">To change an existing Centralized Logging Service scenario provider</span></span>

1.  <span data-ttu-id="c6e04-172">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-172">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c6e04-173">Per aggiornare o modificare la configurazione di un provider esistente, digitare:</span><span class="sxs-lookup"><span data-stu-id="c6e04-173">To update or change the configuration of an existing provider, type:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    <span data-ttu-id="c6e04-174">Aggiornare quindi lo scenario per assegnare il provider digitando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-174">You then update the scenario to assign the provider by typing the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

<span data-ttu-id="c6e04-175">Il risultato finale del comando è l'aggiornamento dei flag per lo scenario site:Redmond/RedmondLyssInfo e l'assegnazione del livello per il provider.</span><span class="sxs-lookup"><span data-stu-id="c6e04-175">The end result of the command is that the scenario site:Redmond/RedmondLyssInfo will have updated flags and level for the provider assigned to it.</span></span> <span data-ttu-id="c6e04-176">Per visualizzare il nuovo scenario, utilizzare Get-CsClsScenario.</span><span class="sxs-lookup"><span data-stu-id="c6e04-176">You can view the new scenario by using Get-CsClsScenario.</span></span> <span data-ttu-id="c6e04-177">Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span><span class="sxs-lookup"><span data-stu-id="c6e04-177">For details, see [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).</span></span>

<div class="">


> [!WARNING]  
> <span data-ttu-id="c6e04-178"><STRONG>New-ClsCsProvider</STRONG> non esegue un controllo per stabilire se i flag sono validi.</span><span class="sxs-lookup"><span data-stu-id="c6e04-178"><STRONG>New-ClsCsProvider</STRONG> does not check to determine whether the flags are valid.</span></span> <span data-ttu-id="c6e04-179">Assicurarsi di digitare correttamente i flag, ad esempio TF_DIAG o TF_CONNECTION.</span><span class="sxs-lookup"><span data-stu-id="c6e04-179">Make sure that the spelling of the flags (for example, TF_DIAG or TF_CONNECTION) is spelled correctly.</span></span> <span data-ttu-id="c6e04-180">Se il nome dei flag non è corretto, il provider non potrà restituire le informazioni di log previste.</span><span class="sxs-lookup"><span data-stu-id="c6e04-180">If the flags are not spelled correctly, the provider cannot return the expected log information.</span></span>



</div>

<span data-ttu-id="c6e04-181">Se si desidera aggiungere ulteriori provider a questo scenario, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-181">If you want to add additional providers to this scenario, type the following:</span></span>

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

<span data-ttu-id="c6e04-182">In cui ogni provider definito con la direttiva Add è già stato definito tramite il processo **New-CsClsProvider**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-182">Where each provider defined with the Add directive has already been defined using the **New-CsClsProvider** process.</span></span>

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a><span data-ttu-id="c6e04-183">Per rimuovere un provider di scenari</span><span class="sxs-lookup"><span data-stu-id="c6e04-183">To remove a scenario provider</span></span>

1.  <span data-ttu-id="c6e04-184">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-184">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c6e04-185">I cmdlet indicati consentono di aggiornare i provider esistenti e di crearne di nuovi.</span><span class="sxs-lookup"><span data-stu-id="c6e04-185">The cmdlets provided allow you to update existing providers and create new providers.</span></span> <span data-ttu-id="c6e04-186">Per rimuovere un provider, è necessario utilizzare la direttiva Replace per il parametro Provider in **Set-CsClsScenario**.</span><span class="sxs-lookup"><span data-stu-id="c6e04-186">To remove a provider, you must use the Replace directive for the Provider parameter to **Set-CsClsScenario**.</span></span> <span data-ttu-id="c6e04-187">L'unico modo per rimuovere completamente un provider consiste nel sostituirlo con un provider ridefinito con lo stesso nome e poi utilizzare la direttiva Update.</span><span class="sxs-lookup"><span data-stu-id="c6e04-187">The only way to completely remove a provider is to replace it with a redefined provider of the same name and use the Update directive.</span></span> <span data-ttu-id="c6e04-188">Ad esempio, il provider LyssProvider è definito con WPP come tipo di log, Level set to debug e flags set are TF\_Connection e TF\_diag.</span><span class="sxs-lookup"><span data-stu-id="c6e04-188">For example, our provider LyssProvider is defined with WPP as the log type, level set to Debug, and flags set are TF\_CONNECTION and TF\_DIAG.</span></span> <span data-ttu-id="c6e04-189">Supponendo di dover modificare i flag e impostare "All".</span><span class="sxs-lookup"><span data-stu-id="c6e04-189">You need to change the flags to “All”.</span></span> <span data-ttu-id="c6e04-190">per modificare il provider digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-190">To change the provider, type the following:</span></span>
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  <span data-ttu-id="c6e04-191">Se si desidera rimuovere completamente uno scenario e i provider associati, digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c6e04-191">If you want to completely remove a scenario and the providers associated with it, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    <span data-ttu-id="c6e04-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c6e04-192">For example:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="c6e04-193">Il cmdlet <STRONG>Remove-CsClsScenario</STRONG> non richiede alcuna conferma.</span><span class="sxs-lookup"><span data-stu-id="c6e04-193">The cmdlet <STRONG>Remove-CsClsScenario</STRONG> does not prompt you for confirmation.</span></span> <span data-ttu-id="c6e04-194">Lo scenario viene eliminato insieme ai provider assegnati.</span><span class="sxs-lookup"><span data-stu-id="c6e04-194">The scenario is deleted, along with the providers that were assigned to it.</span></span> <span data-ttu-id="c6e04-195">È possibile ricreare lo scenario rieseguendo i comandi utilizzati inizialmente per crearlo.</span><span class="sxs-lookup"><span data-stu-id="c6e04-195">You can recreate the scenario by re-running the commands used to create it initially.</span></span> <span data-ttu-id="c6e04-196">Non esiste una procedura per il ripristino di scenari o provider rimossi.</span><span class="sxs-lookup"><span data-stu-id="c6e04-196">There is no procedure to recover removed scenarios or providers.</span></span>

    
    </div>

<span data-ttu-id="c6e04-197">Quando si rimuove uno scenario tramite il cmdlet **Remove-CsClsScenario**, si rimuove completamente lo scenario dall'ambito.</span><span class="sxs-lookup"><span data-stu-id="c6e04-197">When you remove a scenario by using the **Remove-CsClsScenario** cmdlet, you completely remove the scenario from the scope.</span></span> <span data-ttu-id="c6e04-198">Per utilizzare gli scenari creati e i provider che facevano parte dello scenario, creare nuovi provider e assegnarli a un nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="c6e04-198">To use the scenarios that you created and the providers that were a part of the scenario, you create new providers and assign them to a new scenario.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6e04-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6e04-199">See Also</span></span>


[<span data-ttu-id="c6e04-200">Get-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c6e04-200">Get-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[<span data-ttu-id="c6e04-201">New-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c6e04-201">New-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[<span data-ttu-id="c6e04-202">Remove-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c6e04-202">Remove-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[<span data-ttu-id="c6e04-203">Set-CsClsScenario</span><span class="sxs-lookup"><span data-stu-id="c6e04-203">Set-CsClsScenario</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[<span data-ttu-id="c6e04-204">New-CsClsProvider</span><span class="sxs-lookup"><span data-stu-id="c6e04-204">New-CsClsProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

