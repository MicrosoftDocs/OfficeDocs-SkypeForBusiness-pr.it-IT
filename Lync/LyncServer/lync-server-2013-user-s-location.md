---
title: "Lync Server 2013: Posizione dell'utente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9754b75b941944a445da33750190b9347aeb9313
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="f45cb-102">Posizione dell'utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f45cb-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f45cb-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f45cb-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f45cb-104">Il routing basato sulla posizione sfrutta le stesse aree di rete, i siti e le subnet definiti in Lync Server usato da E9-1-1, CAC e bypass multimediale per applicare le restrizioni di routing delle chiamate per evitare l'esclusione del pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f45cb-105">La posizione di un utente è determinata dalla subnet IP degli endpoint di Lync dell'utente da cui sono connessi.</span><span class="sxs-lookup"><span data-stu-id="f45cb-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="f45cb-106">Ogni subnet IP è associata a un sito di rete, che viene aggregato in aree di rete definite dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="f45cb-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="f45cb-107">Il routing basato sulla posizione viene applicato in base al sito di rete dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f45cb-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="f45cb-108">Le regole di routing basate sulla posizione vengono applicate in base al sito di rete, pertanto un set di regole specifico verrà applicato a tutti gli endpoint abilitati per il routing basato sulla posizione che si trovano all'interno dello stesso sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f45cb-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="f45cb-109">Gli amministratori possono applicare il routing basato sulla posizione ai siti di rete che lo richiedono.</span><span class="sxs-lookup"><span data-stu-id="f45cb-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="f45cb-110">I criteri di routing vocale possono essere definiti in base al sito di rete per definire un gateway PSTN specifico che deve essere usato da tutti gli utenti presenti nel sito di rete per chiamare i numeri di telefono PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="f45cb-111">Tali criteri di routing vocale avranno la precedenza sul routing definito dal criterio vocale dell'utente quando l'utente si trova in un sito di rete abilitato per il routing basato sulla posizione e impedirà il routing delle chiamate tramite altri gateway PSTN abilitati per Routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f45cb-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="f45cb-112">Quando un utente di Lync inserisce una chiamata PSTN, il criterio vocale dell'utente determina se l'utente può essere autorizzato a effettuare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f45cb-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="f45cb-113">Se il criterio vocale dell'utente consente all'utente di inserire la chiamata, il routing basato sulla posizione determina il gateway PSTN da cui deve essere uscita la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f45cb-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="f45cb-114">Il routing basato sulla posizione rende questa determinazione in base alla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f45cb-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="f45cb-115">Una posizione utente può essere categorizzata nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f45cb-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="f45cb-116">L'utente si trova in un sito di rete noto abilitato per il routing basato sulla posizione e il suo numero DID (Direct Inward Dial) termina con un gateway PSTN inserito nello stesso sito di rete (ad esempio Office).</span><span class="sxs-lookup"><span data-stu-id="f45cb-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="f45cb-117">Il routing delle chiamate in uscita avverrà tramite il criterio di routing vocale del sito di rete in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="f45cb-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="f45cb-118">Le chiamate PSTN in arrivo all'utente vengono instradate agli endpoint che si trovano nello stesso sito di rete del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="f45cb-119">L'utente si trova in un sito di rete noto che è diverso dal sito di rete in cui si trova il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="f45cb-120">(ossia l'utente ha viaggiato in un altro ufficio aziendale).</span><span class="sxs-lookup"><span data-stu-id="f45cb-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="f45cb-121">Il routing delle chiamate in uscita userà i criteri di routing vocale del sito di rete in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="f45cb-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="f45cb-122">Le chiamate PSTN in arrivo per l'utente non verranno instradate agli endpoint che si trovano in siti diversi rispetto al gateway PSTN per evitare l'esclusione dei pedaggi PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="f45cb-123">Quando un utente si trova in un sito di rete sconosciuto alla distribuzione di Lync Server, il routing delle chiamate in uscita sarà basato sul criterio vocale assegnato all'utente per i gateway PSTN non associati alle restrizioni di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="f45cb-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="f45cb-124">Le chiamate PSTN in arrivo non verranno instradate agli endpoint che si trovano in siti di rete sconosciuti per evitare l'esclusione dei pedaggi PSTN.</span><span class="sxs-lookup"><span data-stu-id="f45cb-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f45cb-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f45cb-125">See Also</span></span>


[<span data-ttu-id="f45cb-126">Linee guida per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f45cb-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

