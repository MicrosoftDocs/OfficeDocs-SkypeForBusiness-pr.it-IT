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
ms.openlocfilehash: e32d43e8052de454647cd9f69b4572d178a0cecb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="0d520-102">Migrazione da Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d520-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d520-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0d520-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0d520-104">Gli argomenti di questa sezione illustrano il processo di migrazione da Office Communications Server 2007 R2 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d520-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d520-105">Questo documento descrive i passaggi in genere necessari per completare ogni fase della migrazione.</span><span class="sxs-lookup"><span data-stu-id="0d520-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="0d520-106">Non affronta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione.</span><span class="sxs-lookup"><span data-stu-id="0d520-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="0d520-107">Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0d520-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="0d520-108">Questo documento offre anche esempi di passaggi di verifica.</span><span class="sxs-lookup"><span data-stu-id="0d520-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="0d520-109">Questi passaggi di verifica vengono forniti per aiutarti a capire cosa è necessario cercare per verificare che ogni fase venga completata correttamente durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="0d520-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="0d520-110">Adattare questi passaggi di verifica al processo di migrazione specifico.</span><span class="sxs-lookup"><span data-stu-id="0d520-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="0d520-111">Questa guida fornisce informazioni specifiche per l'aggiornamento della distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="0d520-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="0d520-112">Non spiega come cambiare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="0d520-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="0d520-113">Questa guida non riguarda l'implementazione delle nuove caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="0d520-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="0d520-114">Quando una procedura dettagliata è documentata in un'altra posizione, questa guida indica la sezione documento o documento appropriata.</span><span class="sxs-lookup"><span data-stu-id="0d520-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="0d520-115">Questo documento definisce i termini specificati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="0d520-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="0d520-116">*migrazione*</span><span class="sxs-lookup"><span data-stu-id="0d520-116">*migration*</span></span>  
    <span data-ttu-id="0d520-117">Spostamento della distribuzione della produzione da una versione precedente di Office Communications Server 2007 R2 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d520-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="0d520-118">*aggiornamento*</span><span class="sxs-lookup"><span data-stu-id="0d520-118">*upgrade*</span></span>  
    <span data-ttu-id="0d520-119">Installazione di una versione più recente del software in un server o un computer client.</span><span class="sxs-lookup"><span data-stu-id="0d520-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="0d520-120">*coesistenza*</span><span class="sxs-lookup"><span data-stu-id="0d520-120">*coexistence*</span></span>  
    <span data-ttu-id="0d520-121">Ambiente temporaneo che esiste durante la migrazione quando alcune funzionalità sono state migrate in Lync Server 2013 e altre funzionalità restano ancora in una versione precedente di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0d520-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="0d520-122">*interoperabilità*</span><span class="sxs-lookup"><span data-stu-id="0d520-122">*interoperability*</span></span>  
    <span data-ttu-id="0d520-123">La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="0d520-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d520-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0d520-124">In This Section</span></span>

  - [<span data-ttu-id="0d520-125">Operazioni preliminari alla migrazione</span><span class="sxs-lookup"><span data-stu-id="0d520-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="0d520-126">Fasi della migrazione</span><span class="sxs-lookup"><span data-stu-id="0d520-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="0d520-127">Fase 1: pianificare la migrazione da Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0d520-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="0d520-128">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="0d520-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="0d520-129">Fase 3: distribuire Lync Server 2013 Pilot pool</span><span class="sxs-lookup"><span data-stu-id="0d520-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="0d520-130">Fase 4: unire le topologie</span><span class="sxs-lookup"><span data-stu-id="0d520-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="0d520-131">Fase 5: configurare il pool di Pilot</span><span class="sxs-lookup"><span data-stu-id="0d520-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="0d520-132">Fase 6: trasferire gli utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="0d520-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="0d520-133">Fase 7: aggiungere Lync Server 2013 Edge Server al pool pilota</span><span class="sxs-lookup"><span data-stu-id="0d520-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="0d520-134">Fase 8: passaggio dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="0d520-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="0d520-135">Fase 9: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="0d520-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="0d520-136">Fase 10: sito legacy decommission</span><span class="sxs-lookup"><span data-stu-id="0d520-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

