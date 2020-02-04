---
title: 'Lync Server 2013: monitoraggio delle prestazioni di rete'
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
ms.openlocfilehash: 504b0c28e42b6975cd411c6628cd9f91a30783ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a><span data-ttu-id="d52a9-102">Monitoraggio delle prestazioni di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d52a9-102">Monitoring network performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d52a9-103">_**Argomento Ultima modifica:** 2016-04-27_</span><span class="sxs-lookup"><span data-stu-id="d52a9-103">_**Topic Last Modified:** 2016-04-27_</span></span>

<span data-ttu-id="d52a9-104">Lync Server 2013 è una tecnologia di comunicazione in tempo reale che si basa molto sulla rete per consentire la comunicazione tra gli utenti, tramite messaggistica istantanea, chiamate vocali o comunicazioni video.</span><span class="sxs-lookup"><span data-stu-id="d52a9-104">Lync Server 2013 is a real-time communications technology that relies heavily on the network to enable communication between users—either through instant messaging (IM), voice calls, or video communication.</span></span> <span data-ttu-id="d52a9-105">È quindi importante monitorare continuamente le prestazioni della rete per garantire che la modalità di comunicazione scelta dall'utente fornisca la migliore esperienza possibile.</span><span class="sxs-lookup"><span data-stu-id="d52a9-105">It is therefore important to monitor the network performance continuously to help guarantee that a user’s chosen communication modality provides the best possible experience.</span></span>

<span data-ttu-id="d52a9-106">Le prestazioni di rete possono essere misurate a due livelli:</span><span class="sxs-lookup"><span data-stu-id="d52a9-106">Network performance can be measured at two levels:</span></span>

  - <span data-ttu-id="d52a9-107">**Prestazioni di rete complessive**   questo livello di misurazione delle prestazioni consentirà a un'organizzazione di creare una visualizzazione "Big-Picture" della propria rete e di solito viene implementata tramite sistemi di monitoraggio della rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-107">**Overall network performance**   This level of performance measurement will allow an organization to create a "big-picture" view of their network and is usually implemented through third-party network monitoring systems.</span></span> <span data-ttu-id="d52a9-108">Questi sistemi riceveranno i dati sulle prestazioni e la capacità da dispositivi di rete remoti come i router e commutati in tutta la rete per consentire agli amministratori di determinare l'integrità di un determinato componente di rete in qualsiasi momento della giornata.</span><span class="sxs-lookup"><span data-stu-id="d52a9-108">These systems will receive performance and capacity data from remote network devices such as routers and switched throughout the network to allow administrators to determine the health of any given network component at any time of day.</span></span>

  - <span data-ttu-id="d52a9-109">**Prestazioni dei singoli server**   questo livello di misurazione delle prestazioni è limitato a un server specifico e aiuta gli amministratori a valutare le prestazioni della rete di un server specifico per facilitare la risoluzione dei problemi di prestazioni o per misurare le prestazioni del server in un determinato periodo nell'ambito di un processo di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="d52a9-109">**Individual server performance**   This level of performance measurement is limited to a specific server and will help administrators with gauging the network performance of a specific server to either help with troubleshooting a specific performance issue or to gauge the respective server’s performance over a given period as part of a capacity planning process.</span></span>

<span data-ttu-id="d52a9-110">È possibile monitorare la rete usando gli strumenti descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-110">You can monitor the network by using the tools described in the following sections.</span></span>

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a><span data-ttu-id="d52a9-111">Strumenti per il monitoraggio complessivo delle prestazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d52a9-111">Tools for Overall Network Performance Monitoring</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="d52a9-112">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="d52a9-112">System Center Operations Manager 2012</span></span>

<span data-ttu-id="d52a9-113">System Center Operations Manager offre una gestione dei servizi end-to-end facile da personalizzare ed estendere per migliorare i livelli di servizio in un ambiente IT.</span><span class="sxs-lookup"><span data-stu-id="d52a9-113">System Center Operations Manager provides end-to-end service management that is easy to customize and extend for improved service levels across an IT environment.</span></span> <span data-ttu-id="d52a9-114">Questo consente alle operazioni e ai team di gestione IT di identificare e risolvere i problemi che interessano l'integrità dei servizi IT distribuiti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-114">This enables Operations and IT Management teams to identify, and resolve issues affecting the health of distributed IT services.</span></span> <span data-ttu-id="d52a9-115">La gestione dei servizi end-to-end non è limitata agli ambienti basati su Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d52a9-115">End-to-end service management is not restricted to Microsoft-based environments.</span></span> <span data-ttu-id="d52a9-116">Il supporto per servizi Web per la gestione (WS-Management), SNMP (Simple Network Management Protocol) e soluzioni partner consente sistemi che non eseguono sistemi operativi Microsoft e hardware da includere nel monitoraggio del servizio all'interno di System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="d52a9-116">Support for Web Services for Management (WS-Management), Simple Network Management Protocol (SNMP), and partner solutions allow for systems that do not run Microsoft operating systems and hardware to be included in service monitoring within System Center Operations Manager 2012.</span></span>

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a><span data-ttu-id="d52a9-117">System Center Operations Manager 2012 e soluzioni di gestione della rete di terze parti</span><span class="sxs-lookup"><span data-stu-id="d52a9-117">System Center Operations Manager 2012 and Third-Party Network Management Solutions</span></span>

<span data-ttu-id="d52a9-118">**EMC Smarts**   EMC Solutions per Operations Manager consente di risolvere rapidamente i problemi che interessano i livelli di servizio.</span><span class="sxs-lookup"><span data-stu-id="d52a9-118">**EMC Smarts**   EMC Solutions for Operations Manager help you quickly resolve issues affecting service levels throughout.</span></span> <span data-ttu-id="d52a9-119">Usando soluzioni EMC per Operations Manager, è possibile gestire e monitorare l'intera catena di servizi IT con una soluzione integrata e automatizzata.</span><span class="sxs-lookup"><span data-stu-id="d52a9-119">By using EMC Solutions for Operations Manager, you can manage and monitor your whole IT service chain with one integrated, automated solution.</span></span> <span data-ttu-id="d52a9-120">Potrai identificare facilmente le cause principali dei problemi di prestazioni e disponibilità e risolverli più rapidamente, riducendo gli effetti e i costi.</span><span class="sxs-lookup"><span data-stu-id="d52a9-120">You'll easily identify the root causes of performance and availability issues, and resolve them faster which reduces effects and costs.</span></span> <span data-ttu-id="d52a9-121">I vantaggi principali includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52a9-121">Key benefits include the following:</span></span>

  - <span data-ttu-id="d52a9-122">Lo stato di gestione avanzato e di facile utilizzo consente di fornire un valore aziendale strategico anziché ordinare manualmente e filtrare gli avvisi confusi.</span><span class="sxs-lookup"><span data-stu-id="d52a9-122">Advanced, easy-to-use management   Focus on delivering strategic business value instead of manually sorting and filtering confusing alerts.</span></span>

  - <span data-ttu-id="d52a9-123">**Risoluzione più rapida**   risolvere i problemi e rispondere alle esigenze aziendali più rapidamente, riducendo l'effetto e il costo.</span><span class="sxs-lookup"><span data-stu-id="d52a9-123">**Faster resolution**   Solve IT issues and respond to business needs faster, reducing effect and cost.</span></span>

  - <span data-ttu-id="d52a9-124">**Le operazioni**   semplificate evitano la complessità combinando più strumenti di gestione, applicazioni e terminali.</span><span class="sxs-lookup"><span data-stu-id="d52a9-124">**Streamlined operations**   Avoid IT complexity by combining multiple management tools, applications, and terminals.</span></span>

<span data-ttu-id="d52a9-125">Altre informazioni possono essere trovate qui:</span><span class="sxs-lookup"><span data-stu-id="d52a9-125">More information can be found here:</span></span>

[<span data-ttu-id="d52a9-126">Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d52a9-126">Microsoft System Center Operations Manager</span></span>](http://go.microsoft.com/fwlink/p/?linkid=243651)

[<span data-ttu-id="d52a9-127">Soluzioni per Microsoft System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d52a9-127">Solutions for Microsoft System Center Operations Manager</span></span>](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a><span data-ttu-id="d52a9-128">Soluzioni di terze parti</span><span class="sxs-lookup"><span data-stu-id="d52a9-128">Third-Party Solutions</span></span>

<span data-ttu-id="d52a9-129">HP **Network Management Center (precedentemente noto come HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) offre una gestione integrata delle prestazioni e degli errori per migliorare la disponibilità e le prestazioni della rete.</span><span class="sxs-lookup"><span data-stu-id="d52a9-129">**HP Network Management Center (previously known as HP OpenView)**   [HP Network Management Center](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) provides integrated fault and performance management to improve network availability and performance.</span></span> <span data-ttu-id="d52a9-130">Network Management Center fa parte della soluzione HP per la gestione della rete automatizzata che unifica l'errore, le prestazioni, la configurazione e la gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="d52a9-130">Network Management Center is part of the HP automated network management solution that unifies fault, performance, configuration, and change management.</span></span>

<span data-ttu-id="d52a9-131">**Cisco Network Management and Automation Products**   for the Enterprise, Cisco offre diversi prodotti di gestione, tra cui la soluzione di gestione LAN CiscoWorks e il modulo Cisco Network Analysis, per migliorare l'efficienza operativa e ridurre i tempi di inattività della rete.</span><span class="sxs-lookup"><span data-stu-id="d52a9-131">**Cisco Network Management and Automation products**   For the Enterprise, Cisco has several management products available including CiscoWorks LAN Management Solution and Cisco Network Analysis Module, to help improve operational efficiency and reduce network downtime.</span></span> <span data-ttu-id="d52a9-132">Per ulteriori informazioni su questi prodotti, vedere il sito Web Cisco all' [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d52a9-132">For additional data on these products, refer to the Cisco website at [http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html).</span></span>

<span data-ttu-id="d52a9-133">Il protocollo SNMP (Simple Network Management Protocol) SNMP è uno standard di gestione della rete che definisce una strategia per la gestione delle reti TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="d52a9-133">Simple Network Management Protocol (SNMP)   Simple Network Management Protocol (SNMP) is a network management standard that defines a strategy for managing TCP/IP networks.</span></span> <span data-ttu-id="d52a9-134">SNMP consente di acquisire informazioni sulla configurazione e sullo stato della rete e inviare le informazioni a un computer designato per il monitoraggio degli eventi.</span><span class="sxs-lookup"><span data-stu-id="d52a9-134">SNMP enables you to capture configuration and status information about the network, and send the information to a designated computer for event monitoring.</span></span> <span data-ttu-id="d52a9-135">Questo protocollo di gestione della rete basato su standard usa un'architettura distribuita che include le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d52a9-135">This standards based network management protocol uses a distributed architecture that includes the following:</span></span>

  - <span data-ttu-id="d52a9-136">Più nodi gestiti, ognuno con un'entità SNMP denominata agente che consente l'accesso remoto alla strumentazione di gestione.</span><span class="sxs-lookup"><span data-stu-id="d52a9-136">Multiple managed nodes, each with an SNMP entity called an agent which provides remote access to management instrumentation.</span></span>

  - <span data-ttu-id="d52a9-137">Almeno un'entità SNMP nota come Manager che esegue le applicazioni di gestione per monitorare e controllare gli elementi gestiti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-137">At least one SNMP entity known as a manager which runs management applications to monitor and control managed elements.</span></span> <span data-ttu-id="d52a9-138">Gli elementi gestiti sono dispositivi come host, router e così via.</span><span class="sxs-lookup"><span data-stu-id="d52a9-138">Managed elements are devices such as hosts, routers, and so on.</span></span> <span data-ttu-id="d52a9-139">Vengono monitorate e controllate accedendo alle informazioni di gestione.</span><span class="sxs-lookup"><span data-stu-id="d52a9-139">They are monitored and controlled by accessing their management information.</span></span>

  - <span data-ttu-id="d52a9-140">Un protocollo di gestione, SNMP, viene usato per comunicare le informazioni di gestione tra le stazioni di gestione e gli agenti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-140">A management protocol, SNMP, is used to communicate management information between the management stations and agents.</span></span> <span data-ttu-id="d52a9-141">Le informazioni di gestione fanno riferimento a una raccolta di oggetti gestiti che vivono in un archivio di informazioni virtuale denominato MIB (Management Information Base).</span><span class="sxs-lookup"><span data-stu-id="d52a9-141">Management information refers to a collection of managed objects that live in a virtual information store called a Management Information Base (MIB).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d52a9-142">Sono disponibili alcuni esempi di soluzioni di monitoraggio della rete di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d52a9-142">Examples of third-party network monitoring solutions are provided above.</span></span> <span data-ttu-id="d52a9-143">Questo elenco non è definitivo e Microsoft non favorisce alcuna soluzione specifica del fornitore.</span><span class="sxs-lookup"><span data-stu-id="d52a9-143">This list is not definitive and Microsoft does not favor any specific vendor solution.</span></span> <span data-ttu-id="d52a9-144">Consultarsi con un provider di servizi di rete e il rispettivo provider di tecnologia per determinare la soluzione di monitoraggio della rete migliore per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d52a9-144">Consult with a network service provider and or your respective technology provider to determine the best network monitoring solution for your organization.</span></span>



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a><span data-ttu-id="d52a9-145">Strumenti per il monitoraggio delle prestazioni delle singole reti del server</span><span class="sxs-lookup"><span data-stu-id="d52a9-145">Tools for Monitoring Individual Server Network Performance</span></span>

<div>

## <a name="system-center-operations-manager-2012"></a><span data-ttu-id="d52a9-146">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="d52a9-146">System Center Operations Manager 2012</span></span>

<span data-ttu-id="d52a9-147">System Center Operations Manager 2012 consente agli amministratori di visualizzare le prestazioni di rete dei singoli server tramite il Management Pack di Windows Server 2012: il Management Pack del sistema operativo Windows Server include un Management Pack "prestazioni" Ciò consentirebbe agli amministratori di monitorare le prestazioni della scheda di rete e l'integrità della scheda.</span><span class="sxs-lookup"><span data-stu-id="d52a9-147">System Center Operations Manager 2012 would allow administrators to view network performance of individual servers through the Windows Server 2012 Management Pack: The Windows Server operating system management pack includes a "Performance" management pack that would allow administrators to monitor Network Adapter performance and adapter health.</span></span>

</div>

<div>

## <a name="windows-network-monitor"></a><span data-ttu-id="d52a9-148">Windows Network Monitor</span><span class="sxs-lookup"><span data-stu-id="d52a9-148">Windows Network Monitor</span></span>

<span data-ttu-id="d52a9-149">Raccoglie, Visualizza, analizza l'utilizzo delle risorse in un server e misura il traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="d52a9-149">Collects, displays, analyzes resource usage on a server, and measures network traffic.</span></span> <span data-ttu-id="d52a9-150">Network Monitor monitora in esclusiva l'attività di rete.</span><span class="sxs-lookup"><span data-stu-id="d52a9-150">Network Monitor exclusively monitors network activity.</span></span> <span data-ttu-id="d52a9-151">Tramite l'acquisizione e l'analisi dei dati di rete e l'uso di questi dati con i registri delle prestazioni, è possibile determinare l'utilizzo della rete, identificare i problemi di rete e prevedere le future esigenze di rete.</span><span class="sxs-lookup"><span data-stu-id="d52a9-151">By capturing and analyzing network data, and using this data with performance logs, you can determine the network usage, identify network issues, and forecast future network needs.</span></span>

<span data-ttu-id="d52a9-152">Per altre informazioni su Network Monitor 3,4 e per scoprire come installare e configurare Network Monitor e acquisire e analizzare i dati, rivedere questa sessione: Panoramica di Network Monitor 3,3.</span><span class="sxs-lookup"><span data-stu-id="d52a9-152">For more information about Network Monitor 3.4, and to learn how to install and configure Network Monitor and capture and analyze data, review this session: Network Monitor 3.3 Overview.</span></span> <span data-ttu-id="d52a9-153">Esaminare inoltre il [Blog di Network Monitor](http://blogs.technet.com/b/netmon/).</span><span class="sxs-lookup"><span data-stu-id="d52a9-153">Also, review the [Network Monitor blog](http://blogs.technet.com/b/netmon/).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

