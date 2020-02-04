---
title: Fasi della migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="f87c1-102">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="f87c1-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f87c1-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f87c1-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f87c1-104">In Lync Server 2013 si definiscono i siti della rete che contengono componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f87c1-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="f87c1-105">Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="f87c1-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="f87c1-106">Un *pool Front-End* è un set di server front-end configurati in modo identico e collaborano per creare servizi per un gruppo di utenti comune.</span><span class="sxs-lookup"><span data-stu-id="f87c1-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="f87c1-107">Un pool offre funzionalità di scalabilità e failover per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f87c1-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="f87c1-108">Ogni server in un pool deve eseguire un ruolo o ruoli del server identico.</span><span class="sxs-lookup"><span data-stu-id="f87c1-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="f87c1-109">Un server Standard Edition, progettato per le piccole organizzazioni, definisce anche un pool ed è in esecuzione su un singolo server.</span><span class="sxs-lookup"><span data-stu-id="f87c1-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="f87c1-110">In questo modo è possibile avere la funzionalità Lync Server 2013 per un costo inferiore, ma non offre una vera soluzione a elevata disponibilità.</span><span class="sxs-lookup"><span data-stu-id="f87c1-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="f87c1-111">Le fasi seguenti descrivono il processo di migrazione del pool da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f87c1-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="f87c1-112">Per più siti che contengono più pool, ogni singolo pool deve seguire questo approccio graduale.</span><span class="sxs-lookup"><span data-stu-id="f87c1-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="f87c1-113">Fase 1: pianificare la migrazione da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f87c1-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="f87c1-114">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="f87c1-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="f87c1-115">Fase 3: distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="f87c1-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="f87c1-116">Fase 4: trasferire gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="f87c1-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="f87c1-117">Fase 5: aggiungere Lync Server 2013 Edge Server al pool pilota</span><span class="sxs-lookup"><span data-stu-id="f87c1-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="f87c1-118">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="f87c1-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="f87c1-119">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="f87c1-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="f87c1-120">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="f87c1-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

