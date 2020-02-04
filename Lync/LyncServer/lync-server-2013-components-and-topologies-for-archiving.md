---
title: "Lync Server 2013: Componenti e topologie per l'archiviazione"
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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="3b263-102">Componenti e topologie per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b263-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b263-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3b263-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3b263-104">Se si vuole archiviare il contenuto di messaggistica istantanea e di conferenza di Lync Server 2013, è possibile implementare l'archiviazione in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b263-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="3b263-105">Archiviazione di componenti</span><span class="sxs-lookup"><span data-stu-id="3b263-105">Archiving Components</span></span>

<span data-ttu-id="3b263-106">La caratteristica archiviazione include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b263-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="3b263-107">**Agenti di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3b263-107">**Archiving agents**.</span></span> <span data-ttu-id="3b263-108">Gli agenti di archiviazione (noti anche come agenti di raccolta dati unificati) vengono installati e attivati automaticamente in tutti i pool Front-end e nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3b263-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="3b263-109">Anche se gli agenti di archiviazione vengono attivati automaticamente, nessun messaggio viene effettivamente acquisito finché l'archiviazione non viene abilitata e configurata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="3b263-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="3b263-110">Archiviazione **dei dati archiviati**.</span><span class="sxs-lookup"><span data-stu-id="3b263-110">**Archiving data storage**.</span></span> <span data-ttu-id="3b263-111">L'archiviazione dei dati per Lync Server 2013 può essere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b263-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="3b263-112">Archiviazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3b263-112">Exchange 2013 storage.</span></span> <span data-ttu-id="3b263-113">Se si Abilita l'opzione di integrazione di Microsoft Exchange, le cassette postali degli utenti ospitate nel server di Exchange 2013 usano lo spazio di archiviazione di Exchange 2013 per i dati archiviati, ma solo se le cassette postali sono state messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="3b263-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="3b263-114">Archiviazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3b263-114">SQL Server storage.</span></span> <span data-ttu-id="3b263-115">Se si hanno utenti nella distribuzione ospitati in Lync Server 2013, è possibile configurare i database di archiviazione che eseguono una versione supportata di SQL Server per consentire l'archiviazione per tali utenti.</span><span class="sxs-lookup"><span data-stu-id="3b263-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="3b263-116">L'archiviazione richiede anche l'archiviazione dei file, ma l'archiviazione usa lo stesso spazio di archiviazione dei file del front end server o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3b263-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="3b263-117">Per un elenco dei requisiti hardware e software per l'archiviazione, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) e [supporto per software e infrastruttura server in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="3b263-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="3b263-118">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="3b263-118">Supported Topologies</span></span>

<span data-ttu-id="3b263-119">Si distribuisce l'archiviazione in ogni pool che include utenti che richiedono il supporto dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3b263-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="3b263-120">L'archiviazione viene eseguita nei server front-end nei pool Enterprise Edition e nei server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3b263-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="3b263-121">L'archiviazione dei dati di archiviazione può essere la seguente:</span><span class="sxs-lookup"><span data-stu-id="3b263-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="3b263-122">Integrazione con lo spazio di archiviazione di Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="3b263-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="3b263-123">Distribuiti tramite database di SQL Server distinti</span><span class="sxs-lookup"><span data-stu-id="3b263-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="3b263-124">Se la distribuzione di Exchange 2013 non include tutti gli utenti nella distribuzione di Lync Server, è necessario usare l'integrazione di Microsoft Exchange per gli utenti le cui cassette postali sono presenti nei server di Exchange 2013 ed è necessario distribuire database di SQL Server distinti per tutti gli altri Utenti di Lync da usare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3b263-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="3b263-125">Collocazione supportata</span><span class="sxs-lookup"><span data-stu-id="3b263-125">Supported Collocation</span></span>

<span data-ttu-id="3b263-126">Lync Server 2013 supporta diversi scenari di collocazione, consentendo la flessibilità per il salvataggio dei costi hardware eseguendo più componenti in un server (se si ha una piccola organizzazione) o per eseguire singoli componenti in server diversi (se si ha un numero maggiore organizzazione che richiede scalabilità e prestazioni).</span><span class="sxs-lookup"><span data-stu-id="3b263-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="3b263-127">I fattori di scalabilità dovrebbero certamente essere presi in considerazione prima di decidere se collocare i componenti.</span><span class="sxs-lookup"><span data-stu-id="3b263-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="3b263-128">L'archiviazione viene distribuita nei server front-end di un pool o di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3b263-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="3b263-129">Per informazioni dettagliate sui componenti che possono essere collocati in questa posizione, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="3b263-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="3b263-130">Se si usano database di SQL Server distinti per l'archiviazione, anziché o oltre ad integrare lo spazio di archiviazione con lo spazio di archiviazione di Exchange 2013, è possibile collocare il database di archiviazione con uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b263-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="3b263-131">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="3b263-131">Monitoring database</span></span>

  - <span data-ttu-id="3b263-132">Database back-end di un pool di front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3b263-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b263-133">Il server che ospita il database di archiviazione può ospitare altri database.</span><span class="sxs-lookup"><span data-stu-id="3b263-133">The server hosting the Archiving database can host other databases.</span></span> <span data-ttu-id="3b263-134">Tuttavia, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può essere molto elevato.</span><span class="sxs-lookup"><span data-stu-id="3b263-134">However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="3b263-135">Per questo motivo, non è consigliabile collocare il database di archiviazione con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="3b263-135">For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="3b263-136">Se si colloca il database di archiviazione con il database di monitoraggio, il database back-end o entrambi i database, è possibile usare una singola istanza di SQL per uno o tutti i database oppure è possibile usare un'istanza SQL separata per ogni database, con le operazioni seguenti limitazione</span><span class="sxs-lookup"><span data-stu-id="3b263-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="3b263-137">Ogni istanza di SQL può contenere solo un database back-end, un singolo database di monitoraggio e un singolo database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3b263-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="3b263-138">Per informazioni dettagliate sulla collocazione di tutti i ruoli e i database del server, vedere [collocazione del server supportata in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="3b263-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

