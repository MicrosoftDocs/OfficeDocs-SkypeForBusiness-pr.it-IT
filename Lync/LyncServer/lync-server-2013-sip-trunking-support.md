---
title: 'Lync Server 2013: Supporto per il trunking SIP'
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
ms.openlocfilehash: 58108df8795aaae8d431b320125d34d14ee3a275
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="97cbd-102">Supporto per il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97cbd-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97cbd-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="97cbd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="97cbd-104">Se si prevede di usare VoIP aziendale con il trunking SIP, è necessario distribuire un Mediation Server e verificare che altri componenti e infrastrutture soddisfino i requisiti di supporto appropriati per il modello di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="97cbd-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="97cbd-105">Per informazioni dettagliate su come determinare se implementare il trunking SIP, vedere [Panoramica del trunking SIP in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="97cbd-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="97cbd-106">È possibile usare il programma Microsoft Unified Communications Open Interoperability per l'infrastruttura per la telefonia aziendale per trovare i gateway PSTN (Public Switched Telephone Network) qualificati, i PBX IP e i servizi di trunking SIP, inclusa la telefonia IP qualificata provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="97cbd-107">Per informazioni dettagliate, vedere il sito Web Microsoft Unified Communications Open Interoperability Program all' [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="97cbd-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="97cbd-108">Supporto di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="97cbd-108">Mediation Server Support</span></span>

<span data-ttu-id="97cbd-109">Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra client Lync Server 2013 e il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="97cbd-110">Il Mediation Server decodifica il traffico multimediale da client e server e lo codifica di nuovo prima di inviarlo al provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="97cbd-111">La ricodifica è necessaria perché i trunk SIP non supportano alcuni codec usati, come la negoziazione in Real time audio (RTA) o il protocollo ICE (Interactive Connectivity Establishment) per l'attraversamento del firewall.</span><span class="sxs-lookup"><span data-stu-id="97cbd-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="97cbd-112">Ogni Mediation Server può avere due schede di rete, che offrono un'interfaccia di rete interna e esterna.</span><span class="sxs-lookup"><span data-stu-id="97cbd-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="97cbd-113">L'interfaccia esterna viene comunemente chiamata interfaccia gateway perché, tradizionalmente, è stata usata per la connessione a un gateway PSTN o a un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="97cbd-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="97cbd-114">Per implementare un trunk SIP, Connetti l'interfaccia esterna a un SBC (Session Border Controller) in un provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="97cbd-115">Trunking SIP distribuito o centralizzato</span><span class="sxs-lookup"><span data-stu-id="97cbd-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="97cbd-116">*Centralizzato* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il Data Center.</span><span class="sxs-lookup"><span data-stu-id="97cbd-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="97cbd-117">Il modello di distribuzione centralizzato è semplice, conveniente ed è in genere l'approccio preferito per l'implementazione di trunk SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97cbd-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="97cbd-118">A seconda dei modelli di utilizzo all'interno dell'organizzazione, potrebbe non essere necessario instradare tutti gli utenti tramite il trunk SIP centralizzato.</span><span class="sxs-lookup"><span data-stu-id="97cbd-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="97cbd-119">Per analizzare le proprie esigenze, rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="97cbd-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="97cbd-120">Quant'è grande ogni sito?</span><span class="sxs-lookup"><span data-stu-id="97cbd-120">How big is each site?</span></span> <span data-ttu-id="97cbd-121">Quanti utenti?</span><span class="sxs-lookup"><span data-stu-id="97cbd-121">How many users?</span></span>

  - <span data-ttu-id="97cbd-122">Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?</span><span class="sxs-lookup"><span data-stu-id="97cbd-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="97cbd-123">*Distribuiti* Trunking SIP è un modello di distribuzione in cui è possibile implementare un trunk SIP locale in uno o più siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="97cbd-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="97cbd-124">Il traffico VoIP viene quindi instradato dal sito della filiale direttamente al proprio provider di servizi, senza passare al Data Center.</span><span class="sxs-lookup"><span data-stu-id="97cbd-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="97cbd-125">Il trunking SIP distribuito è obbligatorio solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="97cbd-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="97cbd-126">Il sito della filiale richiede una connettività telefonica superstite, ad esempio se la rete WAN viene rimandata.</span><span class="sxs-lookup"><span data-stu-id="97cbd-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="97cbd-127">Se il ramo ha bisogno di ridondanza e failover, il provider di servizi addebiterà di più e la configurazione richiederà più tempo.</span><span class="sxs-lookup"><span data-stu-id="97cbd-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="97cbd-128">Questa operazione deve essere analizzata per ogni sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="97cbd-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="97cbd-129">Alcune delle branche potrebbero richiedere ridondanza e failover, mentre altre potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="97cbd-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="97cbd-130">Il sito e il centro dati della filiale si trovano in paesi/aree geografiche diverse.</span><span class="sxs-lookup"><span data-stu-id="97cbd-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="97cbd-131">Per motivi di compatibilità e legali, è necessario almeno un trunk SIP per paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="97cbd-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="97cbd-132">Decidere se distribuire il trunking SIP centralizzato o distribuito richiede un'analisi costi/benefici.</span><span class="sxs-lookup"><span data-stu-id="97cbd-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="97cbd-133">In alcuni casi, può essere vantaggioso optare per la modalità di distribuzione distribuita, anche se non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="97cbd-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="97cbd-134">In una distribuzione completamente centralizzata, tutto il traffico del sito della filiale viene instradato su collegamenti WAN.</span><span class="sxs-lookup"><span data-stu-id="97cbd-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="97cbd-135">Invece di pagare la larghezza di banda necessaria per il collegamento WAN, è consigliabile usare il trunking SIP distribuito.</span><span class="sxs-lookup"><span data-stu-id="97cbd-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97cbd-136">Per informazioni dettagliate sul motivo e sulla modalità di utilizzo del trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="97cbd-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="97cbd-137">Tipi di connessione di trunking SIP supportati</span><span class="sxs-lookup"><span data-stu-id="97cbd-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="97cbd-138">Lync Server 2013 supporta i tipi di connessione seguenti per il trunking SIP:</span><span class="sxs-lookup"><span data-stu-id="97cbd-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="97cbd-139">Il cambio di etichetta Multiprotocol (MPLS) è una rete privata che indirizza e trasporta i dati da un nodo di rete a quello successivo.</span><span class="sxs-lookup"><span data-stu-id="97cbd-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="97cbd-140">La larghezza di banda in una rete MPLS viene condivisa con altri abbonati e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un utente da un altro.</span><span class="sxs-lookup"><span data-stu-id="97cbd-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="97cbd-141">Questo tipo di connessione non richiede VPN.</span><span class="sxs-lookup"><span data-stu-id="97cbd-141">This connection type does not require VPN.</span></span> <span data-ttu-id="97cbd-142">Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP, a meno che non venga data priorità al traffico VoIP.</span><span class="sxs-lookup"><span data-stu-id="97cbd-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="97cbd-143">Una connessione privata senza altro traffico è in genere il tipo di connessione più affidabile e sicuro, ad esempio una connessione in fibra ottica affittata o una linea T1.</span><span class="sxs-lookup"><span data-stu-id="97cbd-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="97cbd-144">Questo tipo di connessione offre la maggiore capacità di trasporto delle chiamate, ma in genere è la più costosa.</span><span class="sxs-lookup"><span data-stu-id="97cbd-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="97cbd-145">La VPN non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="97cbd-145">VPN is not required.</span></span> <span data-ttu-id="97cbd-146">Le connessioni private sono appropriate per le organizzazioni con elevati volumi di chiamate o requisiti di sicurezza e disponibilità severi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="97cbd-147">Internet pubblico è il tipo di connessione meno costoso, ma anche il meno affidabile e quello con la più bassa capacità di trasporto delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="97cbd-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="97cbd-148">Il provider di servizi di telefonia Internet (ITSP) può aiutare a proteggere questo tipo di connessione trunk SIP se supporta TLS (Transport Layer Security) e SRTP (Secure Real-Time Transport Protocol) per crittografare il traffico di segnalazione e multimediale.</span><span class="sxs-lookup"><span data-stu-id="97cbd-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="97cbd-149">Se non è possibile configurare una connessione trunk SIP tramite Internet per l'uso di TLS e SRTP, è consigliabile usare un tunnel VPN per garantire una connessione più sicura.</span><span class="sxs-lookup"><span data-stu-id="97cbd-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="97cbd-150">Contattare il ITSP per determinare se fornisce il supporto per TLS con SRTP.</span><span class="sxs-lookup"><span data-stu-id="97cbd-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="97cbd-151">Selezione di un tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="97cbd-151">Selecting a Connection Type</span></span>

<span data-ttu-id="97cbd-152">Il tipo di connessione di trunking SIP più appropriato per l'azienda dipende dalle esigenze e dal budget.</span><span class="sxs-lookup"><span data-stu-id="97cbd-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="97cbd-153">Per un'azienda di medie dimensioni o più grande, una rete MPLS fornisce in genere il valore più elevato.</span><span class="sxs-lookup"><span data-stu-id="97cbd-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="97cbd-154">Può specificare la larghezza di banda necessaria a una tariffa più economica rispetto a una rete privata specializzata.</span><span class="sxs-lookup"><span data-stu-id="97cbd-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="97cbd-155">Le grandi imprese possono richiedere una connessione a fibre ottiche o T1 private.</span><span class="sxs-lookup"><span data-stu-id="97cbd-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="97cbd-156">Per una piccola impresa o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="97cbd-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="97cbd-157">Questo tipo di connessione non è tuttavia consigliato per i siti di medie dimensioni o più grandi.</span><span class="sxs-lookup"><span data-stu-id="97cbd-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="97cbd-158">Supporto per codec</span><span class="sxs-lookup"><span data-stu-id="97cbd-158">Codec Support</span></span>

<span data-ttu-id="97cbd-159">Il proxy del provider di servizi deve supportare i codec seguenti:</span><span class="sxs-lookup"><span data-stu-id="97cbd-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="97cbd-160">G. 711 a-Law (usato principalmente al di fuori del Nord America)</span><span class="sxs-lookup"><span data-stu-id="97cbd-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="97cbd-161">G. 711 µ-Law (usato in Nord America)</span><span class="sxs-lookup"><span data-stu-id="97cbd-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

