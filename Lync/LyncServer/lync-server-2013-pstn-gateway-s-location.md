---
title: 'Lync Server 2013: Posizione del gateway PSTN'
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
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="9fd36-102">Posizione del gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fd36-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fd36-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="9fd36-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="9fd36-104">Le chiamate instradate tramite gateway e PBX PSTN potrebbero richiedere restrizioni di routing basate sulla posizione a seconda della posizione di tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="9fd36-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="9fd36-105">Il routing basato sulla posizione può essere abilitato alla granularità per ogni trunk base.</span><span class="sxs-lookup"><span data-stu-id="9fd36-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="9fd36-106">Il routing basato sulla posizione introduce il set di regole seguente quando è abilitato su un trunk:</span><span class="sxs-lookup"><span data-stu-id="9fd36-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="9fd36-107">Quando il routing basato sulla posizione è abilitato per ogni trunk, le regole definite in tale trunk verranno applicate solo alle chiamate instradate tramite il trunk.</span><span class="sxs-lookup"><span data-stu-id="9fd36-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="9fd36-108">Per impedire l'esclusione dei pedaggi PSTN in cui le chiamate provengono da un sito di rete diverso da quello del sito di rete in cui si trova il gateway PSTN, il routing basato sulla posizione introduce l'associazione di un sito di rete a un trunk specifico.</span><span class="sxs-lookup"><span data-stu-id="9fd36-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="9fd36-109">Questo definisce il sito di rete che consente alle chiamate di essere indirizzate a un trunk specifico.</span><span class="sxs-lookup"><span data-stu-id="9fd36-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="9fd36-110">Trunks può essere abilitato per il routing basato sulla posizione in due modi:</span><span class="sxs-lookup"><span data-stu-id="9fd36-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="9fd36-111">Il trunk viene definito per un gateway PSTN che egresses chiama alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="9fd36-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="9fd36-112">Le chiamate in arrivo instradate da un trunk di questo tipo verranno instradate solo agli endpoint situati nello stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="9fd36-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="9fd36-113">Il trunk viene definito per un peer di Mediation Server che non consente l'uscita delle chiamate agli utenti di servizi e PSTN con telefoni legacy in posizioni statiche (ad esempio telefoni PBX).</span><span class="sxs-lookup"><span data-stu-id="9fd36-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="9fd36-114">Per questa particolare configurazione, tutte le chiamate in arrivo instradate da un trunk di questo tipo verranno considerate come originarie dello stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="9fd36-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="9fd36-115">Le chiamate degli utenti PBX avranno la stessa applicazione di routing basata sulla posizione degli utenti di Lync che si trovano nello stesso sito di rete del trunk.</span><span class="sxs-lookup"><span data-stu-id="9fd36-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="9fd36-116">Se due sistemi PBX situati in siti di rete separati sono connessi tramite Lync Server, il routing basato sulla posizione consentirà il routing da un endpoint PBX in un sito di rete a un altro endpoint PBX nell'altro sito di rete.</span><span class="sxs-lookup"><span data-stu-id="9fd36-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="9fd36-117">Questo scenario non verrà bloccato dal routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="9fd36-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="9fd36-118">Oltre a questo scenario e in modo simile a quello di un utente di Lync nella stessa posizione, gli endpoint connessi a un peer di Mediation Server con questa configurazione saranno in grado di effettuare o ricevere chiamate da e verso altri peer di Mediation Server che non instradano le chiamate alla rete PSTN (i. e. endpoint connesso a un PBX diverso indipendentemente dal sito di rete a cui è associato il peer di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9fd36-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="9fd36-119">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e i forward di chiamata che coinvolgono endpoint PSTN saranno soggetti al routing basato sulla posizione per usare solo gateway PSTN definiti come locali a tale peer di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9fd36-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9fd36-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fd36-120">See Also</span></span>


[<span data-ttu-id="9fd36-121">Linee guida per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fd36-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

