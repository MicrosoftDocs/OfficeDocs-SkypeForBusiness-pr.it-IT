---
title: Migrazione a Skype for Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Gli argomenti di questa sezione illustrano il processo di migrazione a Skype for Business Server 2019.
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238087"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="e922f-103">Migrazione a Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e922f-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="e922f-104">Gli argomenti di questa sezione illustrano il processo di migrazione a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e922f-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="e922f-105">Questo articolo illustra la migrazione di Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e922f-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e922f-106">In tutto il contenuto viene usato il termine *legacy* per fare riferimento all'legacy Lync Server 2013 o Skype for business server 2015 che si sta eseguendo la migrazione a Skype for business server 2019.</span><span class="sxs-lookup"><span data-stu-id="e922f-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e922f-107">Questa guida descrive i passaggi in genere necessari per completare ogni fase della migrazione.</span><span class="sxs-lookup"><span data-stu-id="e922f-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="e922f-108">Non affronta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione.</span><span class="sxs-lookup"><span data-stu-id="e922f-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="e922f-109">Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e922f-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="e922f-110">Questa guida contiene anche esempi di passaggi di verifica.</span><span class="sxs-lookup"><span data-stu-id="e922f-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="e922f-111">Questi passaggi di verifica vengono forniti per aiutarti a capire cosa è necessario cercare per verificare che ogni fase venga completata correttamente durante la migrazione.</span><span class="sxs-lookup"><span data-stu-id="e922f-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="e922f-112">Adattare questi passaggi di verifica al processo di migrazione specifico.</span><span class="sxs-lookup"><span data-stu-id="e922f-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="e922f-113">Questa guida fornisce informazioni specifiche per l'aggiornamento della distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="e922f-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="e922f-114">Non spiega come cambiare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="e922f-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="e922f-115">Questa guida non riguarda l'implementazione delle nuove caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="e922f-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="e922f-116">Quando una procedura dettagliata è documentata altrove, questa guida indica la sezione articolo o articolo.</span><span class="sxs-lookup"><span data-stu-id="e922f-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="e922f-117">Questo articolo definisce i termini specificati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="e922f-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="e922f-118">**migrazione:** Spostamento della distribuzione della produzione da Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e922f-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="e922f-119">**coesistenza:** L'ambiente temporaneo che esiste durante la migrazione quando alcune funzionalità sono state migrate in Skype for Business Server 2019 e altre funzionalità restano ancora in una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e922f-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="e922f-120">**interoperabilità:** La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="e922f-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="e922f-121">**legacy:** Il sistema a cui si sta eseguendo la migrazione, ovvero Lync Server 2013 o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e922f-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="e922f-122">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e922f-122">In this section</span></span>

- [<span data-ttu-id="e922f-123">Prima di iniziare la migrazione</span><span class="sxs-lookup"><span data-stu-id="e922f-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="e922f-124">Fase 1: pianificare la migrazione</span><span class="sxs-lookup"><span data-stu-id="e922f-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="e922f-125">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="e922f-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="e922f-126">Fase 3: distribuire il pool di piloti</span><span class="sxs-lookup"><span data-stu-id="e922f-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="e922f-127">Fase 4: trasferire gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="e922f-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="e922f-128">Fase 5: aggiungere Edge Server al pool di piloti</span><span class="sxs-lookup"><span data-stu-id="e922f-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="e922f-129">Fase 6: passaggio dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="e922f-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="e922f-130">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="e922f-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="e922f-131">Fase 8: rimuovere i pool legacy</span><span class="sxs-lookup"><span data-stu-id="e922f-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

