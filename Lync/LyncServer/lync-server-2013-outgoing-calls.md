---
title: 'Lync Server 2013: chiamate in uscita'
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
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="ac5bc-102">Chiamate in uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac5bc-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac5bc-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ac5bc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ac5bc-104">Il routing delle chiamate in uscita degli utenti abilitati per il routing in base alla posizione è influenzato dal percorso di rete dell'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="ac5bc-105">Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in uscita a seconda del percorso dell'endpoint del chiamante.</span><span class="sxs-lookup"><span data-stu-id="ac5bc-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="ac5bc-106">Chiamante che effettua una chiamata in uscita alla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="ac5bc-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ac5bc-107">Endpoint utente che si trova in un sito di rete abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="ac5bc-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="ac5bc-108">Endpoint utente che si trova in un sito di rete sconosciuto o non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="ac5bc-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac5bc-109">Autorizzazione delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="ac5bc-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="ac5bc-110">La chiamata è autorizzata in base ai criteri vocali dell'utente</span><span class="sxs-lookup"><span data-stu-id="ac5bc-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="ac5bc-111">La chiamata è autorizzata in base ai criteri vocali dell'utente</span><span class="sxs-lookup"><span data-stu-id="ac5bc-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac5bc-112">Routing delle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="ac5bc-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="ac5bc-113">La chiamata viene instradata in base al criterio di routing vocale del sito di rete</span><span class="sxs-lookup"><span data-stu-id="ac5bc-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="ac5bc-114">La chiamata viene instradata in base ai criteri vocali dell'utente e solo tramite trunk non abilitato per il routing in base alla posizione (se disponibile)</span><span class="sxs-lookup"><span data-stu-id="ac5bc-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ac5bc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5bc-115">See Also</span></span>


[<span data-ttu-id="ac5bc-116">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac5bc-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

