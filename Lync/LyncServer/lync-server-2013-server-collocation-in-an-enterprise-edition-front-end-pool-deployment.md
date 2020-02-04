---
title: 'Lync Server 2013: Collocazione dei server in una distribuzione di pool Enterprise Edition Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad549c614fc14b74126a7e81e0223ad584e68141
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="1709a-102">Collocazione dei server in una distribuzione di pool Enterprise Edition Front End per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1709a-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1709a-103">_**Argomento Ultima modifica:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="1709a-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="1709a-104">In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione del pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1709a-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="1709a-105">Ruoli del server</span><span class="sxs-lookup"><span data-stu-id="1709a-105">Server Roles</span></span>

<span data-ttu-id="1709a-106">In Lync Server 2013, il servizio di conferenza A/V, il servizio di mediazione, il monitoraggio e l'archiviazione sono collocati nel server front-end, ma è necessaria una configurazione aggiuntiva per abilitarli.</span><span class="sxs-lookup"><span data-stu-id="1709a-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="1709a-107">Se non si vuole collocare il Mediation Server con il front end server, è possibile distribuirlo come Mediation Server autonomo in un computer separato.</span><span class="sxs-lookup"><span data-stu-id="1709a-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="1709a-108">È possibile collocare un server delle applicazioni attendibile con il server front-end.</span><span class="sxs-lookup"><span data-stu-id="1709a-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="1709a-109">I ruoli del server seguenti devono essere distribuiti in un computer separato:</span><span class="sxs-lookup"><span data-stu-id="1709a-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="1709a-110">Director</span><span class="sxs-lookup"><span data-stu-id="1709a-110">Director</span></span>

  - <span data-ttu-id="1709a-111">Edge Server</span><span class="sxs-lookup"><span data-stu-id="1709a-111">Edge Server</span></span>

  - <span data-ttu-id="1709a-112">Mediation Server (se non è collocato nel server front-end)</span><span class="sxs-lookup"><span data-stu-id="1709a-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="1709a-113">Server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="1709a-113">Office Web Apps Server</span></span>

<span data-ttu-id="1709a-114">Non è possibile collocare il ruolo del server di chat persistente con il server front-end.</span><span class="sxs-lookup"><span data-stu-id="1709a-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="1709a-115">Database</span><span class="sxs-lookup"><span data-stu-id="1709a-115">Databases</span></span>

<span data-ttu-id="1709a-116">È possibile collocare tutti i database seguenti nello stesso server di database:</span><span class="sxs-lookup"><span data-stu-id="1709a-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="1709a-117">Database back-end</span><span class="sxs-lookup"><span data-stu-id="1709a-117">Back-end database</span></span>

  - <span data-ttu-id="1709a-118">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="1709a-118">Monitoring database</span></span>

  - <span data-ttu-id="1709a-119">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1709a-119">Archiving database</span></span>

  - <span data-ttu-id="1709a-120">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="1709a-120">Persistent Chat database</span></span>

  - <span data-ttu-id="1709a-121">Database di conformità della chat persistente</span><span class="sxs-lookup"><span data-stu-id="1709a-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="1709a-122">È possibile collocare tutti o uno o tutti questi database in una singola istanza di SQL Server o utilizzare un'istanza distinta di SQL Server per ognuno di essi, con le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1709a-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="1709a-123">Ogni istanza di SQL Server può contenere solo un singolo database back-end, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1709a-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="1709a-124">Il server di database non può supportare più di un pool Front-End, una distribuzione di archiviazione e una distribuzione di monitoraggio, ma può supportare uno di essi, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1709a-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="1709a-125">È possibile collocare una condivisione di file con i database, come descritto più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="1709a-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1709a-126">In Lync Server 2013 è possibile integrare lo spazio di archiviazione di archiviazione con lo spazio di archiviazione di Exchange 2013 per alcuni o tutti gli utenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1709a-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="1709a-127">Non è possibile distribuire tutti i server che utilizzano Lync Server o componenti nello stesso server dell'archivio di Exchange.</span><span class="sxs-lookup"><span data-stu-id="1709a-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1709a-128">Anche se è supportata la collocazione dei database, è possibile che le dimensioni dei database crescano rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1709a-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="1709a-129">Ad esempio, se si considera la collocazione del database di archiviazione con altri database, tenere presente che, se si archiviano i messaggi di più utenti, lo spazio su disco necessario per il database di archiviazione può diventare molto grande.</span><span class="sxs-lookup"><span data-stu-id="1709a-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="1709a-130">Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente o il database di conformità della chat persistente con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="1709a-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="1709a-131">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="1709a-131">File Share</span></span>

<span data-ttu-id="1709a-132">La condivisione file può essere un server separato o può essere collocata nello stesso server di una o tutte le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1709a-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="1709a-133">Server di database, incluso il server back-end di un pool Front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="1709a-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="1709a-134">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="1709a-134">Archiving database</span></span>

  - <span data-ttu-id="1709a-135">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="1709a-135">Monitoring database</span></span>

  - <span data-ttu-id="1709a-136">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="1709a-136">Persistent Chat database</span></span>

  - <span data-ttu-id="1709a-137">Database di conformità della chat persistente</span><span class="sxs-lookup"><span data-stu-id="1709a-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="1709a-138">È possibile usare una singola condivisione di file per più pool Front-End, server Standard Edition (tutti nello stesso sito).</span><span class="sxs-lookup"><span data-stu-id="1709a-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1709a-139">In Lync Server 2013 il monitoraggio e l'archiviazione usano la condivisione file di Lync Server come server front-end.</span><span class="sxs-lookup"><span data-stu-id="1709a-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="1709a-140">Altri componenti</span><span class="sxs-lookup"><span data-stu-id="1709a-140">Other Components</span></span>

<span data-ttu-id="1709a-141">Non è possibile collocare un server proxy inverso, che non è un componente Lync Server 2013, ma è necessario nella distribuzione se si vuole supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1709a-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="1709a-142">Puoi tuttavia implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto di un server proxy inverso esistente nell'organizzazione usato per altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1709a-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="1709a-143">Non è possibile collocare un componente di messaggistica UNIFICAta di Exchange o un componente di SharePoint con qualsiasi ruolo di SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="1709a-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

