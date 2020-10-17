---
title: 'Lync Server 2013: squillo simultaneo'
description: 'Lync Server 2013: squillo simultaneo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 595c8c1d4ce105e2189002f18733ffae92cff8bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555662"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="b5098-103">Squillo simultaneo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5098-103">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5098-104">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b5098-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b5098-105">Quando la parte chiamata è abilitata alla suoneria simultanea, Location-Based routing analizza la posizione della parte chiamante e gli endpoint delle parti denominate per determinare se la chiamata deve essere instradata.</span><span class="sxs-lookup"><span data-stu-id="b5098-105">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="b5098-106">Nella tabella seguente è illustrato un utente configurato con squillo simultaneo e la destinazione di squillo simultaneo è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b5098-106">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5098-107">Chiamata PSTN in ingresso per</span><span class="sxs-lookup"><span data-stu-id="b5098-107">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="b5098-108">Si trova nello stesso sito di rete del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="b5098-108">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="b5098-109">Si trova in un sito di rete diverso dal destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="b5098-109">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="b5098-110">Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="b5098-110">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5098-111">Utente di Lync</span><span class="sxs-lookup"><span data-stu-id="b5098-111">Lync user</span></span></p></td>
<td><p><span data-ttu-id="b5098-112">Squillo simultaneo consentito</span><span class="sxs-lookup"><span data-stu-id="b5098-112">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="b5098-113">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="b5098-113">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="b5098-114">Squillo simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="b5098-114">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="b5098-115">Nella tabella seguente viene illustrata una chiamata proveniente da un utente Lync (ovvero il chiamante Lync) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b5098-115">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="b5098-116">Il destinatario della chiamata ha un endpoint PSTN (i.e. cellulare) configurato come destinazione anello simultaneo.</span><span class="sxs-lookup"><span data-stu-id="b5098-116">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="b5098-117">In questo scenario, Location-Based routing determinerà se la chiamata deve essere instradata alla destinazione dell'anello simultaneo (i.e. cellulare) del destinatario della chiamata oppure no.</span><span class="sxs-lookup"><span data-stu-id="b5098-117">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5098-118">Destinazione anello simultaneo</span><span class="sxs-lookup"><span data-stu-id="b5098-118">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="b5098-119">Si trova nello stesso sito di rete del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="b5098-119">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="b5098-120">Si trova in un sito di rete diverso dal destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="b5098-120">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="b5098-121">Si trova in un sito di rete sconosciuto o non è abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="b5098-121">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5098-122">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="b5098-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b5098-123">Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</span><span class="sxs-lookup"><span data-stu-id="b5098-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b5098-124">Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</span><span class="sxs-lookup"><span data-stu-id="b5098-124">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b5098-125">Squillo simultaneo consentito tramite il criterio vocale del chiamante ai trunk non abilitati per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="b5098-125">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b5098-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5098-126">See Also</span></span>


[<span data-ttu-id="b5098-127">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5098-127">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

