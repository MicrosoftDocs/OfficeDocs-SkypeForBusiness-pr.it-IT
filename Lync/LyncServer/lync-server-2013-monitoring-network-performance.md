---
title: 'Lync Server 2013: monitoraggio delle prestazioni della rete'
description: 'Lync Server 2013: monitoraggio delle prestazioni della rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ead7e3f9001b06c783c9b22327581e795a20322
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549452"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="a1514-103">Monitoraggio delle prestazioni di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1514-103">Monitoring network performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1514-104">_**Ultimo argomento modificato:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="a1514-104">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="a1514-105">Lync Server 2013 è una tecnologia di comunicazione in tempo reale che si basa fortemente sulla rete per abilitare la comunicazione tra gli utenti, tramite la messaggistica istantanea (IM), le chiamate vocali o la comunicazione video.</span><span class="sxs-lookup"><span data-stu-id="a1514-105">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="a1514-106">È pertanto importante monitorare continuamente le prestazioni della rete per garantire che la modalità di comunicazione scelta dall'utente offra la migliore esperienza possibile.</span><span class="sxs-lookup"><span data-stu-id="a1514-106">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="a1514-107">Le prestazioni di rete possono essere misurate a due livelli:</span><span class="sxs-lookup"><span data-stu-id="a1514-107">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="a1514-108">Prestazioni complessive della **rete**     Questo livello di misura delle prestazioni consentirà a un'organizzazione di creare una visualizzazione "Big-Picture" della propria rete e di solito viene implementata attraverso sistemi di monitoraggio della rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="a1514-108">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="a1514-109">Questi sistemi riceveranno i dati sulle prestazioni e la capacità dei dispositivi di rete remota, come i router e commutati in tutta la rete, per consentire agli amministratori di determinare l'integrità di un determinato componente di rete in qualsiasi momento della giornata.</span><span class="sxs-lookup"><span data-stu-id="a1514-109">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="a1514-110">Prestazioni del singolo **Server**     Questo livello di misura delle prestazioni è limitato a un server specifico e consente agli amministratori di valutare le prestazioni di rete di un server specifico per facilitare la risoluzione dei problemi di prestazioni specifici o per misurare le prestazioni del rispettivo server in un determinato periodo nell'ambito di un processo di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="a1514-110">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="a1514-111">È possibile monitorare la rete utilizzando gli strumenti descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a1514-111">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="a1514-112">Strumenti per il monitoraggio globale delle prestazioni della rete</span><span class="sxs-lookup"><span data-stu-id="a1514-112">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="a1514-113">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a1514-113">System Center Operations Manager 2012</span></span>

<span data-ttu-id="a1514-114">System Center Operations Manager fornisce la gestione dei servizi end-to-end facile da personalizzare ed estendere per migliorare i livelli di servizio in un ambiente IT.</span><span class="sxs-lookup"><span data-stu-id="a1514-114">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="a1514-115">Questo consente alle operazioni e ai team di gestione IT di identificare e risolvere i problemi relativi all'integrità dei servizi IT distribuiti.</span><span class="sxs-lookup"><span data-stu-id="a1514-115">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="a1514-116">La gestione dei servizi end-to-end non è limitata agli ambienti basati su Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1514-116">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="a1514-117">Il supporto per i servizi Web per la gestione (WS-Management), il protocollo SNMP (Simple Network Management Protocol) e le soluzioni partner consentono sistemi che non eseguono sistemi operativi e hardware Microsoft da includere nel monitoraggio del servizio all'interno di System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="a1514-117">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="a1514-118">System Center Operations Manager 2012 e soluzioni di gestione della rete di terze parti</span><span class="sxs-lookup"><span data-stu-id="a1514-118">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="a1514-119">**Smarts EMC**     Le soluzioni EMC per Operations Manager consentono di risolvere rapidamente i problemi che interessano i livelli di servizio in tutto.</span><span class="sxs-lookup"><span data-stu-id="a1514-119">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="a1514-120">Utilizzando soluzioni EMC per Operations Manager, è possibile gestire e monitorare la propria intera catena di servizi IT con una soluzione integrata e automatizzata.</span><span class="sxs-lookup"><span data-stu-id="a1514-120">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="a1514-121">È possibile identificare facilmente le cause principali dei problemi relativi a prestazioni e disponibilità e risolverli in modo più rapido, riducendo gli effetti e i costi.</span><span class="sxs-lookup"><span data-stu-id="a1514-121">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="a1514-122">I principali vantaggi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1514-122">Key benefits include the following:</span></span>

  - <span data-ttu-id="a1514-123">Lo stato di gestione avanzato e facile da usare per la distribuzione di un valore aziendale strategico invece di ordinare manualmente e filtrare gli avvisi confusi.</span><span class="sxs-lookup"><span data-stu-id="a1514-123">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="a1514-124">**Risoluzione**     più rapida Risolvere i problemi IT e rispondere alle esigenze aziendali più velocemente, riducendo gli effetti e i costi.</span><span class="sxs-lookup"><span data-stu-id="a1514-124">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="a1514-125">**Operazioni**     semplificate Evitare la complessità della IT combinando più strumenti di gestione, applicazioni e terminali.</span><span class="sxs-lookup"><span data-stu-id="a1514-125">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="a1514-126">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="a1514-126">More information can be found here:</span></span>

[<span data-ttu-id="a1514-127">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a1514-127">Microsoft System Center Operations Manager</span></span>](https://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="a1514-128">Soluzioni per Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a1514-128">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="a1514-129">Soluzioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="a1514-129">Third-Party Solutions</span></span>

<span data-ttu-id="a1514-130">HP Network **Management Center (precedentemente noto come HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) fornisce la gestione integrata dei guasti e delle prestazioni per migliorare la disponibilità e le prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="a1514-130">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="a1514-131">Network Management Center fa parte della soluzione HP di gestione della rete automatizzata che unifica la gestione dei guasti, delle prestazioni, della configurazione e delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="a1514-131">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="a1514-132">Prodotti di automazione **e gestione della rete Cisco**     Per l'azienda, Cisco dispone di diversi prodotti di gestione, tra cui la soluzione di gestione LAN CiscoWorks e il modulo di analisi di rete Cisco, per migliorare l'efficienza operativa e ridurre i tempi di inattività della rete.</span><span class="sxs-lookup"><span data-stu-id="a1514-132">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="a1514-133">Per ulteriori informazioni su questi prodotti, vedere il sito Web Cisco all'indirizzo [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) .</span><span class="sxs-lookup"><span data-stu-id="a1514-133">For additional data on these products, refer to the Cisco website at [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="a1514-134">Simple Network Management Protocol (SNMP) Simple Network Management Protocol (SNMP) è uno standard di gestione della rete che definisce una strategia per la gestione delle reti TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="a1514-134">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="a1514-135">SNMP consente di acquisire informazioni sulla configurazione e sullo stato della rete e di inviare le informazioni a un computer designato per il monitoraggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="a1514-135">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="a1514-136">Questo protocollo di gestione della rete basato su standard utilizza un'architettura distribuita che include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1514-136">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="a1514-137">Più nodi gestiti, ognuno con un'entità SNMP chiamata agente che fornisce accesso remoto alla strumentazione di gestione.</span><span class="sxs-lookup"><span data-stu-id="a1514-137">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="a1514-138">Almeno un'entità SNMP nota come Manager che esegue le applicazioni di gestione per monitorare e controllare gli elementi gestiti.</span><span class="sxs-lookup"><span data-stu-id="a1514-138">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="a1514-139">Gli elementi gestiti sono dispositivi, ad esempio host, router e così via.</span><span class="sxs-lookup"><span data-stu-id="a1514-139">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="a1514-140">Sono monitorate e controllate tramite l'accesso alle informazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="a1514-140">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="a1514-141">Un protocollo di gestione, SNMP, viene utilizzato per comunicare informazioni di gestione tra le stazioni di gestione e gli agenti.</span><span class="sxs-lookup"><span data-stu-id="a1514-141">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="a1514-142">Le informazioni di gestione si riferiscono a un insieme di oggetti gestiti che vivono in un archivio di informazioni virtuale denominato un MIB (Management Information Base).</span><span class="sxs-lookup"><span data-stu-id="a1514-142">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1514-143">Di seguito sono riportati alcuni esempi di soluzioni di monitoraggio della rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="a1514-143">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="a1514-144">Questo elenco non è definitivo e Microsoft non privilegia una soluzione specifica del fornitore.</span><span class="sxs-lookup"><span data-stu-id="a1514-144">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="a1514-145">Consultare un provider di servizi di rete o il rispettivo provider di tecnologia per determinare la migliore soluzione di monitoraggio della rete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1514-145">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="a1514-146">Strumenti per il monitoraggio delle prestazioni di rete di singoli server</span><span class="sxs-lookup"><span data-stu-id="a1514-146">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="a1514-147">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a1514-147">System Center Operations Manager 2012</span></span>

<span data-ttu-id="a1514-148">System Center Operations Manager 2012 consentirebbe agli amministratori di visualizzare le prestazioni di rete dei singoli server tramite il Management Pack di Windows Server 2012: il Management Pack del sistema operativo Windows Server include un Management Pack "performance" che consentirebbe agli amministratori di monitorare le prestazioni della scheda di rete e l'integrità dell'adattatore.</span><span class="sxs-lookup"><span data-stu-id="a1514-148">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="a1514-149">Windows Network Monitor</span><span class="sxs-lookup"><span data-stu-id="a1514-149">Windows Network Monitor</span></span>

<span data-ttu-id="a1514-150">Raccoglie, Visualizza, analizza l'utilizzo delle risorse in un server e misura il traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="a1514-150">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="a1514-151">Network Monitor esegue esclusivamente il monitoraggio delle attività di rete.</span><span class="sxs-lookup"><span data-stu-id="a1514-151">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="a1514-152">Tramite l'acquisizione e l'analisi dei dati di rete e l'utilizzo di tali dati con i registri delle prestazioni, è possibile determinare l'utilizzo della rete, identificare i problemi di rete e prevedere le future esigenze di rete.</span><span class="sxs-lookup"><span data-stu-id="a1514-152">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="a1514-153">Per ulteriori informazioni su Network Monitor 3,4 e per sapere come installare e configurare Network Monitor e acquisire e analizzare i dati, vedere la sessione seguente: Network Monitor 3,3 Overview.</span><span class="sxs-lookup"><span data-stu-id="a1514-153">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="a1514-154">Esaminare inoltre il [Blog di Network Monitor](https://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="a1514-154">Also, review the [Network Monitor blog](https://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

