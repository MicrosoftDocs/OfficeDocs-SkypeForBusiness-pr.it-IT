---
title: Distribuire disponibilità elevata e ripristino di emergenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790124"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a><span data-ttu-id="4b6c2-103">Distribuire disponibilità elevata e ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="4b6c2-103">Deploy high availability and disaster recovery</span></span>
 
<span data-ttu-id="4b6c2-104">Skype for Business Server offre una disponibilità elevata con il pooling dei server, il ripristino di emergenza con l'associazione di pool e diverse modalità di disponibilità elevata del server back-end, inclusi gruppi di disponibilità AlwaysOn, mirroring del database e clustering di failover SQL.</span><span class="sxs-lookup"><span data-stu-id="4b6c2-104">Skype for Business Server offers high availability with server pooling, disaster recovery with pool pairing, and several modes of Back End Server high availability, including AlwaysOn Availability groups, database mirroring, and SQL failover clustering.</span></span> 
  
<span data-ttu-id="4b6c2-105">L'elevata disponibilità fa riferimento a garantire che i servizi di Skype for Business Server siano disponibili anche se uno o più server vengono abbattuti. Il ripristino di emergenza si riferisce a mantenere i servizi in corso in caso di un disastro naturale o causato dall'uomo e a preservare il maggior quantità possibile di dati prima del disastro.</span><span class="sxs-lookup"><span data-stu-id="4b6c2-105">High availability refers to making sure that Skype for Business Server services are available even if one or more servers goes down.Disaster recovery refers to keeping services going in the event of a natural or human-caused disaster, and preserving as much data from before the disaster as possible.</span></span>
  
<span data-ttu-id="4b6c2-106">Questa sezione spiega come distribuire queste funzionalità e copre anche i passaggi che è possibile eseguire per l'elevata disponibilità e il ripristino di emergenza per alcuni altri ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="4b6c2-106">This section tells how to deploy these features, and also covers what steps you can take for high availability and disaster recovery for some of your other server roles.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6c2-107">Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4b6c2-107">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4b6c2-108">I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4b6c2-108">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="4b6c2-109">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4b6c2-109">Related sections</span></span>

[<span data-ttu-id="4b6c2-110">Pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b6c2-110">Plan for high availability and disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a><span data-ttu-id="4b6c2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6c2-111">See also</span></span>

[<span data-ttu-id="4b6c2-112">Distribuire un gruppo di disponibilità AlwaysOn in un server back-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b6c2-112">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server</span></span>](alwayson-availability-group.md)

[<span data-ttu-id="4b6c2-113">Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4b6c2-113">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>](front-end-pools-for-disaster-recovery.md)
  
[<span data-ttu-id="4b6c2-114">Distribuire il mirroring SQL per l'elevata disponibilità del server back-end in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4b6c2-114">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](sql-mirroring-for-high-availability.md)
  
