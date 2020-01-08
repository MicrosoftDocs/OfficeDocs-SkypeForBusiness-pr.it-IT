---
title: 'Lync Server 2013: Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ccae081e80b61be767dfbdc82664ff90d4dfabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="10085-102">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10085-102">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10085-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="10085-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="10085-104">Nella topologia del pool di Edge Server due o più Edge Server vengono distribuiti come pool con bilanciamento del carico nella rete perimetrale del Data Center.</span><span class="sxs-lookup"><span data-stu-id="10085-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="10085-105">Il bilanciamento del carico DNS (Domain Name System) viene usato per il traffico sia per le interfacce esterne che per quelle interne.</span><span class="sxs-lookup"><span data-stu-id="10085-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="10085-106">Se l'organizzazione richiede il supporto per più di 15.000 connessioni client del servizio Edge di Access, le connessioni client del servizio Web di servizi di conferenza Active Lync Server di 1.000 o le sessioni A/V Edge di 500 simultanee e/o l'elevata disponibilità del server perimetrale sono importanti, questa topologia offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="10085-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="10085-107">La figura non Mostra gli amministratori, un ruolo facoltativo del server distribuito nella rete interna tra i server Edge e i pool o il server front-end.</span><span class="sxs-lookup"><span data-stu-id="10085-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="10085-108">Per informazioni dettagliate sulla topologia di Director, vedere [componenti necessari per il Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="10085-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="10085-109">La figura rappresenta un singolo proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="10085-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="10085-110">La figura mostrata riguarda l'orientamento e l'indirizzo IP di esempio, ma non intende rappresentare flussi di comunicazione effettivi con il traffico in entrata e in uscita corretto.</span><span class="sxs-lookup"><span data-stu-id="10085-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="10085-111">La figura rappresenta una visualizzazione di alto livello del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="10085-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="10085-112">I dettagli relativi al flusso di traffico in ingresso (alle porte in ascolto) e in uscita (per i server o i client di destinazione) sono rappresentati nel diagramma di riepilogo della porta in ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="10085-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="10085-113">Ad esempio, TCP 443 è effettivamente in ingresso (al proxy Edge o reverse) solo ed è solo un flusso bidirezionale da una prospettiva di protocollo (TCP).</span><span class="sxs-lookup"><span data-stu-id="10085-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="10085-114">Inoltre, la figura mostra la natura del traffico che cambia quando si verifica NAT (Network Address Translation) (l'indirizzo di destinazione viene modificato in ingresso, l'indirizzo di origine viene modificato in uscita).</span><span class="sxs-lookup"><span data-stu-id="10085-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="10085-115">Ad esempio, i firewall esterni e interni e le interfacce server vengono visualizzati solo per scopi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="10085-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="10085-116">Infine, se necessario, vengono mostrati i rapporti di gateway e route predefiniti di esempio.</span><span class="sxs-lookup"><span data-stu-id="10085-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="10085-117">Si noti inoltre che il diagramma usa la zona DNS <EM>. com</EM> per rappresentare la zona DNS esterna sia per il proxy inverso che per i server perimetrali e la zona DNS <EM>.NET</EM> si riferisce alla zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="10085-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="10085-118">Una novità di Microsoft Lync Server 2013 è il supporto per l'indirizzamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="10085-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="10085-119">Analogamente all'indirizzamento IPv4, gli indirizzi IPv6 devono essere assegnati in modo che gli indirizzi facciano parte dello spazio degli indirizzi IPv6 assegnato.</span><span class="sxs-lookup"><span data-stu-id="10085-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="10085-120">Gli indirizzi in questo argomento sono ad esempio solo.</span><span class="sxs-lookup"><span data-stu-id="10085-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="10085-121">Devi acquisire gli indirizzi IPv6 che funzioneranno nella distribuzione, specificare l'ambito corretto e interagire con l'indirizzamento interno ed esterno.</span><span class="sxs-lookup"><span data-stu-id="10085-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="10085-122">Windows Server offre una caratteristica importante per l'operazione di transizione IPv6 e la comunicazione IPv4-IPv6 chiamata *dual stack*.</span><span class="sxs-lookup"><span data-stu-id="10085-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="10085-123">Lo stack duale è uno stack di rete distinto per IPv4 e per IPv6.</span><span class="sxs-lookup"><span data-stu-id="10085-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="10085-124">Lo stack duale consente di assegnare contemporaneamente l'indirizzo per IPv4 e IPv6 e consente al server di comunicare con altri host e client in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="10085-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="10085-125">I tipi di indirizzo tipici che verranno usati per l'indirizzamento IPv6 saranno gli indirizzi globali IPv6 (in modo simile agli indirizzi IPv4 pubblici), gli indirizzi locali univoci IPv6 (in modo simile agli intervalli di indirizzi IPv4 privati) e i collegamenti IPv6-indirizzi locali (in modo simile all'IP privato automatico indirizzi in Windows Server per IPv4)</span><span class="sxs-lookup"><span data-stu-id="10085-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="10085-126">Esistono le tecnologie NAT (Network Address Translation Technologies) per IPv6 che consentiranno l'uso di NAT IPv6 per IPv4 (comunemente indicato come NAT64) e per NAT IPv6 to IPv6 (comunemente denominato NAT66).</span><span class="sxs-lookup"><span data-stu-id="10085-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="10085-127">L'esistenza di tecnologie NAT indica che i cinque scenari presentati per Lync Server Edge Server sono ancora validi.</span><span class="sxs-lookup"><span data-stu-id="10085-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="10085-128">IPv6 è un argomento complesso e richiede una pianificazione accurata con il team di rete e il provider Internet per assicurarsi che gli indirizzi assegnati a livello di Windows Server e a livello di Lync Server 2013 funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="10085-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="10085-129">Vedere i collegamenti alla fine di questo argomento per altre risorse sull'indirizzamento e la pianificazione IPv6.</span><span class="sxs-lookup"><span data-stu-id="10085-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="10085-130">![899546d4-2eef-44D2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44D2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="10085-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10085-131">Se si usa il controllo di ammissione chiamata (CAC), è comunque necessario assegnare gli indirizzi IPv4 all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="10085-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="10085-132">CAC usa gli indirizzi IPv4 e deve renderli disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="10085-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="10085-133">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="10085-133">In This Section</span></span>

  - [<span data-ttu-id="10085-134">Riepilogo dei certificati - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10085-134">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="10085-135">Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10085-135">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="10085-136">Riepilogo di DNS - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10085-136">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10085-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10085-137">See Also</span></span>


[<span data-ttu-id="10085-138">Architettura di indirizzamento IP versione 6</span><span class="sxs-lookup"><span data-stu-id="10085-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="10085-139">Formato di indirizzo unicast globale IPv6</span><span class="sxs-lookup"><span data-stu-id="10085-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="10085-140">Indirizzi unicast IPv6 locali univoci</span><span class="sxs-lookup"><span data-stu-id="10085-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

