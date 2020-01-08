---
title: 'Lync Server 2013: Chiamate in arrivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="34cd2-102">Chiamate in arrivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34cd2-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34cd2-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="34cd2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="34cd2-104">Il routing delle chiamate in arrivo agli utenti abilitati per il routing basato sulla posizione dipende dalla posizione dell'endpoint dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34cd2-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="34cd2-105">Il routing delle chiamate in arrivo è influenzato dal modo seguente.</span><span class="sxs-lookup"><span data-stu-id="34cd2-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="34cd2-106">Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova nello stesso sito di rete del gateway PSTN, la chiamata verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="34cd2-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="34cd2-107">Se un utente ha una chiamata in arrivo a un endpoint situato in un sito di rete abilitato per il routing basato sulla posizione e l'endpoint si trova in un sito di rete diverso rispetto al gateway PSTN, la chiamata non verrà instradata.</span><span class="sxs-lookup"><span data-stu-id="34cd2-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="34cd2-108">Quando un utente non ha endpoint situati nello stesso sito di rete del gateway PSTN in cui viene originata la chiamata in arrivo, la chiamata in arrivo verrà instradata direttamente alla segreteria telefonica dell'utente e verrà inviata una notifica di chiamata senza risposta alla festa chiamata.</span><span class="sxs-lookup"><span data-stu-id="34cd2-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="34cd2-109">Le impostazioni di inoltro di chiamata di un utente abilitato per il routing basato sulla posizione continueranno ad essere applicate, tuttavia, le chiamate inoltrate saranno soggette alle restrizioni di routing basate sulla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34cd2-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="34cd2-110">Nella tabella seguente viene illustrato il modo in cui il routing basato sulla posizione influisce sul routing delle chiamate in ingresso a seconda della posizione dell'endpoint del destinatario.</span><span class="sxs-lookup"><span data-stu-id="34cd2-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="34cd2-111">Il sito di rete del gateway PSTN è abilitato per il routing basato sulla posizione e il routing basato sulla posizione consente solo il routing delle chiamate PSTN agli endpoint nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="34cd2-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="34cd2-112">Chiamata in ricezione di una chiamata in ingresso dalla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="34cd2-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="34cd2-113">Endpoint di callee situato nello stesso sito di rete di gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="34cd2-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="34cd2-114">Endpoint del destinatario non presente nello stesso sito di rete di gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="34cd2-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="34cd2-115">Endpoint del destinatario situato nel sito di rete sconosciuto o non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="34cd2-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34cd2-116">Routing della chiamata PSTN in ingresso</span><span class="sxs-lookup"><span data-stu-id="34cd2-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="34cd2-117">La chiamata in arrivo viene instradata agli endpoint del chiamato</span><span class="sxs-lookup"><span data-stu-id="34cd2-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="34cd2-118">La chiamata in arrivo non viene instradata agli endpoint del chiamato</span><span class="sxs-lookup"><span data-stu-id="34cd2-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="34cd2-119">La chiamata in arrivo non viene instradata agli endpoint del chiamato</span><span class="sxs-lookup"><span data-stu-id="34cd2-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="34cd2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34cd2-120">See Also</span></span>


[<span data-ttu-id="34cd2-121">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34cd2-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

