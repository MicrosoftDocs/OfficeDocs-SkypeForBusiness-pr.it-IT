---
title: 'Lync Server 2013: Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9830a-102">Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9830a-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9830a-103">_**Argomento Ultima modifica:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="9830a-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="9830a-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9830a-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9830a-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="9830a-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9830a-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="9830a-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9830a-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="9830a-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9830a-108">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="9830a-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9830a-109">**Rete perimetrale aziendale per il bordo consolidato in scala con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="9830a-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="9830a-110">![96f5a8f5-16D2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16D2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="9830a-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9830a-111">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="9830a-111">Port and Protocol Details</span></span>

<span data-ttu-id="9830a-112">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9830a-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9830a-113">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentito per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="9830a-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="9830a-114">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="9830a-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="9830a-115">Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia esterna-node 1 e node 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="9830a-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9830a-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9830a-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9830a-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9830a-117">Source IP address</span></span></th>
<th><span data-ttu-id="9830a-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9830a-118">Destination IP address</span></span></th>
<th><span data-ttu-id="9830a-119">Note</span><span class="sxs-lookup"><span data-stu-id="9830a-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9830a-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9830a-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9830a-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-122">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="9830a-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9830a-123">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="9830a-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9830a-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9830a-125">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="9830a-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9830a-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-127">Il servizio proxy XMPP invia il traffico ai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="9830a-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9830a-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9830a-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-130">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-131">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="9830a-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9830a-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9830a-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-135">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="9830a-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9830a-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9830a-137">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-139">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="9830a-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-140">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-143">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="9830a-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-145">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-145">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-146">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-147">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="9830a-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-148">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-149">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-150">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-151">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="9830a-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-152">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-153">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-153">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-154">Edge Server Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-155">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="9830a-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9830a-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9830a-157">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-159">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9830a-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9830a-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9830a-161">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-162">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-163">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9830a-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9830a-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9830a-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-166">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-167">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9830a-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9830a-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9830a-169">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-169">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-170">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-171">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9830a-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9830a-173">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-175">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="9830a-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9830a-176">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="9830a-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9830a-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-179">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-180">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-182">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-183">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-184">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-186">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-187">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-187">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-188">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="9830a-189">Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia interna-nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="9830a-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9830a-190">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9830a-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9830a-191">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9830a-191">Source IP address</span></span></th>
<th><span data-ttu-id="9830a-192">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9830a-192">Destination IP address</span></span></th>
<th><span data-ttu-id="9830a-193">Commenti</span><span class="sxs-lookup"><span data-stu-id="9830a-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9830a-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9830a-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9830a-195">Any (può essere definito come indirizzo del server front-end o indirizzo IP del pool Front-end che gestisce il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="9830a-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9830a-196">Indirizzo IP dell'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9830a-197">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="9830a-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-199">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="9830a-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9830a-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-201">Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</span><span class="sxs-lookup"><span data-stu-id="9830a-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-203">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-204">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="9830a-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9830a-205">Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="9830a-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9830a-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9830a-207">Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="9830a-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9830a-208">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-209">Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="9830a-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9830a-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9830a-211">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="9830a-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9830a-212">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-213">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="9830a-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9830a-215">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-215">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-216">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-217">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9830a-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-219">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-219">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-220">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-221">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="9830a-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9830a-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9830a-223">Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="9830a-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9830a-224">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-225">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="9830a-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9830a-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9830a-227">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-227">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-228">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-229">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="9830a-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9830a-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9830a-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-231">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-232">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-233">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="9830a-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9830a-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9830a-235">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-235">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-236">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9830a-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9830a-237">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="9830a-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9830a-238">Riepilogo del firewall per la Federazione</span><span class="sxs-lookup"><span data-stu-id="9830a-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9830a-239">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9830a-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9830a-240">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9830a-240">Source IP address</span></span></th>
<th><span data-ttu-id="9830a-241">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9830a-241">Destination IP address</span></span></th>
<th><span data-ttu-id="9830a-242">Note</span><span class="sxs-lookup"><span data-stu-id="9830a-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9830a-243">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-244">Indirizzo IP pubblico del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="9830a-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9830a-245">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-245">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-246">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="9830a-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9830a-247">Riepilogo firewall-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9830a-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9830a-248">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9830a-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9830a-249">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9830a-249">Source IP address</span></span></th>
<th><span data-ttu-id="9830a-250">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9830a-250">Destination IP address</span></span></th>
<th><span data-ttu-id="9830a-251">Note</span><span class="sxs-lookup"><span data-stu-id="9830a-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9830a-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-253">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9830a-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9830a-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-255">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="9830a-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-256">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9830a-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9830a-257">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-258">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9830a-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9830a-259">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="9830a-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-260">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9830a-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9830a-261">Client</span><span class="sxs-lookup"><span data-stu-id="9830a-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="9830a-262">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-263">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="9830a-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9830a-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9830a-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-266">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="9830a-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9830a-267">Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="9830a-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9830a-269">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-270">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="9830a-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9830a-271">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9830a-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9830a-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9830a-273">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="9830a-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9830a-274">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="9830a-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9830a-275">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9830a-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9830a-276">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="9830a-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9830a-277">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9830a-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9830a-278">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9830a-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="9830a-279">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9830a-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9830a-280">Commenti</span><span class="sxs-lookup"><span data-stu-id="9830a-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9830a-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9830a-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9830a-282">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-282">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-283">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="9830a-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9830a-284">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9830a-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9830a-285">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="9830a-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9830a-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9830a-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9830a-287">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="9830a-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9830a-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-288">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-289">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9830a-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9830a-290">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="9830a-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9830a-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9830a-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9830a-292">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9830a-292">Any</span></span></p></td>
<td><p><span data-ttu-id="9830a-293">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="9830a-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="9830a-294">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</span><span class="sxs-lookup"><span data-stu-id="9830a-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

