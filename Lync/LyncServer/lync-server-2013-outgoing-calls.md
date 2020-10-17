---
title: 'Lync Server 2013: chiamate in uscita'
description: 'Lync Server 2013: chiamate in uscita.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546852"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="c657d-103">Chiamate in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c657d-103">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c657d-104">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c657d-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c657d-105">Il routing delle chiamate in uscita degli utenti abilitati per il routing Location-Based è influenzato dal percorso di rete dell'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c657d-105">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="c657d-106">Nella tabella seguente viene illustrato il modo in cui Location-Based routing influisce sul routing delle chiamate in uscita a seconda del percorso dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c657d-106">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="c657d-107">Chiamante che effettua una chiamata in uscita alla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="c657d-107">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c657d-108">Endpoint utente che si trova in un sito di rete abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="c657d-108">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="c657d-109">Endpoint utente che si trova in un sito di rete sconosciuto o non abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="c657d-109">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c657d-110">Autorizzazione delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="c657d-110">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="c657d-111">La chiamata è autorizzata in base ai criteri vocali dell'utente</span><span class="sxs-lookup"><span data-stu-id="c657d-111">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="c657d-112">La chiamata è autorizzata in base ai criteri vocali dell'utente</span><span class="sxs-lookup"><span data-stu-id="c657d-112">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c657d-113">Routing delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="c657d-113">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="c657d-114">La chiamata viene instradata in base al criterio di routing vocale del sito di rete</span><span class="sxs-lookup"><span data-stu-id="c657d-114">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="c657d-115">La chiamata viene instradata in base ai criteri vocali dell'utente e solo tramite trunk non abilitato per il routing Location-Based (se disponibile)</span><span class="sxs-lookup"><span data-stu-id="c657d-115">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c657d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c657d-116">See Also</span></span>


[<span data-ttu-id="c657d-117">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c657d-117">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

