---
title: "Lync Server 2013: Preparazione dell'infrastruttura e dei sistemi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="09baa-102">Preparazione dell'infrastruttura e dei sistemi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09baa-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="09baa-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="09baa-104">La distribuzione di Lync Server 2013 richiede l'uso di generatore di topologia per definire e pubblicare la struttura della topologia.</span><span class="sxs-lookup"><span data-stu-id="09baa-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="09baa-105">Per identificare i componenti necessari per la topologia, è possibile usare generatore di topologia per creare e salvare una struttura di topologia.</span><span class="sxs-lookup"><span data-stu-id="09baa-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="09baa-106">Prima di pubblicare la topologia in Generatore di topologie, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="09baa-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="09baa-107">Acquisire e installare l'hardware per ogni componente nella progettazione della topologia creata e salvata con generatore di topologia, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services ( IIS) e invertire i server proxy, come appropriato), le schede di rete, i dispositivi di bilanciamento del carico hardware e gli strumenti di archiviazione, ad esempio i file server.</span><span class="sxs-lookup"><span data-stu-id="09baa-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="09baa-108">Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="09baa-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="09baa-109">Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="09baa-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="09baa-110">Verificare che l'infrastruttura di rete soddisfi i requisiti.</span><span class="sxs-lookup"><span data-stu-id="09baa-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="09baa-111">Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di rete per Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="09baa-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="09baa-112">Configurare servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="09baa-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="09baa-113">Per pubblicare e abilitare la topologia, è necessario che i server interni siano rappresentati da account di computer in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="09baa-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="09baa-114">Questa operazione viene eseguita unendo i computer a servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="09baa-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="09baa-115">Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="09baa-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="09baa-116">Creare una condivisione file.</span><span class="sxs-lookup"><span data-stu-id="09baa-116">Create a file share.</span></span> <span data-ttu-id="09baa-117">I server Standard Edition possono ospitare la condivisione file per il file richiesto, mentre in una distribuzione aziendale la condivisione file non può essere ospitata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="09baa-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="09baa-118">Le autorizzazioni e le appartenenze ai gruppi necessarie per la distribuzione e l'impostazione dell'elenco di controllo di accesso (ACL) nella cartella e della condivisione devono essere impostate correttamente per il completamento corretto di generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="09baa-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="09baa-119">Devi verificare che la persona che ha eseguito Generatore di topologia disponga delle autorizzazioni e delle appartenenze ai gruppi seguenti:</span><span class="sxs-lookup"><span data-stu-id="09baa-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="09baa-120">Membro degli amministratori locali</span><span class="sxs-lookup"><span data-stu-id="09baa-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="09baa-121">Membro degli utenti del dominio</span><span class="sxs-lookup"><span data-stu-id="09baa-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="09baa-122">Controllo completo sulla condivisione e la cartella di file Store</span><span class="sxs-lookup"><span data-stu-id="09baa-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="09baa-123">Per Enterprise Edition, installare e configurare SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09baa-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="09baa-124">Per il completamento dell'installazione di SQL Server, il server basato su SQL Server deve essere online e la persona che pubblica la topologia è un amministratore locale di SQL Server e deve essere un membro del gruppo sysadmin di SQL Server nell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="09baa-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="09baa-125">Dopo aver completato tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia è necessario eseguire anche le altre attività di preparazione, tra cui l'installazione dei sistemi operativi Windows e altro software prerequisito, la configurazione IIS e configurazione di DNS.</span><span class="sxs-lookup"><span data-stu-id="09baa-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="09baa-126">Per informazioni dettagliate su queste attività, vedere [requisiti di sistema per i server che utilizzano Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurare IIS per Lync Server 2013](lync-server-2013-configure-iis.md)e [preparare l'infrastruttura e i sistemi per Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span><span class="sxs-lookup"><span data-stu-id="09baa-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="09baa-127">È inoltre necessario acquisire familiarità con i client e i requisiti client.</span><span class="sxs-lookup"><span data-stu-id="09baa-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="09baa-128">Per informazioni dettagliate, vedere [distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="09baa-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09baa-129">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="09baa-129">In This Section</span></span>

  - [<span data-ttu-id="09baa-130">Configurazione hardware per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="09baa-131">Installazione del software per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="09baa-132">Preparazione di Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="09baa-133">Configurare SQL Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="09baa-134">Configurare record DNS in Lync Server 2013 per un pool Front End o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09baa-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="09baa-135">Installare gli strumenti di amministrazione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09baa-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

