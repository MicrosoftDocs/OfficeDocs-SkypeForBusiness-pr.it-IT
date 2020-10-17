---
title: 'Lync Server 2013: Panoramica del routing di Location-Based'
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
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520963"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="65816-102">Panoramica del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65816-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65816-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="65816-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="65816-104">Location-Based routing introduce un nuovo set di regole che consente di modificare il routing delle chiamate PSTN nazionali e internazionali per evitare il bypass a pedaggio.</span><span class="sxs-lookup"><span data-stu-id="65816-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="65816-105">Location-Based routing offre la possibilità di applicare queste regole a aree specifiche, gateway specifici o solo a un insieme specifico di utenti.</span><span class="sxs-lookup"><span data-stu-id="65816-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="65816-106">Negli scenari seguenti vengono illustrati i principali tipi di restrizioni Location-Based il routing può applicare:</span><span class="sxs-lookup"><span data-stu-id="65816-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="65816-107">Chiamate in uscita – Location-Based il routing può applicare le chiamate in uscita per l'ingresso da un gateway PSTN che si trova nella stessa regione in cui il chiamante deve impedire il bypass a pedaggio PSTN, impedendo le chiamate in uscita da un gateway PSTN che si trova in un'area diversa come chiamante.</span><span class="sxs-lookup"><span data-stu-id="65816-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="65816-108">Ingress calls – Location-Based routing può impedire le chiamate PSTN in arrivo per suonare gli endpoint di Lync se il gateway PSTN che instrada la chiamata in arrivo non si trova nella stessa area dell'utente denominato Lync.</span><span class="sxs-lookup"><span data-stu-id="65816-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="65816-109">Aree sconosciute – Location-Based il routing limita le chiamate PSTN in ingresso e in uscita da e verso gli utenti che si trovano in posizioni Indeterminate (ad esempio, gli utenti remoti che si connettono da Internet o che si trovano in aree sconosciute).</span><span class="sxs-lookup"><span data-stu-id="65816-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="65816-110">Aree internazionali – Location-Based il routing impone il routing delle chiamate in uscita attraverso i gateway PSTN internazionali se non è possibile trovare un gateway locale per la posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="65816-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="65816-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65816-111">See Also</span></span>


[<span data-ttu-id="65816-112">Pianificazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65816-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

