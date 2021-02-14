---
title: Migrazione a Skype for Business Server 2019
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
description: Gli argomenti di questa sezione guidano l'utente nel processo di migrazione a Skype for Business Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752618"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="5f68c-103">Migrazione a Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5f68c-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="5f68c-104">Gli argomenti di questa sezione guidano l'utente nel processo di migrazione a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f68c-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="5f68c-105">In questo articolo viene illustrata la migrazione di Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f68c-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f68c-106">In tutto il contenuto viene utilizzato il termine *legacy* per fare riferimento a Lync Server 2013 o Skype for Business Server 2015 legacy di cui si esegue la migrazione a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f68c-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f68c-107">In questa guida vengono descritti i passaggi generalmente necessari per eseguire ogni fase della migrazione.</span><span class="sxs-lookup"><span data-stu-id="5f68c-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="5f68c-108">Non viene trattata ogni possibile topologia di distribuzione legacy o ogni possibile scenario di migrazione.</span><span class="sxs-lookup"><span data-stu-id="5f68c-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="5f68c-109">Di conseguenza, potrebbe non essere necessario eseguire tutti i passaggi descritti oppure eseguire passaggi aggiuntivi, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5f68c-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="5f68c-110">In questa guida vengono inoltre forniti esempi di passaggi di verifica.</span><span class="sxs-lookup"><span data-stu-id="5f68c-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="5f68c-111">Questi passaggi di verifica consentono di comprendere cosa è necessario cercare per garantire che ogni fase sia completata correttamente man mano che si procede con la migrazione.</span><span class="sxs-lookup"><span data-stu-id="5f68c-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="5f68c-112">Adattare questi passaggi di verifica al processo di migrazione specifico.</span><span class="sxs-lookup"><span data-stu-id="5f68c-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="5f68c-113">In questa guida vengono fornite informazioni specifiche per l'aggiornamento della distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="5f68c-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="5f68c-114">Non viene spiegato come modificare la topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="5f68c-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="5f68c-115">In questa guida non viene trattata l'implementazione di nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5f68c-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="5f68c-116">Quando una procedura dettagliata viene documentata altrove, questa guida consente di accedere all'articolo o alla sezione dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="5f68c-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="5f68c-117">In questo articolo vengono definiti i termini specificati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="5f68c-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="5f68c-118">**migrazione:** Spostamento della distribuzione di produzione da Lync Server 2013 o Skype for Business Server 2015 a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5f68c-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="5f68c-119">**coesistenza:** L'ambiente temporaneo esistente durante la migrazione quando è stata eseguita la migrazione di alcune funzionalità a Skype for Business Server 2019 e altre funzionalità rimangono ancora in una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5f68c-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="5f68c-120">**interoperabilità:** La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.</span><span class="sxs-lookup"><span data-stu-id="5f68c-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="5f68c-121">**legacy:** Il sistema da cui si sta eseguendo la migrazione, ovvero Lync Server 2013 o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f68c-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="5f68c-122">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5f68c-122">In this section</span></span>

- [<span data-ttu-id="5f68c-123">Operazioni preliminari alla migrazione</span><span class="sxs-lookup"><span data-stu-id="5f68c-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="5f68c-124">Fase 1: pianificare la migrazione</span><span class="sxs-lookup"><span data-stu-id="5f68c-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="5f68c-125">Fase 2: preparare la migrazione</span><span class="sxs-lookup"><span data-stu-id="5f68c-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="5f68c-126">Fase 3: distribuire il pool pilota</span><span class="sxs-lookup"><span data-stu-id="5f68c-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="5f68c-127">Fase 4: spostare gli utenti di test nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="5f68c-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="5f68c-128">Fase 5: aggiungere Edge Server al pool pilota</span><span class="sxs-lookup"><span data-stu-id="5f68c-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="5f68c-129">Fase 6: passare dalla distribuzione pilota alla produzione</span><span class="sxs-lookup"><span data-stu-id="5f68c-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="5f68c-130">Fase 7: completare le attività successive alla migrazione</span><span class="sxs-lookup"><span data-stu-id="5f68c-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="5f68c-131">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="5f68c-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

