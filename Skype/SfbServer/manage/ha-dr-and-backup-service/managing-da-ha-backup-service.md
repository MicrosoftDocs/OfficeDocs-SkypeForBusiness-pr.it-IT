---
title: Gestire il ripristino di emergenza, la disponibilità elevata e il servizio di backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informazioni sulle procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front-End associati.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195532"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="3ba44-103">Gestire il ripristino di emergenza di Skype for Business Server, la disponibilità elevata e il servizio di backup</span><span class="sxs-lookup"><span data-stu-id="3ba44-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="3ba44-104">Questa sezione contiene le procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front-End associati.</span><span class="sxs-lookup"><span data-stu-id="3ba44-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="3ba44-105">Le procedure di ripristino di emergenza, sia failover che failback, sono manuali.</span><span class="sxs-lookup"><span data-stu-id="3ba44-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="3ba44-106">In caso di emergenza, l'amministratore deve richiamare manualmente le procedure di failover.</span><span class="sxs-lookup"><span data-stu-id="3ba44-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="3ba44-107">Lo stesso vale per il failback dopo la riparazione del pool.</span><span class="sxs-lookup"><span data-stu-id="3ba44-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="3ba44-108">Le procedure di ripristino di emergenza in questa sezione presuppongono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3ba44-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="3ba44-109">Si dispone di una distribuzione con pool Front-End associati, che si trova in siti diversi, come descritto in [pianificare l'elevata disponibilità e il ripristino di emergenza](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="3ba44-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="3ba44-110">Il servizio di backup è stato eseguito in questi pool associati per mantenerli sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="3ba44-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="3ba44-111">Se l'archivio di gestione centrale è ospitato in un pool, viene installato ed eseguito in entrambi i pool associati, con uno di questi pool che ospitano l'Active master e l'altro pool che ospita la modalità standby.</span><span class="sxs-lookup"><span data-stu-id="3ba44-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ba44-112">Nelle procedure seguenti il parametro *PoolFqdn* si riferisce al nome di dominio completo del pool interessato da Disaster, non al pool in cui vengono reindirizzati gli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="3ba44-112">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="3ba44-113">Per lo stesso set di utenti interessati, si riferisce allo stesso pool sia in cmdlet di failover che di failback, ovvero il pool che ha prima ospitato gli utenti prima del failover.</span><span class="sxs-lookup"><span data-stu-id="3ba44-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="3ba44-114">Ad esempio, supponiamo che un caso in cui tutti gli utenti ospitati in un pool P1 non siano stati rilevati nel pool di backup, P2.</span><span class="sxs-lookup"><span data-stu-id="3ba44-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="3ba44-115">Se l'amministratore vuole trasferire tutti gli utenti attualmente serviti da P2 per essere serviti da P1, l'amministratore deve eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ba44-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="3ba44-116">Non eseguire il backup di tutti gli utenti originariamente assegnati a P1 da P2 a P1 usando il cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="3ba44-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="3ba44-117">In questo caso, *PoolFqdn* è il nome di dominio completo di P1.</span><span class="sxs-lookup"><span data-stu-id="3ba44-117">In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ba44-118">Non eseguire il failover di tutti gli utenti originariamente ospitati in P2 in P1 usando il cmdlet per l'uso del protocollo.</span><span class="sxs-lookup"><span data-stu-id="3ba44-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="3ba44-119">In questo caso, PoolFQDN è il nome di dominio completo di P2's.</span><span class="sxs-lookup"><span data-stu-id="3ba44-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ba44-120">Se l'amministratore vuole in seguito riuscire a restituire gli utenti P2 a P2, PoolFQDN è il nome di dominio completo di P2's.</span><span class="sxs-lookup"><span data-stu-id="3ba44-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="3ba44-121">Tieni presente che il passaggio 1 deve essere eseguito prima del passaggio 2 per mantenere l'integrità del pool.</span><span class="sxs-lookup"><span data-stu-id="3ba44-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="3ba44-122">Se si prova il passaggio 2 prima del passaggio 1, il cmdlet Step 2 non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="3ba44-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="3ba44-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ba44-123">See Also</span></span>

[<span data-ttu-id="3ba44-124">Pianificare l'elevata disponibilità e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="3ba44-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
