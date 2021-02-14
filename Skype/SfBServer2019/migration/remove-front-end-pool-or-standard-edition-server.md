---
title: Rimuovere pool Front End o server Standard Edition
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
description: In questo argomento viene illustrato il processo di rimozione di un pool Front End o di un Front End Server Standard Edition. Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool. Quando si rimuove un Front End Server Standard Edition, è necessario rimuovere la definizione dell SQL store dal Generatore di topologie.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752278"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="c1def-105">Rimuovere pool Front End o server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c1def-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="c1def-106">In questo articolo viene illustrata la procedura di rimozione di un pool Front End o di un Front End Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c1def-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="c1def-107">Quando si rimuove un pool Front End, si rimuove ogni Front End Server appartenente al pool come parte del processo di rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="c1def-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="c1def-108">Quando si rimuove un Front End Server Standard Edition, è necessario rimuovere la definizione dell SQL store dal Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="c1def-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="c1def-109">Per rimuovere un pool di Font End Server</span><span class="sxs-lookup"><span data-stu-id="c1def-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="c1def-110">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="c1def-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="c1def-111">Passare al nodo legacy.</span><span class="sxs-lookup"><span data-stu-id="c1def-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="c1def-112">Espandere **Pool Enterprise Edition Front End,** espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front End che si desidera rimuovere e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="c1def-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="c1def-113">Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata legacy in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1def-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="c1def-114">Per rimuovere un server Standard Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="c1def-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="c1def-115">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="c1def-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="c1def-116">Passare al nodo delle installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="c1def-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="c1def-117">Espandere **Standard Edition Front End Server,** fare clic con il pulsante destro del mouse sul Front End Server che si desidera rimuovere e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="c1def-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="c1def-118">Espandere **SQL archivi,** fare clic con il pulsante destro del mouse sul database SQL Server associato al Front End Server Standard Edition e quindi scegliere **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="c1def-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c1def-119">È necessario rimuovere la definizione dei database SQL Server collocati dal Front End Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c1def-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="c1def-120">Pubblicare la topologia, controllare lo stato della replica ed eseguire la Distribuzione guidata in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c1def-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

