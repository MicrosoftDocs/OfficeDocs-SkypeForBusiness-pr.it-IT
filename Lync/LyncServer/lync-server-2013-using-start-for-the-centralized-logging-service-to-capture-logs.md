---
title: Uso di Start per il servizio di registrazione centralizzato per acquisire i registri
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
ms.openlocfilehash: 75090036b7120c8af7cda132c26d5b4fb02d3dab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="6d4a8-102">Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d4a8-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d4a8-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6d4a8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6d4a8-104">Per acquisire i registri di traccia usando il servizio di registrazione centralizzato, viene emesso un comando per iniziare la registrazione in uno o più computer e pool.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="6d4a8-105">È inoltre possibile emettere parametri che definiscono i computer o i pool, quali scenari eseguire, ad esempio AlwaysOn, un altro scenario predefinito o uno scenario creato, quali componenti di Lync Server (ad esempio, S4, SipStack) devono essere rintracciati.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="6d4a8-106">Per acquisire le informazioni appropriate, è necessario assicurarsi di usare lo scenario giusto per raccogliere informazioni rilevanti per il problema.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="6d4a8-107">Nel servizio di registrazione centralizzato, uno scenario è il concetto di attivazione della registrazione basato su una raccolta di componenti server, livelli di registrazione e contrassegni, che è molto più efficiente e utile che definire questi elementi in base al server.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="6d4a8-108">Puoi definire e specificare uno scenario da eseguire e lo scenario viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="6d4a8-109">Lo scenario predefinito è denominato **AlwaysOn**.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-109">The default scenario is called **AlwaysOn**.</span></span> <span data-ttu-id="6d4a8-110">Lo scopo previsto per AlwaysOn è l'esecuzione costante dello scenario, come implica il nome dello scenario.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-110">The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies.</span></span> <span data-ttu-id="6d4a8-111">Lo scenario AlwaysOn raccoglie informazioni a livello di informazioni (si noti che il livello di registrazione info include fatale, Error e Warning oltre ai messaggi info) per molti dei componenti server più comuni.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-111">The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components.</span></span> <span data-ttu-id="6d4a8-112">AlwaysOn raccoglie le informazioni prima, durante e dopo che si verifica un problema.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-112">AlwaysOn collects information before, during, and after a problem occurs.</span></span> <span data-ttu-id="6d4a8-113">Ciò si differenzia in modo significativo dal comportamento tipico degli strumenti di registrazione precedenti, ad esempio OCSLogger.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-113">This differs dramatically from the typical behavior of previous logging tools such as OCSLogger.</span></span> <span data-ttu-id="6d4a8-114">Hai eseguito OCSLogger dopo che il problema era già avvenuto, rendendo più difficile la risoluzione dei problemi perché i dati che hai sono reattivi e non proattivi.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-114">You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive.</span></span> <span data-ttu-id="6d4a8-115">Se AlwaysOn non contiene le informazioni che si stanno cercando per fare riferimento al componente problema e indicare una linea di azione per risolverlo (che non è probabilmente dato l'ampiezza e la profondità dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole conferma per determinare altre informazioni utili, ad esempio la creazione di un nuovo scenario, la raccolta di altri dati, l'esecuzione di una ricerca diversa per raccogliere dettagli più mirati e così via.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-115">If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="6d4a8-116">Il servizio di registrazione centralizzato offre due modi per emettere comandi.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="6d4a8-117">Un certo numero di argomenti sono stati concentrati sull'uso di Windows PowerShell tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="6d4a8-118">La possibilità di usare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'uso del servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="6d4a8-119">Dato che Windows PowerShell tramite Lync Server Management Shell è quasi onnipresente per tutte le funzioni di Lync Server, vengono discussi solo i comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6d4a8-120">Se si decide di usare il set di comandi limitato disponibile dalla riga di comando, è possibile ottenere assistenza con CLSController. exe digitando <CODE>ClsController.exe</CODE>.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="6d4a8-121">Per impostazione predefinita, <STRONG>ClsController. exe</STRONG> viene installato nella directory C:\Programmi\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="6d4a8-122">Per eseguire Start-CsClsLogging con Windows PowerShell usando i comandi di base</span><span class="sxs-lookup"><span data-stu-id="6d4a8-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="6d4a8-123">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6d4a8-124">Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="6d4a8-125">Ad esempio, per avviare lo scenario **AlwaysOn** , digitare:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6d4a8-126">Lo scenario AlwaysOn non ha durata predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="6d4a8-127">Questo scenario verrà eseguito fino a quando non lo Interrompi esplicitamente con il cmdlet <STRONG>Stop-CsClsLogging</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="6d4a8-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="6d4a8-128">Per informazioni dettagliate, vedere <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-128">For details, see <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="6d4a8-129">Per tutti gli altri scenari, la durata predefinita è di 4 ore.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="6d4a8-130">Premere INVIO per eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6d4a8-131">Potrebbe essere necessario un breve lasso di tempo (da 30 a 60 secondi) per i comandi da eseguire e per ricevere lo stato di nuovo dai computer della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="6d4a8-132">![Esecuzione di Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="6d4a8-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="6d4a8-133">Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire come indicato di seguito, ad esempio l' **autenticazione**dello scenario:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6d4a8-134">È possibile avere un totale di due scenari in esecuzione in qualsiasi computer specifico in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="6d4a8-135">Se il comando è globale nell'ambito, tutti i computer della distribuzione eseguiranno lo scenario o gli scenari.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="6d4a8-136">Per avviare un terzo scenario, è necessario interrompere la registrazione nel computer, nel pool, nel sito o nell'ambito globale in cui si vuole eseguire il nuovo scenario.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="6d4a8-137">Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o entrambi gli scenari in uno o più computer e pool.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="6d4a8-138">Per informazioni dettagliate sulla gestione degli scenari in uso, vedere <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013</A> e <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="6d4a8-139">Per eseguire Start-CsClsLogging con Windows PowerShell tramite comandi avanzati</span><span class="sxs-lookup"><span data-stu-id="6d4a8-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="6d4a8-140">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6d4a8-141">Sono disponibili parametri aggiuntivi per gestire i comandi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="6d4a8-142">È possibile usare la durata per regolare il periodo di tempo per l'esecuzione dello scenario.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="6d4a8-143">È anche possibile definire-computer, un elenco di nomi di dominio completi di computer (FQDN) separati da una virgola o da-pools, un elenco delimitato da virgole di FQDN per i pool di cui si vuole eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="6d4a8-144">Si avvia una sessione di registrazione per lo scenario *UserReplicator* nel pool "pool01.contoso.NET".</span><span class="sxs-lookup"><span data-stu-id="6d4a8-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="6d4a8-145">Puoi anche definire la durata della sessione di registrazione a 8 ore.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="6d4a8-146">A tale scopo, digitare:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="6d4a8-147">L'esecuzione corretta di questo scenario restituisce un risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="6d4a8-148">![Esecuzione di Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="6d4a8-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="6d4a8-149">Tieni presente che in questo esempio viene eseguito lo scenario AlwaysOn e lo scenario UserReplicator è in corso.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d4a8-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d4a8-150">See Also</span></span>


[<span data-ttu-id="6d4a8-151">Panoramica del servizio di registrazione centralizzato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d4a8-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

