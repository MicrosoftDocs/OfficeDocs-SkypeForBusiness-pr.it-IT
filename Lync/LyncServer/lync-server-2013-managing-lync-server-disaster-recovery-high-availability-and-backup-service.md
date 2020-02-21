---
title: Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c18076a2bbc34386872a7fbee92c26b8084598
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="29de4-102">Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29de4-103">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="29de4-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="29de4-104">In questa sezione sono incluse le procedure per le operazioni di ripristino di emergenza e per la gestione del servizio di backup che esegue la sincronizzazione dei dati nei pool Front End abbinati.</span><span class="sxs-lookup"><span data-stu-id="29de4-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="29de4-p101">Le procedure di ripristino di emergenza, sia di failover che di failback, sono manuali. In caso di emergenza, è necessario che l'amministratore richiami manualmente le procedure di failover. La stessa procedura si applica al failback dopo che il pool è stato ripristinato.</span><span class="sxs-lookup"><span data-stu-id="29de4-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="29de4-108">Per le procedure di ripristino di emergenza presenti nel resto della sezione vengono presupposti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29de4-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="29de4-109">Si dispone di una distribuzione con pool Front End associati, che si trovano in siti diversi, come descritto in [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="29de4-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="29de4-110">Il servizio di backup è stato eseguito nei pool abbinati per mantenerli sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="29de4-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="29de4-111">Se l'archivio di gestione centrale è ospitato in un pool, è installato e in esecuzione su entrambi i pool associati, con uno dei pool che ospitano il master attivo e l'altro pool che ospita la modalità standby.</span><span class="sxs-lookup"><span data-stu-id="29de4-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="29de4-p103">Nelle procedure seguenti il parametro <EM>PoolFQDN</EM> si riferisce al nome di dominio completo (FQDN) del pool interessato dall'emergenza, non al pool da cui gli utenti interessati dal problema vengono reindirizzati. Per lo stesso gruppo di utenti interessati dal problema, si riferisce allo stesso pool nei cmdlet di failover e failback (il pool che ospitava gli utenti prima del failover).</span><span class="sxs-lookup"><span data-stu-id="29de4-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="29de4-p104">Si supponga ad esempio un caso in cui per tutti gli utenti ospitati in un pool P1 sia stato eseguito il failover nel pool di backup, P2. Se l'amministratore desidera spostare tutti gli utenti serviti da P2 in modo che siano serviti da P1, è necessario che esegua le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="29de4-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="29de4-p105">Eseguire il failback di tutti gli utenti originariamente ospitati in P1 da P2 a P1 utilizzando il cmdlet di failback. In tal caso, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P1.</span><span class="sxs-lookup"><span data-stu-id="29de4-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="29de4-p106">Eseguire il failover di tutti gli utenti originariamente ospitati in P2 a P1 utilizzando il cmdlet di failover. In tal caso, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P2.</span><span class="sxs-lookup"><span data-stu-id="29de4-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="29de4-120">Se successivamente l'amministratore desidera eseguire il failback degli utenti P2 a P2, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P2.</span><span class="sxs-lookup"><span data-stu-id="29de4-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="29de4-121">Per preservare l'integrità del pool, è necessario eseguire la procedura 1 prima della procedura 2.</span><span class="sxs-lookup"><span data-stu-id="29de4-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="29de4-122">Se si esegue la procedura 2 prima della procedura 1, il cmdlet della procedura 2 avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="29de4-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29de4-123">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="29de4-123">In This Section</span></span>

  - [<span data-ttu-id="29de4-124">Configurazione e monitoraggio del servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="29de4-125">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="29de4-126">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="29de4-127">Failover di un database con mirroring in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="29de4-128">Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="29de4-129">Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="29de4-130">Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="29de4-131">Modifica del pool di server perimetrali associato a un pool Front end in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="29de4-132">Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29de4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29de4-133">See Also</span></span>


[<span data-ttu-id="29de4-134">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29de4-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

