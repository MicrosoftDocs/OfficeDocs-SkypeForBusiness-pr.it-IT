---
title: Fasi di migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype for Business Server 2019 si definiscono i siti della rete che contengono componenti di Skype for Business Server 2019. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195007"
---
# <a name="migration-phases"></a><span data-ttu-id="24188-104">Fasi di migrazione</span><span class="sxs-lookup"><span data-stu-id="24188-104">Migration phases</span></span>

<span data-ttu-id="24188-105">In Skype for Business Server 2019 si definiscono i siti della rete che contengono componenti di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24188-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="24188-106">Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="24188-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="24188-107">Un pool Front-End è un set di server front-end configurati in modo identico e collaborano per creare servizi per un gruppo di utenti comune.</span><span class="sxs-lookup"><span data-stu-id="24188-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="24188-108">Un pool offre funzionalità di scalabilità e failover per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="24188-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="24188-109">Ogni server in un pool deve eseguire un ruolo o ruoli del server identico.</span><span class="sxs-lookup"><span data-stu-id="24188-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="24188-110">Un server Standard Edition, progettato per le piccole organizzazioni, definisce anche un pool ed è in esecuzione su un singolo server.</span><span class="sxs-lookup"><span data-stu-id="24188-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="24188-111">In questo modo è possibile avere una funzionalità di Skype for Business Server 2019 per un costo minore, ma non offre una vera soluzione a elevata disponibilità.</span><span class="sxs-lookup"><span data-stu-id="24188-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="24188-112">Le fasi seguenti descrivono il processo di migrazione del pool a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="24188-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="24188-113">Per più siti che contengono più pool, ogni singolo pool deve seguire questo approccio graduale.</span><span class="sxs-lookup"><span data-stu-id="24188-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="24188-114">Fase 1: pianificare la migrazione</span><span class="sxs-lookup"><span data-stu-id="24188-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="24188-115">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="24188-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="24188-116">Fase 3: distribuire Skype for Business Server 2019 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="24188-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="24188-117">Fase 4: trasferire gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="24188-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="24188-118">Fase 5: aggiungere Skype for Business Server 2019 Edge Server al pool pilota</span><span class="sxs-lookup"><span data-stu-id="24188-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="24188-119">Fase 6: passaggio dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="24188-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="24188-120">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="24188-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="24188-121">Fase 8: rimuovere i pool legacy</span><span class="sxs-lookup"><span data-stu-id="24188-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

