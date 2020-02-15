---
title: Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b32a746f6614ea72e9f0f085a3d3731969cf5f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="28060-102">Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28060-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28060-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="28060-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="28060-104">Per acquisire i log di traccia utilizzando il servizio di registrazione centralizzato, è possibile eseguire un comando per iniziare la registrazione su uno o più computer e pool.</span><span class="sxs-lookup"><span data-stu-id="28060-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="28060-105">È inoltre possibile emettere parametri che definiscono i computer o i pool, quali scenari eseguire (ad esempio, AlwaysOn, un altro scenario predefinito o uno scenario creato), quali componenti di Lync Server (ad esempio, S4, SipStack) devono essere rintracciati.</span><span class="sxs-lookup"><span data-stu-id="28060-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="28060-106">Per acquisire le informazioni giuste è necessario assicurarsi di usare lo scenario corretto per la raccolta di informazioni pertinenti al problema.</span><span class="sxs-lookup"><span data-stu-id="28060-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="28060-107">Nel servizio di registrazione centralizzato, uno scenario è il concetto di attivazione della registrazione in base a un insieme di componenti server, livelli di registrazione e flag, che è molto più efficiente e utile rispetto alla necessità di definire tali elementi in base ai singoli server.</span><span class="sxs-lookup"><span data-stu-id="28060-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="28060-108">Si definisce e specifica uno scenario da eseguire, e questo viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="28060-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="28060-p103">Lo scenario predefinito è denominato **AlwaysOn**. Lo scopo di AlwaysOn, come indicato dal nome, è l'esecuzione costante dello scenario. Lo scenario AlwaysOn raccoglie informazioni a livello Info su molti dei più comuni componenti server. Tenere presente che questo livello di registrazione include, in aggiunta ai messaggi di informazioni, i messaggi di tipo Fatal, Error e Warning, ovvero relativi ad avvisi, errori ed errori irreversibili. AlwaysOn raccoglie informazioni prima, durante e dopo il verificarsi di un problema. Questo comportamento è radicalmente diverso rispetto a quello degli strumenti di registrazione precedenti, ad esempio OCSLogger. L'esecuzione di OCSLogger avveniva quando il problema si era già verificato, rendendone più difficoltosa la risoluzione poiché i dati raccolti erano di tipo reattivo e non proattivo. Se AlwaysOn non contiene le informazioni cercate per individuare il componente che causa il problema e indicare le azioni per la risoluzione (evento improbabile, data l'estensione e il livello di dettaglio dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole per determinare le altre operazioni da eseguire, ad esempio creare un nuovo scenario, raccogliere altre informazioni, eseguire una ricerca diversa per raccogliere dettagli più specifici e così via.</span><span class="sxs-lookup"><span data-stu-id="28060-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="28060-116">Il servizio di registrazione centralizzato offre due modalità di esecuzione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="28060-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="28060-117">Un certo numero di argomenti sono stati concentrati sull'utilizzo di Windows PowerShell tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="28060-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="28060-118">La possibilità di utilizzare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'utilizzo del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="28060-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="28060-119">Poiché Windows PowerShell tramite Lync Server Management Shell è quasi onnipresente per tutte le funzioni di Lync Server, vengono descritti solo i comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28060-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="28060-120">Se si decide di utilizzare il set di comandi limitato disponibile dalla riga di comando, è possibile ottenere assistenza con CLSController. exe digitando <CODE>ClsController.exe</CODE>.</span><span class="sxs-lookup"><span data-stu-id="28060-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="28060-121">Per impostazione predefinita, <STRONG>ClsController. exe</STRONG> è installato nella directory C:\Programmi\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="28060-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="28060-122">Per eseguire Start-CsClsLogging con Windows PowerShell utilizzando i comandi di base</span><span class="sxs-lookup"><span data-stu-id="28060-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="28060-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="28060-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="28060-124">Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="28060-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="28060-125">Ad esempio, per avviare lo scenario **AlwaysOn** digitare:</span><span class="sxs-lookup"><span data-stu-id="28060-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="28060-126">Lo scenario AlwaysOn non ha una durata predefinita.</span><span class="sxs-lookup"><span data-stu-id="28060-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="28060-127">Verrà eseguito finché non lo si interrompe esplicitamente con il cmdlet <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="28060-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="28060-128">Per informazioni dettagliate, vedere <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="28060-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="28060-129">Per tutti gli altri scenari, la durata predefinita è 4 ore.</span><span class="sxs-lookup"><span data-stu-id="28060-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="28060-130">Premere INVIO per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="28060-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="28060-131">Per l'esecuzione dei comandi e la comunicazione dello stato dai computer della distribuzione possono essere necessari da 30 a 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="28060-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="28060-132">![Esecuzione di Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="28060-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="28060-133">Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire (ad esempio lo scenario **Authentication**) come segue:</span><span class="sxs-lookup"><span data-stu-id="28060-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="28060-134">È possibile eseguire un totale di due scenari su qualsiasi computer in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="28060-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="28060-135">Se l'ambito del comando è globale, lo o gli scenari verranno eseguiti da tutti i computer della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="28060-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="28060-136">Per avviare un terzo scenario è necessario interrompere la registrazione nel computer, pool, sito o ambito globale in cui si vuole eseguire il nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="28060-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="28060-137">Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o per entrambi gli scenari in uno o più computer e pool.</span><span class="sxs-lookup"><span data-stu-id="28060-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="28060-138">Per informazioni dettagliate sulla gestione degli scenari in esecuzione, vedere <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using stop for the accentrated Logging Service in Lync Server 2013</A> e <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="28060-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="28060-139">Per eseguire Start-CsClsLogging con Windows PowerShell tramite comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="28060-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="28060-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="28060-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="28060-141">Sono disponibili ulteriori parametri per la gestione dei comandi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="28060-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="28060-142">–Duration consente di regolare la durata di esecuzione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="28060-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="28060-143">È anche possibile definire –Computers, un elenco di nomi di dominio completi (FQDN) di computer separati da una virgola, oppure –Pools, un elenco di FQDN separati da una virgola dei pool nei quali si vuole eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="28060-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="28060-144">È possibile avviare una sessione di registrazione per lo scenario di *UserReplicator* nel pool "pool01.contoso.NET".</span><span class="sxs-lookup"><span data-stu-id="28060-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="28060-145">La durata della sessione di registrazione deve essere di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="28060-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="28060-146">A questo scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="28060-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="28060-147">L'esecuzione corretta dello scenario restituisce un risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="28060-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="28060-148">![Esecuzione di Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="28060-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="28060-149">Si noti che in questo esempio gli scenari AlwaysOn e UserReplicator sono entrambi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="28060-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28060-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28060-150">See Also</span></span>


[<span data-ttu-id="28060-151">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28060-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

