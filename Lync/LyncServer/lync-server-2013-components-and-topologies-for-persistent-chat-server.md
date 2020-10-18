---
title: 'Lync Server 2013: componenti e topologie per il server Chat persistente'
description: 'Lync Server 2013: componenti e topologie per il server Chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937b3d6f2716d9471e61cffd651847f6de9d83f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576812"
---
# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d9589-103">Componenti e topologie per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9589-103">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9589-104">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d9589-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d9589-105">Il server Chat persistente supporta configurazioni a server singolo e configurazioni con più server.</span><span class="sxs-lookup"><span data-stu-id="d9589-105">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="d9589-106">Il server Chat persistente può anche essere eseguito su un server Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d9589-106">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="d9589-107">Queste configurazioni sono costituite dai seguenti componenti e topologie del server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9589-107">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="d9589-108">Componenti del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="d9589-108">Persistent Chat Server Components</span></span>

<span data-ttu-id="d9589-109">L'installazione della versione più recente del server di chat persistente richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9589-109">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="d9589-110">Uno o più computer che eseguono il server Chat persistente e offrono i servizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9589-110">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="d9589-111">Servizio chat persistente</span><span class="sxs-lookup"><span data-stu-id="d9589-111">Persistent Chat service</span></span>
    
      - <span data-ttu-id="d9589-112">Servizio di conformità, attivato se la conformità è abilitata</span><span class="sxs-lookup"><span data-stu-id="d9589-112">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d9589-113">In Lync Server 2013, i servizi Web di chat persistente per il caricamento e il download dei file sono ora collocati con Lync Server 2013 &nbsp; front end server.</span><span class="sxs-lookup"><span data-stu-id="d9589-113">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="d9589-114">I servizi Web di chat persistente per la gestione delle chat room sono collocati anche con Lync Server 2013 &nbsp; front end server.</span><span class="sxs-lookup"><span data-stu-id="d9589-114">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="d9589-115">Server (più server se si utilizza il mirroring) che ospitano il database back-end di SQL Server per ospitare il database del contenuto di chat persistente in cui vengono archiviati il contenuto delle chat room, le sale e le categorie.</span><span class="sxs-lookup"><span data-stu-id="d9589-115">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9589-116">Nel database back-end sono archiviati i dati della cronologia chat, incluse le informazioni sulle categorie e le chat room persistenti create.</span><span class="sxs-lookup"><span data-stu-id="d9589-116">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="d9589-117">Se la conformità è abilitata, vengono archiviati i server (più server se si utilizza il mirroring) che ospitano il database back-end di SQL Server per ospitare il database di conformità di Persistent Chat, in cui vengono memorizzati gli eventi di conformità e il contenuto della chat ai fini della conformità.</span><span class="sxs-lookup"><span data-stu-id="d9589-117">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="d9589-118">Per amministrare il server Chat persistente da un computer separato, ad esempio una console di amministrazione, utilizzare il pannello di controllo di Lync Server nel computer.</span><span class="sxs-lookup"><span data-stu-id="d9589-118">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="d9589-119">Il computer deve quindi essere distribuito in un dominio di servizi di dominio Active Directory, con almeno un server di catalogo globale nella radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="d9589-119">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="d9589-120">Per informazioni dettagliate sui requisiti hardware e software per il server Chat persistente, vedere [requisiti tecnici per il server Chat persistente in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md)e supporto dell'infrastruttura e del [software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d9589-120">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="d9589-121">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="d9589-121">Supported Collocation</span></span>

<span data-ttu-id="d9589-122">Lync Server 2013 supporta una serie di scenari di collocazione, offrendo la flessibilità necessaria per salvare i costi hardware eseguendo più componenti in un server (se si dispone di un'organizzazione di piccole dimensioni) o per eseguire singoli componenti in server diversi (se si dispone di un'organizzazione di dimensioni superiori che richiede scalabilità e prestazioni).</span><span class="sxs-lookup"><span data-stu-id="d9589-122">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="d9589-123">Prima di decidere se collocare i componenti, è sicuramente importante considerare i fattori di scalabilità.</span><span class="sxs-lookup"><span data-stu-id="d9589-123">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="d9589-124">Il servizio di conformità di Persistent Chat, se la conformità è abilitata, è collocato con il front end server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9589-124">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="d9589-125">Il server Chat persistente può essere distribuito nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d9589-125">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="d9589-126">Il server back-end server di chat persistente e il database di conformità di chat persistente possono essere collocati nel server Standard Edition sul server SQL Server Express back-end locale.</span><span class="sxs-lookup"><span data-stu-id="d9589-126">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="d9589-127">Per informazioni dettagliate sui componenti che possono essere collocati in tale posizione, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d9589-127">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d9589-128">Per Lync Server 2013 Enterprise Edition, i server di chat persistente non possono essere collocati nel server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d9589-128">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="d9589-129">Il database di SQL Server per il server Chat persistente può essere collocato con il database del server back-end di un pool Enterprise Edition front end.</span><span class="sxs-lookup"><span data-stu-id="d9589-129">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="d9589-130">Il database di SQL Server per la conformità della chat persistente può anche essere collocato con il database del server back-end di un pool Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="d9589-130">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9589-131">Il server che ospita il database di chat persistente può ospitare altri database.</span><span class="sxs-lookup"><span data-stu-id="d9589-131">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="d9589-132">Tuttavia, se si considera la collocazione del database di chat persistente con altri database, tenere presente che se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di chat persistente può aumentare molto.</span><span class="sxs-lookup"><span data-stu-id="d9589-132">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="d9589-133">Per questo motivo, non è consigliabile collocare il database di Persistent Chat con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="d9589-133">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="d9589-134">Se si colloca il database di chat persistente con il database back-end, è possibile utilizzare una singola istanza di SQL Server per uno o per tutti i database oppure è possibile utilizzare un'istanza separata di SQL Server per ogni database, con la limitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="d9589-134">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="d9589-135">Ogni istanza di SQL Server può contenere solo un singolo database back-end e un singolo database di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9589-135">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="d9589-136">Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="d9589-136">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="d9589-137">Topologie del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="d9589-137">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="d9589-138">Il server Chat persistente supporta le topologie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9589-138">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="d9589-139">Lync Server 2013 Enterprise Edition single server Persistent Chat Server front end server</span><span class="sxs-lookup"><span data-stu-id="d9589-139">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="d9589-140">Lync Server 2013 Enterprise Edition server front end server con più server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="d9589-140">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="d9589-141">Lync Server 2013 Standard Edition server con SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="d9589-141">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="d9589-142">Lync Server 2013 Standard Edition Server e Persistent Chat Server in un server separato che utilizza il server Standard Edition come server dell'hop successivo.</span><span class="sxs-lookup"><span data-stu-id="d9589-142">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="d9589-143">È possibile aggiungere il server Chat persistente alla distribuzione di Lync Server 2013 utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d9589-143">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="d9589-144">È possibile aggiungere un singolo server o un pool di server Chat persistente a più server alla topologia.</span><span class="sxs-lookup"><span data-stu-id="d9589-144">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9589-145">Dopo aver creato un pool di server Chat persistente con un singolo server utilizzando Generatore di topologie, non è possibile aggiungere altri server al pool.</span><span class="sxs-lookup"><span data-stu-id="d9589-145">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="d9589-146">Topologia a server singolo</span><span class="sxs-lookup"><span data-stu-id="d9589-146">Single-Server Topology</span></span>

<span data-ttu-id="d9589-147">La configurazione minima e la distribuzione più semplice per il server Chat persistente è una singola topologia del server front-end del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9589-147">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="d9589-148">Questa distribuzione richiede un singolo server che esegue il server Chat persistente (che, facoltativamente, esegue il servizio di conformità, se la conformità è abilitata), un server che ospita il database di SQL Server e, se necessario, il database di SQL Server per archiviare i dati di conformità.</span><span class="sxs-lookup"><span data-stu-id="d9589-148">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9589-149">Non è possibile aggiungere altri server a un pool di server Chat persistente avviato come distribuzione a server singolo in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d9589-149">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="d9589-150">È consigliabile utilizzare la topologia con pool di più server, anche se si utilizza un singolo server, in modo da poter aggiungere ulteriori server in seguito all'occorrenza.</span><span class="sxs-lookup"><span data-stu-id="d9589-150">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="d9589-151">Nella figura seguente vengono illustrati tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end di Persistent Chat Server con conformità.</span><span class="sxs-lookup"><span data-stu-id="d9589-151">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="d9589-152">**Singolo server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="d9589-152">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="d9589-153">![Topologia a server singolo con servizio di conformità](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a server singolo con servizio di conformità")</span><span class="sxs-lookup"><span data-stu-id="d9589-153">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="d9589-154">Topologia a più server</span><span class="sxs-lookup"><span data-stu-id="d9589-154">Multiple-Server Topology</span></span>

<span data-ttu-id="d9589-155">Per garantire maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="d9589-155">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="d9589-156">La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby).</span><span class="sxs-lookup"><span data-stu-id="d9589-156">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="d9589-157">Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server.</span><span class="sxs-lookup"><span data-stu-id="d9589-157">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="d9589-158">Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="d9589-158">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="d9589-159">Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Lync Server e il servizio di conformità.</span><span class="sxs-lookup"><span data-stu-id="d9589-159">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="d9589-160">Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.</span><span class="sxs-lookup"><span data-stu-id="d9589-160">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="d9589-161">**Più server Persistent Chat**</span><span class="sxs-lookup"><span data-stu-id="d9589-161">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="d9589-162">![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")</span><span class="sxs-lookup"><span data-stu-id="d9589-162">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="d9589-163">Le topologie a più server consentono di creare pool delle funzionalità dei server.</span><span class="sxs-lookup"><span data-stu-id="d9589-163">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="d9589-164">In un pool di server, i servizi chat persistente comunicano e condividono i dati.</span><span class="sxs-lookup"><span data-stu-id="d9589-164">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="d9589-165">Ad esempio, la cronologia delle chat originariamente inviata a un servizio di chat persistente è disponibile da qualsiasi servizio chat persistente nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d9589-165">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="d9589-166">È possibile accedere a un file caricato tramite un servizio di chat persistente da qualsiasi servizio chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9589-166">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="d9589-167">Gli utenti possono essere connessi a diversi server front-end di chat persistente e possono chattare e comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="d9589-167">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="d9589-168">La porta predefinita di TCP 8011 connette un server a un pool di server e viene utilizzata dal servizio chat persistente per comunicare tra loro o a fini amministrativi.</span><span class="sxs-lookup"><span data-stu-id="d9589-168">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

