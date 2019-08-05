---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business Server 2019 supporta distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:'
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195009"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="0e4fa-104">Migrazione di più siti e pool</span><span class="sxs-lookup"><span data-stu-id="0e4fa-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="0e4fa-105">Skype for Business Server 2019 supporta distribuzioni multisito e multi-pool.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="0e4fa-106">Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e4fa-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="0e4fa-107">Dopo aver distribuito un pool pilota di Skype for Business Server 2019, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Skype for Business Server 2019 e una metodologia per la convalida della funzionalità degli utenti.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="0e4fa-108">Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che il criterio di conferenza dell'utente sia stato spostato in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="0e4fa-109">Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="0e4fa-110">La chat persistente, il mirroring SQL e la funzionalità XMPP sono deprecati in Skype for Business Server 2019 e non sono più disponibili come funzionalità di Skype for Business Server 2019, ma possono essere proseguiti in un ambiente di coesistenza se in precedenza sono stati distribuiti in un ambiente legacy.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="0e4fa-111">Se si vuole continuare a usare queste funzionalità, è consigliabile continuare con un ambiente di coesistenza in cui alcuni utenti rimarranno in pool legacy.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="0e4fa-112">Dopo la transizione dei server Edge delle route federate ai server Edge pilota di Skype for Business Server 2019, è necessario verificare che gli utenti federati possano comunicare con il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="0e4fa-113">Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool legacy sia vuoto.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="0e4fa-114">Dopo aver verificato che il pool legacy sia vuoto, è possibile disattivare il pool.</span><span class="sxs-lookup"><span data-stu-id="0e4fa-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="0e4fa-115">Per informazioni dettagliate su come disattivare il pool e i server legacy, vedere la [fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="0e4fa-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

