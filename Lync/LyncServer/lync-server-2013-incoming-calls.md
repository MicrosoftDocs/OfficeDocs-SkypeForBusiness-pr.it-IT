---
title: 'Lync Server 2013: chiamate in ingresso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb8be496e863058ddec27dd92b994d94b86a26e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="2a3d7-102">Chiamate in arrivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a3d7-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a3d7-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="2a3d7-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="2a3d7-104">Il routing delle chiamate in arrivo agli utenti abilitati per il routing in base alla posizione dipende dalla posizione dell'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="2a3d7-105">Il routing delle chiamate in arrivo è influenzato nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="2a3d7-106">Se un utente dispone di una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato per il routing basato sul percorso e che l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="2a3d7-107">Se un utente dispone di una chiamata in arrivo a un endpoint che si trova in un sito di rete abilitato per il routing basato sul percorso e che l'endpoint si trova in un sito di rete diverso rispetto al gateway PSTN, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="2a3d7-108">Quando un utente non dispone di endpoint situati nello stesso sito di rete del gateway PSTN da cui proviene la chiamata in arrivo, la chiamata in arrivo viene instradata direttamente alla segreteria telefonica dell'utente e viene inviata una notifica di chiamata senza risposta all'interlocutore chiamato.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="2a3d7-109">Le impostazioni di inoltro di chiamata di un utente abilitato per il routing in base alla posizione continueranno a essere applicate, tuttavia, le chiamate inoltrate saranno soggette alle restrizioni di routing basate sul percorso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="2a3d7-110">Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in ingresso a seconda del percorso dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="2a3d7-111">Il sito di rete del gateway PSTN è abilitato per il routing in base alla posizione e il routing in base alla posizione consente solo il routing delle chiamate PSTN agli endpoint all'interno dello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="2a3d7-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="2a3d7-112">Destinatario chiamata che riceve una chiamata in ingresso dalla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="2a3d7-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="2a3d7-113">Endpoint del destinatario della chiamata che si trova nello stesso sito di rete del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="2a3d7-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="2a3d7-114">Endpoint del destinatario della chiamata non presente nello stesso sito di rete del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="2a3d7-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="2a3d7-115">Endpoint del destinatario della chiamata che si trova nel sito di rete sconosciuto o non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="2a3d7-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a3d7-116">Routing della chiamata PSTN in ingresso</span><span class="sxs-lookup"><span data-stu-id="2a3d7-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="2a3d7-117">La chiamata in arrivo viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="2a3d7-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="2a3d7-118">La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="2a3d7-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="2a3d7-119">La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="2a3d7-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="2a3d7-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a3d7-120">See Also</span></span>


[<span data-ttu-id="2a3d7-121">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a3d7-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

