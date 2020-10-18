---
title: 'Lync Server 2013: requisiti DNS per i server perimetrali e le funzionalità'
description: 'Lync Server 2013: requisiti DNS per i server perimetrali e le funzionalità.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bcfd00080e765924eecc3138bc3d552ce331b63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574392"
---
# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="38332-103">Requisiti DNS per i server perimetrali e le funzionalità in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-103">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38332-104">_**Ultimo argomento modificato:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="38332-104">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="38332-105">I server perimetrali di Lync Server 2013, i pool perimetrali e i proxy inversi presentano requisiti specifici per i record DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="38332-105">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="38332-106">In Lync Server 2013 quando IPv4 e IPv6 sono in uso, è necessario pianificare entrambi i record host A e AAAA.</span><span class="sxs-lookup"><span data-stu-id="38332-106">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="38332-107">Negli argomenti elencati di seguito viene illustrato l'utilizzo dei record DNS per la pianificazione della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="38332-107">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="38332-108">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="38332-108">In This Section</span></span>

  - [<span data-ttu-id="38332-109">Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-109">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="38332-110">Riepilogo DNS-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-110">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="38332-111">Server perimetrale consolidato in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="38332-111">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="38332-112">Server perimetrale consolidato in scala di riepilogo DNS, bilanciamento del carico DNS con indirizzi IP pubblici in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="38332-112">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="38332-113">Server di sintesi DNS-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="38332-113">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="38332-114">Riepilogo DNS-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-114">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="38332-115">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38332-115">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

