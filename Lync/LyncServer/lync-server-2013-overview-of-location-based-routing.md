---
title: 'Lync Server 2013: Panoramica del routing basato sulla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a7db57d506b892fd030efccfb304c7103e1e9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e42c0-102">Panoramica del routing basato sulla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42c0-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e42c0-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e42c0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e42c0-104">Il routing basato sulla posizione introduce un nuovo set di regole che modifica il routing delle chiamate PSTN nazionali e internazionali per evitare l'esclusione dei pedaggi.</span><span class="sxs-lookup"><span data-stu-id="e42c0-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="e42c0-105">Il routing basato sulla posizione offre la flessibilità per l'ambito di queste regole per specifiche aree geografiche, gateway specifici o solo set di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="e42c0-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="e42c0-106">Gli scenari seguenti illustrano i tipi principali di restrizioni che il routing basato sulla posizione può applicare:</span><span class="sxs-lookup"><span data-stu-id="e42c0-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="e42c0-107">Le chiamate in uscita: il routing basato sulla posizione può applicare le chiamate in uscita a un gateway PSTN che si trova nella stessa area geografica in cui il chiamante deve impedire l'esclusione del pedaggio PSTN, impedendo le chiamate all'uscita da un gateway PSTN situato in un'area diversa come chiamante.</span><span class="sxs-lookup"><span data-stu-id="e42c0-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="e42c0-108">Chiamate di ingresso: il routing basato sulla posizione può impedire alle chiamate PSTN in arrivo di squillare gli endpoint di Lync se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente di Lync chiamato.</span><span class="sxs-lookup"><span data-stu-id="e42c0-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="e42c0-109">Aree sconosciute: il routing basato sulla posizione limita le chiamate PSTN in ingresso e in uscita a e da utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o si trovano in aree sconosciute).</span><span class="sxs-lookup"><span data-stu-id="e42c0-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="e42c0-110">Aree internazionali: il routing basato sulla posizione impone il routing delle chiamate in uscita tramite gateway PSTN internazionali se non è possibile trovare un gateway locale nella posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e42c0-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e42c0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e42c0-111">See Also</span></span>


[<span data-ttu-id="e42c0-112">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42c0-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

