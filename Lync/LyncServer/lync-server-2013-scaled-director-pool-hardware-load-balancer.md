---
title: 'Lync Server 2013: Pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0faf0983830466b44c91532f4fd80d72abb37fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="2f3f0-102">Pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3f0-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f3f0-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2f3f0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2f3f0-104">Un pool di Director in scala, in cui sono distribuiti più direttori per gestire capacità aggiuntive e per assicurare una disponibilità elevata, richiede il bilanciamento del carico per distribuire le comunicazioni client e server a tutti i membri del pool.</span><span class="sxs-lookup"><span data-stu-id="2f3f0-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="2f3f0-105">Un amministratore ospita i servizi Web in modo molto simile a un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="2f3f0-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="2f3f0-106">Il bilanciamento del carico hardware è necessario per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="2f3f0-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="2f3f0-107">Gli argomenti seguenti descrivono le considerazioni sulla pianificazione per la distribuzione di un pool di Director tramite bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="2f3f0-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="2f3f0-108">Se si intende usare il bilanciamento del carico hardware e il bilanciamento del carico DNS per il pool di Director, vedere l'argomento [pool Director in scala-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) che descrive i requisiti di pianificazione per la topologia.</span><span class="sxs-lookup"><span data-stu-id="2f3f0-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="2f3f0-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="2f3f0-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f3f0-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2f3f0-110">In This Section</span></span>

  - [<span data-ttu-id="2f3f0-111">Riepilogo dei certificati - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3f0-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="2f3f0-112">Riepilogo delle porte - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3f0-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="2f3f0-113">Riepilogo di DNS - pool di server Director con scalabilità implementata, servizio di bilanciamento del carico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f3f0-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

