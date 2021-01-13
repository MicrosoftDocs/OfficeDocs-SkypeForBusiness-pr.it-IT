---
title: Aggiungere l'FQDN del pool Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Specificare il nome di dominio completo (FQDN) del pool Front End che si sta creando. Non è possibile modificare l'FQDN di un pool Front End dopo avere pubblicato la topologia contenente il pool. Se si desidera rinominare un pool, è necessario eliminare il pool e quindi aggiungerne uno nuovo con il nuovo FQDN.
ms.openlocfilehash: 45fa22a6ce69b900fc57618825d299ec0930900a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833356"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="a0d5e-105">Aggiungere il nome di dominio completo (FQDN) del pool Front End</span><span class="sxs-lookup"><span data-stu-id="a0d5e-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="a0d5e-p102">Specificare il nome di dominio completo (FQDN) del pool Front End che si sta creando. Non è possibile modificare l'FQDN di un pool Front End dopo avere pubblicato la topologia contenente il pool. Se si desidera rinominare un pool, è necessario eliminare il pool e quindi aggiungerne uno nuovo con il nuovo FQDN.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="a0d5e-109">Se si prevede di implementare in futuro un pool Front End, selezionare **Pool di più computer**.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="a0d5e-110">Anche se per definizione un pool è costituito da due o più computer con il carico bilanciato, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="a0d5e-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool Front end tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="a0d5e-112">È inoltre necessario aggiungere il nuovo membro del pool ai servizi o ai dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="a0d5e-113">In molti casi possono essere in uso tutti e due i sistemi di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="a0d5e-114">Ricordarsi di aggiungere il nuovo server membro a entrambi.</span><span class="sxs-lookup"><span data-stu-id="a0d5e-114">Be sure that you are adding the new member server to both.</span></span> 
  

