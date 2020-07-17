---
title: Migrazione di più siti e pool
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
description: 'Skype for Business Server 2019 supporta le distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752658"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="21fde-104">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="21fde-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="21fde-105">Skype for Business Server 2019 supporta le distribuzioni multisito e multi-pool.</span><span class="sxs-lookup"><span data-stu-id="21fde-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="21fde-106">Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="21fde-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="21fde-107">Dopo aver distribuito un pool pilota di Skype for Business Server 2019, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Skype for Business Server 2019 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="21fde-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="21fde-108">Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che i criteri di conferenza dell'utente siano stati spostati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="21fde-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="21fde-109">Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="21fde-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="21fde-110">La chat persistente, il mirroring SQL e la funzionalità XMPP sono deprecati in Skype for Business Server 2019 e non sono più disponibili come funzionalità di Skype for Business Server 2019, ma possono essere continuati in un ambiente di coesistenza se sono stati precedentemente distribuiti in un ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="21fde-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="21fde-111">Se si desidera continuare a utilizzare queste funzionalità, è consigliabile pianificare la prosecuzione di un ambiente di coesistenza in cui alcuni utenti rimarranno nei pool legacy.</span><span class="sxs-lookup"><span data-stu-id="21fde-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="21fde-112">Dopo aver eseguito la transizione dei server perimetrali delle route federate ai server Edge di Skype for Business Server 2019 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="21fde-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="21fde-113">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool legacy sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="21fde-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="21fde-114">Dopo aver verificato che il pool legacy è vuoto, sarà possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="21fde-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="21fde-115">Per informazioni dettagliate su come disattivare i server e il pool legacy, vedere [Phase 8: decommission legacy pools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="21fde-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

