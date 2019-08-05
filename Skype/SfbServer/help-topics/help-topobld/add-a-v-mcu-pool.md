---
title: Aggiungere un pool di MCU A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Tutti i server front-end Enterprise Edition di un sito centrale che non dispongono di un servizio A/V Conferencing collocato possono usare lo stesso pool di servizi di conferenza A/V autonomo. Per ogni pool di servizi di conferenza A/V, è necessario specificare un nome di dominio completo (FQDN) per il pool e se avrà un solo server A/V Conferencing o più server di conferenza A/V con bilanciamento del carico.
ms.openlocfilehash: b854e7ecaeed13bd7df15c3ac0439323f3deb311
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195634"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="19ff7-104">Aggiungere un pool di MCU A/V</span><span class="sxs-lookup"><span data-stu-id="19ff7-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="19ff7-105">Tutti i server front-end Enterprise Edition di un sito centrale che non dispongono di un servizio A/V Conferencing collocato possono usare lo stesso pool di servizi di conferenza A/V autonomo.</span><span class="sxs-lookup"><span data-stu-id="19ff7-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="19ff7-106">Per ogni pool di servizi di conferenza A/V, è necessario specificare un nome di dominio completo (FQDN) per il pool e se avrà un solo server A/V Conferencing o più server di conferenza A/V con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="19ff7-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19ff7-107">Non è possibile convertire un pool a server singolo in un pool a più server.</span><span class="sxs-lookup"><span data-stu-id="19ff7-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="19ff7-108">Se in seguito si decide che l'organizzazione ha bisogno di un pool a più server, è necessario eliminare il pool a server singolo e quindi aggiungere il pool a più server.</span><span class="sxs-lookup"><span data-stu-id="19ff7-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="19ff7-109">Se si prevede di implementare un pool di servizi di conferenza a/V in futuro, selezionare **più pool di computer**.</span><span class="sxs-lookup"><span data-stu-id="19ff7-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="19ff7-110">Anche se per definizione un pool è costituito da due o più computer con bilanciamento del carico, è possibile creare un pool di un singolo computer e un FQDN del pool per questo computer.</span><span class="sxs-lookup"><span data-stu-id="19ff7-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="19ff7-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario di nuovo generatore di topologia per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool di servizi di conferenza A/V tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="19ff7-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="19ff7-112">I pool di servizi a/V Conferencing Server sono univoci in quanto non necessitano di servizi di bilanciamento del carico per creare un pool.</span><span class="sxs-lookup"><span data-stu-id="19ff7-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="19ff7-113">I pool di servizi di conferenza A/V si equilibrano internamente e non necessitano di hardware aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="19ff7-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

