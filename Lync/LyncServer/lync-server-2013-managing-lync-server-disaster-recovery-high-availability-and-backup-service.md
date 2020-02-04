---
title: Gestione del ripristino di emergenza di Lync Server, disponibilità elevata e servizio di backup
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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="9220d-102">Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9220d-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="9220d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="9220d-104">Questa sezione contiene le procedure per le operazioni di ripristino di emergenza e per il mantenimento del servizio di backup che sincronizza i dati in pool Front-End associati.</span><span class="sxs-lookup"><span data-stu-id="9220d-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="9220d-105">Le procedure di ripristino di emergenza, sia failover che failback, sono manuali.</span><span class="sxs-lookup"><span data-stu-id="9220d-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="9220d-106">In caso di emergenza, l'amministratore deve richiamare manualmente le procedure di failover.</span><span class="sxs-lookup"><span data-stu-id="9220d-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="9220d-107">Lo stesso vale per il failback dopo la riparazione del pool.</span><span class="sxs-lookup"><span data-stu-id="9220d-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="9220d-108">Le procedure di ripristino di emergenza nella parte restante di questa sezione presuppongono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9220d-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="9220d-109">Si dispone di una distribuzione con pool Front-End associati, che si trova in siti diversi, come descritto in [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9220d-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="9220d-110">Il servizio di backup è stato eseguito in questi pool associati per mantenerli sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="9220d-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="9220d-111">Se l'archivio di gestione centrale è ospitato in un pool, viene installato ed eseguito in entrambi i pool associati, con uno di questi pool che ospitano l'Active master e l'altro pool che ospita la modalità standby.</span><span class="sxs-lookup"><span data-stu-id="9220d-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9220d-112">Nelle procedure seguenti il parametro <EM>PoolFqdn</EM> si riferisce al nome di dominio completo del pool interessato da Disaster, non al pool in cui vengono reindirizzati gli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="9220d-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="9220d-113">Per lo stesso set di utenti interessati, si riferisce allo stesso pool sia in cmdlet di failover che di failback, ovvero il pool che ha prima ospitato gli utenti prima del failover.</span><span class="sxs-lookup"><span data-stu-id="9220d-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="9220d-114">Ad esempio, supponiamo che un caso in cui tutti gli utenti ospitati in un pool P1 non siano stati rilevati nel pool di backup, P2.</span><span class="sxs-lookup"><span data-stu-id="9220d-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="9220d-115">Se l'amministratore vuole trasferire tutti gli utenti attualmente serviti da P2 per essere serviti da P1, l'amministratore deve eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9220d-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="9220d-116">Non eseguire il backup di tutti gli utenti originariamente assegnati a P1 da P2 a P1 usando il cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="9220d-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="9220d-117">In questo caso, <EM>PoolFqdn</EM> è il nome di dominio completo di P1.</span><span class="sxs-lookup"><span data-stu-id="9220d-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="9220d-118">Non eseguire il failover di tutti gli utenti originariamente ospitati in P2 in P1 usando il cmdlet per l'uso del protocollo.</span><span class="sxs-lookup"><span data-stu-id="9220d-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="9220d-119">In questo caso, <EM>PoolFqdn</EM> è il nome di dominio completo di P2's.</span><span class="sxs-lookup"><span data-stu-id="9220d-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="9220d-120">Se l'amministratore vuole in seguito riuscire a restituire gli utenti P2 a P2, <EM>PoolFqdn</EM> è il nome di dominio completo di P2's.</span><span class="sxs-lookup"><span data-stu-id="9220d-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="9220d-121">Tieni presente che il passaggio 1 deve essere eseguito prima del passaggio 2 per mantenere l'integrità del pool.</span><span class="sxs-lookup"><span data-stu-id="9220d-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="9220d-122">Se si prova il passaggio 2 prima del passaggio 1, il cmdlet Step 2 non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="9220d-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9220d-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9220d-123">In This Section</span></span>

  - [<span data-ttu-id="9220d-124">Configurazione e monitoraggio del servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="9220d-125">Failover di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="9220d-126">Failback di un pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="9220d-127">Failover di un database con mirroring in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="9220d-128">Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="9220d-129">Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="9220d-130">Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="9220d-131">Modifica del pool di server perimetrali associato a un pool Front End in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="9220d-132">Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9220d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9220d-133">See Also</span></span>


[<span data-ttu-id="9220d-134">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9220d-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

