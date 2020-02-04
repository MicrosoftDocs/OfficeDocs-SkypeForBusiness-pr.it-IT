---
title: 'Lync Server 2013: Configurare le interfacce di rete per i server perimetrali'
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
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="80ba7-102">Configurare le interfacce di rete per i server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80ba7-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80ba7-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="80ba7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="80ba7-104">Ogni Edge Server è un computer multihome con interfacce esterne e interne.</span><span class="sxs-lookup"><span data-stu-id="80ba7-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="80ba7-105">Le impostazioni DNS (adapter Domain Name System) dipendono dalla presenza di server DNS nella rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="80ba7-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="80ba7-106">Se nel perimetro sono presenti server DNS, è necessario che dispongano di una zona contenente uno o più record DNS per il server o il pool di hop successivo, ovvero un pool di Director o di front-end designato, e per le query esterne che fanno riferimento alle ricerche dei nomi ad altri server DNS pubblici.</span><span class="sxs-lookup"><span data-stu-id="80ba7-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="80ba7-107">Se nel perimetro non sono presenti server DNS, gli Edge Server usano server DNS esterni per risolvere le ricerche di nomi Internet e ogni Edge Server usa un HOST per risolvere i nomi dei server dell'hop successivo in indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="80ba7-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sicurezza" alt="security" /><span data-ttu-id="80ba7-109">Nota sulla sicurezza:</span><span class="sxs-lookup"><span data-stu-id="80ba7-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="80ba7-110">Per motivi di sicurezza, è consigliabile non avere l'accesso dei server Edge a un server DNS situato nella rete interna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="80ba7-111">Per configurare le interfacce con i server DNS nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="80ba7-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="80ba7-112">Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia di rivestimento interno e uno per l'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="80ba7-113">Le subnet interne ed esterne non devono essere instradate tra loro.</span><span class="sxs-lookup"><span data-stu-id="80ba7-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="80ba7-114">Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna (nota anche come DMZ, zona demilitarizzata e subnet schermata) e puntare il gateway predefinito all'interfaccia interna del firewall esterno.</span><span class="sxs-lookup"><span data-stu-id="80ba7-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="80ba7-115">Configurare le impostazioni DNS della scheda in maniera che puntino a una coppia di server DNS perimetrali.</span><span class="sxs-lookup"><span data-stu-id="80ba7-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80ba7-116">È possibile usare un solo indirizzo IP per questa interfaccia, ma per eseguire questa operazione è necessario modificare le assegnazioni della porta in valori non standard.</span><span class="sxs-lookup"><span data-stu-id="80ba7-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="80ba7-117">Questa operazione viene determinata quando si crea la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="80ba7-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="80ba7-118">Nell'interfaccia interna configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="80ba7-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="80ba7-119">Configurare le impostazioni DNS adapter in maniera che puntino ad almeno un server DNS, preferibilmente una coppia di server DNS perimetrali.</span><span class="sxs-lookup"><span data-stu-id="80ba7-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="80ba7-120">Creare route statiche permanenti sull'interfaccia interna per tutte le reti interne in cui risiedono i client, i server Lync Server 2013 e la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="80ba7-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="80ba7-121">Per configurare le interfacce senza server DNS nella rete perimetrale</span><span class="sxs-lookup"><span data-stu-id="80ba7-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="80ba7-122">Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia di rivestimento interno e uno per l'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="80ba7-123">Le subnet interne ed esterne non devono essere instradate tra loro.</span><span class="sxs-lookup"><span data-stu-id="80ba7-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="80ba7-124">Nell'interfaccia esterna configurare tre indirizzi IP statici nella subnet della rete perimetrale esterna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="80ba7-125">È anche possibile configurare il gateway predefinito nell'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="80ba7-126">Ad esempio, Definisci il router che si affaccia su Internet o il firewall esterno come gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="80ba7-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="80ba7-127">Configurare le impostazioni DNS in maniera che puntino a un server DNS, preferibilmente a una coppia di server DNS esterni.</span><span class="sxs-lookup"><span data-stu-id="80ba7-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80ba7-128">È possibile, ma non consigliabile, usare il minor numero di un indirizzo IP per l'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="80ba7-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="80ba7-129">Per consentire il funzionamento, è necessario modificare le assegnazioni della porta in valori non standard e non la porta predefinita 443 che è in genere "firewall friendly" per la comunicazione client.</span><span class="sxs-lookup"><span data-stu-id="80ba7-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="80ba7-130">Puoi determinare l'impostazione dell'indirizzo IP e le impostazioni della porta quando crei la topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="80ba7-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="80ba7-131">Nell'interfaccia interna configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito.</span><span class="sxs-lookup"><span data-stu-id="80ba7-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="80ba7-132">Abbandonare le impostazioni DNS della scheda vuoto.</span><span class="sxs-lookup"><span data-stu-id="80ba7-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="80ba7-133">Creare route statiche permanenti sull'interfaccia interna per tutte le reti interne in cui risiedono i client Lync o i server che utilizzano Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="80ba7-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="80ba7-134">Modificare il file HOST in ogni Edge Server in modo che contenga un record per il server hop successivo o l'IP virtuale (VIP) (il record sarà il Director, il server Standard Edition o un pool Front-end configurato come indirizzo hop successivo di Edge Server in Generatore di topologia).</span><span class="sxs-lookup"><span data-stu-id="80ba7-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="80ba7-135">Se si usa il bilanciamento del carico DNS, includere una riga per ogni membro del pool hop successivo.</span><span class="sxs-lookup"><span data-stu-id="80ba7-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

