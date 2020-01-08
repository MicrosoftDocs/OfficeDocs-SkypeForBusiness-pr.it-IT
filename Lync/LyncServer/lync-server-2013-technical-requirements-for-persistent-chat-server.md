---
title: 'Lync Server 2013: requisiti tecnici per il server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b84f1a2932b76c8030c907463e8f0f2e93bedda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5a7e0-102">Requisiti tecnici per il server di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a7e0-102">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a7e0-103">_**Argomento Ultima modifica:** 2013-01-06_</span><span class="sxs-lookup"><span data-stu-id="5a7e0-103">_**Topic Last Modified:** 2013-01-06_</span></span>

<span data-ttu-id="5a7e0-104">Ogni computer che ospita il server di chat persistente deve avere accesso a una topologia di Lync Server 2013 esistente con i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7e0-104">Each computer that hosts Persistent Chat Server must have access to an existing Lync Server 2013 topology with the following components:</span></span>

  - <span data-ttu-id="5a7e0-105">**Lync Server 2013, server front-end.**  Il server front-end è la base per il routing SIP (Session Initiation Protocol), che rende possibile la comunicazione tra i computer che eseguono il server di chat persistente e la funzionalità di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-105">**Lync Server 2013, Front End Server.** The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> <span data-ttu-id="5a7e0-106">Prima di iniziare a distribuire il server di chat persistente, verificare la distribuzione di Lync Server 2013, Standard Edition o un pool di front-end di Lync Server e tutti gli altri computer interni che eseguono Lync Server, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-106">Before you begin to deploy Persistent Chat Server, verify the deployment of Lync Server 2013, Standard Edition, or a Lync Server Front End pool and any other internal computers running Lync Server, as appropriate to your organization.</span></span>

<span data-ttu-id="5a7e0-107">Nelle sezioni seguenti vengono descritti i requisiti specifici per il server di chat persistente e il database in cui sono archiviati i dati della chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-107">The following sections describe the specific requirements for the Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

<div>

## <a name="persistent-chat-server-requirements"></a><span data-ttu-id="5a7e0-108">Requisiti del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="5a7e0-108">Persistent Chat Server Requirements</span></span>

<span data-ttu-id="5a7e0-109">Per informazioni dettagliate sull'hardware consigliato per la distribuzione di Lync Server e la versione più recente del server di chat persistente, vedere [piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-109">For details about the recommended hardware for deploying Lync Server and the latest version of Persistent Chat Server, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5a7e0-110">Per informazioni dettagliate sul supporto del sistema operativo server e strumenti per Lync Server e il server di chat persistente, vedere [supporto dei sistemi operativi server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-110">For details about the server and tools operating system support for Lync Server and Persistent Chat Server, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5a7e0-111">Per informazioni dettagliate sul software aggiuntivo necessario per la distribuzione del server di chat persistente, vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-111">For details about additional software required for deploying Persistent Chat Server, see the following table.</span></span>

### <a name="persistent-chat-server-software-prerequisites"></a><span data-ttu-id="5a7e0-112">Prerequisiti software per la chat persistente</span><span class="sxs-lookup"><span data-stu-id="5a7e0-112">Persistent Chat Server Software Prerequisites</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a7e0-113">Software</span><span class="sxs-lookup"><span data-stu-id="5a7e0-113">Software</span></span></th>
<th><span data-ttu-id="5a7e0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a7e0-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a7e0-115">Accodamento messaggi</span><span class="sxs-lookup"><span data-stu-id="5a7e0-115">Message Queuing</span></span></p></td>
<td><p><span data-ttu-id="5a7e0-116">Usato dal server di chat persistente e dal servizio di conformità della chat persistente, se distribuito.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-116">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="5a7e0-117">Requisiti del database del server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="5a7e0-117">Persistent Chat Server Database Requirements</span></span>

<span data-ttu-id="5a7e0-118">Persistent Chat Server usa il database di chat persistente per archiviare la cronologia delle chat, la configurazione e i dati di provisioning degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-118">Persistent Chat Server uses the Persistent Chat database to store chat history, configuration, and user provisioning data.</span></span> <span data-ttu-id="5a7e0-119">Facoltativamente, usa il database di conformità della chat persistente per archiviare i dati di conformità.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-119">Optionally, it uses the Persistent Chat compliance database to store compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a7e0-120">Il database di chat persistente (MGC) e il database di conformità (mgccomp) possono trovarsi nella stessa istanza di SQL Server o in server SQL diversi.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-120">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>



</div>

<span data-ttu-id="5a7e0-121">Per preparare una piattaforma del server di database, assicurarsi che ogni computer soddisfi i requisiti hardware e quindi installare il software prerequisito.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-121">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span>

<span data-ttu-id="5a7e0-122">La piattaforma server per i server di database della chat persistente richiede lo stesso hardware del server di database back-end di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-122">The server platform for the Persistent Chat database servers requires the same hardware as the Lync Server back-end database server.</span></span> <span data-ttu-id="5a7e0-123">Per informazioni dettagliate, vedere [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-123">For details, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5a7e0-124">Nel server database verificare che sia installata una delle applicazioni software seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a7e0-124">On the database server, be sure that one of the following software applications is installed:</span></span>

  - <span data-ttu-id="5a7e0-125">Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-125">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="5a7e0-126">Per informazioni dettagliate su come installare Microsoft SQL Server 2012, vedere "installare SQL Server 2012" [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span><span class="sxs-lookup"><span data-stu-id="5a7e0-126">For details about how to install Microsoft SQL Server 2012, see "Install SQL Server 2012" at [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).</span></span>

  - <span data-ttu-id="5a7e0-127">Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-127">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="5a7e0-128">Per informazioni dettagliate su come installare Microsoft SQL Server 2008 R2, vedere la pagina relativa all' [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)installazione di SQL Server (sql Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="5a7e0-128">For details about how to install Microsoft SQL Server 2008 R2, see "SQL Server Installation (SQL Server 2008 R2)" at [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).</span></span>

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="5a7e0-129">Requisiti del certificato del server di chat persistente</span><span class="sxs-lookup"><span data-stu-id="5a7e0-129">Persistent Chat Server Certificate Requirements</span></span>

<span data-ttu-id="5a7e0-130">Per informazioni dettagliate sull'acquisizione di certificati, sulla creazione del database di SQL Server e sulla creazione di archivi di file, vedere [distribuzione di Lync Server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5a7e0-130">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

