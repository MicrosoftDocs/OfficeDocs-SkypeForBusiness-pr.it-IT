---
title: 'Lync Server 2013: Configurazione hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="5b8b8-102">Configurazione hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8b8-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b8b8-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5b8b8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5b8b8-104">La configurazione dell'hardware e di altri componenti necessari nell'infrastruttura necessaria per implementare la topologia richiede che, prima di pubblicare la topologia in Generatore di topologie, sia necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b8b8-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="5b8b8-105">Installare l'hardware per ogni componente nella progettazione della topologia creata e salvata con generatore di topologia, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services (IIS) e invertire i server proxy, a seconda delle esigenze), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="5b8b8-106">Verificare di aver seguito le indicazioni relative al numero e alla velocità per le schede di rete.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="5b8b8-107">Se si utilizzeranno i dispositivi di bilanciamento del carico hardware, verificare di avere le informazioni appropriate del fornitore per configurarle per l'uso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="5b8b8-108">Se si vuole usare un file server o un altro server per ospitare la condivisione di file richiesta da Lync Server, verificare che il server sia disponibile e pronto per la configurazione della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="5b8b8-109">Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="5b8b8-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="5b8b8-110">Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="5b8b8-111">Verificare che l'infrastruttura di rete soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="5b8b8-112">Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di rete per Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="5b8b8-113">Configurare servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="5b8b8-114">La configurazione di servizi di dominio Active Directory include la preparazione di servizi di dominio Active Directory e la definizione di tutti i componenti da distribuire in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="5b8b8-115">Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory, vedere Preparazione della documentazione per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella pagina relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="5b8b8-116">Configurare le autorizzazioni necessarie per la creazione della condivisione file.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="5b8b8-117">Le autorizzazioni per l'uso delle condivisioni file di Lync Server 2013 vengono configurate automaticamente da generatore di topologie quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="5b8b8-118">Tuttavia, l'account utente usato per pubblicare la topologia deve avere il controllo completo (lettura/scrittura/modifica) nella condivisione file in modo che generatore di topologie configuri le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="5b8b8-119">Per assicurarsi che la condivisione di file possa essere gestita correttamente durante il processo di pubblicazione del generatore di topologia, l'utente o il gruppo di domini di cui l'utente è membro deve essere membro del gruppo Administrators locale nel computer in cui si trova la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="5b8b8-120">In uno scenario con più domini, il dominio di un utente o di un gruppo deve essere un membro del gruppo Administrators locale nel computer nel dominio B in cui si troverà la condivisione file.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="5b8b8-121">Per informazioni dettagliate sull'aggiornamento con le condivisioni file in un file System distribuito (DFS), vedere [configurare l'archiviazione dei file per Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span><span class="sxs-lookup"><span data-stu-id="5b8b8-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5b8b8-122">La condivisione file per Lync Server 2013, Enterprise Edition non può essere posizionata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="5b8b8-123">Installare e configurare il servizio di bilanciamento del carico hardware per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="5b8b8-124">Con il bilanciamento del carico DNS (Domain Name System) distribuito, è comunque necessario usare anche i dispositivi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="5b8b8-125">Il bilanciamento del carico hardware viene usato per il traffico HTTPS dai client sulle porte 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="5b8b8-126">Anche se hai ancora bisogno di bilanciamento del carico hardware per questi pool, la configurazione e l'amministrazione saranno principalmente per il traffico HTTP/HTTPS, a cui sono abituati gli amministratori dei dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5b8b8-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="5b8b8-127">Dopo aver completato tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia è anche necessario:</span><span class="sxs-lookup"><span data-stu-id="5b8b8-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="5b8b8-128">Installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8b8-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="5b8b8-129">Configurare IIS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8b8-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="5b8b8-130">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b8b8-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="5b8b8-131">Configurare record DNS in Lync Server 2013 per un pool Front End o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5b8b8-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

