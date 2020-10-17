---
title: 'Lync Server 2013: posizione del gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512443"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="4e4e1-102">Posizione del gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4e1-102">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e4e1-103">_**Ultimo argomento modificato:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4e4e1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4e4e1-104">Le chiamate instradate tramite gateway PSTN e PBX potrebbero richiedere Location-Based limitazioni del routing in base alla posizione di tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="4e4e1-105">Location-Based il routing può essere abilitato alla granularità per ogni base trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="4e4e1-106">Location-Based routing introduce il set di regole seguente quando è abilitato su un trunk:</span><span class="sxs-lookup"><span data-stu-id="4e4e1-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="4e4e1-107">Quando Location-Based routing è abilitato per ogni trunk, le regole definite su tale trunk verranno applicate solo alle chiamate instradate attraverso il trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="4e4e1-108">Per evitare che i pedaggi PSTN vengano ignorati in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, Location-Based routing introduce l'associazione di un sito di rete a un trunk specificato.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="4e4e1-109">In questo modo viene definito il sito di rete che consente di instradare le chiamate a un determinato trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="4e4e1-110">I trunk possono essere abilitati per il routing Location-Based in due modi:</span><span class="sxs-lookup"><span data-stu-id="4e4e1-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="4e4e1-111">Il trunk è definito per un gateway PSTN che egresses le chiamate alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="4e4e1-112">Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati all'interno dello stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="4e4e1-113">Il trunk è definito per un peer di Mediation Server che non consente di uscire dalle chiamate agli utenti di servizi PSTN e con i telefoni legacy in posizioni statiche (ovvero telefoni PBX).</span><span class="sxs-lookup"><span data-stu-id="4e4e1-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="4e4e1-114">Per questa configurazione specifica, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originate dallo stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="4e4e1-115">Le chiamate provenienti da utenti PBX avranno lo stesso Location-Based l'applicazione di routing come utenti di Lync che si trovano nello stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="4e4e1-116">Se due sistemi PBX situati in siti di rete separati sono connessi tramite Lync Server, Location-Based routing consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="4e4e1-117">Questo scenario non verrà bloccato da Location-Based routing.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="4e4e1-118">Oltre a questo scenario e in modo analogo a quello di un utente Lync nello stesso percorso, gli endpoint connessi a un peer di Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate verso e da altri peer di Mediation Server che non instradano le chiamate alla rete PSTN (ovvero un endpoint connesso a un altro sistema PBX) indipendentemente dal sito di rete a cui è associato il peer di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="4e4e1-119">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e gli inoltri di chiamata che coinvolgono endpoint PSTN sono soggetti al routing basato sulla posizione per l'utilizzo di solo gateway PSTN definiti come locali per tale peer di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4e4e1-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4e4e1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e4e1-120">See Also</span></span>


[<span data-ttu-id="4e4e1-121">Linee guida per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e4e1-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

