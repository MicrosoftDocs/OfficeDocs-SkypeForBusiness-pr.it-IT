---
title: Aggiungere il pool MCU A/V
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Tutti i Front End Server Enterprise Edition di un sito centrale che non hanno un servizio per conferenze A/V collocato possono utilizzare lo stesso pool A/V Conferencing autonomo. Per ogni pool di questo tipo, è necessario specificare un nome di dominio completo (FQDN) e il fatto che disponga solo di uno oppure di più A/V Conferencing Server con bilanciamento del carico.
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217477"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="d5ab6-104">Aggiungere il pool MCU A/V</span><span class="sxs-lookup"><span data-stu-id="d5ab6-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="d5ab6-p102">Tutti i Front End Server Enterprise Edition di un sito centrale che non hanno un servizio per conferenze A/V collocato possono utilizzare lo stesso pool A/V Conferencing autonomo. Per ogni pool di questo tipo, è necessario specificare un nome di dominio completo (FQDN) e il fatto che disponga solo di uno oppure di più A/V Conferencing Server con bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d5ab6-p103">Non è possibile convertire un pool di server singolo in un pool di più server. Se successivamente si decide che l'organizzazione necessita di un pool di più server, sarà necessario eliminare il pool di server singolo e quindi aggiungere il pool di più server.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d5ab6-109">Se si prevede di implementare in futuro un pool A/V Conferencing, selezionare **Pool di più computer**.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="d5ab6-110">Anche se per definizione un pool è costituito da due o più computer con il carico bilanciato, è possibile creare un pool di computer singolo e creare un FQDN del pool per il computer in questione.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="d5ab6-111">Quando si è pronti per aggiungere più computer al pool in un secondo momento, è necessario eseguire di nuovo il generatore di topologie per definire il nuovo membro del pool, pubblicare la nuova topologia e quindi configurare il nuovo membro del pool A/V Conferencing tramite la distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d5ab6-112">I pool di A/V Conferencing Server sono particolari, in quanto per essere creati non richiedono dispositivi di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="d5ab6-113">I pool A/V Conferencing eseguono il bilanciamento del carico internamente e non hanno bisogno di altro hardware.</span><span class="sxs-lookup"><span data-stu-id="d5ab6-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

