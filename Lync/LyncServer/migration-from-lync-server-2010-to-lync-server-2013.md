---
title: Migrazione da Lync Server 2010 a Lync Server 2013
description: Migrazione da Lync Server 2010 a Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543202"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="26689-103">Migrazione da Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26689-103">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26689-104">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="26689-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="26689-105">Negli argomenti di questa sezione viene illustrato il processo di migrazione da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26689-105">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="26689-p101">Questo documento descrive i passaggi normalmente necessari per eseguire ogni fase della migrazione. Non sono descritti tutti gli scenari di migrazione o tutte le topologie di distribuzione legacy possibili. Per questi motivi, potrebbe non essere necessario eseguire tutti i passaggi descritti oppure potrebbero servirne altri, a seconda della distribuzione. Nel documento sono inoltre disponibili alcuni esempi dei passaggi di verifica, forniti allo scopo di illustrare quali aspetti ed elementi considerare per assicurarsi che ogni fase venga completata correttamente, man mano che si procede nella migrazione. Adattare tali passaggi di verifica allo specifico processo di migrazione.</span><span class="sxs-lookup"><span data-stu-id="26689-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="26689-p102">Questa guida include informazioni specifiche per l'aggiornamento della distribuzione esistente e non spiega come modificare la topologia esistente. Non viene descritta l'implementazione delle nuove caratteristiche. Se una procedura dettagliata è descritta altrove, in questa guida vengono forniti riferimenti al documento o alla sezione del documento appropriato.</span><span class="sxs-lookup"><span data-stu-id="26689-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="26689-116">Nel documento vengono utilizzati termini specifici, con le definizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="26689-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="26689-117">*migrazione*</span><span class="sxs-lookup"><span data-stu-id="26689-117">*migration*</span></span>  
    <span data-ttu-id="26689-118">Spostamento della distribuzione di produzione da una versione precedente di Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="26689-118">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="26689-119">*aggiornamento*</span><span class="sxs-lookup"><span data-stu-id="26689-119">*upgrade*</span></span>  
    <span data-ttu-id="26689-120">Installare una versione più recente del software in un computer server o client.</span><span class="sxs-lookup"><span data-stu-id="26689-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="26689-121">*coesistenza*</span><span class="sxs-lookup"><span data-stu-id="26689-121">*coexistence*</span></span>  
    <span data-ttu-id="26689-122">Ambiente temporaneo esistente durante la migrazione, quando è stata eseguita la migrazione di alcune funzionalità a Lync Server 2013 e altre funzionalità rimangono ancora in una versione precedente di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="26689-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="26689-123">*interoperabilità*</span><span class="sxs-lookup"><span data-stu-id="26689-123">*interoperability*</span></span>  
    <span data-ttu-id="26689-124">Capacità della distribuzione di operare in modo corretto durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="26689-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26689-125">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="26689-125">In This Section</span></span>

  - [<span data-ttu-id="26689-126">Operazioni preliminari alla migrazione</span><span class="sxs-lookup"><span data-stu-id="26689-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="26689-127">Fase 1: pianificare la migrazione da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="26689-127">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="26689-128">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="26689-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="26689-129">Fase 3: distribuire il pool pilota di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26689-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="26689-130">Fase 4: spostare gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="26689-130">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="26689-131">Fase 5: aggiungere il server perimetrale di Lync Server 2013 al pool pilota</span><span class="sxs-lookup"><span data-stu-id="26689-131">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="26689-132">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="26689-132">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="26689-133">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="26689-133">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="26689-134">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="26689-134">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

