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
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="0f8ce-102">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="0f8ce-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f8ce-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="0f8ce-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="0f8ce-104">In Lync Server 2013, è possibile definire i siti della rete che contengono componenti di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="0f8ce-105">Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="0f8ce-106">Un *pool Front End* è un gruppo di Front End Server configurati in modo identico che collaborano per offrire servizi a un gruppo comune di utenti.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="0f8ce-107">Un pool garantisce scalabilità e funzionalità di failover per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="0f8ce-108">Ogni server in un pool deve eseguire uno o più ruoli del server identici.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="0f8ce-109">Un server Standard Edition, disegnato per organizzazioni di piccole dimensioni, definisce anche un pool e viene eseguito su un server singolo.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="0f8ce-110">In questo modo è possibile disporre di una funzionalità di Lync Server 2013 per un costo minore, ma non fornisce una vera soluzione a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="0f8ce-111">Nelle fasi seguenti viene descritto il processo di migrazione del pool da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="0f8ce-112">Nel caso di più siti che includono più pool, per ogni singolo pool sarà necessario adottare questo approccio in più fasi.</span><span class="sxs-lookup"><span data-stu-id="0f8ce-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="0f8ce-113">Fase 1: pianificare la migrazione da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0f8ce-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="0f8ce-114">Fase 2: preparazione per la migrazione</span><span class="sxs-lookup"><span data-stu-id="0f8ce-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="0f8ce-115">Fase 3: distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f8ce-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="0f8ce-116">Fase 4: spostare gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="0f8ce-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="0f8ce-117">Fase 5: aggiungere il server perimetrale di Lync Server 2013 al pool pilota</span><span class="sxs-lookup"><span data-stu-id="0f8ce-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="0f8ce-118">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="0f8ce-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="0f8ce-119">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="0f8ce-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="0f8ce-120">Fase 8: rimuovere i pool legacy</span><span class="sxs-lookup"><span data-stu-id="0f8ce-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

