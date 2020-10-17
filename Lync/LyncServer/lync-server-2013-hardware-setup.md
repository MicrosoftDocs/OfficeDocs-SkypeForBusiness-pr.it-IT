---
title: 'Lync Server 2013: installazione hardware'
description: 'Lync Server 2013: installazione hardware.'
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
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552912"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="64c72-103">Installazione hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64c72-103">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64c72-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="64c72-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="64c72-105">Se si configura l'hardware e gli altri componenti necessari nell'infrastruttura necessaria per implementare la topologia, prima di pubblicare la topologia in Generatore di topologie è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64c72-105">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="64c72-106">Installare l'hardware per ogni componente nella progettazione della topologia creata e salvata utilizzando Generatore di topologie, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services (IIS) e server proxy inversi, a seconda dei casi), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server.</span><span class="sxs-lookup"><span data-stu-id="64c72-106">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="64c72-107">Assicurarsi di aver rispettato i consigli relativi al numero e alla velocità delle schede di rete.</span><span class="sxs-lookup"><span data-stu-id="64c72-107">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="64c72-108">Se si utilizzano i dispositivi di bilanciamento del carico hardware, verificare di disporre delle informazioni appropriate del fornitore per configurarle per l'utilizzo con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64c72-108">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="64c72-109">Se si utilizzerà un file server o un altro server per ospitare la condivisione file richiesta da Lync Server, assicurarsi che il server sia disponibile e pronto per la configurazione della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="64c72-109">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="64c72-110">Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="64c72-110">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="64c72-111">Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="64c72-111">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="64c72-112">Verificare che l'infrastruttura di rete soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="64c72-112">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="64c72-113">Per informazioni dettagliate, vedere [Network Infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="64c72-113">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="64c72-114">Configurare servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64c72-114">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="64c72-115">Tra le attività di configurazione sono incluse la preparazione di Servizi di dominio Active Directory e la definizione di tutti i componenti che si desidera distribuire in questo servizio.</span><span class="sxs-lookup"><span data-stu-id="64c72-115">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="64c72-116">Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="64c72-116">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="64c72-117">Impostare le autorizzazioni necessarie per creare la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="64c72-117">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="64c72-118">Le autorizzazioni per l'utilizzo di condivisioni di file da Lync Server 2013 vengono configurate automaticamente dal generatore di topologie quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="64c72-118">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="64c72-119">Tuttavia, l'account utente utilizzato per pubblicare la topologia deve disporre del controllo completo (lettura/scrittura/modifica) sulla condivisione file affinché il generatore di topologie configuri le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="64c72-119">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="64c72-120">Per assicurarsi che la condivisione file possa essere gestita correttamente durante il processo di pubblicazione del generatore di topologie, è necessario che l'utente o il gruppo di dominio a cui appartiene l'utente sia membro del gruppo Administrators locale nel computer in cui si trova la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="64c72-120">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="64c72-121">In uno scenario multidominio l'utente o il gruppo del Dominio A deve essere membro del gruppo Administrators locale nel computer nel Dominio B in cui verrà posizionata la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="64c72-121">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="64c72-122">Per informazioni dettagliate sull'aggiornamento tramite condivisioni file in un file System distribuito (DFS), vedere [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="64c72-122">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="64c72-123">La condivisione file per Lync Server 2013, Enterprise Edition non può essere posizionata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="64c72-123">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="64c72-124">Installare e configurare il servizio di bilanciamento del carico hardware per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="64c72-124">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="64c72-125">Dopo aver distribuito il servizio di bilanciamento del carico DNS (Domain Name System), è ancora necessario utilizzare anche i servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="64c72-125">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="64c72-126">Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client sulle porte 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="64c72-126">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="64c72-127">Sebbene sia comunque necessario disporre di dispositivi di bilanciamento del carico hardware per questi pool, le impostazioni e l'amministrazione di tale bilanciamento saranno destinate principalmente al traffico HTTP/HTTPS, a cui gli amministratori del bilanciamento del carico hardware sono abituati.</span><span class="sxs-lookup"><span data-stu-id="64c72-127">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="64c72-128">Dopo aver eseguito tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia, è inoltre necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64c72-128">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="64c72-129">Installare i sistemi operativi e il software prerequisito sui server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64c72-129">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="64c72-130">Configurare IIS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64c72-130">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="64c72-131">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64c72-131">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="64c72-132">Configurare i record DNS in Lync Server 2013 per un pool Front end o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="64c72-132">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

