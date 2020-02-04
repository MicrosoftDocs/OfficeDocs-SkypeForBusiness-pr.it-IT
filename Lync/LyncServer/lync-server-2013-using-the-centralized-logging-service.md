---
title: 'Lync Server 2013: uso del servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="29cd6-102">Uso del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29cd6-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29cd6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29cd6-104">Il servizio di registrazione centralizzato è una nuova funzionalità di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29cd6-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="29cd6-105">Si tratta di una sostituzione avanzata per gli strumenti **OCSLogger** e **OCSTracer** forniti nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="29cd6-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="29cd6-106">È possibile usare il servizio di registrazione centralizzato per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="29cd6-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="29cd6-107">Avviare la registrazione in uno o più computer e pool da un'unica posizione e comando.</span><span class="sxs-lookup"><span data-stu-id="29cd6-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="29cd6-108">Interrompere la registrazione in uno o più computer e pool da un'unica posizione e comando.</span><span class="sxs-lookup"><span data-stu-id="29cd6-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="29cd6-109">Eseguire ricerche nei registri in uno o più computer e pool per una singola posizione e un comando.</span><span class="sxs-lookup"><span data-stu-id="29cd6-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="29cd6-110">È possibile personalizzare il comando Cerca per restituire l'intera aggregazione dei log acquisiti e archiviati in tutti i computer oppure restituire un risultato ritagliato che acquisisce dati specifici.</span><span class="sxs-lookup"><span data-stu-id="29cd6-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="29cd6-111">Configurare le sessioni di registrazione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="29cd6-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="29cd6-112">Definire uno **scenario**oppure usare uno scenario predefinito.</span><span class="sxs-lookup"><span data-stu-id="29cd6-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="29cd6-113">Uno *scenario* in un servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome di scenario per identificare lo scopo dello scenario e uno o più provider.</span><span class="sxs-lookup"><span data-stu-id="29cd6-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="29cd6-114">È possibile eseguire due scenari in qualsiasi momento in un computer.</span><span class="sxs-lookup"><span data-stu-id="29cd6-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="29cd6-115">Utilizzare un *provider* esistente o creare un nuovo provider.</span><span class="sxs-lookup"><span data-stu-id="29cd6-115">Use an existing *provider* or create a new provider.</span></span> <span data-ttu-id="29cd6-116">Un *provider* definisce la raccolta della sessione di registrazione, il livello di dettaglio, i componenti da tracciare e i contrassegni applicati.</span><span class="sxs-lookup"><span data-stu-id="29cd6-116">A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="29cd6-117">Se si ha familiarità con OCSLogger, i <EM>provider</EM> di termini fanno riferimento alla raccolta di <STRONG>componenti</STRONG> (ad esempio, S4, SipStack), a un <STRONG>tipo di registrazione</STRONG> (ad esempio, WPP, EventLog o Logfile di IIS), a un <STRONG>livello di traccia</STRONG> , ad esempio all, Verbose, debug, e ai <STRONG>Contrassegni</STRONG> , ad esempio TF_COMPONENT, TF_DIAG.</span><span class="sxs-lookup"><span data-stu-id="29cd6-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="29cd6-118">Questi elementi sono definiti nel provider (una variabile di Windows PowerShell) e passati al comando servizio registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="29cd6-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="29cd6-119">Configurare i computer e i pool da cui si vogliono raccogliere i log.</span><span class="sxs-lookup"><span data-stu-id="29cd6-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="29cd6-120">Definire l'ambito per la sessione di registrazione dal **sito** delle opzioni (eseguire le acquisizioni di registrazione nei computer solo in questo sito) oppure **globale** (eseguire l'acquisizione di registrazione in tutti i computer della distribuzione).</span><span class="sxs-lookup"><span data-stu-id="29cd6-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="29cd6-121">Il servizio di registrazione centralizzato è estremamente potente e può soddisfare quasi tutte le esigenze di risoluzione dei problemi, ovvero grandi o piccoli.</span><span class="sxs-lookup"><span data-stu-id="29cd6-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="29cd6-122">Dall'analisi causa radice ai problemi di prestazioni, il servizio di registrazione centralizzato può essere uno strumento importante per qualsiasi amministratore.</span><span class="sxs-lookup"><span data-stu-id="29cd6-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="29cd6-123">Tutti gli esempi vengono visualizzati con Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="29cd6-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="29cd6-124">Esiste un componente della riga di comando per il servizio di registrazione centralizzato denominato **CLSController. exe**.</span><span class="sxs-lookup"><span data-stu-id="29cd6-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="29cd6-125">La guida viene fornita per lo strumento della riga di comando tramite lo strumento stesso.</span><span class="sxs-lookup"><span data-stu-id="29cd6-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="29cd6-126">Tuttavia, esiste un set limitato di funzioni che è possibile eseguire dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="29cd6-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="29cd6-127">L'uso di Lync Server Management Shell consente di accedere a un insieme di caratteristiche molto più ampio e configurabile.</span><span class="sxs-lookup"><span data-stu-id="29cd6-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="29cd6-128">Quando si usa il servizio di registrazione centralizzato, è consigliabile considerare sempre Lync Server Management Shell come primo e più importante metodo.</span><span class="sxs-lookup"><span data-stu-id="29cd6-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="29cd6-129">Gli argomenti di questa sezione spiegano come usare il servizio di registrazione centralizzato ed esempi di come usare le numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="29cd6-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29cd6-130">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="29cd6-130">In This Section</span></span>

  - [<span data-ttu-id="29cd6-131">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="29cd6-132">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="29cd6-133">Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="29cd6-134">Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="29cd6-135">Uso di stop per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="29cd6-136">Uso della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="29cd6-137">Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29cd6-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

