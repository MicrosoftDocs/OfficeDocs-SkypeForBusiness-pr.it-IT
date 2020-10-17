---
title: 'Lync Server 2013: trasferimenti di chiamata e inoltro di chiamata'
description: 'Lync Server 2013: trasferimenti di chiamata e inoltro di chiamata.'
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
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565252"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="36a5a-103">Trasferimenti di chiamata e inoltro di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36a5a-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36a5a-104">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="36a5a-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="36a5a-105">Quando viene coinvolto un endpoint PSTN, Location-Based routing analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero la destinazione di trasferimento/inoltro).</span><span class="sxs-lookup"><span data-stu-id="36a5a-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="36a5a-106">Location-Based il routing determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="36a5a-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="36a5a-107">Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un endpoint PSTN e l'utente di Lync trasferisce la chiamata a un altro utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="36a5a-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="36a5a-108">A seconda del percorso del sito di rete dell'endpoint del cessionario, Location-Based routing influisce sul routing del trasferimento di chiamata o su Inoltra.</span><span class="sxs-lookup"><span data-stu-id="36a5a-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="36a5a-109">Avvio del trasferimento delle chiamate o dell'inoltro</span><span class="sxs-lookup"><span data-stu-id="36a5a-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36a5a-110">Utente che avvia il trasferimento di chiamata/inoltra</span><span class="sxs-lookup"><span data-stu-id="36a5a-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="36a5a-111">L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="36a5a-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="36a5a-112">L'endpoint di destinazione si trova in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="36a5a-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="36a5a-113">L'endpoint di destinazione è in sito di rete sconosciuto o sito di rete non abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="36a5a-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36a5a-114">Utente di Lync</span><span class="sxs-lookup"><span data-stu-id="36a5a-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="36a5a-115">Inoltro di chiamata o trasferimento consentito</span><span class="sxs-lookup"><span data-stu-id="36a5a-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="36a5a-116">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="36a5a-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="36a5a-117">Non è consentito l'inoltro di chiamata o il trasferimento</span><span class="sxs-lookup"><span data-stu-id="36a5a-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="36a5a-118">Ad esempio, un utente di Lync in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente Lync che si trova nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="36a5a-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="36a5a-119">In questo caso, il trasferimento di chiamata è consentito.</span><span class="sxs-lookup"><span data-stu-id="36a5a-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="36a5a-120">Nella tabella seguente viene illustrato lo scenario di un utente Lync in una chiamata con un altro utente Lync e uno degli utenti trasferisce la chiamata a un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="36a5a-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="36a5a-121">A seconda della posizione dell'utente in cui viene trasferita la chiamata, la tabella descrive in che modo Location-Based instradamento influisce sulla chiamata.</span><span class="sxs-lookup"><span data-stu-id="36a5a-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="36a5a-122">Trasferimento di chiamata o inoltra all'endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="36a5a-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="36a5a-123">Destinazione endpoint trasferimento/inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="36a5a-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="36a5a-124">Utenti di Lync nello stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="36a5a-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="36a5a-125">Utenti di Lync in siti di rete diversi</span><span class="sxs-lookup"><span data-stu-id="36a5a-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="36a5a-126">Uno o entrambi gli utenti di Lync nel sito di rete o sito di rete sconosciuto non sono abilitati per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="36a5a-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="36a5a-127">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="36a5a-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="36a5a-128">Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="36a5a-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="36a5a-129">Chiamata inoltra o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="36a5a-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="36a5a-130">Chiamata inoltrata o trasferimento consentita dal criterio vocale dell'utente trasferito solo tramite trunk non abilitato per il routing Location-Based</span><span class="sxs-lookup"><span data-stu-id="36a5a-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="36a5a-131">Ad esempio, un utente di Lync in una chiamata con un altro utente Lync che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento di chiamata è consentito.</span><span class="sxs-lookup"><span data-stu-id="36a5a-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="36a5a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36a5a-132">See Also</span></span>


[<span data-ttu-id="36a5a-133">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36a5a-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

