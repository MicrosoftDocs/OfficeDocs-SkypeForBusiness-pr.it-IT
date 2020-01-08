---
title: 'Lync Server 2013: Panoramica del bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="18c3a-102">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c3a-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c3a-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="18c3a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="18c3a-104">Il bypass multimediale è utile quando si vuole ridurre al minimo il numero di server di mediazione distribuiti.</span><span class="sxs-lookup"><span data-stu-id="18c3a-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="18c3a-105">In genere, un pool di Mediation Server verrà distribuito in un sito centrale e controllerà i gateway nei siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="18c3a-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="18c3a-106">L'abilitazione del bypass multimediale consente alle chiamate PSTN (Public Switched Telephone Network) dei client in siti di succursale di scorrere direttamente attraverso i gateway in questi siti.</span><span class="sxs-lookup"><span data-stu-id="18c3a-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="18c3a-107">Le route delle chiamate in uscita di Lync Server 2013 e i criteri VoIP aziendale devono essere configurati correttamente in modo che le chiamate PSTN da client in un sito di succursale vengano indirizzate al gateway appropriato.</span><span class="sxs-lookup"><span data-stu-id="18c3a-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="18c3a-108">Le reti Wi-Fi in genere avvertono più perdita di pacchetti rispetto alle reti cablate.</span><span class="sxs-lookup"><span data-stu-id="18c3a-108">Wi-Fi networks typically experience more packet loss than wired networks.</span></span> <span data-ttu-id="18c3a-109">Il ripristino da questa perdita di pacchetti non è in genere un elemento che può essere ospitato da gateway.</span><span class="sxs-lookup"><span data-stu-id="18c3a-109">Recovery from this packet loss is not typically something that can be accommodated by gateways.</span></span> <span data-ttu-id="18c3a-110">Per questo motivo, ti consigliamo di valutare la qualità di una rete Wi-Fi prima di determinare se l'esclusione deve essere abilitata per una subnet wireless.</span><span class="sxs-lookup"><span data-stu-id="18c3a-110">Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet.</span></span> <span data-ttu-id="18c3a-111">C'è un compromesso nella riduzione della latenza rispetto al recupero dalla perdita di pacchetti da considerare anche.</span><span class="sxs-lookup"><span data-stu-id="18c3a-111">There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well.</span></span> <span data-ttu-id="18c3a-112">RTAudio, un codec disponibile per le chiamate che non ignorano il Mediation Server, è più adatto per la gestione della perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="18c3a-112">RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="18c3a-113">Una volta posizionata la struttura VoIP aziendale, la pianificazione per il bypass multimediale è semplice.</span><span class="sxs-lookup"><span data-stu-id="18c3a-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="18c3a-114">Se si ha una topologia centralizzata senza collegamenti WAN a siti di succursale, è possibile abilitare il bypass multimediale globale, perché il controllo ottimizzato non è necessario.</span><span class="sxs-lookup"><span data-stu-id="18c3a-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="18c3a-115">Se si dispone di una topologia distribuita costituita da una o più aree di rete e dai siti di filiale affiliati, determinare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18c3a-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="18c3a-116">Se i peer di Mediation Server sono in grado di supportare le funzionalità necessarie per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="18c3a-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="18c3a-117">I siti di ogni area di rete sono ben connessi.</span><span class="sxs-lookup"><span data-stu-id="18c3a-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="18c3a-118">Quale combinazione di bypass multimediale e controllo di ammissione di chiamata è appropriata per la rete.</span><span class="sxs-lookup"><span data-stu-id="18c3a-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="18c3a-119">Quando si Abilita il bypass multimediale, viene generato automaticamente un ID di bypass univoco per un'area di rete e per tutti i siti di rete senza vincoli di larghezza di banda all'interno dell'area geografica.</span><span class="sxs-lookup"><span data-stu-id="18c3a-119">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region.</span></span> <span data-ttu-id="18c3a-120">I siti con vincoli di larghezza di banda nell'area geografica e i siti connessi all'area geografica con collegamenti WAN con vincoli di larghezza di banda sono assegnati ad ognuno un ID di bypass univoco.</span><span class="sxs-lookup"><span data-stu-id="18c3a-120">Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="18c3a-121">Quando un utente effettua una chiamata alla rete PSTN, il Mediation Server confronta l'ID di bypass della subnet client con l'ID di bypass della subnet del gateway.</span><span class="sxs-lookup"><span data-stu-id="18c3a-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="18c3a-122">Se i due ID di bypass corrispondono, per la chiamata viene usato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="18c3a-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="18c3a-123">Se gli ID di bypass non corrispondono, il supporto per la chiamata deve fluire attraverso il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="18c3a-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="18c3a-124">Quando un utente riceve una chiamata dalla rete PSTN, il client dell'utente confronta il proprio ID di esclusione con quello del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="18c3a-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="18c3a-125">Se i due ID di bypass corrispondono, il flusso multimediale passa direttamente dal gateway al client, bypassando il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="18c3a-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="18c3a-126">Solo i client e i dispositivi Lync 2010 o superiore supportano le interazioni media bypass con un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="18c3a-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="18c3a-127">Oltre a consentire il bypass multimediale a livello globale, è necessario abilitare individualmente il bypass multimediale in ogni trunk PSTN.</span><span class="sxs-lookup"><span data-stu-id="18c3a-127">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk.</span></span> <span data-ttu-id="18c3a-128">Se il bypass è abilitato globalmente, ma non è abilitato per un trunk PSTN specifico, il bypass multimediale non verrà richiamato per le chiamate che coinvolgono il trunk PSTN.</span><span class="sxs-lookup"><span data-stu-id="18c3a-128">If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk.</span></span> <span data-ttu-id="18c3a-129">Inoltre, quando il bypass multimediale è impostato per l' <STRONG>uso di informazioni sul sito e sull'area geografica</STRONG>, è necessario associare tutte le subnet instradabili ai siti in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="18c3a-129">In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located.</span></span> <span data-ttu-id="18c3a-130">Se sono presenti subnet instradabili all'interno di un sito per cui il bypass non è desiderato, queste subnet devono essere raggruppate all'interno di un nuovo sito prima di abilitare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="18c3a-130">If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass.</span></span> <span data-ttu-id="18c3a-131">In questo modo si assicurerà che alle subnet non instradabili sia assegnato un ID di bypass diverso.</span><span class="sxs-lookup"><span data-stu-id="18c3a-131">Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18c3a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18c3a-132">See Also</span></span>


[<span data-ttu-id="18c3a-133">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c3a-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="18c3a-134">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c3a-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="18c3a-135">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18c3a-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

