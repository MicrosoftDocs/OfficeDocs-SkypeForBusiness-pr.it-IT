---
title: Rimuovere un Front End Server da un pool
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
description: Il front end server non può esistere come computer autonomo. Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752318"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="3bf11-104">Rimuovere un Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="3bf11-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="3bf11-105">Il front end server non può esistere come computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="3bf11-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="3bf11-106">Deve essere definito come un pool Front End, anche se è presente un solo computer nel pool.</span><span class="sxs-lookup"><span data-stu-id="3bf11-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="3bf11-107">In questo argomento vengono illustrate le procedure per la rimozione di un singolo front end server da un pool Front end esistente.</span><span class="sxs-lookup"><span data-stu-id="3bf11-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="3bf11-108">Se il front end server è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [Remove front end pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="3bf11-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="3bf11-109">Non è necessario rimuovere i singoli Front End Server prima di rimuovere il pool Front end.</span><span class="sxs-lookup"><span data-stu-id="3bf11-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="3bf11-110">Quando si rimuove il pool, è necessario rimuovere ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="3bf11-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="3bf11-111">Per rimuovere un server Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="3bf11-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="3bf11-112">Nel server front end di Skype for Business Server 2019 aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3bf11-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="3bf11-113">Passare al nodo di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="3bf11-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="3bf11-114">Espandere **pool Enterprise Edition front end**, espandere il pool Front end con il front end server che si desidera rimuovere, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3bf11-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

