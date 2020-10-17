---
title: 'Lync Server 2013: base di riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
description: 'Lync Server 2013: Consolidated Edge di riepilogo delle porte, bilanciamento del carico DNS con indirizzi IP privati tramite NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563942"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9fb99-103">Riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fb99-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fb99-104">_**Ultimo argomento modificato:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="9fb99-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="9fb99-105">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9fb99-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9fb99-106">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="9fb99-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9fb99-107">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="9fb99-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9fb99-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="9fb99-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9fb99-109">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="9fb99-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9fb99-110">**Rete perimetrale aziendale per l'Edge consolidato in scala con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="9fb99-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="9fb99-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="9fb99-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9fb99-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="9fb99-112">Port and Protocol Details</span></span>

<span data-ttu-id="9fb99-113">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9fb99-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9fb99-p103">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.</span><span class="sxs-lookup"><span data-stu-id="9fb99-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="9fb99-116">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia esterna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="9fb99-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb99-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9fb99-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9fb99-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9fb99-118">Source IP address</span></span></th>
<th><span data-ttu-id="9fb99-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9fb99-119">Destination IP address</span></span></th>
<th><span data-ttu-id="9fb99-120">Note</span><span class="sxs-lookup"><span data-stu-id="9fb99-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9fb99-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9fb99-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-122">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-123">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="9fb99-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-124">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="9fb99-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9fb99-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9fb99-126">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="9fb99-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-127">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-128">Il servizio proxy XMPP invia traffico ai contatti XMPP nelle federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="9fb99-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9fb99-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9fb99-130">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-131">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-132">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="9fb99-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-133">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9fb99-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9fb99-134">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-135">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-136">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="9fb99-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-137">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9fb99-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9fb99-138">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-139">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-140">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="9fb99-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-141">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-142">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-143">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-144">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="9fb99-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-145">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-146">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-146">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-147">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-148">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9fb99-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-149">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-150">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-151">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-151">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-152">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9fb99-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-153">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="9fb99-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-154">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-155">Servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-156">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="9fb99-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-157">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9fb99-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9fb99-158">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-159">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-160">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9fb99-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-161">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9fb99-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9fb99-162">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-163">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-164">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9fb99-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-165">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9fb99-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9fb99-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-166">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-167">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-168">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9fb99-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-169">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9fb99-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9fb99-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-170">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-171">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-172">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9fb99-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9fb99-174">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-175">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-176">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="9fb99-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9fb99-177">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="9fb99-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-178">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9fb99-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-179">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-180">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-181">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-183">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-183">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-184">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-186">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-187">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-188">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-188">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-189">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="9fb99-190">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia interna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="9fb99-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb99-191">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9fb99-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9fb99-192">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9fb99-192">Source IP address</span></span></th>
<th><span data-ttu-id="9fb99-193">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9fb99-193">Destination IP address</span></span></th>
<th><span data-ttu-id="9fb99-194">Commenti</span><span class="sxs-lookup"><span data-stu-id="9fb99-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9fb99-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9fb99-196">Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP del pool Front end che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="9fb99-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-197">Indirizzo IP dell'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9fb99-198">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="9fb99-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-200">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="9fb99-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-201">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-202">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-204">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-205">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="9fb99-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-206">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9fb99-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9fb99-208">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="9fb99-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-210">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9fb99-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9fb99-212">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="9fb99-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-214">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9fb99-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-216">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-218">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9fb99-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-220">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-220">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-222">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="9fb99-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9fb99-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-224">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="9fb99-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9fb99-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-226">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9fb99-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9fb99-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-228">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-230">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9fb99-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9fb99-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9fb99-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-232">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-234">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9fb99-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9fb99-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9fb99-236">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-236">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-237">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9fb99-238">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9fb99-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9fb99-239">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="9fb99-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb99-240">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9fb99-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9fb99-241">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9fb99-241">Source IP address</span></span></th>
<th><span data-ttu-id="9fb99-242">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9fb99-242">Destination IP address</span></span></th>
<th><span data-ttu-id="9fb99-243">Note</span><span class="sxs-lookup"><span data-stu-id="9fb99-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-244">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-245">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="9fb99-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9fb99-246">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-246">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-247">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9fb99-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9fb99-248">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9fb99-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb99-249">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9fb99-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9fb99-250">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9fb99-250">Source IP address</span></span></th>
<th><span data-ttu-id="9fb99-251">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9fb99-251">Destination IP address</span></span></th>
<th><span data-ttu-id="9fb99-252">Note</span><span class="sxs-lookup"><span data-stu-id="9fb99-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-253">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-254">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9fb99-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9fb99-255">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-256">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9fb99-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-257">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9fb99-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9fb99-258">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-259">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9fb99-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9fb99-260">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9fb99-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-261">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9fb99-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9fb99-262">Client</span><span class="sxs-lookup"><span data-stu-id="9fb99-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="9fb99-263">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-264">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="9fb99-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-265">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9fb99-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9fb99-266">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-267">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9fb99-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9fb99-268">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="9fb99-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9fb99-270">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-271">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9fb99-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9fb99-272">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9fb99-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-273">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9fb99-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9fb99-274">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9fb99-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9fb99-275">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9fb99-276">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9fb99-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9fb99-277">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="9fb99-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb99-278">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9fb99-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9fb99-279">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9fb99-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="9fb99-280">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9fb99-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9fb99-281">Commenti</span><span class="sxs-lookup"><span data-stu-id="9fb99-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9fb99-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9fb99-283">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-283">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-284">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9fb99-285">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9fb99-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9fb99-286">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="9fb99-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb99-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9fb99-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9fb99-288">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9fb99-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-289">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-290">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9fb99-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9fb99-291">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="9fb99-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb99-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9fb99-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9fb99-293">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9fb99-293">Any</span></span></p></td>
<td><p><span data-ttu-id="9fb99-294">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="9fb99-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="9fb99-295">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="9fb99-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

