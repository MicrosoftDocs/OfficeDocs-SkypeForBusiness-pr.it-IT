---
title: Supporto per il trunking SIP di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fd2bd6d66b8b4f040e654f2412f86027071f9ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="0e711-102">Supporto per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e711-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e711-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0e711-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0e711-104">Se si prevede di utilizzare VoIP aziendale con trunking SIP, è necessario distribuire un Mediation Server e verificare che altre infrastrutture e componenti soddisfino i requisiti di supporto adatti al modello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0e711-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="0e711-105">Per informazioni dettagliate sulla determinazione dell'implementazione del trunking SIP, vedere [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0e711-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="0e711-106">È possibile utilizzare il programma Microsoft Unified Communications Open Interoperability Program for Enterprise telefonia Infrastructure per trovare i gateway PSTN (Public Switched Telephone Network), i sistemi IP-PBX e i servizi di trunking SIP, inclusa la telefonia IP qualificata provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="0e711-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="0e711-107">Per ulteriori informazioni, vedere il sito Web Microsoft Unified Communications Open Interoperability Program all' [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0e711-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="0e711-108">Supporto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="0e711-108">Mediation Server Support</span></span>

<span data-ttu-id="0e711-109">Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra i client di Lync Server 2013 e il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="0e711-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="0e711-110">Il Mediation Server decodifica il traffico multimediale proveniente da client e server e lo ricodifica prima di inviarlo al provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="0e711-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="0e711-111">La ricodifica è necessaria perché i trunk SIP non supportano alcuni codec utilizzati, ad esempio la negoziazione di protocollo di accesso interattivi (RTA) o Interactive Connectivity Establishment (ICE) per l'attraversamento del firewall.</span><span class="sxs-lookup"><span data-stu-id="0e711-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="0e711-112">Ogni Mediation Server può includere due schede di rete, che forniscono un'interfaccia di rete interna e una esterna.</span><span class="sxs-lookup"><span data-stu-id="0e711-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="0e711-113">L'interfaccia esterna è comunemente chiamata interfaccia gateway perché, tradizionalmente, è stata utilizzata per la connessione a un gateway PSTN o a un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="0e711-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="0e711-114">Per implementare un trunk SIP, connettere l'interfaccia esterna a un SBC (Session Border Controller) presso un provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="0e711-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="0e711-115">Trunking SIP centralizzato o distribuito</span><span class="sxs-lookup"><span data-stu-id="0e711-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="0e711-116">*Centralizzata* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il Data Center.</span><span class="sxs-lookup"><span data-stu-id="0e711-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="0e711-117">Il modello di distribuzione centralizzato è semplice, redditizio ed è in genere l'approccio preferito per l'implementazione dei trunk SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e711-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="0e711-p106">A seconda dei modelli di utilizzo adottati dall'organizzazione, è possibile decidere di non instradare tutti gli utente attraverso il trunk SIP centralizzato. Per analizzare le specifiche esigenze, rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e711-p106">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk. To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="0e711-p107">Quanto è grande ogni sito? Quanti utenti?</span><span class="sxs-lookup"><span data-stu-id="0e711-p107">How big is each site? How many users?</span></span>

  - <span data-ttu-id="0e711-122">Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?</span><span class="sxs-lookup"><span data-stu-id="0e711-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="0e711-p108">Il trunking SIP *distribuito* è un modello di distribuzione in cui si implementa un trunk SIP locale in uno o più siti di succursale. Il traffico VoIP viene quindi instradato dal sito di succursale direttamente al provider di servizi, senza passare per il data center.</span><span class="sxs-lookup"><span data-stu-id="0e711-p108">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites. VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="0e711-125">Il trunking SIP distribuito è necessario solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e711-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="0e711-126">Il sito di succursale richiede la connettività del telefono superstite (ad esempio, se la rete WAN va verso il basso).</span><span class="sxs-lookup"><span data-stu-id="0e711-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="0e711-127">Se il Branch ha bisogno di ridondanza e failover, il provider di servizi addebiterà di più e la configurazione richiederà più tempo.</span><span class="sxs-lookup"><span data-stu-id="0e711-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="0e711-128">Questo dovrebbe essere analizzato per ogni sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="0e711-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="0e711-129">Alcuni dei rami potrebbero richiedere ridondanza e failover, mentre altri potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="0e711-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="0e711-p110">Il sito di succursale e il data center si trovano in paesi o aree geografiche diverse. Per motivi legali e di compatibilità, è necessario almeno un trunk SIP per ogni paese o area geografica.</span><span class="sxs-lookup"><span data-stu-id="0e711-p110">The branch site and data center are in different countries/regions. For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="0e711-132">Se si decide di distribuire il trunking SIP centralizzato o distribuito, è necessaria un'analisi costi/benefici.</span><span class="sxs-lookup"><span data-stu-id="0e711-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="0e711-133">In alcuni casi, può essere vantaggioso optare per la modalità di distribuzione distribuita, anche se non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="0e711-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="0e711-134">In una distribuzione completamente centralizzata, tutto il traffico dei siti di succursale viene instradato su collegamenti WAN.</span><span class="sxs-lookup"><span data-stu-id="0e711-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="0e711-135">Per non incorrere nei costi della larghezza di banda necessaria per i collegamenti WAN, può essere preferibile utilizzare il trunking SIP distribuito.</span><span class="sxs-lookup"><span data-stu-id="0e711-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e711-136">Per informazioni dettagliate sul perché e su come utilizzare il trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">branching SIP trunking site in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="0e711-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="0e711-137">Tipi di connessione supportati per il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="0e711-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="0e711-138">Lync Server 2013 supporta i tipi di connessione seguenti per il trunking SIP:</span><span class="sxs-lookup"><span data-stu-id="0e711-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="0e711-p112">MPLS (Multiprotocol Label Switching) è una rete privata che indirizza e trasferisce i dati da un nodo di rete al successivo. La larghezza di banda di una rete MPLS è condivisa con altri sottoscrittori e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un sottoscrittore da quelli di un altro. Questo tipo di connessione non richiede VPN. Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP a meno che non abbai priorità.</span><span class="sxs-lookup"><span data-stu-id="0e711-p112">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require VPN. A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="0e711-p113">Una connessione privata senza altro traffico è in genere il tipo più affidabile e sicuro, ad esempio una connessione in fibra ottica dedicata, o linea T1. Questo tipo di connessione offre la massima capacità per il trasferimento delle chiamate, ma è in genere la più costosa. Non è richiesta una VPN. Le connessioni private sono appropriate per organizzazioni con volumi di chiamate elevate o requisiti rigorosi di sicurezza e disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0e711-p113">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line). This connection type provides the highest call-carrying capacity, but is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="0e711-147">La rete Internet pubblica è il tipo di connessione meno costosa, ma anche la meno affidabile e quella con la capacità minore di trasferimento di chiamate.</span><span class="sxs-lookup"><span data-stu-id="0e711-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="0e711-148">Il provider di servizi di telefonia Internet (ITSP) consente di proteggere questo tipo di connessione trunk SIP se supporta TLS (Transport Layer Security) e SRTP (Secure Real-Time Transport Protocol) per crittografare la segnalazione e il traffico multimediale.</span><span class="sxs-lookup"><span data-stu-id="0e711-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="0e711-149">Se non è possibile configurare una connessione di trunk SIP tramite Internet per l'utilizzo di TLS e SRTP, è consigliabile utilizzare un tunnel VPN per una maggiore sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0e711-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="0e711-150">Contattare l'ITSP per verificare se fornisce il supporto per TLS con SRTP.</span><span class="sxs-lookup"><span data-stu-id="0e711-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="0e711-151">Selezione di un tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="0e711-151">Selecting a Connection Type</span></span>

<span data-ttu-id="0e711-152">Il tipo di connessione per il trunking SIP più appropriato per la propria azienda dipende dalle diverse esigenze e dal budget a disposizione.</span><span class="sxs-lookup"><span data-stu-id="0e711-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="0e711-153">Per un'azienda di medie o grandi dimensioni, una rete MPLS fornisce generalmente la maggior parte dei valori.</span><span class="sxs-lookup"><span data-stu-id="0e711-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="0e711-154">È in grado di fornire la larghezza di banda necessaria a un tasso più conveniente rispetto a una rete privata specializzata.</span><span class="sxs-lookup"><span data-stu-id="0e711-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="0e711-155">Per le grandi aziende può essere necessaria una connessione in fibra ottica privata o T1.</span><span class="sxs-lookup"><span data-stu-id="0e711-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="0e711-156">Per una piccola azienda o un sito di succursale con volume di chiamata basso, il trunking SIP tramite Internet potrebbe essere la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="0e711-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="0e711-157">Tuttavia, questo tipo di connessione non è consigliato per siti di medie o grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0e711-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="0e711-158">Codec supportati</span><span class="sxs-lookup"><span data-stu-id="0e711-158">Codec Support</span></span>

<span data-ttu-id="0e711-159">Il proxy del provider di servizi deve supportare i codec seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e711-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="0e711-160">G.711 a-law (utilizzato prevalentemente all'esterno del Nord America)</span><span class="sxs-lookup"><span data-stu-id="0e711-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="0e711-161">G.711 µ-law (utilizzato in Nord America)</span><span class="sxs-lookup"><span data-stu-id="0e711-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

