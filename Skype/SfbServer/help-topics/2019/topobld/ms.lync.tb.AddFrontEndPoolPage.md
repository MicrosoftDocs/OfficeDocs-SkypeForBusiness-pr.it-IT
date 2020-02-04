---
title: Aggiungere il nome di dominio completo (FQDN) del pool Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Specificare il nome di dominio completo (FQDN) del pool Front-end che si sta creando. Non è possibile modificare il nome di dominio completo di un pool dopo la pubblicazione della topologia contenente il pool Front-end. Se è necessario rinominare un pool, è necessario eliminare il pool e quindi aggiungere un nuovo pool con il nuovo nome di dominio completo.
ms.openlocfilehash: 0d05455a1b57394eaf0b6b11c70d3a6e9d1f84ae
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689325"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="6c0c2-105">Aggiungere il nome di dominio completo (FQDN) del pool Front End</span><span class="sxs-lookup"><span data-stu-id="6c0c2-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="6c0c2-106">Specificare il nome di dominio completo (FQDN) del pool Front-end che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="6c0c2-107">Non è possibile modificare il nome di dominio completo di un pool dopo la pubblicazione della topologia contenente il pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="6c0c2-108">Se è necessario rinominare un pool, è necessario eliminare il pool e quindi aggiungere un nuovo pool con il nuovo nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="6c0c2-109">Se si prevede di implementare un pool Front-end in futuro, selezionare **più pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="6c0c2-110">Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di un singolo computer e un FQDN del pool per questo computer.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="6c0c2-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool Front end tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="6c0c2-112">È inoltre necessario aggiungere il nuovo membro del pool agli appropriati dispositivi di bilanciamento del carico per il pool, il bilanciamento del carico DNS (Domain Name System) o il servizio di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="6c0c2-113">In molti casi, è necessario disporre entrambi i sistemi di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="6c0c2-114">Assicurarsi di aggiungere il nuovo server membro a entrambi.</span><span class="sxs-lookup"><span data-stu-id="6c0c2-114">Be sure that you are adding the new member server to both.</span></span> 
  

