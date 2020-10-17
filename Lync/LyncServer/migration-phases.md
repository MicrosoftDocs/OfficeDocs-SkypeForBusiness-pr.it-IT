---
title: Fasi della migrazione
description: Fasi di migrazione.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547052"
---
# <a name="migration-phases"></a><span data-ttu-id="e785e-103">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="e785e-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e785e-104">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e785e-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e785e-105">In Lync Server 2013, è possibile definire i siti della rete che contengono componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e785e-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="e785e-106">Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="e785e-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="e785e-107">Un *pool Front End* è un gruppo di Front End Server configurati in modo identico che collaborano per offrire servizi a un gruppo comune di utenti.</span><span class="sxs-lookup"><span data-stu-id="e785e-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="e785e-108">Un pool garantisce scalabilità e funzionalità di failover per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e785e-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="e785e-109">Ogni server in un pool deve eseguire uno o più ruoli del server identici.</span><span class="sxs-lookup"><span data-stu-id="e785e-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="e785e-110">Un server Standard Edition, disegnato per organizzazioni di piccole dimensioni, definisce anche un pool e viene eseguito su un server singolo.</span><span class="sxs-lookup"><span data-stu-id="e785e-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="e785e-111">In questo modo è possibile disporre di una funzionalità di Lync Server 2013 per un costo minore, ma non fornisce una vera soluzione a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="e785e-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="e785e-112">Nelle fasi seguenti viene descritto il processo di migrazione del pool da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e785e-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="e785e-113">Nel caso di più siti che includono più pool, per ogni singolo pool sarà necessario adottare questo approccio in più fasi.</span><span class="sxs-lookup"><span data-stu-id="e785e-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="e785e-114">Fase 1: pianificare la migrazione da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e785e-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="e785e-115">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="e785e-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="e785e-116">Fase 3: distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e785e-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="e785e-117">Fase 4: spostare gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="e785e-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="e785e-118">Fase 5: aggiungere il server perimetrale di Lync Server 2013 al pool pilota</span><span class="sxs-lookup"><span data-stu-id="e785e-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="e785e-119">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="e785e-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="e785e-120">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="e785e-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="e785e-121">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="e785e-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

