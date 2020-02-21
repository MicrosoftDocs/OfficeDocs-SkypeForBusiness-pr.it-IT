---
title: 'Lync Server 2013: come implementare il trunking SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d9b55dff41e0013852b52eee97eb26fef3997e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="47578-102">Come implementare il trunking SIP in Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="47578-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47578-103">_**Ultimo argomento modificato:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="47578-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="47578-104">Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra i client di Lync Server 2013 e il provider di servizi e i supporti di transcodifica, se necessario.</span><span class="sxs-lookup"><span data-stu-id="47578-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="47578-105">Ogni Mediation Server dispone di un'interfaccia di rete interna e di un'interfaccia di rete esterna.</span><span class="sxs-lookup"><span data-stu-id="47578-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="47578-106">L'interfaccia interna si connette ai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="47578-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="47578-107">L'interfaccia esterna è comunemente chiamata interfaccia gateway perché è stata utilizzata tradizionalmente per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="47578-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="47578-108">Per implementare un trunk SIP, è necessario connettere l'interfaccia esterna del Mediation Server al componente perimetrale esterno di ITSP.</span><span class="sxs-lookup"><span data-stu-id="47578-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47578-109">Il componente perimetrale esterno dell'ITSP potrebbe essere un servizio Session Border Controller (SBC), un router o un gateway.</span><span class="sxs-lookup"><span data-stu-id="47578-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="47578-110">Per informazioni dettagliate su Mediation Server, vedere [Mediation Server Component in Lync server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="47578-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="47578-111">Trunking SIP centralizzato o distribuito</span><span class="sxs-lookup"><span data-stu-id="47578-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="47578-112">*Centralizzata* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, tramite il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="47578-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="47578-113">Il modello di distribuzione centralizzato è semplice, redditizio ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47578-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="47578-114">*Distribuiti* Il trunking SIP è un modello di distribuzione in cui viene implementato un trunk SIP locale in uno o più siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="47578-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="47578-115">Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare attraverso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="47578-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="47578-116">Il trunking SIP distribuito è necessario solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="47578-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="47578-117">Il sito di succursale richiede la connettività del telefono superstite (ad esempio, se la rete WAN va verso il basso).</span><span class="sxs-lookup"><span data-stu-id="47578-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="47578-118">Questo requisito deve essere analizzato per ogni sito di succursale. alcuni dei rami possono richiedere ridondanza e failover, mentre altri potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="47578-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="47578-119">È necessaria una resilienza tra due siti centrali.</span><span class="sxs-lookup"><span data-stu-id="47578-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="47578-120">È necessario verificare che un trunk SIP termini in ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="47578-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="47578-121">Ad esempio, se si dispone di siti centrali Dublin e Tukwila ed entrambi utilizzano solo trunk SIP di un sito, se il trunk si abbassa, gli utenti dell'altro sito non possono effettuare chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="47578-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="47578-122">Il sito di succursale e il sito centrale si trovano in paesi/aree geografiche diverse.</span><span class="sxs-lookup"><span data-stu-id="47578-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="47578-123">Per motivi legali e di compatibilità, è necessario almeno un trunk SIP per paese.</span><span class="sxs-lookup"><span data-stu-id="47578-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="47578-124">Nell'Unione Europea ad esempio le comunicazioni non possono uscire da un paese senza terminare localmente in un punto centralizzato.</span><span class="sxs-lookup"><span data-stu-id="47578-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="47578-125">A seconda della posizione geografica dei siti e del traffico previsto all'interno dell'organizzazione, è possibile che non si desideri instradare tutti gli utenti nel trunk SIP centrale oppure che alcuni utenti vengano instradati tramite un trunk SIP nel relativo sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="47578-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="47578-126">Per valutare le proprie esigenze, analizzare gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="47578-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="47578-127">Quanto è grande ogni sito, ovvero il numero di utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="47578-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="47578-128">Numeri DID (Direct Inward Dialing) presso ogni sito che ricevono più telefonate</span><span class="sxs-lookup"><span data-stu-id="47578-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="47578-129">Per scegliere se distribuire il trunking SIP centralizzato o distribuito, è necessaria un'analisi costi-benefici.</span><span class="sxs-lookup"><span data-stu-id="47578-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="47578-130">In alcuni casi può essere vantaggioso scegliere il modello di trunking SIP distribuito, anche quando non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="47578-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="47578-131">In una distribuzione completamente centralizzata, tutto il traffico dei siti di succursale viene instradato su collegamenti WAN.</span><span class="sxs-lookup"><span data-stu-id="47578-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="47578-132">Per non incorrere nei costi della larghezza di banda necessaria per i collegamenti WAN, può essere preferibile utilizzare il trunking SIP distribuito.</span><span class="sxs-lookup"><span data-stu-id="47578-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="47578-133">Ad esempio, è consigliabile distribuire un server Standard Edition in un sito di succursale con la Federazione al sito centrale oppure è possibile distribuire un Survivable Branch Appliance o un Survivable Branch Server con un gateway di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="47578-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47578-134">Per informazioni dettagliate sul trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="47578-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="47578-135">Tipi di connessione supportati per il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="47578-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="47578-136">Lync Server supporta i tipi di connessione seguenti per il trunking SIP:</span><span class="sxs-lookup"><span data-stu-id="47578-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="47578-p109">MPLS (Multiprotocol Label Switching). Si tratta di una rete privata che indirizza e trasporta i dati da un nodo di rete al successivo. La larghezza di banda in una rete MPLS è condivisa con altri sottoscrittori e a ogni pacchetto dati è assegnata un'etichetta per distinguere i dati di un sottoscrittore da quelli di un altro. Questo tipo di connessione non richiede una rete privata virtuale (VPN). Un potenziale svantaggio è rappresentato dal rischio che un eccessivo traffico IP possa interferire con il funzionamento di VoIP, a meno che non venga assegnata priorità al traffico VoIP.</span><span class="sxs-lookup"><span data-stu-id="47578-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="47578-p110">Una connessione privata senza altro traffico, ad esempio una connessione su fibra ottica dedicata o linea T1. Questo tipo di connessione è in genere il più affidabile e sicuro. Garantisce un'elevata capacità di trasporto delle chiamate, ma è anche il più costoso. Non è richiesta una VPN. Le connessioni private sono appropriate per le organizzazioni con un elevato volume di chiamate o con requisiti di disponibilità e sicurezza rigorosi.</span><span class="sxs-lookup"><span data-stu-id="47578-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="47578-145">Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile.</span><span class="sxs-lookup"><span data-stu-id="47578-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="47578-146">La connessione Internet è l'unico tipo di connessione del trunking SIP di Lync Server che richiede la VPN.</span><span class="sxs-lookup"><span data-stu-id="47578-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="47578-147">Scelta di un tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="47578-147">Selecting a Connection Type</span></span>

<span data-ttu-id="47578-148">Il tipo di connessione per il trunking SIP più appropriato per la propria azienda dipende dalle diverse esigenze e dal budget a disposizione.</span><span class="sxs-lookup"><span data-stu-id="47578-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="47578-p112">Per un'azienda di medie o grandi dimensioni, una rete MPLS in genere è la soluzione più appropriata, poiché offre la larghezza di banda necessaria a una tariffa più conveniente rispetto a una rete privata specializzata.</span><span class="sxs-lookup"><span data-stu-id="47578-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="47578-151">Per le aziende di dimensioni maggiori può essere necessaria una connessione su fibra ottica privata, T1, T3 o superiore (E1, E3 o superiore nell'Unione Europea).</span><span class="sxs-lookup"><span data-stu-id="47578-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="47578-152">Per una piccola azienda o un sito di succursale con volume di chiamata basso, il trunking SIP tramite Internet potrebbe essere la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="47578-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="47578-153">Questo tipo di connessione non è consigliato per siti di medie o grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="47578-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="47578-154">Requisiti di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="47578-154">Bandwidth Requirements</span></span>

<span data-ttu-id="47578-p114">La larghezza di banda richiesta da un'implementazione dipende dalla capacità di chiamata, ovvero dal numero di chiamate simultanee che devono essere supportate. È necessario tenere conto della disponibilità della larghezza di banda in modo da poter usufruire pienamente della capacità di picco per cui si paga. Usare la formula seguente per calcolare il requisito di larghezza di banda di picco di un trunk SIP:</span><span class="sxs-lookup"><span data-stu-id="47578-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="47578-158">Larghezza di banda di picco di trunk SIP = Numero massimo di chiamate simultanee x (64 kbps + dimensioni delle intestazioni)</span><span class="sxs-lookup"><span data-stu-id="47578-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47578-159">Le dimensioni massime delle intestazioni corrispondono a 20 byte.</span><span class="sxs-lookup"><span data-stu-id="47578-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="47578-160">Supporto di codec</span><span class="sxs-lookup"><span data-stu-id="47578-160">Codec Support</span></span>

<span data-ttu-id="47578-161">Lync Server 2013 supporta solo i codec seguenti:</span><span class="sxs-lookup"><span data-stu-id="47578-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="47578-162">G.711 a-law (utilizzato principalmente al di fuori dell'America del Nord)</span><span class="sxs-lookup"><span data-stu-id="47578-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="47578-163">G.711 µ-law (utilizzato nell'America del Nord)</span><span class="sxs-lookup"><span data-stu-id="47578-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="47578-164">Provider di servizi di telefonia Internet</span><span class="sxs-lookup"><span data-stu-id="47578-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="47578-165">La modalità di implementazione del lato provider di servizi di una connessione trunk SIP varia da un ITSP all'altro.</span><span class="sxs-lookup"><span data-stu-id="47578-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="47578-166">Per informazioni sulla distribuzione, contattare il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="47578-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="47578-167">Per un elenco dei provider di servizi di trunking SIP certificati, vedere [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="47578-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="47578-168">Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il rappresentante Microsoft.</span><span class="sxs-lookup"><span data-stu-id="47578-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="47578-p116">È necessario usare un provider di servizi certificato Microsoft per garantire che il provider ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi. Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati. Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usarlo come ISP, passando a un provider certificato Microsoft per il trunking SIP.
</span><span class="sxs-lookup"><span data-stu-id="47578-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

