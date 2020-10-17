---
title: 'Lync Server 2013: Panoramica del bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b354ff3f2f22cbfb03974eaa7bc164ce4b7679d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520933"
---
# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="27d5a-102">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d5a-102">Overview of media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27d5a-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="27d5a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="27d5a-104">La funzionalità bypass multimediale è utile se si desidera ridurre il numero dei Mediation Server distribuiti.</span><span class="sxs-lookup"><span data-stu-id="27d5a-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="27d5a-105">Un pool Mediation Server viene in genere distribuito in un sito centrale e controlla i gateway nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="27d5a-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="27d5a-106">Abilitando il bypass multimediale, gli elementi multimediali per chiamate PSTN da client dei siti di succursale possono attraversare direttamente i gateway di tali siti.</span><span class="sxs-lookup"><span data-stu-id="27d5a-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="27d5a-107">Lync Server 2013 le route delle chiamate in uscita e i criteri VoIP aziendale devono essere adeguatamente configurati in modo che le chiamate PSTN dai client in un sito di succursale vengano instradate al gateway appropriato.</span><span class="sxs-lookup"><span data-stu-id="27d5a-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="27d5a-p102">Nelle reti Wi-Fi in genere si verificano più perdite di pacchetti rispetto alle reti cablate. Il recupero da queste perdite di pacchetti non può solitamente essere supportato dai gateway. Pertanto, è consigliabile valutare la qualità di una rete Wi-Fi prima di stabilire se abilitare il bypass per una subnet wireless. È inoltre necessario valutare il compromesso tra la riduzione della latenza e la perdita di pacchetti. RTAudio, un codec non disponibile per le chiamate che non aggirano il Mediation Server, è più indicato per la gestione della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="27d5a-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="27d5a-113">Dopo l'implementazione della struttura di VoIP aziendale, la pianificazione del bypass multimediale è semplice.</span><span class="sxs-lookup"><span data-stu-id="27d5a-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="27d5a-114">Se si dispone di una topologia centralizzata senza collegamenti WAN ai siti di succursale, è possibile abilitare un bypass multimediale globale, perché non è necessario un controllo capillare.</span><span class="sxs-lookup"><span data-stu-id="27d5a-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="27d5a-115">Se si dispone di una topologia distribuita costituita da una o più aree di rete e relativi siti di succursale affiliati, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="27d5a-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="27d5a-116">Se i peer di Mediation Server sono in grado di supportare le funzionalità necessarie per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="27d5a-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="27d5a-117">Quali siti in ogni area di rete sono ben connessi.</span><span class="sxs-lookup"><span data-stu-id="27d5a-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="27d5a-118">Quale combinazione di bypass multimediale e controllo di ammissione di chiamata è appropriato per la rete.</span><span class="sxs-lookup"><span data-stu-id="27d5a-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="27d5a-p103">Quando si abilita il bypass multimediale, viene generato automaticamente un ID bypass univoco per un'area della rete e per tutti i siti della rete senza vincoli di larghezza di banda nell'ambito di tale area. Ai siti con vincoli di larghezza di banda nell'ambito dell'area e ai siti connessi a tale area tramite collegamenti WAN con vincoli di larghezza di banda vengono assegnati ID di bypass univoci specifici.</span><span class="sxs-lookup"><span data-stu-id="27d5a-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="27d5a-121">Quando un utente effettua una chiamata alla rete PSTN, Mediation Server confronta l'ID di bypass della subnet client con l'ID di bypass della subnet del gateway.</span><span class="sxs-lookup"><span data-stu-id="27d5a-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="27d5a-122">Se i due ID combaciano, per la chiamata viene utilizzato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="27d5a-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="27d5a-123">Se gli ID di bypass non corrispondono, il supporto per la chiamata deve fluire tramite Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="27d5a-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="27d5a-124">Quando un utente riceve una chiamata dalla rete PSTN, il client dell'utente confronta il proprio ID bypass a quello del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="27d5a-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="27d5a-125">Se i due ID di bypass corrispondono, i flussi multimediali passano direttamente dal gateway al client, ignorando il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="27d5a-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="27d5a-126">Solo i client e i dispositivi Lync 2010 o superiori supportano le interazioni di bypass multimediale con un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="27d5a-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="27d5a-p106">Oltre che a livello globale, il bypass multimediale deve essere abilitato singolarmente in ogni trunk PSTN. Se il bypass viene abilitato globalmente ma non per un determinato trunk PSTN, non verrà richiamato per le chiamate che coinvolgono questo trunk PSTN. Inoltre, se il bypass multimediale è impostato per l'utilizzo delle informazioni del sito e dell'area geografica,<STRONG></STRONG> è necessario associare tutte le subnet instradabili ai siti in cui si trovano. Se in un sito sono presenti subnet instradabili per cui non si desidera il bypass, sarà necessario raggruppare queste subnet in un nuovo sito prima di abilitare il bypass multimediale. In questo modo, le subnet non instradabili verranno assegnate a un ID bypass diverso.</span><span class="sxs-lookup"><span data-stu-id="27d5a-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27d5a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d5a-132">See Also</span></span>


[<span data-ttu-id="27d5a-133">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d5a-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="27d5a-134">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d5a-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="27d5a-135">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d5a-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

