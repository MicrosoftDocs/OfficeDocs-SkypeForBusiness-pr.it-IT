---
title: Requisiti per il bilanciamento del carico di Lync Server 2013
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
ms.openlocfilehash: 016ace11375483fbeaa59199e9f1cdae23654cd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513823"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="40be7-102">Requisiti per il bilanciamento del carico per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40be7-102">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40be7-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="40be7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="40be7-104">Se si dispone di pool Front End, pool di Director o pool di server perimetrali, è necessario distribuire il bilanciamento del carico per questi pool.</span><span class="sxs-lookup"><span data-stu-id="40be7-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="40be7-105">Il bilanciamento del carico consente di distribuire il traffico tra i server in un pool.</span><span class="sxs-lookup"><span data-stu-id="40be7-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="40be7-106">Lync Server 2013 supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="40be7-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="40be7-107">Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Lync Server da eventuali problemi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="40be7-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="40be7-108">Per stabilire quale soluzione di bilanciamento del carico è appropriata per ogni pool nella distribuzione, tenere presenti le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40be7-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="40be7-p103">Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="40be7-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="40be7-p104">Alcuni tipi di traffico richiedono un servizio di bilanciamento del carico hardware. Il traffico HTTP richiede, ad esempio, un servizio di bilanciamento del carico hardware anziché il bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="40be7-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="40be7-114">Per ulteriori informazioni sulla scelta di una soluzione di bilanciamento del carico hardware, vedere [requisiti hardware del dispositivo di bilanciamento del carico per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40be7-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="40be7-115">Se si sceglie di utilizzare il bilanciamento del carico DNS per un pool, ma è comunque necessario implementare servizi di bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei servizi di bilanciamento del carico hardware risulta notevolmente semplificata.</span><span class="sxs-lookup"><span data-stu-id="40be7-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="40be7-116">Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice poiché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="40be7-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="40be7-117">Per ulteriori informazioni, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="40be7-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="40be7-118">Per il traffico da server a server, Lync Server 2013 utilizza il bilanciamento del carico in grado di riconoscere la topologia.</span><span class="sxs-lookup"><span data-stu-id="40be7-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="40be7-119">I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server.</span><span class="sxs-lookup"><span data-stu-id="40be7-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="40be7-120">Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="40be7-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="40be7-121">Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci degli indirizzi IP dal nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="40be7-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="40be7-122">È necessario rimuovere anche la voce DNS per il computer.</span><span class="sxs-lookup"><span data-stu-id="40be7-122">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

