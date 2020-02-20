---
title: 'Lync Server 2013: configurare le interfacce di rete per i server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e736a7782908479e670b7127c7518e044978ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="7757d-102">Configurare le interfacce di rete per i server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7757d-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7757d-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7757d-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7757d-p101">Ogni Edge Server è un computer multihomed con interfacce rivolte verso l'esterno e verso l'interno. Le impostazioni DNS (Domain Name System ) della scheda dipendono dalla presenza di server DNS nella rete perimetrale. Se nel perimetro sono presenti server DNS, devono disporre di un'area contenente uno o più record A DNS per il server hop successivo o per il pool (ovvero un pool Director o un pool Front End designato) e per query esterne che per le ricerche dei nomi fanno riferimento ad altri server DNS pubblici. Se nel perimetro non sono presenti server DNS, il server o i server Edge Server utilizzeranno i server DNS esterni per risolvere le ricerche dei nomi Internet e ogni Edge Server utilizzerà un HOST per risolvere i nomi di server hop successivo in indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="7757d-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="7757d-109">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="7757d-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7757d-110">Per motivi di protezione, è consigliabile non consentire agli Edge Server di accedere a un server DNS presente nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="7757d-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="7757d-111">Per configurare le interfacce con i server DNS nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="7757d-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="7757d-112">Installare due schede di rete per ogni Edge Server, una per l'interfaccia connessa alla rete interna e una per quella connessa alla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="7757d-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7757d-113">Le subnet interna ed esterna non devono essere vicendevolmente instradabili.</span><span class="sxs-lookup"><span data-stu-id="7757d-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="7757d-p102">Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna, denominata anche DMZ o subnet schermata, e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in modo da puntare a una coppia di server DNS perimetrali.</span><span class="sxs-lookup"><span data-stu-id="7757d-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7757d-116">È possibile utilizzare anche un solo indirizzo IP per questa interfaccia, ma a tale scopo sarà necessario modificare le assegnazioni delle porte con valori non standard.</span><span class="sxs-lookup"><span data-stu-id="7757d-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="7757d-117">Questa operazione viene determinata quando si crea la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7757d-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="7757d-p104">Nell'interfaccia interna, configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Configurare le impostazioni DNS della scheda in modo da puntare ad almeno un server DNS, preferibilmente una coppia di server DNS perimetrali.</span><span class="sxs-lookup"><span data-stu-id="7757d-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="7757d-120">Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono i client, Lync Server 2013 e i server di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="7757d-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="7757d-121">Per configurare le interfacce senza server DNS nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="7757d-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="7757d-122">Installare due schede di rete per ogni Edge Server, una per l'interfaccia connessa alla rete interna e una per quella connessa alla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="7757d-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7757d-123">Le subnet interna ed esterna non devono essere vicendevolmente instradabili.</span><span class="sxs-lookup"><span data-stu-id="7757d-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="7757d-p105">Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna. È inoltre possibile configurare il gateway predefinito nell'interfaccia esterna. Ad esempio, definire il router con connessione Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS in modo da puntare a un server DNS, preferibilmente a una coppia di server DNS esterni.</span><span class="sxs-lookup"><span data-stu-id="7757d-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7757d-128">È possibile, ma non consigliabile, utilizzare anche un solo indirizzo IP per l'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="7757d-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="7757d-129">A tale scopo, è necessario impostare le assegnazioni delle porte su valori non standard e lontani dalla porta predefinita 443 che in genere è appropriata per il firewall per la comunicazione client.</span><span class="sxs-lookup"><span data-stu-id="7757d-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="7757d-130">È possibile determinare l'impostazione dell'indirizzo IP e le impostazioni della porta quando si crea la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="7757d-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="7757d-p107">Nell'interfaccia interna, configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Lasciare le impostazioni DNS della scheda vuote.</span><span class="sxs-lookup"><span data-stu-id="7757d-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="7757d-133">Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono i client o i server Lync che eseguono Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7757d-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="7757d-134">Modificare il file HOST in ogni server perimetrale in modo che contenga un record per il server dell'hop successivo o l'IP virtuale (VIP) (il record sarà il server Director, Standard Edition o un pool Front end configurato come indirizzo hop successivo del server perimetrale in Generatore di topologie).</span><span class="sxs-lookup"><span data-stu-id="7757d-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="7757d-135">Se si utilizza il bilanciamento del carico DNS, includere una riga per ogni membro del pool di hop successivo.</span><span class="sxs-lookup"><span data-stu-id="7757d-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

