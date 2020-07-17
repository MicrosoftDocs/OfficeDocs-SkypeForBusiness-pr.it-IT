---
title: Fasi della migrazione
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server 2019, è possibile definire i siti della rete che contengono i componenti di Skype for Business Server 2019. Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752628"
---
# <a name="migration-phases"></a><span data-ttu-id="cb28a-104">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="cb28a-104">Migration phases</span></span>

<span data-ttu-id="cb28a-105">In Skype for Business Server 2019, è possibile definire i siti della rete che contengono i componenti di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb28a-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="cb28a-106">Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="cb28a-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="cb28a-107">Un pool Front End è un gruppo di Front End Server configurati in modo identico che collaborano per offrire servizi a un gruppo comune di utenti.</span><span class="sxs-lookup"><span data-stu-id="cb28a-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="cb28a-108">Un pool garantisce scalabilità e funzionalità di failover per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cb28a-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="cb28a-109">Ogni server in un pool deve eseguire uno o più ruoli del server identici.</span><span class="sxs-lookup"><span data-stu-id="cb28a-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="cb28a-110">Un server Standard Edition, disegnato per organizzazioni di piccole dimensioni, definisce anche un pool e viene eseguito su un server singolo.</span><span class="sxs-lookup"><span data-stu-id="cb28a-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="cb28a-111">In questo modo è possibile utilizzare le funzionalità di Skype for Business Server 2019 per un costo minore, ma non fornisce una vera soluzione a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="cb28a-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="cb28a-112">Nelle fasi seguenti viene descritto il processo di migrazione del pool a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb28a-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="cb28a-113">Nel caso di più siti che includono più pool, per ogni singolo pool sarà necessario adottare questo approccio in più fasi.</span><span class="sxs-lookup"><span data-stu-id="cb28a-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="cb28a-114">Fase 1: pianificare la migrazione</span><span class="sxs-lookup"><span data-stu-id="cb28a-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="cb28a-115">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="cb28a-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="cb28a-116">Fase 3: distribuire il pool pilota di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cb28a-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="cb28a-117">Fase 4: spostare gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="cb28a-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="cb28a-118">Fase 5: aggiungere il server perimetrale Skype for Business Server 2019 al pool pilota</span><span class="sxs-lookup"><span data-stu-id="cb28a-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="cb28a-119">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="cb28a-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="cb28a-120">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="cb28a-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="cb28a-121">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="cb28a-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

