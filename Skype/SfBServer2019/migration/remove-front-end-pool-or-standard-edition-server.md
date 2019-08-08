---
title: Rimuovere il pool Front-end o il server Standard Edition
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Questo argomento illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition. Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool. Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.
ms.openlocfilehash: 57679fb248c9281b79c12be98b7fd5246c9afd38
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244491"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="ec2fc-105">Rimuovere il pool Front-end o il server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ec2fc-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="ec2fc-106">Questo articolo illustra il processo di rimozione di un pool Front-end o di un server front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="ec2fc-107">Quando si rimuove un pool Front-End, si rimuove ogni server front-end che appartiene al pool come parte del processo di rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="ec2fc-108">Quando si rimuove un server front-end Standard Edition, è necessario rimuovere la definizione di SQL Store da generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="ec2fc-109">Per rimuovere un pool di server front-end</span><span class="sxs-lookup"><span data-stu-id="ec2fc-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="ec2fc-110">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ec2fc-111">Passare al nodo Legacy.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="ec2fc-112">Espandere pool di **front-end Enterprise Edition**, espandere il pool Front-End, fare clic con il pulsante destro del mouse sul pool Front-end che si desidera rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="ec2fc-113">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata legacy in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="ec2fc-114">Per rimuovere un server front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ec2fc-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="ec2fc-115">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="ec2fc-116">Passare al nodo installazioni legacy.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="ec2fc-117">Espandere i **server front-end Standard Edition**, fare clic con il pulsante destro del mouse sul server front-end che si desidera rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="ec2fc-118">Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al server front-end Standard Edition e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ec2fc-119">È necessario rimuovere la definizione dei database di SQL Server collocati dal server front-end Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="ec2fc-120">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ec2fc-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

