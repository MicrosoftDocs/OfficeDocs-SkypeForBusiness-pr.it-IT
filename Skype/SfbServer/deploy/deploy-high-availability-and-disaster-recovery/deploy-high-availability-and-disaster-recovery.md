---
title: Distribuire disponibilità elevata e ripristino di emergenza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL.
ms.openlocfilehash: 68baae183ff45571e38e922035d287e733bcc930
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830616"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="a5c4c-103">Distribuire disponibilità elevata e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="a5c4c-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="a5c4c-104">Skype for Business Server offre disponibilità elevata con pool di server, ripristino di emergenza con l'abbinamento del pool e diverse modalità di disponibilità elevata del server back-end, inclusi i gruppi di disponibilità AlwaysOn, il mirroring del database e il clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="a5c4c-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="a5c4c-105">La disponibilità elevata si riferisce al fare in modo che i servizi di Skype for Business Server siano disponibili anche se uno o più server sono inattivi. Il ripristino di emergenza si riferisce alla conservazione dei servizi in caso di emergenza naturale o causata da un ambiente umano e alla conservazione del maggior quantità possibile di dati prima del verificarsi del disastro.</span><span class="sxs-lookup"><span data-stu-id="a5c4c-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="a5c4c-106">In questa sezione viene descritto come distribuire queste funzionalità e vengono illustrati i passaggi che è possibile eseguire per la disponibilità elevata e il ripristino di emergenza per alcuni degli altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="a5c4c-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="a5c4c-107">Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c4c-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5c4c-108">I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c4c-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="a5c4c-109">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a5c4c-109">Related sections</span></span>

[<span data-ttu-id="a5c4c-110">Pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5c4c-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="a5c4c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5c4c-111">See also</span></span>

[<span data-ttu-id="a5c4c-112">Distribuire un gruppo di disponibilità AlwaysOn su un server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5c4c-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="a5c4c-113">Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a5c4c-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="a5c4c-114">Distribuire il mirroring di SQL per la disponibilità elevata del server back-end in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a5c4c-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
