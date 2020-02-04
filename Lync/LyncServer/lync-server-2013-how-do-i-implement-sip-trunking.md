---
title: 'Lync Server 2013: Come implementare il trunking SIP'
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
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="b9970-102">Come implementare il trunking SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9970-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9970-103">_**Argomento Ultima modifica:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="b9970-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="b9970-104">Per implementare il trunking SIP, è necessario instradare la connessione tramite un Mediation Server, che funge da proxy per le sessioni di comunicazione tra client Lync Server 2013 e il provider di servizi e transcodifica il contenuto multimediale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="b9970-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="b9970-105">Ogni Mediation Server include un'interfaccia di rete interna e un'interfaccia di rete esterna.</span><span class="sxs-lookup"><span data-stu-id="b9970-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="b9970-106">L'interfaccia interna si connette ai server front-end.</span><span class="sxs-lookup"><span data-stu-id="b9970-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="b9970-107">L'interfaccia esterna viene comunemente chiamata interfaccia gateway perché è stata usata tradizionalmente per connettere il Mediation Server a un gateway PSTN (Public Switched Telephone Network) o a un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b9970-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="b9970-108">Per implementare un trunk SIP, Connetti l'interfaccia esterna di Mediation Server al componente bordo esterno di ITSP.</span><span class="sxs-lookup"><span data-stu-id="b9970-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9970-109">Il componente bordo esterno di ITSP può essere un SBC (Session Border Controller), un router o un gateway.</span><span class="sxs-lookup"><span data-stu-id="b9970-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="b9970-110">Per informazioni dettagliate su Mediation Server, vedere [Componente Mediation Server in Lync server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="b9970-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="b9970-111">Trunking SIP distribuito o centralizzato</span><span class="sxs-lookup"><span data-stu-id="b9970-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="b9970-112">*Centralizzato* Il trunking SIP instrada tutto il traffico VoIP (Voice over Internet Protocol), incluso il traffico del sito di succursale, attraverso il sito centrale.</span><span class="sxs-lookup"><span data-stu-id="b9970-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="b9970-113">Il modello di distribuzione centralizzato è semplice, conveniente ed è in genere l'approccio consigliato per l'implementazione di trunk SIP con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9970-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="b9970-114">*Distribuiti* Trunking SIP è un modello di distribuzione in cui è possibile implementare un trunk SIP locale in uno o più siti di succursale.</span><span class="sxs-lookup"><span data-stu-id="b9970-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="b9970-115">Il traffico VoIP viene quindi instradato dal sito di succursale direttamente a un provider di servizi senza passare al sito centrale.</span><span class="sxs-lookup"><span data-stu-id="b9970-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="b9970-116">Il trunking SIP distribuito è obbligatorio solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9970-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="b9970-117">Il sito della filiale richiede una connettività telefonica superstite, ad esempio se la rete WAN viene rimandata.</span><span class="sxs-lookup"><span data-stu-id="b9970-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="b9970-118">Questo requisito deve essere analizzato per ogni sito filiale; alcune delle branche potrebbero richiedere ridondanza e failover, mentre altre potrebbero non essere disponibili.</span><span class="sxs-lookup"><span data-stu-id="b9970-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="b9970-119">La resilienza è necessaria tra due siti centrali.</span><span class="sxs-lookup"><span data-stu-id="b9970-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="b9970-120">È necessario assicurarsi che un trunk SIP termini in ogni sito centrale.</span><span class="sxs-lookup"><span data-stu-id="b9970-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="b9970-121">Se ad esempio sono presenti i siti centrali Dublin e Tukwila ed entrambi usano solo il trunk SIP di un sito, se il trunk scende, gli utenti dell'altro sito non possono effettuare chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="b9970-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="b9970-122">Il sito della filiale e il sito centrale si trovano in paesi/aree geografiche diverse.</span><span class="sxs-lookup"><span data-stu-id="b9970-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="b9970-123">Per motivi di compatibilità e legali, è necessario almeno un trunk SIP per paese/area geografica.</span><span class="sxs-lookup"><span data-stu-id="b9970-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="b9970-124">Ad esempio, nell'Unione europea le comunicazioni non possono uscire da un paese/area geografica senza terminare localmente in un punto centralizzato.</span><span class="sxs-lookup"><span data-stu-id="b9970-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="b9970-125">A seconda della posizione geografica dei siti e della quantità di traffico che anticipi all'interno dell'organizzazione, potresti non voler instradare tutti gli utenti tramite il trunk SIP centrale oppure scegliere di instradare alcuni utenti attraverso un trunk SIP presso il proprio sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="b9970-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="b9970-126">Per analizzare le proprie esigenze, rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9970-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="b9970-127">Quanto è grande ogni sito, ovvero il numero di utenti abilitati per VoIP aziendale?</span><span class="sxs-lookup"><span data-stu-id="b9970-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="b9970-128">Quali numeri DID (Direct Inward Dialing) in ogni sito ricevono la maggior parte delle telefonate?</span><span class="sxs-lookup"><span data-stu-id="b9970-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="b9970-129">La decisione di distribuire il trunking SIP centralizzato o distribuito richiede un'analisi costi/benefici.</span><span class="sxs-lookup"><span data-stu-id="b9970-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="b9970-130">In alcuni casi, può essere vantaggioso optare per il modello di distribuzione distribuita anche se non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="b9970-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="b9970-131">In una distribuzione completamente centralizzata, tutto il traffico del sito della filiale viene instradato su collegamenti WAN.</span><span class="sxs-lookup"><span data-stu-id="b9970-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="b9970-132">Invece di pagare la larghezza di banda necessaria per il collegamento WAN, è consigliabile usare il trunking SIP distribuito.</span><span class="sxs-lookup"><span data-stu-id="b9970-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="b9970-133">Ad esempio, potresti voler distribuire un server standard in un sito di succursale con la Federazione al sito centrale oppure vuoi distribuire un Survivable Branch Appliance o un Survivable Branch Server con un piccolo gateway.</span><span class="sxs-lookup"><span data-stu-id="b9970-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9970-134">Per informazioni dettagliate sul trunking SIP distribuito, vedere <A href="lync-server-2013-branch-site-sip-trunking.md">trunking SIP del sito di succursale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b9970-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="b9970-135">Tipi di connessione di trunking SIP supportati</span><span class="sxs-lookup"><span data-stu-id="b9970-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="b9970-136">Lync Server supporta i tipi di connessione seguenti per il trunking SIP:</span><span class="sxs-lookup"><span data-stu-id="b9970-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="b9970-137">Il cambio di etichetta Multiprotocol (MPLS) è una rete privata che indirizza e trasporta i dati da un nodo di rete a quello successivo.</span><span class="sxs-lookup"><span data-stu-id="b9970-137">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="b9970-138">La larghezza di banda in una rete MPLS viene condivisa con altri abbonati e a ogni pacchetto di dati viene assegnata un'etichetta per distinguere i dati di un utente da un altro.</span><span class="sxs-lookup"><span data-stu-id="b9970-138">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="b9970-139">Questo tipo di connessione non richiede una rete privata virtuale (VPN).</span><span class="sxs-lookup"><span data-stu-id="b9970-139">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="b9970-140">Un potenziale svantaggio è che il traffico IP eccessivo può interferire con l'operazione VoIP, a meno che non venga data priorità al traffico VoIP.</span><span class="sxs-lookup"><span data-stu-id="b9970-140">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="b9970-141">Una connessione privata senza altro traffico, ad esempio una connessione in fibra ottica affittata o una linea T1, è in genere il tipo di connessione più affidabile e sicuro.</span><span class="sxs-lookup"><span data-stu-id="b9970-141">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="b9970-142">Questo tipo di connessione offre la maggiore capacità di trasporto delle chiamate, ma in genere è la più costosa.</span><span class="sxs-lookup"><span data-stu-id="b9970-142">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="b9970-143">La VPN non è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b9970-143">VPN is not required.</span></span> <span data-ttu-id="b9970-144">Le connessioni private sono appropriate per le organizzazioni con elevati volumi di chiamate o requisiti di sicurezza e disponibilità severi.</span><span class="sxs-lookup"><span data-stu-id="b9970-144">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="b9970-145">Internet è il tipo di connessione meno costoso, ma è anche il meno affidabile.</span><span class="sxs-lookup"><span data-stu-id="b9970-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="b9970-146">Connessione Internet è l'unico tipo di connessione di trunking SIP di Lync Server che richiede VPN.</span><span class="sxs-lookup"><span data-stu-id="b9970-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="b9970-147">Selezione di un tipo di connessione</span><span class="sxs-lookup"><span data-stu-id="b9970-147">Selecting a Connection Type</span></span>

<span data-ttu-id="b9970-148">Il tipo di connessione di trunking SIP più appropriato per l'azienda dipende dalle esigenze e dal budget.</span><span class="sxs-lookup"><span data-stu-id="b9970-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="b9970-149">Per un'azienda di medie dimensioni o più grande, una rete MPLS offre in genere il valore più grande.</span><span class="sxs-lookup"><span data-stu-id="b9970-149">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="b9970-150">Può specificare la larghezza di banda necessaria a una tariffa più economica rispetto a una rete privata specializzata.</span><span class="sxs-lookup"><span data-stu-id="b9970-150">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="b9970-151">Le grandi imprese possono richiedere una connessione a fibre ottiche, T1, T3 o superiore privata (E1, E3 o superiore nell'Unione europea).</span><span class="sxs-lookup"><span data-stu-id="b9970-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="b9970-152">Per una piccola impresa o un sito di succursale con un volume di chiamate basso, il trunking SIP tramite Internet può essere la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="b9970-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="b9970-153">Questo tipo di connessione non è consigliato per i siti di medie dimensioni o più grandi.</span><span class="sxs-lookup"><span data-stu-id="b9970-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="b9970-154">Requisiti di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="b9970-154">Bandwidth Requirements</span></span>

<span data-ttu-id="b9970-155">La quantità di larghezza di banda necessaria per l'implementazione dipende dalla capacità delle chiamate (il numero di chiamate simultanee che è necessario supportare).</span><span class="sxs-lookup"><span data-stu-id="b9970-155">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="b9970-156">È necessario prendere in considerazione la disponibilità della larghezza di banda, in modo da poter sfruttare al massimo la capacità di picco pagata.</span><span class="sxs-lookup"><span data-stu-id="b9970-156">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="b9970-157">Usare la formula seguente per calcolare il fabbisogno di larghezza di banda Peak del trunk SIP:</span><span class="sxs-lookup"><span data-stu-id="b9970-157">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="b9970-158">Larghezza di banda massima del trunk SIP = chiamate simultanee max x (64 kbps + Dimensione intestazione)</span><span class="sxs-lookup"><span data-stu-id="b9970-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9970-159">La dimensione dell'intestazione è massima di 20 byte.</span><span class="sxs-lookup"><span data-stu-id="b9970-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="b9970-160">Supporto per codec</span><span class="sxs-lookup"><span data-stu-id="b9970-160">Codec Support</span></span>

<span data-ttu-id="b9970-161">Lync Server 2013 supporta solo i codec seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9970-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="b9970-162">G. 711 a-Law (usato principalmente al di fuori del Nord America)</span><span class="sxs-lookup"><span data-stu-id="b9970-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="b9970-163">G. 711 µ-Law (usato in Nord America)</span><span class="sxs-lookup"><span data-stu-id="b9970-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="b9970-164">Provider di servizi di telefonia Internet</span><span class="sxs-lookup"><span data-stu-id="b9970-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="b9970-165">Il modo in cui implementare il lato provider di servizi di una connessione trunk SIP varia da un ITSP a un altro.</span><span class="sxs-lookup"><span data-stu-id="b9970-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="b9970-166">Per informazioni sulla distribuzione, contattare il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="b9970-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="b9970-167">Per un elenco dei provider di servizi di trunking SIP certificati, vedere [sito Web Microsoft Unified Communications Open Interoperability Program](http://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="b9970-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="b9970-168">Per informazioni dettagliate sui provider di trunking SIP certificati Microsoft, contattare il proprio rappresentante Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9970-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9970-169">Devi usare un provider di Servizi certificati Microsoft per assicurarti che ITSP supporti tutte le funzionalità che attraversano il trunk SIP, ad esempio la configurazione e la gestione delle sessioni e il supporto di tutti i servizi VoIP estesi.</span><span class="sxs-lookup"><span data-stu-id="b9970-169">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="b9970-170">Il supporto tecnico Microsoft non si estende alle configurazioni che usano provider non certificati.</span><span class="sxs-lookup"><span data-stu-id="b9970-170">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="b9970-171">Se attualmente si usa un provider di servizi Internet non certificato per il trunking SIP, è possibile scegliere di continuare a usare il provider come ISP e usare un provider certificato da Microsoft per il trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="b9970-171">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

