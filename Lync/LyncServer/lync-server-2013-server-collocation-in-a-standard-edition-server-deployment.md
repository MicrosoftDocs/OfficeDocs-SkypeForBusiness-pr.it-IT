---
title: Collocazione del server Lync Server 2013 in una distribuzione di server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e50aa9339d992e73cf4e5b32b1e49fc2a144e67
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510313"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="07b7d-102">Collocazione dei server in una distribuzione di server Standard Edition per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07b7d-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07b7d-103">_**Ultimo argomento modificato:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="07b7d-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="07b7d-104">In questa sezione vengono descritti i ruoli del server, i database e le condivisioni di file che è possibile collocare in una distribuzione di Lync Server 2013 Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="07b7d-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="07b7d-105">Ruoli del server</span><span class="sxs-lookup"><span data-stu-id="07b7d-105">Server Roles</span></span>

<span data-ttu-id="07b7d-106">In Lync Server 2013, il servizio A/V Conferencing, il servizio Mediation, il monitoraggio e l'archiviazione sono collocati nel server Standard Edition, ma è necessaria una configurazione aggiuntiva per abilitarli.</span><span class="sxs-lookup"><span data-stu-id="07b7d-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="07b7d-107">È possibile scegliere di distribuire il servizio Mediation su server distinti.</span><span class="sxs-lookup"><span data-stu-id="07b7d-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="07b7d-108">È possibile collocare un server applicazioni attendibile con un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="07b7d-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="07b7d-109">I ruoli del server seguenti devono essere ognuno distribuito in un computer distinto:</span><span class="sxs-lookup"><span data-stu-id="07b7d-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="07b7d-110">Director</span><span class="sxs-lookup"><span data-stu-id="07b7d-110">Director</span></span>

  - <span data-ttu-id="07b7d-111">Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="07b7d-111">Edge Server</span></span>

  - <span data-ttu-id="07b7d-112">Mediation Server (se non collocato con il server Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="07b7d-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="07b7d-113">server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="07b7d-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="07b7d-114">Database</span><span class="sxs-lookup"><span data-stu-id="07b7d-114">Databases</span></span>

<span data-ttu-id="07b7d-115">Per impostazione predefinita, il database back-end di SQL Server Express è collocato nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="07b7d-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="07b7d-116">Non è possibile spostarlo in un computer separato.</span><span class="sxs-lookup"><span data-stu-id="07b7d-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="07b7d-117">Con un'eccezione, non è possibile collocare altri database nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="07b7d-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="07b7d-118">Se si sceglie di distribuire il server Chat persistente in un server Standard Edition, è possibile collocare il database di chat persistente e il database di conformità di Persistent Chat nello stesso server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="07b7d-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="07b7d-119">È possibile collocare ognuno dei database seguenti in un singolo server di database:</span><span class="sxs-lookup"><span data-stu-id="07b7d-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="07b7d-120">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="07b7d-120">Monitoring database</span></span>

  - <span data-ttu-id="07b7d-121">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="07b7d-121">Archiving database</span></span>

  - <span data-ttu-id="07b7d-122">Un database back-end per un pool Enterprise Edition front end</span><span class="sxs-lookup"><span data-stu-id="07b7d-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="07b7d-123">È possibile collocare uno o più o tutti questi database in una singola istanza di SQL oppure utilizzare istanze SQL separate per ognuna, con le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07b7d-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="07b7d-124">Ogni istanza SQL può contenere un singolo database back-end (per un pool Enterprise Edition front end), un singolo database di monitoraggio, un singolo database di archiviazione, un singolo database di chat persistente e un singolo database di conformità di Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="07b7d-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="07b7d-125">Il server di database non è in grado di supportare più di un pool Enterprise Edition front end, un server che esegue l'archiviazione, un server che esegue il monitoraggio, un singolo database di chat persistente e un database di conformità di chat persistente, ma può supportarne uno, indipendentemente dal fatto che i database utilizzino la stessa istanza di SQL Server o le istanze separate di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07b7d-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="07b7d-126">È possibile collocare una condivisione file con i database, come descritto più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="07b7d-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07b7d-127">In Lync Server 2013, è possibile integrare l'archiviazione di monitoraggio e archiviazione con Exchange 2013 storage per alcuni o tutti gli utenti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="07b7d-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="07b7d-128">Non è possibile distribuire i server che eseguono Lync Server o i componenti negli stessi server dell'archivio di Exchange.</span><span class="sxs-lookup"><span data-stu-id="07b7d-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07b7d-129">Sebbene la collocazione dei database sia supportata, la dimensione dei database può aumentare rapidamente.</span><span class="sxs-lookup"><span data-stu-id="07b7d-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="07b7d-130">Ad esempio, se si intende collocare il database di archiviazione con altri database, è opportuno tenere presente che l'archiviazione dei messaggi di più utenti può comportare un notevole aumento dello spazio su disco richiesto dal database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="07b7d-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="07b7d-131">Per questo motivo, non è consigliabile collocare più database, in particolare il database di archiviazione, il database di chat persistente e il database di conformità di Persistent Chat con il database back-end di un pool Enterprise.</span><span class="sxs-lookup"><span data-stu-id="07b7d-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="07b7d-132">Condivisioni file</span><span class="sxs-lookup"><span data-stu-id="07b7d-132">File Shares</span></span>

<span data-ttu-id="07b7d-133">La condivisione file può essere un server separato o essere collocata nello stesso server utilizzato da uno, più o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07b7d-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="07b7d-134">Server di database, inclusi il server back-end di un pool Enterprise Edition Front End</span><span class="sxs-lookup"><span data-stu-id="07b7d-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="07b7d-135">Database di archiviazione</span><span class="sxs-lookup"><span data-stu-id="07b7d-135">Archiving database</span></span>

  - <span data-ttu-id="07b7d-136">Database di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="07b7d-136">Monitoring database</span></span>

  - <span data-ttu-id="07b7d-137">Database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="07b7d-137">Persistent Chat database</span></span>

  - <span data-ttu-id="07b7d-138">Database di conformità di Persistent Chat</span><span class="sxs-lookup"><span data-stu-id="07b7d-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="07b7d-139">Una singola condivisione file può essere utilizzata per più pool Front End e server Standard Edition, tutti nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="07b7d-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07b7d-140">In Lync Server 2013, il monitoraggio e l'archiviazione utilizzano la condivisione file di Lync Server come server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="07b7d-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="07b7d-141">Altri componenti</span><span class="sxs-lookup"><span data-stu-id="07b7d-141">Other Components</span></span>

<span data-ttu-id="07b7d-142">Non è possibile collocare un server proxy inverso, che non è un componente di Lync Server 2013, ma che è necessario nella distribuzione se si desidera supportare la condivisione di contenuto Web per gli utenti federati con qualsiasi ruolo del server Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07b7d-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="07b7d-143">È tuttavia possibile implementare il supporto del proxy inverso per una distribuzione di Lync Server 2013 configurando il supporto su un server proxy inverso esistente nell'organizzazione utilizzato per altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="07b7d-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="07b7d-144">Non è possibile collocare alcun componente di messaggistica unificata di Exchange o componente di SharePoint con un ruolo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="07b7d-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

