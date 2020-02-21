---
title: 'Lync Server 2013: considerazioni tecniche per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89180087909b71bc9f53f24ee02bbc077d459a17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2041e-102">Considerazioni tecniche per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2041e-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2041e-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="2041e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="2041e-104">Durante la pianificazione del routing in base alla posizione, è opportuno considerare l'impatto sui seguenti scenari.</span><span class="sxs-lookup"><span data-stu-id="2041e-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="2041e-105">Ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="2041e-105">Disaster Recovery</span></span>

<span data-ttu-id="2041e-106">Durante un failover dal pool primario a un pool di backup e durante il ripristino di normali operazioni al pool primario, il routing basato sulla posizione rimane applicato sempre durante una procedura di ripristino e di emergenza.</span><span class="sxs-lookup"><span data-stu-id="2041e-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="2041e-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="2041e-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="2041e-108">La configurazione del routing in base alla posizione ha un impatto sulla pianificazione del percorso in cui vengono distribuiti i gateway associati ai Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="2041e-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="2041e-109">Il gateway associato all'ASB deve trovarsi nello stesso sito di rete del Survivable Branch Appliance. in caso contrario, gli utenti ospitati nel Survivable Branch Appliance non saranno autorizzati a inserire le chiamate in uscita se è configurato il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="2041e-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="2041e-110">Quando la connessione WAN tra il Survivable Branch Appliance e il sito centrale è inattiva, le restrizioni di routing basate sul percorso rimangono applicate.</span><span class="sxs-lookup"><span data-stu-id="2041e-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2041e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2041e-111">See Also</span></span>


[<span data-ttu-id="2041e-112">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2041e-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

