---
title: Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="b83b7-102">Pool di server Director con scalabilità implementata - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b7-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b83b7-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b83b7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b83b7-104">Un pool di Director in scala, in cui sono distribuiti più Director per gestire capacità aggiuntive e per ottenere una disponibilità elevata, richiede il bilanciamento del carico per distribuire le comunicazioni client e server a tutti i membri del pool.</span><span class="sxs-lookup"><span data-stu-id="b83b7-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="b83b7-105">Un amministratore ospita i servizi Web in modo molto simile a un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="b83b7-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="b83b7-106">Per specificare il bilanciamento del carico, è possibile usare il bilanciamento del carico hardware o il bilanciamento del carico del sistema DNS (Domain Name System) e il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="b83b7-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="b83b7-107">Il bilanciamento del carico hardware è necessario per i servizi Web e il bilanciamento del carico DNS da solo non offre le funzionalità necessarie per i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="b83b7-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="b83b7-108">Gli argomenti seguenti descrivono le considerazioni sulla pianificazione per la distribuzione di un pool di Director tramite il bilanciamento del carico DNS in combinazione con il bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="b83b7-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="b83b7-109">Se si intende usare il bilanciamento del carico hardware, ma non il bilanciamento del carico DNS per il pool di Director, vedere l'argomento servizio di bilanciamento del carico hardware per il [pool di Director in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) che descrive i requisiti di pianificazione per tale topologia.</span><span class="sxs-lookup"><span data-stu-id="b83b7-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="b83b7-110">(images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool di Director scalato") ![pool Director]scalato</span><span class="sxs-lookup"><span data-stu-id="b83b7-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b83b7-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b83b7-111">In This Section</span></span>

  - [<span data-ttu-id="b83b7-112">Riepilogo dei certificati - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b7-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="b83b7-113">Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b7-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="b83b7-114">Riepilogo di DNS - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b83b7-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

