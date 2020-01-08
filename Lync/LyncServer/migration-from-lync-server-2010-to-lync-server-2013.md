---
title: Migrazione da Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="a5b93-102">Migrazione da Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5b93-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b93-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a5b93-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a5b93-104">Negli argomenti di questa sezione viene illustrata la procedura di migrazione da Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5b93-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a5b93-105">Questo documento descrive i passaggi in genere necessari per completare ogni fase della migrazione.</span><span class="sxs-lookup"><span data-stu-id="a5b93-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="a5b93-106">Non affronta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione.</span><span class="sxs-lookup"><span data-stu-id="a5b93-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="a5b93-107">Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a5b93-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="a5b93-108">Questo documento offre anche esempi di passaggi di verifica.</span><span class="sxs-lookup"><span data-stu-id="a5b93-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="a5b93-109">Questi passaggi di verifica vengono forniti per aiutarti a capire cosa è necessario cercare per verificare che ogni fase venga completata correttamente durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="a5b93-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="a5b93-110">Adattare questi passaggi di verifica al processo di migrazione specifico.</span><span class="sxs-lookup"><span data-stu-id="a5b93-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="a5b93-111">Questa guida fornisce informazioni specifiche per l'aggiornamento della distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="a5b93-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="a5b93-112">Non spiega come cambiare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="a5b93-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="a5b93-113">Questa guida non riguarda l'implementazione delle nuove caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="a5b93-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="a5b93-114">Quando una procedura dettagliata è documentata in un'altra posizione, questa guida indica la sezione documento o documento appropriata.</span><span class="sxs-lookup"><span data-stu-id="a5b93-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="a5b93-115">Questo documento definisce i termini specificati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="a5b93-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="a5b93-116">*migrazione*</span><span class="sxs-lookup"><span data-stu-id="a5b93-116">*migration*</span></span>  
    <span data-ttu-id="a5b93-117">Spostamento della distribuzione della produzione da una versione precedente di Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5b93-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="a5b93-118">*aggiornamento*</span><span class="sxs-lookup"><span data-stu-id="a5b93-118">*upgrade*</span></span>  
    <span data-ttu-id="a5b93-119">Installazione di una versione più recente del software in un server o un computer client.</span><span class="sxs-lookup"><span data-stu-id="a5b93-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="a5b93-120">*coesistenza*</span><span class="sxs-lookup"><span data-stu-id="a5b93-120">*coexistence*</span></span>  
    <span data-ttu-id="a5b93-121">Ambiente temporaneo che esiste durante la migrazione quando alcune funzionalità sono state migrate in Lync Server 2013 e altre funzionalità restano ancora in una versione precedente di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a5b93-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="a5b93-122">*interoperabilità*</span><span class="sxs-lookup"><span data-stu-id="a5b93-122">*interoperability*</span></span>  
    <span data-ttu-id="a5b93-123">La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="a5b93-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5b93-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a5b93-124">In This Section</span></span>

  - [<span data-ttu-id="a5b93-125">Operazioni preliminari alla migrazione</span><span class="sxs-lookup"><span data-stu-id="a5b93-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="a5b93-126">Fase 1: pianificare la migrazione da Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a5b93-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="a5b93-127">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="a5b93-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="a5b93-128">Fase 3: distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="a5b93-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="a5b93-129">Fase 4: trasferire gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="a5b93-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="a5b93-130">Fase 5: aggiungere Lync Server 2013 Edge Server al pool pilota</span><span class="sxs-lookup"><span data-stu-id="a5b93-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="a5b93-131">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="a5b93-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="a5b93-132">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="a5b93-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="a5b93-133">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="a5b93-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

