---
title: 'Lync Server 2013: Delega'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="06868-102">Delega in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06868-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06868-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="06868-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="06868-104">Le funzionalità di delega di Lync sono interessate dal routing basato sulla posizione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="06868-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="06868-105">Quando un delegato abilitato per il routing basato sulla posizione effettua una chiamata per conto di un Manager, il criterio vocale del delegato viene usato per autorizzare la chiamata e i criteri di routing vocale del sito del delegato verranno usati per instradare la chiamata</span><span class="sxs-lookup"><span data-stu-id="06868-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="06868-106">Per le chiamate PSTN in arrivo a un responsabile, le stesse regole applicabili per l'inoltro di chiamata o lo squillo simultaneo verranno applicate come descritto negli argomenti trasferimento chiamate e inoltro e squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="06868-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="06868-107">Quando un delegato imposta un endpoint PSTN come destinazione squillo simultaneo, per una chiamata in arrivo al Manager, il criterio di routing vocale del sito associato al trunk in arrivo verrà usato per instradare la chiamata all'endpoint PSTN del delegato.</span><span class="sxs-lookup"><span data-stu-id="06868-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="06868-108">Per la delega, è consigliabile che il responsabile e i delegati associati si trovino in genere nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="06868-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="06868-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06868-109">See Also</span></span>


[<span data-ttu-id="06868-110">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06868-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

