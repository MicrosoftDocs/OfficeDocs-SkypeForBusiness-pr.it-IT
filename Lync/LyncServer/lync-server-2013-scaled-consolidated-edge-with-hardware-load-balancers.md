---
title: 'Lync Server 2013: Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8942b7d88bf4e52139a62b9a2ee0777b3532cf10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="53258-102">Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53258-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53258-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="53258-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="53258-104">Nella topologia del pool di server perimetrali, vengono distribuiti in due o in più perimetrali come pool con bilanciamento del carico nella rete perimetrale del Data Center.</span><span class="sxs-lookup"><span data-stu-id="53258-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="53258-105">Il bilanciamento del carico hardware viene utilizzato per il traffico verso le interfacce server perimetrali esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="53258-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="53258-106">Se l'organizzazione richiede supporto per oltre 15.000 connessioni client del servizio Access Edge, 1.000 connessioni client Active Web Conferencing Edge, o 500 sessioni A/V Edge Server simultanee e la disponibilità elevata dell'Edge-service è importante, questa topologia offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="53258-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="53258-107">Nella figura non sono visualizzati i direttori, un ruolo del server facoltativo distribuito nella rete interna tra i server perimetrali e i pool o il server front end.</span><span class="sxs-lookup"><span data-stu-id="53258-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="53258-108">.</span><span class="sxs-lookup"><span data-stu-id="53258-108">.</span></span> <span data-ttu-id="53258-109">Per informazioni dettagliate sulla topologia per i Director, vedere [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="53258-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53258-110">La figura mostrata è indicativa e include indirizzi IP di esempio, ma non deve essere interpretata come reale rappresentazione dei flussi di comunicazioni effettivi con un'indicazione corretta del traffico in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="53258-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="53258-111">La figura rappresenta una visualizzazione di livello generale del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="53258-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="53258-112">Le informazioni dettagliate sul flusso di traffico in entrata (verso le porte di attesa ) e in uscita (verso server o client di destinazione) vengono fornite nel diagramma di riepilogo delle porte in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="53258-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="53258-113">Ad esempio, TCP 443 è effettivamente in ingresso (al server perimetrale o al proxy inverso) ed è solo un flusso bidirezionale proveniente da una prospettiva di protocollo (TCP).</span><span class="sxs-lookup"><span data-stu-id="53258-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="53258-114">Nella figura inoltre viene mostrata la natura del traffico con le modifiche implementate con il processo NAT (Network Address Translation), ovvero l'indirizzo di destinazione diventa indirizzo in ingresso e quello di origine diventa indirizzo in uscita.</span><span class="sxs-lookup"><span data-stu-id="53258-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="53258-115">Vengono mostrati inoltre solo come riferimento esempi di firewall interni ed esterni e di interfacce server.</span><span class="sxs-lookup"><span data-stu-id="53258-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="53258-116">Vengono forniti anche esempi delle relazioni predefinite tra gateway e ruote, se applicabili.</span><span class="sxs-lookup"><span data-stu-id="53258-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="53258-117">Si noti inoltre che il diagramma utilizza la zona DNS <EM>. com</EM> per rappresentare la zona DNS esterna sia per il proxy inverso sia per i server perimetrali e che la zona DNS <EM>.NET</EM> si riferisce alla zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="53258-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="53258-118">New to Microsoft Lync Server 2013 è il supporto per l'indirizzamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="53258-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="53258-119">Analogamente agli indirizzi IPv4, gli indirizzi IPv6 devono essere assegnati in modo che facciano parte dello spazio degli indirizzi IPv6 assegnato.</span><span class="sxs-lookup"><span data-stu-id="53258-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="53258-120">Gli indirizzi riportati in questo argomento vengono forniti unicamente a scopo esemplificativo.</span><span class="sxs-lookup"><span data-stu-id="53258-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="53258-121">È necessario acquisire indirizzi IPv6 che funzionino nella propria distribuzione, forniscano l'ambito corretto e interagiscano con gli indirizzi interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="53258-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="53258-122">Windows Server fornisce una caratteristica importante per l'operazione di transizione IPv6 e la comunicazione IPv4-IPv6 chiamata *dual stack*.</span><span class="sxs-lookup"><span data-stu-id="53258-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="53258-123">Il dual stack è uno stack di rete separato e distinto per IPv4 e per IPv6.</span><span class="sxs-lookup"><span data-stu-id="53258-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="53258-124">Consente di assegnare indirizzi per IPv4 e IPv6 simultaneamente e permette al server di comunicare con altri host e client in base ai rispettivi requisiti.</span><span class="sxs-lookup"><span data-stu-id="53258-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="53258-125">I tipi di indirizzi tipici che verranno utilizzati per l'indirizzamento IPv6 saranno gli indirizzi globali IPv6 (simili agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (simili agli intervalli di indirizzi IPv4 privati) e gli indirizzi IPv6 (simili all'IP privato automatico). indirizzi in Windows Server per IPv4)</span><span class="sxs-lookup"><span data-stu-id="53258-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="53258-126">Sono disponibili tecnologie NAT (Network Address Translation) per IPv6 che consentono la conversione NAT da IPv6 a IPv4 (denominata comunemente NAT64) e la conversione NAT da IPv6 a IPv6 (denominata comunemente NAT66).</span><span class="sxs-lookup"><span data-stu-id="53258-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="53258-127">L'esistenza di tecnologie NAT significa che i cinque scenari presentati per i server perimetrali di Lync Server sono ancora validi.</span><span class="sxs-lookup"><span data-stu-id="53258-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="53258-128">IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider di servizi Internet per garantire che gli indirizzi assegnati a livello di Windows Server e al livello di Lync Server 2013 funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="53258-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="53258-129">Per ulteriori risorse sull'indirizzamento e la pianificazione di IPv6, vedere i collegamenti alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="53258-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="53258-130">**Configurazione del servizio di bilanciamento del carico hardware**</span><span class="sxs-lookup"><span data-stu-id="53258-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="53258-131">Per informazioni dettagliate, vedere la sezione "requisiti del dispositivo di bilanciamento del carico hardware per un/V Edge" nei [componenti necessari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="53258-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="53258-132">**Topologia perimetrale consolidata in scala (bilanciamento del carico hardware)**</span><span class="sxs-lookup"><span data-stu-id="53258-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="53258-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="53258-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="53258-134">Se si utilizza il controllo di ammissione di chiamata, è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="53258-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="53258-135">Questo servizio infatti si basa sugli indirizzi IPv4 e deve disporre di tali indirizzi per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="53258-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="53258-136">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="53258-136">In This Section</span></span>

  - [<span data-ttu-id="53258-137">Riepilogo dei certificati-perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53258-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="53258-138">Riepilogo delle porte-perimetro consolidato con bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53258-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="53258-139">Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53258-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53258-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53258-140">See Also</span></span>


[<span data-ttu-id="53258-141">Architettura di indirizzamento IP versione 6</span><span class="sxs-lookup"><span data-stu-id="53258-141">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="53258-142">Formato di indirizzo unicast globale IPv6</span><span class="sxs-lookup"><span data-stu-id="53258-142">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="53258-143">Indirizzi unicast IPv6 locali univoci</span><span class="sxs-lookup"><span data-stu-id="53258-143">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

