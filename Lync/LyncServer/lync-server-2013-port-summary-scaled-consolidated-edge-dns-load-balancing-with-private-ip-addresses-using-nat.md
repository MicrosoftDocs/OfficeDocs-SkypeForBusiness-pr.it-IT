---
title: 'Lync Server 2013: base di riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT'
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
ms.openlocfilehash: 7c26dfe63e468d7b8d6f4ae557c0b84af2ffceaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="a6361-102">Riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6361-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6361-103">_**Ultimo argomento modificato:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a6361-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a6361-104">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a6361-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a6361-105">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="a6361-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a6361-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="a6361-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a6361-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="a6361-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a6361-108">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="a6361-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a6361-109">**Rete perimetrale aziendale per l'Edge consolidato in scala con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="a6361-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="a6361-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="a6361-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a6361-111">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="a6361-111">Port and Protocol Details</span></span>

<span data-ttu-id="a6361-112">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a6361-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a6361-p103">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.</span><span class="sxs-lookup"><span data-stu-id="a6361-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a6361-115">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia esterna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="a6361-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6361-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a6361-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6361-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a6361-117">Source IP address</span></span></th>
<th><span data-ttu-id="a6361-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a6361-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a6361-119">Notes</span><span class="sxs-lookup"><span data-stu-id="a6361-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6361-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6361-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6361-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-121">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-122">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="a6361-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a6361-123">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="a6361-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6361-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6361-125">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="a6361-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a6361-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-127">Il servizio proxy XMPP invia traffico ai contatti XMPP nelle federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="a6361-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a6361-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a6361-129">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-131">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="a6361-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-132">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a6361-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a6361-133">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-135">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="a6361-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-136">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a6361-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a6361-137">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-139">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="a6361-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-140">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-142">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-143">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="a6361-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-144">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-145">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-146">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-147">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="a6361-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-148">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-149">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-151">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="a6361-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-152">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="a6361-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-153">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-153">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-154">Servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-155">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="a6361-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a6361-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6361-157">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-159">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6361-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a6361-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6361-161">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-162">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-163">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a6361-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a6361-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6361-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-165">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-166">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-167">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a6361-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a6361-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6361-169">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-169">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-170">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-171">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a6361-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6361-173">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-174">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-175">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="a6361-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a6361-176">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="a6361-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6361-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-179">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-180">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-182">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-182">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-183">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-184">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-186">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-187">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-187">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-188">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="a6361-189">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT: interfaccia interna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="a6361-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6361-190">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a6361-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6361-191">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a6361-191">Source IP address</span></span></th>
<th><span data-ttu-id="a6361-192">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a6361-192">Destination IP address</span></span></th>
<th><span data-ttu-id="a6361-193">Commenti</span><span class="sxs-lookup"><span data-stu-id="a6361-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6361-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a6361-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a6361-195">Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP del pool Front end che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="a6361-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a6361-196">Indirizzo IP dell'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6361-197">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="a6361-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-199">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="a6361-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a6361-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-201">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-203">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-204">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="a6361-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a6361-205">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a6361-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a6361-207">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="a6361-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="a6361-208">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-209">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a6361-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a6361-211">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="a6361-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a6361-212">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-213">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6361-215">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-215">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-216">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-217">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="a6361-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-219">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-219">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-220">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-221">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="a6361-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a6361-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a6361-223">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="a6361-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a6361-224">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-225">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a6361-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a6361-227">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-227">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-228">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-229">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="a6361-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a6361-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a6361-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-231">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-232">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-233">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="a6361-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a6361-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a6361-235">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-236">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a6361-237">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="a6361-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="a6361-238">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="a6361-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6361-239">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a6361-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6361-240">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a6361-240">Source IP address</span></span></th>
<th><span data-ttu-id="a6361-241">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a6361-241">Destination IP address</span></span></th>
<th><span data-ttu-id="a6361-242">Notes</span><span class="sxs-lookup"><span data-stu-id="a6361-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6361-243">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-244">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="a6361-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a6361-245">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-245">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-246">Per connettività per messaggistica istantanea pubblica e federata tramite SIP</span><span class="sxs-lookup"><span data-stu-id="a6361-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a6361-247">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a6361-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6361-248">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a6361-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6361-249">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a6361-249">Source IP address</span></span></th>
<th><span data-ttu-id="a6361-250">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a6361-250">Destination IP address</span></span></th>
<th><span data-ttu-id="a6361-251">Notes</span><span class="sxs-lookup"><span data-stu-id="a6361-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6361-252">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-253">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a6361-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a6361-254">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-255">Per connettività di messaggistica istantanea pubblica e federata con SIP
</span><span class="sxs-lookup"><span data-stu-id="a6361-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-256">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a6361-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a6361-257">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-258">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a6361-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a6361-259">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="a6361-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-260">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a6361-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a6361-261">Client</span><span class="sxs-lookup"><span data-stu-id="a6361-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="a6361-262">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-263">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="a6361-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a6361-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a6361-265">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-266">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a6361-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6361-267">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="a6361-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6361-269">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-270">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a6361-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6361-271">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a6361-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a6361-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a6361-273">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a6361-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a6361-274">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a6361-275">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a6361-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a6361-276">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="a6361-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6361-277">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a6361-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a6361-278">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="a6361-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="a6361-279">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="a6361-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a6361-280">Commenti</span><span class="sxs-lookup"><span data-stu-id="a6361-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6361-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6361-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6361-282">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-282">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-283">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6361-284">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="a6361-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6361-285">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="a6361-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6361-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a6361-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a6361-287">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a6361-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-289">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="a6361-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a6361-290">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="a6361-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6361-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a6361-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a6361-292">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a6361-292">Any</span></span></p></td>
<td><p><span data-ttu-id="a6361-293">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="a6361-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="a6361-294">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="a6361-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

