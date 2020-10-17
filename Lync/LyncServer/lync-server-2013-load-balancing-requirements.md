---
title: Requisiti per il bilanciamento del carico di Lync Server 2013
description: Requisiti per il bilanciamento del carico di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a768b2cbfe444e6915c932835d3cc2abaf6a98c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550032"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="74770-103">Requisiti per il bilanciamento del carico per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74770-103">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74770-104">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="74770-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="74770-105">Se si dispone di pool Front End, pool di Director o pool di server perimetrali, è necessario distribuire il bilanciamento del carico per questi pool.</span><span class="sxs-lookup"><span data-stu-id="74770-105">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="74770-106">Il bilanciamento del carico consente di distribuire il traffico tra i server in un pool.</span><span class="sxs-lookup"><span data-stu-id="74770-106">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="74770-107">Lync Server 2013 supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="74770-107">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="74770-108">Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Lync Server da eventuali problemi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="74770-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="74770-109">Per stabilire quale soluzione di bilanciamento del carico è appropriata per ogni pool nella distribuzione, tenere presenti le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74770-109">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="74770-p103">Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="74770-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="74770-p104">Alcuni tipi di traffico richiedono un servizio di bilanciamento del carico hardware. Il traffico HTTP richiede, ad esempio, un servizio di bilanciamento del carico hardware anziché il bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="74770-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="74770-115">Per ulteriori informazioni sulla scelta di una soluzione di bilanciamento del carico hardware, vedere [requisiti hardware del dispositivo di bilanciamento del carico per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74770-115">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="74770-116">Se si sceglie di utilizzare il bilanciamento del carico DNS per un pool, ma è comunque necessario implementare servizi di bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei servizi di bilanciamento del carico hardware risulta notevolmente semplificata.</span><span class="sxs-lookup"><span data-stu-id="74770-116">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="74770-117">Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice poiché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="74770-117">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="74770-118">Per ulteriori informazioni, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="74770-118">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="74770-119">Per il traffico da server a server, Lync Server 2013 utilizza il bilanciamento del carico in grado di riconoscere la topologia.</span><span class="sxs-lookup"><span data-stu-id="74770-119">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="74770-120">I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server.</span><span class="sxs-lookup"><span data-stu-id="74770-120">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="74770-121">Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="74770-121">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="74770-122">Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci degli indirizzi IP dal nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="74770-122">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="74770-123">È necessario rimuovere anche la voce DNS per il computer.</span><span class="sxs-lookup"><span data-stu-id="74770-123">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

