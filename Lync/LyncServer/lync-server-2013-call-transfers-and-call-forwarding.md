---
title: 'Lync Server 2013: trasferimenti di chiamata e inoltro di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2d258b5820c95b346c76fb5ee7e47e9749c617
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="e30bc-102">Trasferimenti di chiamata e inoltro di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30bc-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e30bc-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e30bc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e30bc-104">Quando viene coinvolto un endpoint PSTN, il routing in base alla posizione analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero la destinazione di trasferimento/inoltro).</span><span class="sxs-lookup"><span data-stu-id="e30bc-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="e30bc-105">Il routing in base alla posizione determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="e30bc-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="e30bc-106">Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un endpoint PSTN e l'utente di Lync trasferisce la chiamata a un altro utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="e30bc-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="e30bc-107">A seconda della posizione del sito di rete dell'endpoint del cessionario, il routing in base alla posizione influisce sul routing del trasferimento delle chiamate o su Inoltra.</span><span class="sxs-lookup"><span data-stu-id="e30bc-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="e30bc-108">Avvio del trasferimento delle chiamate o dell'inoltro</span><span class="sxs-lookup"><span data-stu-id="e30bc-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30bc-109">Utente che avvia il trasferimento di chiamata/inoltra</span><span class="sxs-lookup"><span data-stu-id="e30bc-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="e30bc-110">L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="e30bc-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e30bc-111">L'endpoint di destinazione si trova in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="e30bc-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="e30bc-112">L'endpoint di destinazione è in sito di rete sconosciuto o sito di rete non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="e30bc-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30bc-113">Utente di Lync</span><span class="sxs-lookup"><span data-stu-id="e30bc-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="e30bc-114">Inoltro di chiamata o trasferimento consentito</span><span class="sxs-lookup"><span data-stu-id="e30bc-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="e30bc-115">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="e30bc-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="e30bc-116">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="e30bc-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="e30bc-117">Ad esempio, un utente di Lync in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente Lync che si trova nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="e30bc-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="e30bc-118">In questo caso, il trasferimento di chiamata è consentito.</span><span class="sxs-lookup"><span data-stu-id="e30bc-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="e30bc-119">Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un altro utente Lync e uno degli utenti trasferisce la chiamata a un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="e30bc-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="e30bc-120">A seconda della posizione dell'utente in cui viene trasferita la chiamata, la tabella descrive in che modo il routing basato sulla posizione influenza la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e30bc-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="e30bc-121">Trasferimento di chiamata o inoltra all'endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="e30bc-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e30bc-122">Destinazione endpoint trasferimento/inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="e30bc-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="e30bc-123">Utenti di Lync nello stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="e30bc-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="e30bc-124">Utenti di Lync in siti di rete diversi</span><span class="sxs-lookup"><span data-stu-id="e30bc-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="e30bc-125">Uno o entrambi gli utenti Lync nel sito di rete o sito di rete sconosciuto non sono abilitati per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="e30bc-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e30bc-126">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="e30bc-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="e30bc-127">Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="e30bc-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e30bc-128">Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="e30bc-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="e30bc-129">Chiamata inoltrata o trasferimento consentita dal criterio vocale dell'utente trasferito solo tramite trunk non abilitato per il routing in base alla posizione</span><span class="sxs-lookup"><span data-stu-id="e30bc-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="e30bc-130">Ad esempio, un utente di Lync in una chiamata con un altro utente Lync che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento di chiamata è consentito.</span><span class="sxs-lookup"><span data-stu-id="e30bc-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e30bc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e30bc-131">See Also</span></span>


[<span data-ttu-id="e30bc-132">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e30bc-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

