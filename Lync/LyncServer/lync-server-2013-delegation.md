---
title: 'Lync Server 2013: delega'
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
ms.openlocfilehash: a9d9f5473f94f093d92cce1b4664f54d6f32430d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="b0760-102">Delega in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0760-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0760-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b0760-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b0760-104">Le funzionalità di delega di Lync sono intaccate dal routing basato sulla posizione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b0760-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="b0760-105">Quando un delegato abilitato per il routing in base alla posizione inserisce una chiamata per conto di un responsabile, il criterio vocale del delegato viene utilizzato per autorizzare la chiamata e il criterio di routing vocale del sito del delegato verrà utilizzato per instradare la chiamata</span><span class="sxs-lookup"><span data-stu-id="b0760-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="b0760-106">Per le chiamate PSTN in arrivo a un Manager, si applicano le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo come descritto negli argomenti trasferimento di chiamata e inoltro e squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="b0760-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="b0760-107">Quando un delegato imposta un endpoint PSTN come destinazione anello simultaneo, per una chiamata in arrivo al responsabile, il criterio di routing vocale del sito associato al trunk in ingresso verrà utilizzato per instradare la chiamata all'endpoint PSTN del delegato.</span><span class="sxs-lookup"><span data-stu-id="b0760-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="b0760-108">Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b0760-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b0760-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0760-109">See Also</span></span>


[<span data-ttu-id="b0760-110">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0760-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

