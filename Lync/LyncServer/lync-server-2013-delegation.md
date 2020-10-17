---
title: 'Lync Server 2013: delega'
description: 'Lync Server 2013: delega.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dc25d0ea3dfd64ee1b71677e6bac55c1cb1ca32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567452"
---
# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="1fc7c-103">Delega in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fc7c-103">Delegation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fc7c-104">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="1fc7c-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="1fc7c-105">Le funzionalità di delega di Lync sono intaccate dal routing Location-Based nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1fc7c-105">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="1fc7c-106">Quando un delegato abilitato per il routing Location-Based inserisce una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata</span><span class="sxs-lookup"><span data-stu-id="1fc7c-106">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="1fc7c-107">Per le chiamate PSTN in arrivo a un Manager, si applicano le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo come descritto negli argomenti trasferimento di chiamata e inoltro e squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-107">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="1fc7c-108">Quando un delegato imposta un endpoint PSTN come destinazione anello simultaneo, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-108">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="1fc7c-109">Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="1fc7c-109">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1fc7c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fc7c-110">See Also</span></span>


[<span data-ttu-id="1fc7c-111">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fc7c-111">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

