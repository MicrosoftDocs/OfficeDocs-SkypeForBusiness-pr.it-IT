---
title: 'Lync Server 2013: Singola topologia perimetrale consolidata con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8189d360a43887e2992b8b8abf063ef96230e06e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="42665-102">Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42665-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="42665-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="42665-104">Se l'organizzazione ha bisogno del supporto per meno di 15.000 connessioni client del servizio Edge di Access, le connessioni client del servizio Web di servizi di conferenza Active Lync Server di 1.000 500 e le sessioni contemporanee A/V Edge e la disponibilità elevata di Edge Server non sono importanti, questa topologia offre i vantaggi del costo hardware più basso e della distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="42665-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="42665-105">Se è necessaria una maggiore capacità o è necessaria una disponibilità elevata, è necessario distribuire una topologia di Edge Server consolidato in scala.</span><span class="sxs-lookup"><span data-stu-id="42665-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="42665-106">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="42665-107">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="42665-108">Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42665-109">Quando si usa l'indirizzo IP pubblico nell'Edge Server, il gateway predefinito nel server perimetrale non è più il firewall o il router, ma il router o il firewall a bordo del perimetro pubblico, che sarà un indirizzo pubblico.</span><span class="sxs-lookup"><span data-stu-id="42665-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="42665-110">Il proxy inverso continua a usare il router o il firewall associato alla rete perimetrale più esterna.</span><span class="sxs-lookup"><span data-stu-id="42665-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="42665-111">La differenza tra il proxy inverso e il server perimetrale con indirizzi IP pubblici è che il proxy inverso sta ancora usando NAT e il server perimetrale usa una relazione di route.</span><span class="sxs-lookup"><span data-stu-id="42665-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="42665-112">La figura non Mostra gli amministratori, un ruolo facoltativo del server distribuito nella rete interna tra i server Edge e i pool o il server front-end.</span><span class="sxs-lookup"><span data-stu-id="42665-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="42665-113">Per informazioni dettagliate sulla topologia di Director, vedere [componenti necessari per il Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="42665-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="42665-114">La figura rappresenta un singolo proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="42665-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42665-115">La figura mostrata riguarda l'orientamento e l'indirizzo IP di esempio, ma non intende rappresentare flussi di comunicazione effettivi con il traffico in entrata e in uscita corretto.</span><span class="sxs-lookup"><span data-stu-id="42665-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="42665-116">La figura rappresenta una visualizzazione di alto livello del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="42665-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="42665-117">I dettagli relativi al flusso di traffico in ingresso (alle porte in ascolto) e in uscita (per i server o i client di destinazione) sono rappresentati nel diagramma di riepilogo della porta in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="42665-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="42665-118">Ad esempio, TCP 443 è effettivamente in ingresso (al proxy Edge o reverse) solo ed è solo un flusso bidirezionale da una prospettiva di protocollo (TCP).</span><span class="sxs-lookup"><span data-stu-id="42665-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="42665-119">Inoltre, la figura mostra la natura del traffico che cambia quando si verifica NAT (Network Address Translation) (l'indirizzo di destinazione viene modificato in ingresso, l'indirizzo di origine viene modificato in uscita).</span><span class="sxs-lookup"><span data-stu-id="42665-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="42665-120">Ad esempio, i firewall esterni e interni e le interfacce server vengono visualizzati solo per scopi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="42665-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="42665-121">Infine, se necessario, vengono mostrati i rapporti di gateway e route predefiniti di esempio.</span><span class="sxs-lookup"><span data-stu-id="42665-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="42665-122">Si noti inoltre che il diagramma usa la zona DNS <EM>. com</EM> per rappresentare la zona DNS esterna sia per il proxy inverso che per i server perimetrali e la zona DNS <EM>.NET</EM> si riferisce alla zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="42665-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="42665-123">Una novità di Microsoft Lync Server 2013 è il supporto per l'indirizzamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="42665-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="42665-124">Analogamente all'indirizzamento IPv4, gli indirizzi IPv6 devono essere assegnati in modo che gli indirizzi facciano parte dello spazio degli indirizzi IPv6 assegnato.</span><span class="sxs-lookup"><span data-stu-id="42665-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="42665-125">Gli indirizzi in questo argomento sono ad esempio solo.</span><span class="sxs-lookup"><span data-stu-id="42665-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="42665-126">Devi acquisire gli indirizzi IPv6 che funzioneranno nella distribuzione, specificare l'ambito corretto e interagire con l'indirizzamento interno ed esterno.</span><span class="sxs-lookup"><span data-stu-id="42665-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="42665-127">Windows Server offre una caratteristica importante per l'operazione di transizione IPv6 e la comunicazione IPv4-IPv6 chiamata *dual stack*.</span><span class="sxs-lookup"><span data-stu-id="42665-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="42665-128">Lo stack duale è uno stack di rete distinto per IPv4 e per IPv6.</span><span class="sxs-lookup"><span data-stu-id="42665-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="42665-129">Lo stack duale consente di assegnare contemporaneamente l'indirizzo per IPv4 e IPv6 e consente al server di comunicare con altri host e client in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="42665-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="42665-130">I tipi di indirizzo tipici che verranno usati per l'indirizzamento IPv6 saranno gli indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e i collegamenti IPv6-indirizzi locali (in modo simile all'IP privato automatico indirizzi in Windows Server per IPv4)</span><span class="sxs-lookup"><span data-stu-id="42665-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="42665-131">Esistono le tecnologie NAT (Network Address Translation Technologies) per IPv6 che consentiranno l'uso di NAT IPv6 per IPv4 (comunemente indicato come NAT64) e per NAT IPv6 to IPv6 (comunemente denominato NAT66).</span><span class="sxs-lookup"><span data-stu-id="42665-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="42665-132">L'esistenza di tecnologie NAT indica che i cinque scenari presentati per Lync Server Edge Server sono ancora validi.</span><span class="sxs-lookup"><span data-stu-id="42665-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="42665-133">IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarsi che gli indirizzi assegnati a livello di Windows Server e a livello di Lync Server 2013 funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="42665-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="42665-134">Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6.</span><span class="sxs-lookup"><span data-stu-id="42665-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="42665-135">**Singolo bordo consolidato con topologia indirizzi IP pubblici**</span><span class="sxs-lookup"><span data-stu-id="42665-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="42665-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="42665-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="42665-137">Se si usa il controllo di ammissione chiamata (CAC), è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="42665-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="42665-138">CAC usa gli indirizzi IPv4 e deve renderli disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="42665-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42665-139">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="42665-139">In This Section</span></span>

  - [<span data-ttu-id="42665-140">Riepilogo dei certificati - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="42665-141">Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="42665-142">Riepilogo di DNS - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42665-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="42665-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42665-143">See Also</span></span>


[<span data-ttu-id="42665-144">Architettura di indirizzamento IP versione 6</span><span class="sxs-lookup"><span data-stu-id="42665-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="42665-145">Formato di indirizzo unicast globale IPv6</span><span class="sxs-lookup"><span data-stu-id="42665-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="42665-146">Indirizzi unicast IPv6 locali univoci</span><span class="sxs-lookup"><span data-stu-id="42665-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

