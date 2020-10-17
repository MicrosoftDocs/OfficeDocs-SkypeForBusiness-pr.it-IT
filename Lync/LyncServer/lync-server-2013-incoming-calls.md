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
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526613"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="e37ae-102">Chiamate in arrivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e37ae-102">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e37ae-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e37ae-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e37ae-104">Il routing delle chiamate in arrivo agli utenti abilitati per il routing Location-Based dipende dalla posizione dell'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e37ae-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="e37ae-105">Il routing delle chiamate in arrivo è influenzato nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="e37ae-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="e37ae-106">Se un utente dispone di una chiamata in arrivo a un endpoint situato in un sito di rete Location-Based abilitato per il routing e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="e37ae-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="e37ae-107">Se un utente dispone di una chiamata in arrivo a un endpoint posizionato in un sito di rete Location-Based abilitato per il routing e l'endpoint si trova in un sito di rete diverso da quello del gateway PSTN, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="e37ae-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="e37ae-108">Quando un utente non dispone di endpoint situati nello stesso sito di rete del gateway PSTN da cui proviene la chiamata in arrivo, la chiamata in arrivo viene instradata direttamente alla segreteria telefonica dell'utente e viene inviata una notifica di chiamata senza risposta all'interlocutore chiamato.</span><span class="sxs-lookup"><span data-stu-id="e37ae-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="e37ae-109">Le impostazioni di inoltro di chiamata di un utente abilitato per il routing di Location-Based continueranno a essere applicate, tuttavia, le chiamate inoltrate saranno soggette a Location-Based limitazioni di routing dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e37ae-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="e37ae-110">Nella tabella seguente viene illustrato il modo in cui Location-Based routing influisce sul routing delle chiamate in ingresso a seconda del percorso dell'endpoint del destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e37ae-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="e37ae-111">Il sito di rete del gateway PSTN è abilitato per il routing Location-Based e Location-Based routing consente solo il routing delle chiamate PSTN agli endpoint all'interno dello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="e37ae-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="e37ae-112">Destinatario chiamata che riceve una chiamata in ingresso dalla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="e37ae-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="e37ae-113">Endpoint del destinatario della chiamata che si trova nello stesso sito di rete del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="e37ae-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="e37ae-114">Endpoint del destinatario della chiamata non presente nello stesso sito di rete del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="e37ae-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="e37ae-115">Endpoint del destinatario della chiamata che si trova nel sito di rete sconosciuto o non abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="e37ae-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e37ae-116">Routing della chiamata PSTN in ingresso</span><span class="sxs-lookup"><span data-stu-id="e37ae-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="e37ae-117">La chiamata in arrivo viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="e37ae-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="e37ae-118">La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="e37ae-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="e37ae-119">La chiamata in arrivo non viene instradata agli endpoint del destinatario chiamata</span><span class="sxs-lookup"><span data-stu-id="e37ae-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="e37ae-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e37ae-120">See Also</span></span>


[<span data-ttu-id="e37ae-121">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e37ae-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

