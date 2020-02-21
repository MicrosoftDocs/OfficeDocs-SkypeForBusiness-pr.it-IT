---
title: "Lync Server 2013: componenti e topologie per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca674be0059a235439df637f07cb4ca834806d4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="be4f6-102">Componenti e topologie per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be4f6-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be4f6-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="be4f6-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="be4f6-104">Se si desidera archiviare i contenuti di messaggistica istantanea e di conferenza di Lync Server 2013, è possibile implementare l'archiviazione in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be4f6-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="be4f6-105">Componenti di archiviazione</span><span class="sxs-lookup"><span data-stu-id="be4f6-105">Archiving Components</span></span>

<span data-ttu-id="be4f6-106">La funzionalità di archiviazione include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="be4f6-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="be4f6-p101">**Agenti di archiviazione**. Gli agenti di archiviazione, noti anche come agenti di raccolta dati unificata, vengono installati e attivati automaticamente in ogni pool Front End e in ogni server Standard Edition. Anche se gli agenti di archiviazione vengono attivati automaticamente, l'acquisizione dei messaggi inizia solo dopo che l'archiviazione è stata abilitata e configurata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="be4f6-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="be4f6-110">**Archivio dati di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="be4f6-110">**Archiving data storage**.</span></span> <span data-ttu-id="be4f6-111">L'archiviazione dei dati per Lync Server 2013 può essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="be4f6-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="be4f6-112">Archiviazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="be4f6-112">Exchange 2013 storage.</span></span> <span data-ttu-id="be4f6-113">Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate sul server Exchange 2013 utilizzano lo spazio di archiviazione di Exchange 2013 per i dati archiviati, ma solo se le cassette postali sono state inserite nel blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="be4f6-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="be4f6-114">Archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be4f6-114">SQL Server storage.</span></span> <span data-ttu-id="be4f6-115">Se nella distribuzione sono presenti utenti che si trovano in Lync Server 2013, è possibile configurare i database di archiviazione che eseguono una versione supportata di SQL Server per abilitare l'archiviazione per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="be4f6-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="be4f6-116">L'archiviazione richiede anche un archivio file, ma usa lo stesso archivio file dei Front End Server o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="be4f6-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="be4f6-117">Per un elenco dei requisiti hardware e software per l'archiviazione, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto dell'infrastruttura e del software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="be4f6-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="be4f6-118">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="be4f6-118">Supported Topologies</span></span>

<span data-ttu-id="be4f6-119">È necessario distribuire la funzionalità di archiviazione in ogni pool in cui si trovano utenti che richiedono il supporto dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="be4f6-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="be4f6-120">L'archiviazione viene eseguita nei Front End Server nei pool Enterprise Edition e nei server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="be4f6-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="be4f6-121">L'archivio dati di archiviazione può essere:</span><span class="sxs-lookup"><span data-stu-id="be4f6-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="be4f6-122">Integrazione con l'archiviazione di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="be4f6-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="be4f6-123">Distribuiti tramite database di SQL Server distinti</span><span class="sxs-lookup"><span data-stu-id="be4f6-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="be4f6-124">Se la distribuzione di Exchange 2013 non include tutti gli utenti nella distribuzione di Lync Server, è necessario utilizzare l'integrazione di Microsoft Exchange per gli utenti le cui cassette postali sono ospitate nei server Exchange 2013 ed è necessario distribuire database SQL Server distinti per tutti gli altri Utenti di Lync da utilizzare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="be4f6-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="be4f6-125">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="be4f6-125">Supported Collocation</span></span>

<span data-ttu-id="be4f6-126">Lync Server 2013 supporta una serie di scenari di collocazione, consentendo la flessibilità per il salvataggio dei costi hardware eseguendo più componenti in un server (se si dispone di una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si dispone di un numero maggiore di organizzazione che richiede scalabilità e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="be4f6-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="be4f6-127">Prima di decidere se collocare i componenti, è sicuramente importante considerare i fattori di scalabilità.</span><span class="sxs-lookup"><span data-stu-id="be4f6-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="be4f6-128">L'archiviazione viene distribuita nei front end server di un pool o di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="be4f6-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="be4f6-129">Per informazioni dettagliate sui componenti che possono essere collocati in tale posizione, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="be4f6-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="be4f6-130">Se si utilizzano database di SQL Server distinti per l'archiviazione, anziché o oltre all'integrazione dell'archiviazione con l'archiviazione di Exchange 2013, è possibile collocare il database di archiviazione con uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="be4f6-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="be4f6-131">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="be4f6-131">Monitoring database</span></span>

  - <span data-ttu-id="be4f6-132">Database back-end di un pool Enterprise Edition Front End</span><span class="sxs-lookup"><span data-stu-id="be4f6-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be4f6-p108">Il server che ospita il database di archiviazione può ospitare altri database. Se, tuttavia, si desidera collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo non è consigliabile collocare il database di archiviazione con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="be4f6-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="be4f6-136">Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza SQL per uno o per tutti i database o, in alternativa, usare un'istanza SQL separata per ogni database, con la limitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="be4f6-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="be4f6-137">Ogni istanza SQL può contenere un singolo database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="be4f6-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="be4f6-138">Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="be4f6-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

