---
title: Requisiti di bilanciamento del carico di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="5088b-102">Requisiti di bilanciamento del carico per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5088b-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5088b-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="5088b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="5088b-104">Se sono presenti pool di front-end, pool di Director o pool di Edge Server, è necessario distribuire il bilanciamento del carico per questi pool.</span><span class="sxs-lookup"><span data-stu-id="5088b-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="5088b-105">Il bilanciamento del carico distribuisce il traffico tra i server in un pool.</span><span class="sxs-lookup"><span data-stu-id="5088b-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="5088b-106">Lync Server 2013 supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5088b-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="5088b-107">Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Lync Server da qualsiasi potenziale problema di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5088b-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="5088b-108">Decidere quale soluzione di bilanciamento del carico è appropriata per ogni pool della distribuzione, tenendo presenti le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5088b-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="5088b-109">L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="5088b-109">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="5088b-110">Non è possibile usare il bilanciamento del carico DNS su un'interfaccia e un bilanciamento del carico hardware dall'altro.</span><span class="sxs-lookup"><span data-stu-id="5088b-110">You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="5088b-111">Alcuni tipi di traffico richiedono un bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5088b-111">Some types of traffic require a hardware load balancer.</span></span> <span data-ttu-id="5088b-112">Ad esempio, il traffico HTTP richiede un bilanciamento del carico hardware invece del bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="5088b-112">For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing.</span></span> <span data-ttu-id="5088b-113">Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.</span><span class="sxs-lookup"><span data-stu-id="5088b-113">DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="5088b-114">Per altre informazioni sulla scelta di una soluzione di bilanciamento del carico hardware, vedere [requisiti di bilanciamento del carico hardware per Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5088b-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="5088b-115">Se si sceglie di usare il bilanciamento del carico DNS per un pool, ma occorre comunque implementare il bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei dispositivi di bilanciamento del carico hardware è notevolmente semplificata.</span><span class="sxs-lookup"><span data-stu-id="5088b-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="5088b-116">Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice perché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="5088b-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="5088b-117">Per informazioni dettagliate, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="5088b-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="5088b-118">Per il traffico da server a server, Lync Server 2013 usa il bilanciamento del carico che supporta la topologia.</span><span class="sxs-lookup"><span data-stu-id="5088b-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="5088b-119">I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server.</span><span class="sxs-lookup"><span data-stu-id="5088b-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="5088b-120">Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="5088b-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="5088b-121">Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="5088b-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="5088b-122">È necessario rimuovere anche la voce DNS per il computer.</span><span class="sxs-lookup"><span data-stu-id="5088b-122">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

