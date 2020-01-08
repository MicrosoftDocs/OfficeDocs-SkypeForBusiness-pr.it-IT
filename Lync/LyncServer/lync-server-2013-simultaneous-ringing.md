---
title: 'Lync Server 2013: Squillo simultaneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="0d014-102">Squillo simultaneo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d014-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d014-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0d014-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0d014-104">Quando l'entità denominata ha attivato la chiamata simultanea, il routing basato sulla posizione analizza la posizione della parte chiamante e gli endpoint delle parti chiamate per determinare se la chiamata deve essere instradata.</span><span class="sxs-lookup"><span data-stu-id="0d014-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="0d014-105">La tabella seguente illustra un utente configurato con squillo simultaneo e la destinazione di chiamata simultanea è un utente nello stesso sito di rete, in un sito di rete diverso o in un sito di rete sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0d014-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d014-106">Chiamata PSTN in arrivo per</span><span class="sxs-lookup"><span data-stu-id="0d014-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="0d014-107">Situato nello stesso sito di rete di un chiamato</span><span class="sxs-lookup"><span data-stu-id="0d014-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="0d014-108">Situato in un sito di rete diverso rispetto al chiamato</span><span class="sxs-lookup"><span data-stu-id="0d014-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="0d014-109">Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0d014-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d014-110">Utenti di Lync</span><span class="sxs-lookup"><span data-stu-id="0d014-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="0d014-111">Squillo simultaneo consentito</span><span class="sxs-lookup"><span data-stu-id="0d014-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="0d014-112">Anello simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="0d014-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="0d014-113">Anello simultaneo non consentito</span><span class="sxs-lookup"><span data-stu-id="0d014-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="0d014-114">Nella tabella seguente viene illustrata una chiamata da un utente di Lync (ad esempio il chiamante di Lync) nello stesso sito di rete, in un sito di rete diverso o da un sito di rete sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0d014-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="0d014-115">Il chiamato ha un endpoint PSTN (i.e. cellulare) configurato come destinazione squillo simultaneo.</span><span class="sxs-lookup"><span data-stu-id="0d014-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="0d014-116">In questo scenario, il routing basato sulla posizione determinerà se la chiamata deve essere instradata alla destinazione squillo simultanea (ad esempio cellulare) del destinatario o meno.</span><span class="sxs-lookup"><span data-stu-id="0d014-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d014-117">Destinazione anello simultaneo</span><span class="sxs-lookup"><span data-stu-id="0d014-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="0d014-118">Situato nello stesso sito di rete di un chiamato</span><span class="sxs-lookup"><span data-stu-id="0d014-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="0d014-119">Situato in un sito di rete diverso rispetto al chiamato</span><span class="sxs-lookup"><span data-stu-id="0d014-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="0d014-120">Si trova in un sito di rete sconosciuto o non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0d014-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d014-121">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="0d014-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="0d014-122">Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</span><span class="sxs-lookup"><span data-stu-id="0d014-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0d014-123">Squillo simultaneo consentito tramite il criterio di routing vocale del sito del chiamante</span><span class="sxs-lookup"><span data-stu-id="0d014-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0d014-124">Squillo simultaneo consentito tramite il criterio vocale del chiamante per Trunks non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0d014-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0d014-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d014-125">See Also</span></span>


[<span data-ttu-id="0d014-126">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d014-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

