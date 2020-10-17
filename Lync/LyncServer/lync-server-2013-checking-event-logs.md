---
title: 'Lync Server 2013: controllo dei registri eventi'
description: 'Lync Server 2013: controllo dei registri eventi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6617bde846fd38ab3282fd023b16e0a921f48920
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570982"
---
# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="2b547-103">Controllo dei registri eventi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b547-103">Checking event logs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b547-104">_**Ultimo argomento modificato:** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="2b547-104">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="2b547-105">È possibile utilizzare il [Visualizzatore eventi di Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) per visualizzare i registri eventi e ottenere informazioni sugli errori relativi ai servizi, sui problemi di replica in servizi di dominio Active Directory e sugli avvisi relativi alle risorse di sistema, ad esempio la memoria virtuale e lo spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="2b547-105">You can use [Windows Event Viewer](https://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="2b547-106">Il Visualizzatore eventi è incluso in Windows Server 2008 e 2012.</span><span class="sxs-lookup"><span data-stu-id="2b547-106">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="2b547-107">Nello strumento di registrazione di Lync Server 2013, quando si termina la sessione di debug, fare clic su **Analizza file di registro** per visualizzare i file di registro utilizzando lo strumento Snooper.</span><span class="sxs-lookup"><span data-stu-id="2b547-107">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="2b547-108">Il Visualizzatore eventi gestisce i registri sugli eventi relativi a applicazioni, sicurezza e sistema nel computer.</span><span class="sxs-lookup"><span data-stu-id="2b547-108">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="2b547-109">Sia Lync Server 2013 che Windows segnalano gli avvisi e le condizioni di errore nei registri eventi.</span><span class="sxs-lookup"><span data-stu-id="2b547-109">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="2b547-110">Pertanto, esaminare i registri eventi tutti i giorni.</span><span class="sxs-lookup"><span data-stu-id="2b547-110">Therefore, review event logs daily.</span></span>

<span data-ttu-id="2b547-111">Utilizzare il Visualizzatore eventi per:</span><span class="sxs-lookup"><span data-stu-id="2b547-111">Use Event Viewer to:</span></span>

  - <span data-ttu-id="2b547-112">Visualizzare e gestire i registri eventi.</span><span class="sxs-lookup"><span data-stu-id="2b547-112">View and manage event logs.</span></span>

  - <span data-ttu-id="2b547-113">Ottenere informazioni sui problemi di hardware, software e di sistema che devono essere risolti.</span><span class="sxs-lookup"><span data-stu-id="2b547-113">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="2b547-114">Identificare le tendenze che richiedono un'azione futura.</span><span class="sxs-lookup"><span data-stu-id="2b547-114">Identify trends that require future action.</span></span>

<span data-ttu-id="2b547-115">Un server che esegue Lync Server in un sistema operativo Windows Server registra gli eventi in quattro tipi di registri:</span><span class="sxs-lookup"><span data-stu-id="2b547-115">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="2b547-116">**Registri applicazioni**     Il registro applicazioni contiene gli eventi registrati da applicazioni o programmi.</span><span class="sxs-lookup"><span data-stu-id="2b547-116">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="2b547-117">Gli sviluppatori determinano gli eventi da registrare.</span><span class="sxs-lookup"><span data-stu-id="2b547-117">Developers determine which events to log.</span></span> <span data-ttu-id="2b547-118">Ad esempio, un programma di database potrebbe registrare un errore di file nel Registro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2b547-118">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="2b547-119">La maggior parte degli eventi relativi a Lync Server 2013 viene visualizzata nel registro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2b547-119">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="2b547-120">**Registri**     di sicurezza Il registro di sicurezza registra eventi quali tentativi di accesso validi e non validi oltre agli eventi relativi all'utilizzo delle risorse, ad esempio la creazione, l'apertura o l'eliminazione di file o altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="2b547-120">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="2b547-121">Ad esempio, se il controllo all'accesso è abilitato, i tentativi di accedere al sistema vengono registrati nel Registro di protezione.</span><span class="sxs-lookup"><span data-stu-id="2b547-121">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="2b547-122">**Registri**     di sistema Il registro di sistema contiene gli eventi registrati dai componenti di sistema di Windows.</span><span class="sxs-lookup"><span data-stu-id="2b547-122">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="2b547-123">Ad esempio, l'errore di caricamento di un driver o di un altro componente del sistema all'avvio viene registrato nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="2b547-123">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="2b547-124">I tipi di eventi registrati dai componenti del sistema sono predeterminati dal server.</span><span class="sxs-lookup"><span data-stu-id="2b547-124">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="2b547-125">**Lync Server 2013**     Lo strumento di registrazione registra eventi significativi relativi all'autenticazione, alle connessioni e alle azioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="2b547-125">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="2b547-126">Dopo aver abilitato la registrazione diagnostica, è possibile visualizzare le voci del registro nel Visualizzatore eventi.</span><span class="sxs-lookup"><span data-stu-id="2b547-126">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b547-127">Non è consigliabile utilizzare le impostazioni di registrazione massime, a meno che non venga richiesto dal servizio supporto tecnico clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b547-127">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="2b547-128">La registrazione massima consente di drenare risorse significative e può fornire molti "falsi positivi", ovvero errori che vengono registrati solo alla registrazione massima ma che sono realmente previsti e che non sono causa di preoccupazione.</span><span class="sxs-lookup"><span data-stu-id="2b547-128">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="2b547-129">È inoltre consigliabile non abilitare la registrazione diagnostica in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="2b547-129">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="2b547-130">Utilizzarla solo quando si esegue la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="2b547-130">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="2b547-131">All'interno di ogni log del Visualizzatore eventi, Lync Server 2013 registra gli eventi informativi, di avviso e di errore.</span><span class="sxs-lookup"><span data-stu-id="2b547-131">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="2b547-132">Monitorare attentamente i registri per tenere conto dei tipi di transazioni eseguite nei server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b547-132">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="2b547-133">Si consiglia di archiviare periodicamente i registri o di utilizzare il rollover automatico per evitare di esaurire lo spazio sul disco.</span><span class="sxs-lookup"><span data-stu-id="2b547-133">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="2b547-134">Poiché i file di registro possono occupare una quantità di spazio limitata, aumentare le dimensioni del registro, ad esempio a 50 MB, e impostarlo su Overwrite affinché il server Lync Server 2013 possa continuare a scrivere nuovi eventi.</span><span class="sxs-lookup"><span data-stu-id="2b547-134">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="2b547-135">È inoltre possibile automatizzare l'amministrazione del registro eventi utilizzando gli strumenti e le tecnologie seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b547-135">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="2b547-136">System Center Operations Manager monitora l'integrità e l'utilizzo dei server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b547-136">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="2b547-137">Lync Server 2013 Management Pack per Operations Manager estende Operations Manager fornendo il monitoraggio specializzato per i server che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b547-137">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="2b547-138">Lync Server 2013 Management Pack per Operations Manager monitora standard e Enterprise Edition di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b547-138">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="2b547-139">Questa versione include anche il Management Pack per la qualità di esperienza (QoE) precedentemente costituito da un Management Pack separato.</span><span class="sxs-lookup"><span data-stu-id="2b547-139">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="2b547-140">I tipi monitorati sono le voci del registro eventi, i contatori delle prestazioni e il monitoraggio dello stato di QoE.</span><span class="sxs-lookup"><span data-stu-id="2b547-140">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="2b547-141">Questa versione del Management Pack monitora solo Lync Server 2013 e 2010 e non può essere utilizzata per monitorare Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="2b547-141">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="2b547-142">Il Management Pack fornisce le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b547-142">The management pack provides the following features:</span></span>

  - <span data-ttu-id="2b547-143">Avvisi che indicano gli eventi che interessano il servizio</span><span class="sxs-lookup"><span data-stu-id="2b547-143">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="2b547-144">Avvisi che indicano la configurazione e altri problemi di impatto non del servizio</span><span class="sxs-lookup"><span data-stu-id="2b547-144">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="2b547-145">Monitoraggio dello stato dei servizi di Lync Server</span><span class="sxs-lookup"><span data-stu-id="2b547-145">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="2b547-146">Conoscenza del prodotto: causa e risoluzione dei problemi identificati</span><span class="sxs-lookup"><span data-stu-id="2b547-146">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="2b547-147">Per ulteriori informazioni su Lync Server 2013 Management Pack, fare riferimento a [monitoraggio di Lync server 2013 con System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2b547-147">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="2b547-148">**Pettine eventi**     Lo strumento pettini eventi raccoglie eventi specifici dai registri eventi di diversi computer in una posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="2b547-148">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="2b547-149">Consente di segnalare solo gli ID eventi o le origini eventi specificate.</span><span class="sxs-lookup"><span data-stu-id="2b547-149">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="2b547-150">Per ulteriori informazioni su pettine eventi, vedere il sito Web [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="2b547-150">For more information about Event Comb, see the [Account Lockout and Management Tools](https://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="2b547-151">**Trigger**     di evento In Windows Server 2012 è possibile "collegare un'attività a questo evento" all'interno del Visualizzatore eventi di Windows, in cui un amministratore può eseguire un programma, inviare un messaggio di posta elettronica o visualizzare un messaggio sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="2b547-151">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="2b547-152">Per ulteriori informazioni su questa funzionalità, vedere l'argomento Windows Server 2008 R2 [eseguire un'attività in risposta a un determinato evento](https://technet.microsoft.com/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b547-152">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](https://technet.microsoft.com/library/cc748900.aspx).</span></span> <span data-ttu-id="2b547-153">È inoltre possibile utilizzare gli strumenti da riga di comando, ad esempio "Eventtrigger.exe", per creare e eseguire query sui registri eventi e associare programmi con eventi registrati specifici.</span><span class="sxs-lookup"><span data-stu-id="2b547-153">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="2b547-154">Tramite Eventtriggers.exe, è possibile creare trigger di evento che eseguono programmi quando si verificano eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="2b547-154">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2b547-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b547-155">See Also</span></span>


[<span data-ttu-id="2b547-156">Visualizzatore eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="2b547-156">Windows Event Viewer</span></span>](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

