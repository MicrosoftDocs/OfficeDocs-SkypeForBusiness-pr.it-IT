---
title: Requisiti per le porte di Lync Server 2013
description: Requisiti di porta di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba7ae9a1ee098f55c61ae476f12c3b856c69f90e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543162"
---
# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="27d96-103">Requisiti relativi alle porte per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-103">Port requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27d96-104">_**Ultimo argomento modificato:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="27d96-104">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="27d96-105">Lync Server richiede che le porte specifiche del firewall siano aperte.</span><span class="sxs-lookup"><span data-stu-id="27d96-105">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="27d96-106">Se nell'organizzazione viene distribuita IPsec (Internet Protocol Security), IPsec deve essere disabilitato nell'intervallo di porte utilizzate per il recapito di audio, video e video panoramici.</span><span class="sxs-lookup"><span data-stu-id="27d96-106">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27d96-107">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="27d96-107">In This Section</span></span>

<span data-ttu-id="27d96-108">In questa sezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="27d96-108">This section includes the following topics:</span></span>

  - [<span data-ttu-id="27d96-109">Porte e protocolli per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-109">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="27d96-110">Eccezioni IPsec in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-110">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="27d96-111">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-111">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="27d96-112">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-112">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="27d96-113">Riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-113">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="27d96-114">Riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-114">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="27d96-115">Riepilogo delle porte-perimetro consolidato con bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-115">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="27d96-116">Riepilogo delle porte-proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-116">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="27d96-117">Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27d96-117">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

