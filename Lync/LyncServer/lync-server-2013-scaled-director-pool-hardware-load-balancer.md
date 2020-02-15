---
title: 'Lync Server 2013: pool di Director in scala-bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d690c224556953086128b8d7fc52f2d72f6b06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="d15b8-102">Pool di server Director con scalabilità orizzontale-bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d15b8-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d15b8-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d15b8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d15b8-104">Un pool di server Director con scalabilità orizzontale, in cui sono distribuiti più Director per gestire la capacità aggiuntiva e fornire disponibilità elevata, richiede il bilanciamento del carico per la distribuzione della comunicazione tra client e servizi per tutti i membri del pool.</span><span class="sxs-lookup"><span data-stu-id="d15b8-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="d15b8-105">Un amministratore ospita i servizi Web molto simile a un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="d15b8-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="d15b8-106">Per i servizi Web è richiesto il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d15b8-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="d15b8-107">Negli argomenti seguenti vengono illustrate le considerazioni relative alla pianificazione per la distribuzione di un pool di server Director tramite bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="d15b8-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="d15b8-108">Se si intende utilizzare il bilanciamento del carico hardware e il bilanciamento del carico DNS per il pool di server Director, vedere l'argomento relativo al pool di server [Director-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) che descrive i requisiti di pianificazione per la topologia.</span><span class="sxs-lookup"><span data-stu-id="d15b8-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="d15b8-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="d15b8-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d15b8-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d15b8-110">In This Section</span></span>

  - [<span data-ttu-id="d15b8-111">Riepilogo del certificato-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d15b8-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="d15b8-112">Riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d15b8-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="d15b8-113">Pool di server Director con scalabilità verticale di riepilogo DNS, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d15b8-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

