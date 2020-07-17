---
title: Rimuovere pool Front End o server Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b004426c65157ef7ad1120728c9daeea1b68f161
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="e4daa-102">Rimuovere pool Front End o server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e4daa-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4daa-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="e4daa-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="e4daa-104">In questo argomento vengono illustrate le procedure per la rimozione di un pool Front end o di un front end server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4daa-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="e4daa-105">Quando si rimuove un pool Front End, è necessario rimuovere ogni front end server che appartiene al pool come parte del processo di rimozione del pool.</span><span class="sxs-lookup"><span data-stu-id="e4daa-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="e4daa-106">Quando si rimuove un front end server Standard Edition, è necessario rimuovere la definizione dell'archivio SQL da generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e4daa-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="e4daa-107">Per rimuovere un pool di Font End Server</span><span class="sxs-lookup"><span data-stu-id="e4daa-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="e4daa-108">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="e4daa-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="e4daa-109">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e4daa-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="e4daa-110">Espandere Pool **Enterprise Edition front end**, espandere il pool Front End, fare clic con il pulsante destro del mouse sul pool Front end che si desidera rimuovere e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e4daa-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="e4daa-111">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e4daa-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="e4daa-112">Per rimuovere un server Standard Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="e4daa-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="e4daa-113">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="e4daa-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="e4daa-114">Passare al nodo Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e4daa-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="e4daa-115">Espandere **Standard Edition Front End Server**, fare clic con il pulsante destro del mouse sul front end server che si desidera rimuovere, quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e4daa-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="e4daa-116">Espandere **Archivi SQL**, fare clic con il pulsante destro del mouse sul database di SQL Server associato al front end server Standard Edition e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e4daa-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e4daa-117">È necessario rimuovere la definizione dei database di SQL Server collocati dal front end server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e4daa-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="e4daa-118">Pubblicare la topologia, controllare lo stato della replica e quindi eseguire la distribuzione guidata di Lync Server in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="e4daa-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

