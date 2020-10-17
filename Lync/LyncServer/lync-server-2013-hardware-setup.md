---
title: 'Lync Server 2013: installazione hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528343"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="48cee-102">Installazione hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cee-102">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48cee-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="48cee-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="48cee-104">Se si configura l'hardware e gli altri componenti necessari nell'infrastruttura necessaria per implementare la topologia, prima di pubblicare la topologia in Generatore di topologie è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48cee-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="48cee-105">Installare l'hardware per ogni componente nella progettazione della topologia creata e salvata utilizzando Generatore di topologie, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services (IIS) e server proxy inversi, a seconda dei casi), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server.</span><span class="sxs-lookup"><span data-stu-id="48cee-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="48cee-106">Assicurarsi di aver rispettato i consigli relativi al numero e alla velocità delle schede di rete.</span><span class="sxs-lookup"><span data-stu-id="48cee-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="48cee-107">Se si utilizzano i dispositivi di bilanciamento del carico hardware, verificare di disporre delle informazioni appropriate del fornitore per configurarle per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48cee-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="48cee-108">Se si utilizzerà un file server o un altro server per ospitare la condivisione file richiesta da Lync Server, assicurarsi che il server sia disponibile e pronto per la configurazione della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="48cee-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="48cee-109">Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="48cee-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="48cee-110">Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="48cee-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="48cee-111">Verificare che l'infrastruttura di rete soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="48cee-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="48cee-112">Per informazioni dettagliate, vedere [Network Infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="48cee-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="48cee-113">Configurare servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48cee-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="48cee-114">Tra le attività di configurazione sono incluse la preparazione di Servizi di dominio Active Directory e la definizione di tutti i componenti che si desidera distribuire in questo servizio.</span><span class="sxs-lookup"><span data-stu-id="48cee-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="48cee-115">Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="48cee-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="48cee-116">Impostare le autorizzazioni necessarie per creare la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="48cee-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="48cee-117">Le autorizzazioni per l'utilizzo di condivisioni di file da Lync Server 2013 vengono configurate automaticamente dal generatore di topologie quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="48cee-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="48cee-118">Tuttavia, l'account utente utilizzato per pubblicare la topologia deve disporre del controllo completo (lettura/scrittura/modifica) sulla condivisione file affinché il generatore di topologie configuri le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="48cee-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="48cee-119">Per assicurarsi che la condivisione file possa essere gestita correttamente durante il processo di pubblicazione del generatore di topologie, è necessario che l'utente o il gruppo di dominio a cui appartiene l'utente sia membro del gruppo Administrators locale nel computer in cui si trova la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="48cee-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="48cee-120">In uno scenario multidominio l'utente o il gruppo del Dominio A deve essere membro del gruppo Administrators locale nel computer nel Dominio B in cui verrà posizionata la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="48cee-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="48cee-121">Per informazioni dettagliate sull'aggiornamento tramite condivisioni file in un file System distribuito (DFS), vedere [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="48cee-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="48cee-122">La condivisione file per Lync Server 2013, Enterprise Edition non può essere posizionata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="48cee-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="48cee-123">Installare e configurare il servizio di bilanciamento del carico hardware per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="48cee-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="48cee-124">Dopo aver distribuito il servizio di bilanciamento del carico DNS (Domain Name System), è ancora necessario utilizzare anche i servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="48cee-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="48cee-125">Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client sulle porte 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="48cee-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="48cee-126">Sebbene sia comunque necessario disporre di dispositivi di bilanciamento del carico hardware per questi pool, le impostazioni e l'amministrazione di tale bilanciamento saranno destinate principalmente al traffico HTTP/HTTPS, a cui gli amministratori del bilanciamento del carico hardware sono abituati.</span><span class="sxs-lookup"><span data-stu-id="48cee-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="48cee-127">Dopo aver eseguito tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia, è inoltre necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48cee-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="48cee-128">Installare i sistemi operativi e il software prerequisito sui server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cee-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="48cee-129">Configurare IIS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cee-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="48cee-130">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48cee-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="48cee-131">Configurare i record DNS in Lync Server 2013 per un pool Front end o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="48cee-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

