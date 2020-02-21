---
title: Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dc2d23fb2dac39ed568fb4aab6ab49f9e6213cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="53d12-102">Pool di server Director con scalabilità orizzontale-bilanciamento del carico DNS e bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="53d12-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d12-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="53d12-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="53d12-104">Un pool di server Director con scalabilità orizzontale, in cui sono distribuiti più Director per gestire la capacità aggiuntiva e per garantire la disponibilità elevata, richiede il bilanciamento del carico per la distribuzione delle comunicazioni client e di tutti i membri del pool.</span><span class="sxs-lookup"><span data-stu-id="53d12-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="53d12-105">Un amministratore ospita i servizi Web molto simile a un pool Front end.</span><span class="sxs-lookup"><span data-stu-id="53d12-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="53d12-106">Per garantire il bilanciamento del carico, è possibile utilizzare il bilanciamento del carico hardware oppure il bilanciamento del carico DNS (Domain Name System) insieme al bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="53d12-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="53d12-107">Quest'ultimo è necessario per i servizi Web e il bilanciamento del carico DNS da solo non offre le funzionalità richieste per tali servizi.</span><span class="sxs-lookup"><span data-stu-id="53d12-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="53d12-108">Negli argomenti seguenti vengono illustrate le considerazioni relative alla pianificazione per la distribuzione di un pool di server Director tramite bilanciamento del carico DNS in combinazione con il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="53d12-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="53d12-109">Se si intende utilizzare il bilanciamento del carico hardware, ma non il bilanciamento del carico DNS per il pool di server Director, vedere l'argomento relativo al pool di bilanciamento del carico [hardware in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) che descrive i requisiti di pianificazione per la topologia.</span><span class="sxs-lookup"><span data-stu-id="53d12-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="53d12-110">![Pool di server Director con scalabilità implementata](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool di server Director con scalabilità implementata")</span><span class="sxs-lookup"><span data-stu-id="53d12-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="53d12-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="53d12-111">In This Section</span></span>

  - [<span data-ttu-id="53d12-112">Riepilogo del certificato-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53d12-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="53d12-113">Riepilogo delle porte-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53d12-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="53d12-114">Riepilogo DNS-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53d12-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

