---
title: Aggiungere un pool di Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Per eseguire l'operazione Definisci FQDN pool Director, selezionare un Pool di più computer costituito da due o più server Director in un pool con bilanciamento del carico oppure un Pool di computer singolo. È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per la connessione al pool di server Director o all'FQDN del singolo Director. Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219487"
---
# <a name="add-director-pool"></a><span data-ttu-id="2bc80-105">Aggiungere un pool di Director</span><span class="sxs-lookup"><span data-stu-id="2bc80-105">Add Director Pool</span></span>
 
<span data-ttu-id="2bc80-106">Per eseguire l'operazione **Definisci FQDN pool Director**, selezionare un **Pool di più computer** costituito da due o più server Director in un pool con bilanciamento del carico oppure un **Pool di computer singolo**.</span><span class="sxs-lookup"><span data-stu-id="2bc80-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="2bc80-107">È inoltre necessario digitare il nome di dominio completo (FQDN) che verrà utilizzato per la connessione al pool di server Director o all'FQDN del singolo Director.</span><span class="sxs-lookup"><span data-stu-id="2bc80-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="2bc80-108">Per un pool di computer Director, corrisponderà alla voce DNS (Domain Name System) dell'IP virtuale di un servizio di bilanciamento del carico hardware oppure alla voce DNS condivisa del bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="2bc80-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="2bc80-109">Se si prevede di implementare in futuro un pool di server Director, selezionare **Pool di più computer**.</span><span class="sxs-lookup"><span data-stu-id="2bc80-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="2bc80-110">Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione.</span><span class="sxs-lookup"><span data-stu-id="2bc80-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="2bc80-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di Director tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2bc80-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="2bc80-112">È inoltre necessario aggiungere il nuovo membro del pool ai servizi o dispositivi di bilanciamento del carico appropriati per il pool, ovvero il bilanciamento del carico DNS (Domain Name System) o i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="2bc80-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="2bc80-113">In molti casi possono essere in uso tutti e due i sistemi di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="2bc80-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="2bc80-114">Ricordarsi di aggiungere il nuovo server membro a entrambi.</span><span class="sxs-lookup"><span data-stu-id="2bc80-114">Be sure that you are adding the new member server to both.</span></span> 
  

