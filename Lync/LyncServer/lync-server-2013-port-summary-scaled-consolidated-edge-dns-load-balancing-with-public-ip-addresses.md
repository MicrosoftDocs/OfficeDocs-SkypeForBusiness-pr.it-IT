---
title: 'Lync Server 2013: Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2095df7ebd68265d135a8b174ce2d1d3ae76ca5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="3671b-102">Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3671b-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3671b-103">_**Argomento Ultima modifica:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="3671b-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="3671b-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3671b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3671b-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="3671b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3671b-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="3671b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3671b-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="3671b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3671b-108">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="3671b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3671b-109">**Rete perimetrale aziendale per il bordo consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici**</span><span class="sxs-lookup"><span data-stu-id="3671b-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="3671b-110">![96f5a8f5-16D2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16D2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3671b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3671b-111">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="3671b-111">Port and Protocol Details</span></span>

<span data-ttu-id="3671b-112">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3671b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3671b-113">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentito per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="3671b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="3671b-114">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="3671b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3671b-115">Riepilogo del firewall per il bordo consolidato in scala, il bilanciamento del carico DNS con gli indirizzi IP pubblici: interfaccia esterna-node 1 e node 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="3671b-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3671b-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="3671b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3671b-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="3671b-117">Source IP address</span></span></th>
<th><span data-ttu-id="3671b-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="3671b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="3671b-119">Note</span><span class="sxs-lookup"><span data-stu-id="3671b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3671b-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3671b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3671b-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-122">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="3671b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3671b-123">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="3671b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3671b-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3671b-125">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-127">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="3671b-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3671b-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3671b-129">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-131">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="3671b-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3671b-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3671b-133">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-135">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="3671b-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-136">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-137">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-137">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-138">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-139">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3671b-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-140">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-142">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-143">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="3671b-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-145">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-146">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-146">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-147">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="3671b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-148">Web Conferencing/PSOM (TLS) TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-149">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-150">Indirizzo IP pubblico di Edge Server Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="3671b-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-151">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="3671b-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3671b-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3671b-153">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-154">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-155">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3671b-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3671b-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3671b-157">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-159">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3671b-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3671b-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3671b-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-161">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-162">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-163">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3671b-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3671b-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3671b-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-166">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-167">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3671b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3671b-169">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-170">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-171">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3671b-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3671b-172">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="3671b-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3671b-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-175">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-176">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-179">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-180">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-182">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-183">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-183">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-184">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3671b-185">Riepilogo del firewall per il bordo consolidato in scala, il bilanciamento del carico DNS con gli indirizzi IP pubblici: interfaccia interna-nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="3671b-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3671b-186">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="3671b-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3671b-187">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="3671b-187">Source IP address</span></span></th>
<th><span data-ttu-id="3671b-188">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="3671b-188">Destination IP address</span></span></th>
<th><span data-ttu-id="3671b-189">Commenti</span><span class="sxs-lookup"><span data-stu-id="3671b-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3671b-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3671b-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3671b-191">Any (può essere definito come indirizzo del server front-end o indirizzo IP del pool Front-end che gestisce il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="3671b-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3671b-192">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-193">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="3671b-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-195">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="3671b-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3671b-196">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-197">Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</span><span class="sxs-lookup"><span data-stu-id="3671b-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-199">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-200">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="3671b-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3671b-201">Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3671b-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3671b-203">Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="3671b-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3671b-204">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-205">Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3671b-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3671b-207">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="3671b-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3671b-208">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-209">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3671b-211">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-211">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-212">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-213">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="3671b-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-215">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-216">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-217">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="3671b-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3671b-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3671b-219">Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="3671b-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3671b-220">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-221">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="3671b-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3671b-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3671b-223">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-223">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-224">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-225">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="3671b-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3671b-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3671b-227">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-228">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-229">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="3671b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3671b-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3671b-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-232">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="3671b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3671b-233">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="3671b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3671b-234">Riepilogo del firewall per la Federazione</span><span class="sxs-lookup"><span data-stu-id="3671b-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3671b-235">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="3671b-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3671b-236">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="3671b-236">Source IP address</span></span></th>
<th><span data-ttu-id="3671b-237">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="3671b-237">Destination IP address</span></span></th>
<th><span data-ttu-id="3671b-238">Note</span><span class="sxs-lookup"><span data-stu-id="3671b-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3671b-239">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-240">Indirizzo IP pubblico del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="3671b-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-241">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-241">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-242">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="3671b-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3671b-243">Riepilogo firewall-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="3671b-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3671b-244">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="3671b-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3671b-245">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="3671b-245">Source IP address</span></span></th>
<th><span data-ttu-id="3671b-246">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="3671b-246">Destination IP address</span></span></th>
<th><span data-ttu-id="3671b-247">Note</span><span class="sxs-lookup"><span data-stu-id="3671b-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3671b-248">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-249">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="3671b-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3671b-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-251">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="3671b-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3671b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3671b-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-254">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="3671b-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3671b-255">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="3671b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-256">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3671b-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3671b-257">Client</span><span class="sxs-lookup"><span data-stu-id="3671b-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="3671b-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-259">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3671b-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3671b-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3671b-261">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-262">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="3671b-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3671b-263">Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="3671b-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3671b-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-266">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="3671b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3671b-267">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3671b-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3671b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3671b-269">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="3671b-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3671b-270">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="3671b-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3671b-271">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3671b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3671b-272">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="3671b-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3671b-273">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="3671b-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3671b-274">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="3671b-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="3671b-275">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="3671b-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3671b-276">Commenti</span><span class="sxs-lookup"><span data-stu-id="3671b-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3671b-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3671b-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3671b-278">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-278">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-279">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="3671b-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-280">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="3671b-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3671b-281">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="3671b-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3671b-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3671b-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3671b-283">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="3671b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3671b-284">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-284">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-285">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="3671b-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3671b-286">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="3671b-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3671b-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3671b-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3671b-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="3671b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="3671b-289">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="3671b-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="3671b-290">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</span><span class="sxs-lookup"><span data-stu-id="3671b-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

