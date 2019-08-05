---
title: Aggiungere il pool di Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Per definire il nome di dominio completo del pool di Director, selezionare un pool di computer multipli costituito da due o più direttori in un pool con bilanciamento del carico o da un singolo pool di computer. Devi anche digitare il nome di dominio completo (FQDN) che verrà usato per la connessione al pool di Director o l'FQDN del singolo amministratore. Per un pool di computer Director, questa sarebbe la voce Domain Name System (DNS) per l'IP virtuale di un dispositivo di bilanciamento del carico hardware o della voce DNS condivisa per il bilanciamento del carico DNS.
ms.openlocfilehash: 04fe48423b79a0c5912811b8ce7de67c60594847
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195654"
---
# <a name="add-director-pool"></a><span data-ttu-id="27f84-105">Aggiungere il pool di Director</span><span class="sxs-lookup"><span data-stu-id="27f84-105">Add Director Pool</span></span>
 
<span data-ttu-id="27f84-106">Per **definire il nome di dominio completo del pool di Director**, selezionare un **pool di computer multipli** costituito da due o più direttori in un pool con bilanciamento del carico o da un **singolo pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="27f84-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="27f84-107">Devi anche digitare il nome di dominio completo (FQDN) che verrà usato per la connessione al pool di Director o l'FQDN del singolo amministratore.</span><span class="sxs-lookup"><span data-stu-id="27f84-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="27f84-108">Per un pool di computer Director, questa sarebbe la voce Domain Name System (DNS) per l'IP virtuale di un dispositivo di bilanciamento del carico hardware o della voce DNS condivisa per il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="27f84-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="27f84-109">Se si prevede di implementare un pool di Director in futuro, selezionare **più pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="27f84-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="27f84-110">Anche se un pool è definito come due o più computer con bilanciamento del carico, è possibile creare un singolo pool di computer e creare un nome di dominio completo del pool per il singolo computer.</span><span class="sxs-lookup"><span data-stu-id="27f84-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="27f84-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di Director tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="27f84-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="27f84-112">È inoltre necessario aggiungere il nuovo membro del pool ai relativi equilibri di bilanciamento del carico per il pool, per il bilanciamento del carico DNS (Domain Name System) o per i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="27f84-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="27f84-113">In molti casi è necessario disporre di entrambi i sistemi di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="27f84-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="27f84-114">Assicurarsi di aggiungere il nuovo server membro a entrambi.</span><span class="sxs-lookup"><span data-stu-id="27f84-114">Be sure that you are adding the new member server to both.</span></span> 
  

