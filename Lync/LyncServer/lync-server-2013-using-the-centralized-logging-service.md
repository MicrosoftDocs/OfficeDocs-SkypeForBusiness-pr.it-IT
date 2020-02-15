---
title: 'Lync Server 2013: utilizzo del servizio di registrazione centralizzato'
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
ms.openlocfilehash: 565c71a2a4e52b50b4807d7a5c5673e24c0a1a71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="a212a-102">Utilizzo del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a212a-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a212a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a212a-104">Il servizio di registrazione centralizzato è una nuova funzionalità di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a212a-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="a212a-105">È una versione sostitutiva e migliorata degli strumenti **OCSLogger** e **OCSTracer** presenti nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a212a-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="a212a-106">È possibile utilizzare il servizio di registrazione centralizzato per eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a212a-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="a212a-107">Avviare la registrazione su uno o più computer e pool da una località singola, con un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="a212a-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="a212a-108">Interrompere la registrazione su uno o più computer e pool da una località singola, con un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="a212a-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="a212a-p102">Cercare registri su uno o più computer e pool per località singola o singolo comando. È possibile personalizzare il comando di ricerca affinché restituisce l'intera aggregazione di registri raccolti e archiviati su tutti i computer, o affinché restituisca un risultato più filtrato, contenente soltanto dati specifici.</span><span class="sxs-lookup"><span data-stu-id="a212a-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="a212a-111">Configurare sessioni di registrazione come segue:</span><span class="sxs-lookup"><span data-stu-id="a212a-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="a212a-112">Definire uno **Scenario**, oppure utilizzarne uno predefinito.</span><span class="sxs-lookup"><span data-stu-id="a212a-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="a212a-113">Uno *scenario* nel servizio di registrazione centralizzato è costituito da un ambito (globale o sito), un nome dello scenario per identificare lo scopo dello scenario e uno o più provider.</span><span class="sxs-lookup"><span data-stu-id="a212a-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="a212a-114">È possibile eseguire due scenari contemporaneamente su un computer.</span><span class="sxs-lookup"><span data-stu-id="a212a-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="a212a-p104">Utilizzare un *provider* esistente, o crearne uno nuovo. Un *provider* definisce cosa viene raccolto da una sessione di registrazione, nonché il livello di dettagli, i componenti da tracciare e i contrassegni applicati.</span><span class="sxs-lookup"><span data-stu-id="a212a-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="a212a-117">Se si ha familiarità con OCSLogger, il termine <EM>provider</EM> fa riferimento alla raccolta di <STRONG>componenti</STRONG> (ad esempio, S4, SIPStack), un <STRONG>tipo di registrazione</STRONG> (ad esempio, WPP, EventLog o IIS logfile), un <STRONG>livello di traccia</STRONG> (ad esempio, All, verbose, debug) e <STRONG>contrassegni</STRONG> (ad esempio, TF_COMPONENT, TF_DIAG).</span><span class="sxs-lookup"><span data-stu-id="a212a-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="a212a-118">Questi elementi sono definiti nel provider (variabile di Windows PowerShell) e vengono passati al comando del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="a212a-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="a212a-119">Configurare i computer e i pool dai quali si desidera raccogliere registri.</span><span class="sxs-lookup"><span data-stu-id="a212a-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="a212a-120">Definire l'ambito della sessione di registrazione dalle opzioni **Sito** (per eseguire raccolte di registri su computer che si trovano su quel sito soltanto), o **Globale** (per eseguire raccolte di registri su tutti i computer della distribuzione).</span><span class="sxs-lookup"><span data-stu-id="a212a-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="a212a-121">Il servizio di registrazione centralizzato è estremamente potente e può soddisfare quasi tutte le esigenze per la risoluzione dei problemi, ovvero grandi o piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a212a-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="a212a-122">Dall'analisi delle cause radice ai problemi di prestazioni, il servizio di registrazione centralizzato può essere uno strumento importante per tutti gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="a212a-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="a212a-123">Tutti gli esempi vengono visualizzati utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a212a-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="a212a-124">È presente un componente della riga di comando per il servizio di registrazione centralizzato denominato **CLSController. exe**.</span><span class="sxs-lookup"><span data-stu-id="a212a-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="a212a-125">Allo strumento da riga di comando viene offerto supporto dallo strumento stesso.</span><span class="sxs-lookup"><span data-stu-id="a212a-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="a212a-126">Tuttavia, le funzioni eseguibili dalla riga di comando sono limitate.</span><span class="sxs-lookup"><span data-stu-id="a212a-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="a212a-127">Utilizzando Lync Server Management Shell, è possibile accedere a un insieme di caratteristiche molto più grande e configurabile.</span><span class="sxs-lookup"><span data-stu-id="a212a-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="a212a-128">Quando si utilizza il servizio di registrazione centralizzato, è consigliabile considerare sempre Lync Server Management Shell come primo e principale metodo.</span><span class="sxs-lookup"><span data-stu-id="a212a-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="a212a-129">Negli argomenti di questa sezione viene illustrato come utilizzare il servizio di registrazione centralizzato ed esempi di utilizzo delle numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a212a-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a212a-130">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a212a-130">In This Section</span></span>

  - [<span data-ttu-id="a212a-131">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="a212a-132">Gestione delle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="a212a-133">Informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="a212a-134">Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="a212a-135">Utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="a212a-136">Utilizzo della ricerca nei registri di acquisizione creati dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="a212a-137">Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a212a-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

