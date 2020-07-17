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
description: In questo argomento vengono illustrate le procedure per la rimozione di un pool Front end o di un front end server Standard Edition. Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752278"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="3bc8f-105">Rimuovere pool Front End o server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3bc8f-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="3bc8f-106">In questo articolo vengono illustrate le procedure per la rimozione di un pool Front end o di un server Standard Edition front end.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="3bc8f-107">Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="3bc8f-108">Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="3bc8f-109">Per rimuovere un pool di Font End Server</span><span class="sxs-lookup"><span data-stu-id="3bc8f-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="3bc8f-110">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="3bc8f-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="3bc8f-111">Passare al nodo Legacy.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="3bc8f-112">Espandere Pool **Enterprise Edition front end**, espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front end che si desidera rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="3bc8f-113">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata legacy in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="3bc8f-114">Per rimuovere un server Standard Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="3bc8f-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="3bc8f-115">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="3bc8f-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="3bc8f-116">Passare al nodo installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="3bc8f-117">Espandere **Standard Edition Front End Server**, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="3bc8f-118">Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al front end server Standard Edition e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3bc8f-119">È necessario rimuovere la definizione dei database di SQL Server collocati dal front end server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="3bc8f-120">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3bc8f-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

