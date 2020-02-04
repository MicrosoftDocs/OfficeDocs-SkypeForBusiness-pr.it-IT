---
title: 'Lync Server 2013: Trasferimento e inoltro di chiamata'
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
ms.openlocfilehash: 512deaf8af03f112e35443c25e46685c42a2f2e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="0b620-102">Trasferimento e inoltro di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b620-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b620-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0b620-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0b620-104">Quando si tratta di un endpoint PSTN, il routing basato sulla posizione analizza la posizione dell'endpoint di Calle e dell'endpoint in cui verrà trasferita o inoltrata la chiamata (ovvero destinazione di trasferimento/inoltro).</span><span class="sxs-lookup"><span data-stu-id="0b620-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="0b620-105">Il routing basato sulla posizione determina se la chiamata deve essere trasferita o inoltrata a seconda della posizione di entrambi gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="0b620-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="0b620-106">La tabella seguente illustra lo scenario di un utente di Lync in una chiamata con un endpoint PSTN e l'utente di Lync trasferisce la chiamata a un altro utente di Lync.</span><span class="sxs-lookup"><span data-stu-id="0b620-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="0b620-107">A seconda della posizione del sito di rete dell'endpoint del cessionario, il routing basato sulla posizione influenza il routing del trasferimento delle chiamate o inoltra.</span><span class="sxs-lookup"><span data-stu-id="0b620-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="0b620-108">Avvio del trasferimento delle chiamate o dell'inoltro</span><span class="sxs-lookup"><span data-stu-id="0b620-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b620-109">Utente che avvia il trasferimento/inoltro delle chiamate</span><span class="sxs-lookup"><span data-stu-id="0b620-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="0b620-110">L'endpoint di destinazione si trova nello stesso sito di rete dell'utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="0b620-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="0b620-111">L'endpoint di destinazione è in un sito di rete diverso come utente che avvia il trasferimento delle chiamate o inoltra</span><span class="sxs-lookup"><span data-stu-id="0b620-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="0b620-112">Endpoint di destinazione in un sito di rete o un sito di rete sconosciuto non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0b620-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b620-113">Utenti di Lync</span><span class="sxs-lookup"><span data-stu-id="0b620-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="0b620-114">Inoltro di chiamata o trasferimento consentito</span><span class="sxs-lookup"><span data-stu-id="0b620-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="0b620-115">La chiamata inoltra o transfer non è consentita</span><span class="sxs-lookup"><span data-stu-id="0b620-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="0b620-116">La chiamata inoltra o transfer non è consentita</span><span class="sxs-lookup"><span data-stu-id="0b620-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="0b620-117">Ad esempio, un utente di Lync in una chiamata con un endpoint PSTN trasferisce la chiamata a un altro utente di Lync che si trova nello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="0b620-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="0b620-118">In questo caso, il trasferimento della chiamata è consentito.</span><span class="sxs-lookup"><span data-stu-id="0b620-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="0b620-119">La tabella seguente illustra lo scenario di un utente di Lync in una chiamata con un altro utente di Lync e uno degli utenti trasferisce la chiamata a un endpoint PSTN.</span><span class="sxs-lookup"><span data-stu-id="0b620-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="0b620-120">A seconda della posizione dell'utente a cui viene trasferita la chiamata, la tabella descrive in che modo il routing basato sulla posizione influenza la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b620-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="0b620-121">Trasferimento delle chiamate o inoltro all'endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="0b620-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b620-122">Destinazione dell'endpoint trasferimento/inoltro chiamate</span><span class="sxs-lookup"><span data-stu-id="0b620-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="0b620-123">Utenti di Lync nello stesso sito di rete</span><span class="sxs-lookup"><span data-stu-id="0b620-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="0b620-124">Utenti di Lync in siti di rete diversi</span><span class="sxs-lookup"><span data-stu-id="0b620-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="0b620-125">Uno o entrambi gli utenti di Lync in un sito di rete o un sito di rete sconosciuto non è abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0b620-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b620-126">Endpoint PSTN</span><span class="sxs-lookup"><span data-stu-id="0b620-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="0b620-127">Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="0b620-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0b620-128">Inoltro di chiamata o trasferimento consentito dal criterio di routing vocale del sito dell'utente trasferito</span><span class="sxs-lookup"><span data-stu-id="0b620-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0b620-129">Inoltro di chiamata o trasferimento consentito dal criterio vocale dell'utente trasferito solo tramite Trunks non abilitato per il routing basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="0b620-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="0b620-130">Ad esempio, un utente di Lync in una chiamata con un altro utente Lync che si trova nello stesso sito di rete trasferisce la chiamata a un endpoint PSTN e il trasferimento delle chiamate è consentita.</span><span class="sxs-lookup"><span data-stu-id="0b620-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0b620-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b620-131">See Also</span></span>


[<span data-ttu-id="0b620-132">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b620-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

