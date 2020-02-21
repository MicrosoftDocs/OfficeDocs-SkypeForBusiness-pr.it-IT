---
title: Migrazione da Office Communications Server 2007 R2 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344f15589e113a54b539d351ed8d4745e1fd3a5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="abfa5-102">Migrazione da Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abfa5-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abfa5-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="abfa5-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="abfa5-104">Negli argomenti di questa sezione viene illustrato il processo di migrazione da Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abfa5-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="abfa5-p101">Questo documento descrive i passaggi normalmente necessari per eseguire ogni fase della migrazione. Non sono descritti tutti gli scenari di migrazione o tutte le topologie di distribuzione legacy possibili. Per questi motivi, potrebbe non essere necessario eseguire tutti i passaggi descritti oppure potrebbero servirne altri, a seconda della distribuzione. Nel documento sono inoltre disponibili alcuni esempi dei passaggi di verifica, forniti allo scopo di illustrare quali aspetti ed elementi considerare per assicurarsi che ogni fase venga completata correttamente, man mano che si procede nella migrazione. Adattare tali passaggi di verifica allo specifico processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="abfa5-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="abfa5-p102">Questa guida include informazioni specifiche per l'aggiornamento della distribuzione esistente e non spiega come modificare la topologia esistente. Non viene descritta l'implementazione delle nuove caratteristiche. Se una procedura dettagliata è descritta altrove, in questa guida vengono forniti riferimenti al documento o alla sezione del documento appropriato.</span><span class="sxs-lookup"><span data-stu-id="abfa5-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="abfa5-115">Nel documento vengono utilizzati termini specifici, con le definizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="abfa5-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="abfa5-116">*migrazione*</span><span class="sxs-lookup"><span data-stu-id="abfa5-116">*migration*</span></span>  
    <span data-ttu-id="abfa5-117">Spostamento della distribuzione di produzione da una versione precedente di Office Communications Server 2007 R2 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="abfa5-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="abfa5-118">*aggiornamento*</span><span class="sxs-lookup"><span data-stu-id="abfa5-118">*upgrade*</span></span>  
    <span data-ttu-id="abfa5-119">Installare una versione più recente del software in un computer server o client.</span><span class="sxs-lookup"><span data-stu-id="abfa5-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="abfa5-120">*coesistenza*</span><span class="sxs-lookup"><span data-stu-id="abfa5-120">*coexistence*</span></span>  
    <span data-ttu-id="abfa5-121">Ambiente temporaneo esistente durante la migrazione, quando è stata eseguita la migrazione di alcune funzionalità a Lync Server 2013 e altre funzionalità rimangono ancora in una versione precedente di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="abfa5-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="abfa5-122">*interoperabilità*</span><span class="sxs-lookup"><span data-stu-id="abfa5-122">*interoperability*</span></span>  
    <span data-ttu-id="abfa5-123">Capacità della distribuzione di operare in modo corretto durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="abfa5-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abfa5-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="abfa5-124">In This Section</span></span>

  - [<span data-ttu-id="abfa5-125">Prima di iniziare la migrazione</span><span class="sxs-lookup"><span data-stu-id="abfa5-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="abfa5-126">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="abfa5-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="abfa5-127">Fase 1: pianificare la migrazione da Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="abfa5-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="abfa5-128">Fase 2: preparazione per la migrazione</span><span class="sxs-lookup"><span data-stu-id="abfa5-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="abfa5-129">Fase 3: distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abfa5-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="abfa5-130">Fase 4: unire le topologie</span><span class="sxs-lookup"><span data-stu-id="abfa5-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="abfa5-131">Fase 5: configurare il pool pilota</span><span class="sxs-lookup"><span data-stu-id="abfa5-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="abfa5-132">Fase 6: spostare gli utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="abfa5-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="abfa5-133">Fase 7: aggiungere il server perimetrale di Lync Server 2013 al pool pilota</span><span class="sxs-lookup"><span data-stu-id="abfa5-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="abfa5-134">Fase 8: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="abfa5-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="abfa5-135">Fase 9: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="abfa5-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="abfa5-136">Fase 10: rimuovere il sito legacy</span><span class="sxs-lookup"><span data-stu-id="abfa5-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

