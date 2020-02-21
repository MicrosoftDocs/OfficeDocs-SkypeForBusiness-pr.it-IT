---
title: Collocazione del server Lync Server 2013 in una distribuzione di pool Enterprise Edition front end
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
ms.openlocfilehash: 5ccfb87966008d471d879e2c25a73e098fb28f19
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="a3bb0-102">Collocazione dei server in una distribuzione di pool Enterprise Edition front end per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3bb0-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3bb0-103">_**Ultimo argomento modificato:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="a3bb0-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="a3bb0-104">In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione di pool Front End di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="a3bb0-105">Ruoli del server</span><span class="sxs-lookup"><span data-stu-id="a3bb0-105">Server Roles</span></span>

<span data-ttu-id="a3bb0-106">In Lync Server 2013, il servizio A/V Conferencing, il servizio Mediation, il monitoraggio e l'archiviazione sono collocati nel front end server, ma è necessaria una configurazione aggiuntiva per abilitarli.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="a3bb0-107">Se si sceglie di non collocare il Mediation Server nel Front End Server, è possibile distribuirlo come Mediation Server autonomo in un computer distinto.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="a3bb0-108">È possibile collocare un server applicazioni attendibili nel Front End Server.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="a3bb0-109">I ruoli del server seguenti devono essere ognuno distribuito in un computer distinto:</span><span class="sxs-lookup"><span data-stu-id="a3bb0-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="a3bb0-110">Director</span><span class="sxs-lookup"><span data-stu-id="a3bb0-110">Director</span></span>

  - <span data-ttu-id="a3bb0-111">Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3bb0-111">Edge Server</span></span>

  - <span data-ttu-id="a3bb0-112">Mediation Server (se non collocato con il Front End Server)</span><span class="sxs-lookup"><span data-stu-id="a3bb0-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="a3bb0-113">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="a3bb0-113">Office Web Apps Server</span></span>

<span data-ttu-id="a3bb0-114">Non è possibile collocare il ruolo del server Chat persistente con il front end server.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="a3bb0-115">Database</span><span class="sxs-lookup"><span data-stu-id="a3bb0-115">Databases</span></span>

<span data-ttu-id="a3bb0-116">È possibile collocare ognuno dei database seguenti nello stesso server di database:</span><span class="sxs-lookup"><span data-stu-id="a3bb0-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="a3bb0-117">Database back-end</span><span class="sxs-lookup"><span data-stu-id="a3bb0-117">Back-end database</span></span>

  - <span data-ttu-id="a3bb0-118">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a3bb0-118">Monitoring database</span></span>

  - <span data-ttu-id="a3bb0-119">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a3bb0-119">Archiving database</span></span>

  - <span data-ttu-id="a3bb0-120">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="a3bb0-120">Persistent Chat database</span></span>

  - <span data-ttu-id="a3bb0-121">Database di conformità di Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="a3bb0-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="a3bb0-122">È possibile collocare tutti o uno o tutti questi database in una singola istanza di SQL Server oppure utilizzare un'istanza separata di SQL Server per ognuno, con le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3bb0-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="a3bb0-123">Ogni istanza di SQL Server può contenere solo un singolo database back-end, un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="a3bb0-124">Il server di database non è in grado di supportare più di un pool Front End, una distribuzione di archiviazione e una distribuzione di monitoraggio, ma è in grado di supportare ognuno di essi, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="a3bb0-125">È possibile collocare una condivisione file con i database, come descritto più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3bb0-126">In Lync Server 2013, si ha la possibilità di integrare l'archiviazione di archiviazione con Exchange 2013 storage per alcuni o tutti gli utenti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="a3bb0-127">Non è possibile distribuire i server che eseguono Lync Server o i componenti negli stessi server dell'archivio di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a3bb0-128">Sebbene la collocazione dei database sia supportata, la dimensione dei database può aumentare rapidamente.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="a3bb0-129">Ad esempio, se si intende collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="a3bb0-130">Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente o il database di conformità di Persistent Chat con il database back-end.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="a3bb0-131">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="a3bb0-131">File Share</span></span>

<span data-ttu-id="a3bb0-132">La condivisione file può essere un server separato o essere collocata nello stesso server utilizzato da uno, più o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3bb0-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="a3bb0-133">Server di database, inclusi il server back-end di un pool Enterprise Edition Front End</span><span class="sxs-lookup"><span data-stu-id="a3bb0-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="a3bb0-134">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="a3bb0-134">Archiving database</span></span>

  - <span data-ttu-id="a3bb0-135">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="a3bb0-135">Monitoring database</span></span>

  - <span data-ttu-id="a3bb0-136">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="a3bb0-136">Persistent Chat database</span></span>

  - <span data-ttu-id="a3bb0-137">Database di conformità di Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="a3bb0-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="a3bb0-138">Una singola condivisione file può essere utilizzata per più pool Front End e server Standard Edition, tutti nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3bb0-139">In Lync Server 2013, il monitoraggio e l'archiviazione utilizzano la condivisione file di Lync Server come front end server.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="a3bb0-140">Altri componenti</span><span class="sxs-lookup"><span data-stu-id="a3bb0-140">Other Components</span></span>

<span data-ttu-id="a3bb0-141">Non è possibile collocare un server proxy inverso, che non è un componente di Lync Server 2013, ma che è necessario nella distribuzione se si desidera supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="a3bb0-142">È tuttavia possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="a3bb0-143">Non è possibile collocare alcun componente di messaggistica unificata di Exchange o componente di SharePoint con qualsiasi ruolo di SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="a3bb0-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

