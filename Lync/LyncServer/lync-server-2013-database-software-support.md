---
title: Supporto software per database di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8134c9ab0fe6cd481116c8a3d17636b04c980e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="cfbab-102">Supporto software per database in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfbab-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfbab-103">_**Ultimo argomento modificato:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="cfbab-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="cfbab-104">Lync Server 2013 supporta i sistemi di gestione dei database seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfbab-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="cfbab-105">**Database back-end di un pool Front End, database di archiviazione, database di monitoraggio, database di chat persistente e database di conformità di chat persistente**</span><span class="sxs-lookup"><span data-stu-id="cfbab-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="cfbab-p101">Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="cfbab-p102">Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="cfbab-p103">Microsoft SQL Server 2012 Enterprise (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="cfbab-p104">Microsoft SQL Server 2012 Standard (edizione a 64 bit). È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="cfbab-114">**Database del server Standard Edition e database front end server**</span><span class="sxs-lookup"><span data-stu-id="cfbab-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="cfbab-115">Microsoft SQL Server 2012 Express (versione 64 bit).</span><span class="sxs-lookup"><span data-stu-id="cfbab-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="cfbab-116">È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="cfbab-117">È supportata l'applicazione di patch e l'aggiornamento di Microsoft SQL Server nei front end server e nei server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cfbab-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="cfbab-118">Tuttavia, quando si esegue qualsiasi tipo di aggiornamento o patch nei Front End Server, è necessario tenere conto dei requisiti di quorum.</span><span class="sxs-lookup"><span data-stu-id="cfbab-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="cfbab-119">Per ulteriori informazioni, vedere [aggiornare o aggiornare Front End Server in Lync server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) e [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="cfbab-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cfbab-120">Microsoft SQL Server 2012 Express (versione 64 bit) viene installato automaticamente da Lync Server 2013 in ogni server Standard Edition e in ogni server front end server.</span><span class="sxs-lookup"><span data-stu-id="cfbab-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="cfbab-121">Lync Server 2013 non supporta l'edizione a 32 bit di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfbab-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="cfbab-122">È necessario utilizzare l'edizione a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="cfbab-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="cfbab-123">SQL Server Web Edition e SQL Server Workgroup Edition non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="cfbab-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="cfbab-124">Non è possibile utilizzarli con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfbab-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="cfbab-125">Lync Server 2013 supporta il mirroring del database nativo.</span><span class="sxs-lookup"><span data-stu-id="cfbab-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="cfbab-126">Per utilizzare il ruolo Monitoring Server, è necessario installare SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="cfbab-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="cfbab-127">In un pool Front End, il database back-end può essere un singolo computer SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cfbab-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cfbab-128">Se si installano i database di Lync Server con altri database, è consigliabile valutare tutti i fattori che possono influire sulla disponibilità e sulle prestazioni, nonché garantire che, se un nodo ha esito negativo, il nodo rimanente può gestire il carico.</span><span class="sxs-lookup"><span data-stu-id="cfbab-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="cfbab-129">Per verificare le capacità di failover, è consigliabile testare tutti gli scenari di failover.</span><span class="sxs-lookup"><span data-stu-id="cfbab-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="cfbab-130">Utilizzo del mirroring SQL e del clustering SQL</span><span class="sxs-lookup"><span data-stu-id="cfbab-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="cfbab-131">Lync Server 2013 supporta l'utilizzo del mirroring SQL o del clustering SQL per ogni database di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfbab-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="cfbab-132">È possibile configurare facilmente il mirroring SQL con lo strumento generatore di topologie in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfbab-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="cfbab-133">Per il clustering di failover SQL, è necessario utilizzare SQL Server per il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="cfbab-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="cfbab-134">Lync Server 2013 supporta sia il mirroring SQL che le topologie di clustering SQL per tutte le distribuzioni, incluse le distribuzioni Greenfield e le organizzazioni che hanno eseguito l'aggiornamento dalle versioni precedenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfbab-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="cfbab-135">Il supporto per il clustering di SQL è per una configurazione attiva/passiva.</span><span class="sxs-lookup"><span data-stu-id="cfbab-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="cfbab-136">Per motivi di prestazioni, il nodo passivo non deve essere condiviso da un'altra istanza di SQL.</span><span class="sxs-lookup"><span data-stu-id="cfbab-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="cfbab-137">È incluso il supporto seguente:</span><span class="sxs-lookup"><span data-stu-id="cfbab-137">The following support is included:</span></span>

  - <span data-ttu-id="cfbab-138">Clustering di failover a due nodi per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfbab-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="cfbab-139">Microsoft SQL Server 2012 Standard (edizione a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="cfbab-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="cfbab-140">È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="cfbab-141">Microsoft SQL Server 2008 R2 Standard (edizione a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="cfbab-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="cfbab-142">È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="cfbab-143">Clustering di failover fino a sedici nodi per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfbab-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="cfbab-144">Microsoft SQL Server 2012 Enterprise (edizione a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="cfbab-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="cfbab-145">È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="cfbab-146">Software di database di Microsoft SQL Server 2008 R2 Enterprise (edizione a 64 bit).</span><span class="sxs-lookup"><span data-stu-id="cfbab-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="cfbab-147">È inoltre consigliabile eseguire il Service Pack più recente.</span><span class="sxs-lookup"><span data-stu-id="cfbab-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="cfbab-148">Per ulteriori informazioni sul mirroring SQL, vedere [back end server high availability in Lync server 2013](lync-server-2013-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="cfbab-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="cfbab-149">Per informazioni dettagliate su come distribuire il clustering SQL, vedere [Configure SQL Server clustering for Lync server 2013](lync-server-2013-configure-sql-server-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="cfbab-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="cfbab-150">Per ulteriori informazioni e procedure consigliate per il clustering di failover in SQL Server <https://technet.microsoft.com/library/hh231721.aspx>2012, vedere.</span><span class="sxs-lookup"><span data-stu-id="cfbab-150">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="cfbab-151">Per il clustering di failover in SQL Server 2008 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>, vedere.</span><span class="sxs-lookup"><span data-stu-id="cfbab-151">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

