---
title: Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni sulle procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front End abbinati.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817156"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="a2b9b-103">Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a2b9b-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="a2b9b-104">In questa sezione sono incluse le procedure per le operazioni di ripristino di emergenza, nonché per la gestione del servizio di backup, che sincronizza i dati in pool Front End abbinati.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="a2b9b-p101">Le procedure di ripristino di emergenza, sia di failover che di failback, sono manuali. In caso di emergenza, è necessario che l'amministratore richiami manualmente le procedure di failover. La stessa procedura si applica al failback dopo che il pool è stato ripristinato.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="a2b9b-108">Le procedure per il ripristino di emergenza in questa sezione presuppongono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a2b9b-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="a2b9b-109">Si dispone di una distribuzione con pool Front End associati, che si trova in siti diversi, come descritto in [pianificare la disponibilità elevata e il ripristino di emergenza](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a2b9b-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="a2b9b-110">Il servizio di backup è stato eseguito nei pool abbinati per mantenerli sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="a2b9b-111">Se l'archivio di gestione centrale è ospitato in un pool, è installato e in esecuzione su entrambi i pool associati, con uno dei pool che ospitano il master attivo e l'altro pool che ospita la modalità standby.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2b9b-p103">Nelle procedure seguenti il parametro *PoolFQDN* si riferisce al nome di dominio completo (FQDN) del pool interessato dall'emergenza, non al pool da cui gli utenti interessati dal problema vengono reindirizzati. Per lo stesso gruppo di utenti interessati dal problema, si riferisce allo stesso pool nei cmdlet di failover e failback (il pool che ospitava gli utenti prima del failover).</span><span class="sxs-lookup"><span data-stu-id="a2b9b-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="a2b9b-p104">Si supponga ad esempio un caso in cui per tutti gli utenti ospitati in un pool P1 sia stato eseguito il failover nel pool di backup, P2. Se l'amministratore desidera spostare tutti gli utenti serviti da P2 in modo che siano serviti da P1, è necessario che esegua le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2b9b-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="a2b9b-p105">Eseguire il failback di tutti gli utenti originariamente ospitati in P1 da P2 a P1 utilizzando il cmdlet di failback. In tal caso, *PoolFQDN* è il nome di dominio completo (FQDN) di P1.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="a2b9b-118">Eseguire il failover di tutti gli utenti originariamente ospitati in P2 a P1 utilizzando il cmdlet di failover.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="a2b9b-119">In tal caso, PoolFQDN è il nome di dominio completo (FQDN) di P2.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="a2b9b-120">Se successivamente l'amministratore desidera eseguire il failback degli utenti P2 a P2, PoolFQDN è il nome di dominio completo (FQDN) di P2.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="a2b9b-p107">Per preservare l'integrità del pool, è necessario eseguire la procedura 1 prima della procedura 2. Se si esegue la procedura 2 prima della procedura 1, il cmdlet della procedura 2 avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="a2b9b-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="a2b9b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2b9b-123">See Also</span></span>

[<span data-ttu-id="a2b9b-124">Pianificare la disponibilità elevata e il ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="a2b9b-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
