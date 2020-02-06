---
title: Rimuovere un Front End Server da un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Il server front-end non può esistere come computer autonomo. Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813034"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="79e99-104">Rimuovere un Front End Server da un pool</span><span class="sxs-lookup"><span data-stu-id="79e99-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="79e99-105">Il server front-end non può esistere come computer autonomo.</span><span class="sxs-lookup"><span data-stu-id="79e99-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="79e99-106">Deve essere definito come pool Front-End, anche se è presente solo un singolo computer nel pool.</span><span class="sxs-lookup"><span data-stu-id="79e99-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="79e99-107">Questo argomento illustra il processo di rimozione di un singolo server front-end da un pool Front-end esistente.</span><span class="sxs-lookup"><span data-stu-id="79e99-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="79e99-108">Se il server front-end è l'ultimo server del pool o se si sta rimuovendo completamente il pool, vedere [rimuovere il pool Front-end o il server Standard Edition](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="79e99-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="79e99-109">Non è necessario rimuovere i singoli server front-end prima di rimuovere il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="79e99-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="79e99-110">Quando si rimuove il pool, si rimuove ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="79e99-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="79e99-111">Per rimuovere un server front-end da un pool</span><span class="sxs-lookup"><span data-stu-id="79e99-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="79e99-112">Nel server front-end di Skype for Business Server 2019 aprire Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="79e99-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="79e99-113">Passare al nodo di installazione legacy.</span><span class="sxs-lookup"><span data-stu-id="79e99-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="79e99-114">Espandi i **pool Front End di Enterprise Edition**, Espandi il pool Front end con il front end server che vuoi rimuovere, fai clic con il pulsante destro del mouse sul server front-end che vuoi rimuovere e quindi fai clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="79e99-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

