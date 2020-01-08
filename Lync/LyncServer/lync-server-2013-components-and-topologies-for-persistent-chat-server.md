---
title: 'Lync Server 2013: componenti e topologie per il server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ae22b2afed27109fb6e2c514211293cef42a46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="73a0d-102">Componenti e topologie per il server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73a0d-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73a0d-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="73a0d-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="73a0d-104">Il server di chat persistente supporta sia configurazioni a server singolo che configurazioni multiple-server.</span><span class="sxs-lookup"><span data-stu-id="73a0d-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="73a0d-105">Il server di chat persistente può essere eseguito anche in un server Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="73a0d-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="73a0d-106">Queste configurazioni sono costituite dai componenti e topologie del server di chat persistente seguenti.</span><span class="sxs-lookup"><span data-stu-id="73a0d-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="73a0d-107">Componenti del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="73a0d-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="73a0d-108">L'installazione della versione più recente di Persistent Chat Server richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="73a0d-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="73a0d-109">Uno o più computer che eseguono il server di chat persistente e forniscono i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="73a0d-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="73a0d-110">Servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="73a0d-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="73a0d-111">Servizio conformità, attivato se è abilitata la conformità</span><span class="sxs-lookup"><span data-stu-id="73a0d-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73a0d-112">In Lync Server 2013 i servizi Web di chat persistenti per il caricamento e il download di file sono ora collocati&nbsp;con lync Server 2013 front end server.</span><span class="sxs-lookup"><span data-stu-id="73a0d-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="73a0d-113">I servizi Web di chat persistenti per la gestione delle chat room sono collocati anche&nbsp;con Lync Server 2013 front end server.</span><span class="sxs-lookup"><span data-stu-id="73a0d-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="73a0d-114">Server (più server se si usa il mirroring) che ospitano il database back-end di SQL Server per ospitare il database del contenuto della chat persistente in cui sono archiviati il contenuto della chat room, le camere e le categorie.</span><span class="sxs-lookup"><span data-stu-id="73a0d-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73a0d-115">Il database back-end archivia i dati della cronologia delle chat, incluse le informazioni sulle categorie e le chat room persistenti create.</span><span class="sxs-lookup"><span data-stu-id="73a0d-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="73a0d-116">Se è stata abilitata la conformità, un server (più di un server se viene usato il mirroring) che ospita il database back-end di SQL Server per l'hosting del database di conformità della chat persistente, in cui vengono archiviati gli eventi di conformità e il contenuto della chat per lo scopo della conformità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="73a0d-117">Per amministrare il server di chat persistente da un computer separato, ad esempio una console di amministrazione, usare il pannello di controllo di Lync Server nel computer.</span><span class="sxs-lookup"><span data-stu-id="73a0d-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="73a0d-118">Questo computer deve quindi essere distribuito in un dominio di servizi di dominio Active Directory, con almeno un server di catalogo globale nella radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="73a0d-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="73a0d-119">Per informazioni dettagliate sui requisiti hardware e software per il server di chat persistente, vedere [requisiti tecnici per il server di chat persistente in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md)e [supporto per software e infrastruttura server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="73a0d-120">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="73a0d-120">Supported Collocation</span></span>

<span data-ttu-id="73a0d-121">Lync Server 2013 supporta diversi scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si ha una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si ha un organizzazione più grande che richiede scalabilità e prestazioni).</span><span class="sxs-lookup"><span data-stu-id="73a0d-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="73a0d-122">I fattori di scalabilità dovrebbero certamente essere presi in considerazione prima di decidere se collocare i componenti.</span><span class="sxs-lookup"><span data-stu-id="73a0d-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="73a0d-123">Il servizio di conformità della chat persistente, se è abilitata la conformità, è collocato nel server front-end di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73a0d-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="73a0d-124">Il server di chat persistente può essere distribuito nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="73a0d-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="73a0d-125">Il server di back-end del server di chat persistente e il database di conformità della chat persistente possono essere collocati nel server Standard Edition nel server di SQL Server Express back-end locale.</span><span class="sxs-lookup"><span data-stu-id="73a0d-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="73a0d-126">Per informazioni dettagliate sui componenti che possono essere collocati in questa posizione, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="73a0d-127">Per Lync Server 2013 Enterprise Edition, i server di chat permanenti non possono essere collocati nel server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="73a0d-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="73a0d-128">Il database di SQL Server per il server di chat persistente può essere collocato con il database del server back-end di un pool di front-end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="73a0d-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="73a0d-129">Il database di SQL Server per la conformità della chat persistente può essere collocato anche con il database back-end server di un pool di Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="73a0d-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73a0d-130">Il server che ospita il database di chat persistente può ospitare altri database.</span><span class="sxs-lookup"><span data-stu-id="73a0d-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="73a0d-131">Tuttavia, se si considera la possibilità di collocare il database di chat persistente con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database della chat persistente può diventare molto elevato.</span><span class="sxs-lookup"><span data-stu-id="73a0d-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="73a0d-132">Per questo motivo, non è consigliabile collocare il database di chat persistente con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="73a0d-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="73a0d-133">Se si colloca il database di chat persistente con il database back-end, è possibile usare una singola istanza di SQL Server per uno o tutti i database oppure si può usare un'istanza distinta di SQL Server per ogni database, con la limitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="73a0d-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="73a0d-134">Ogni istanza di SQL Server può contenere solo un database back-end e un singolo database di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="73a0d-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="73a0d-135">Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="73a0d-136">Topologie del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="73a0d-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="73a0d-137">Il server di chat persistente supporta le topologie seguenti:</span><span class="sxs-lookup"><span data-stu-id="73a0d-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="73a0d-138">Lync Server 2013 Enterprise Edition single server front end server</span><span class="sxs-lookup"><span data-stu-id="73a0d-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="73a0d-139">Lync Server 2013 Enterprise Edition più server front end server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="73a0d-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="73a0d-140">Lync Server 2013 Standard Edition server con SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="73a0d-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="73a0d-141">Lync Server 2013 Standard Edition Server e il server di chat persistente in un server separato usando il server Standard Edition come server dell'hop successivo.</span><span class="sxs-lookup"><span data-stu-id="73a0d-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="73a0d-142">È possibile aggiungere il server di chat persistente alla distribuzione di Lync Server 2013 tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="73a0d-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="73a0d-143">È possibile aggiungere un singolo server o un pool di server di chat persistente in più server alla topologia.</span><span class="sxs-lookup"><span data-stu-id="73a0d-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73a0d-144">Dopo aver creato un pool di server di chat persistente con un singolo server tramite Generatore di topologia, non è possibile aggiungere altri server al pool.</span><span class="sxs-lookup"><span data-stu-id="73a0d-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="73a0d-145">Topologia a server singolo</span><span class="sxs-lookup"><span data-stu-id="73a0d-145">Single-Server Topology</span></span>

<span data-ttu-id="73a0d-146">La configurazione minima e la distribuzione più semplice per il server di chat persistente è una singola topologia del server front end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="73a0d-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="73a0d-147">Questa distribuzione richiede un singolo server che esegue il server di chat persistente (che facoltativamente esegue il servizio di conformità, se è abilitata la conformità), un server che ospita sia il database di SQL Server che se è necessaria la conformità, il database di SQL Server per archiviare il dati sulla conformità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73a0d-148">Non è possibile aggiungere altri server a un pool di server di chat persistente avviato come distribuzione a server singolo in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="73a0d-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="73a0d-149">È consigliabile usare la topologia di pool a più server, anche se si usa un singolo server, in modo che sia possibile aggiungere altri server in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="73a0d-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="73a0d-150">La figura seguente mostra tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end del server di chat persistente con conformità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="73a0d-151">**Singolo server di chat persistente**</span><span class="sxs-lookup"><span data-stu-id="73a0d-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="73a0d-152">![Topologia a server singolo con](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "topologia del servizio conformità Single Server con servizio conformità")</span><span class="sxs-lookup"><span data-stu-id="73a0d-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="73a0d-153">Topologia a più server</span><span class="sxs-lookup"><span data-stu-id="73a0d-153">Multiple-Server Topology</span></span>

<span data-ttu-id="73a0d-154">Per avere maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="73a0d-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="73a0d-155">La topologia a più server può includere fino a quattro computer attivi che eseguono il server di chat persistente (le configurazioni ad alta disponibilità e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le rimanenti quattro in standby).</span><span class="sxs-lookup"><span data-stu-id="73a0d-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="73a0d-156">Ogni server può supportare tutti gli utenti simultanei di 20.000, per un totale di 80.000 utenti simultanei connessi a un pool di server di chat persistente con 4 server.</span><span class="sxs-lookup"><span data-stu-id="73a0d-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="73a0d-157">Una topologia a più server è uguale alla topologia a server singolo, ad eccezione del fatto che più server ospitano il server di chat persistente e possono essere ridimensionati in modo più elevato.</span><span class="sxs-lookup"><span data-stu-id="73a0d-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="73a0d-158">Più computer che eseguono il server di chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory di Lync Server e nel servizio conformità.</span><span class="sxs-lookup"><span data-stu-id="73a0d-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="73a0d-159">La figura seguente mostra tutti i componenti di una topologia a più server con più computer che eseguono il server di chat persistente, il servizio di conformità facoltativo e un database di conformità separato.</span><span class="sxs-lookup"><span data-stu-id="73a0d-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="73a0d-160">**Più server di chat persistenti**</span><span class="sxs-lookup"><span data-stu-id="73a0d-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="73a0d-161">Topologia multiple server(images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "multiple") ![topologia]server</span><span class="sxs-lookup"><span data-stu-id="73a0d-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="73a0d-162">Le topologie con più server consentono di creare pool di funzionalità del server.</span><span class="sxs-lookup"><span data-stu-id="73a0d-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="73a0d-163">In un pool di server i servizi di chat persistenti comunicano e condividono i dati.</span><span class="sxs-lookup"><span data-stu-id="73a0d-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="73a0d-164">Ad esempio, la cronologia delle chat pubblicata in origine in un servizio di chat persistente è disponibile presso qualsiasi servizio di chat persistente nel sistema.</span><span class="sxs-lookup"><span data-stu-id="73a0d-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="73a0d-165">Un file caricato tramite un servizio di chat persistente può essere accessibile da qualsiasi servizio di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="73a0d-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="73a0d-166">Gli utenti possono essere connessi a diversi server front end del server di chat persistente e possono essere chattati e comunicanti tra loro.</span><span class="sxs-lookup"><span data-stu-id="73a0d-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="73a0d-167">La porta predefinita di TCP 8011 connette un server a un pool di server e viene usata dal servizio chat persistente per comunicare tra loro o per scopi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="73a0d-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

