---
title: "Lync Server 2013: componenti e topologie per l'archiviazione"
description: "Lync Server 2013: componenti e topologie per l'archiviazione."
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
ms.openlocfilehash: f6ccb62993dc6a8dbc098d4a9c5f28b9b3f7fac9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576922"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="34e0b-103">Componenti e topologie per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34e0b-103">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e0b-104">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="34e0b-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="34e0b-105">Se si desidera archiviare i contenuti di messaggistica istantanea e di conferenza di Lync Server 2013, è possibile implementare l'archiviazione in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="34e0b-105">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="34e0b-106">Componenti di archiviazione</span><span class="sxs-lookup"><span data-stu-id="34e0b-106">Archiving Components</span></span>

<span data-ttu-id="34e0b-107">La funzionalità di archiviazione include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e0b-107">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="34e0b-p101">**Agenti di archiviazione**. Gli agenti di archiviazione, noti anche come agenti di raccolta dati unificata, vengono installati e attivati automaticamente in ogni pool Front End e in ogni server Standard Edition. Anche se gli agenti di archiviazione vengono attivati automaticamente, l'acquisizione dei messaggi inizia solo dopo che l'archiviazione è stata abilitata e configurata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="34e0b-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="34e0b-111">**Archivio dati di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="34e0b-111">**Archiving data storage**.</span></span> <span data-ttu-id="34e0b-112">L'archiviazione dei dati per Lync Server 2013 può essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="34e0b-112">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="34e0b-113">Archiviazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="34e0b-113">Exchange 2013 storage.</span></span> <span data-ttu-id="34e0b-114">Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate sul server Exchange 2013 utilizzano lo spazio di archiviazione di Exchange 2013 per i dati archiviati, ma solo se le cassette postali sono state inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="34e0b-114">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="34e0b-115">Archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="34e0b-115">SQL Server storage.</span></span> <span data-ttu-id="34e0b-116">Se nella distribuzione sono presenti utenti che si trovano in Lync Server 2013, è possibile configurare i database di archiviazione che eseguono una versione supportata di SQL Server per abilitare l'archiviazione per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="34e0b-116">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="34e0b-117">L'archiviazione richiede anche un archivio file, ma usa lo stesso archivio file dei Front End Server o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34e0b-117">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="34e0b-118">Per un elenco dei requisiti hardware e software per l'archiviazione, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto dell'infrastruttura e del software server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="34e0b-118">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="34e0b-119">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="34e0b-119">Supported Topologies</span></span>

<span data-ttu-id="34e0b-120">È necessario distribuire la funzionalità di archiviazione in ogni pool in cui si trovano utenti che richiedono il supporto dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="34e0b-120">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="34e0b-121">L'archiviazione viene eseguita nei Front End Server nei pool Enterprise Edition e nei server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34e0b-121">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="34e0b-122">L'archivio dati di archiviazione può essere:</span><span class="sxs-lookup"><span data-stu-id="34e0b-122">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="34e0b-123">Integrazione con l'archiviazione di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="34e0b-123">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="34e0b-124">Distribuiti tramite database di SQL Server distinti</span><span class="sxs-lookup"><span data-stu-id="34e0b-124">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="34e0b-125">Se la distribuzione di Exchange 2013 non include tutti gli utenti nella distribuzione di Lync Server, è necessario utilizzare l'integrazione di Microsoft Exchange per gli utenti le cui cassette postali sono ospitate nei server Exchange 2013 ed è necessario distribuire database SQL Server distinti per tutti gli altri utenti di Lync da utilizzare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="34e0b-125">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="34e0b-126">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="34e0b-126">Supported Collocation</span></span>

<span data-ttu-id="34e0b-127">Lync Server 2013 supporta diversi scenari di collocazione, consentendo la flessibilità per il salvataggio dei costi hardware eseguendo più componenti in un server (se si dispone di un'organizzazione di piccole dimensioni) o per eseguire singoli componenti in server diversi (se si dispone di un'organizzazione di dimensioni superiori che richiede scalabilità e prestazioni).</span><span class="sxs-lookup"><span data-stu-id="34e0b-127">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="34e0b-128">Prima di decidere se collocare i componenti, è sicuramente importante considerare i fattori di scalabilità.</span><span class="sxs-lookup"><span data-stu-id="34e0b-128">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="34e0b-129">L'archiviazione viene distribuita nei front end server di un pool o di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="34e0b-129">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="34e0b-130">Per informazioni dettagliate sui componenti che possono essere collocati in tale posizione, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="34e0b-130">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="34e0b-131">Se si utilizzano database di SQL Server distinti per l'archiviazione, anziché o oltre all'integrazione dell'archiviazione con l'archiviazione di Exchange 2013, è possibile collocare il database di archiviazione con uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="34e0b-131">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="34e0b-132">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="34e0b-132">Monitoring database</span></span>

  - <span data-ttu-id="34e0b-133">Database back-end di un pool Enterprise Edition Front End</span><span class="sxs-lookup"><span data-stu-id="34e0b-133">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34e0b-p108">Il server che ospita il database di archiviazione può ospitare altri database. Se, tuttavia, si desidera collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione. Per questo motivo non è consigliabile collocare il database di archiviazione con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="34e0b-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="34e0b-137">Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza SQL per uno o per tutti i database o, in alternativa, usare un'istanza SQL separata per ogni database, con la limitazione seguente:</span><span class="sxs-lookup"><span data-stu-id="34e0b-137">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="34e0b-138">Ogni istanza SQL può contenere un singolo database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="34e0b-138">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="34e0b-139">Per informazioni dettagliate sulla collocazione di tutti i ruoli del server e dei database, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="34e0b-139">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

