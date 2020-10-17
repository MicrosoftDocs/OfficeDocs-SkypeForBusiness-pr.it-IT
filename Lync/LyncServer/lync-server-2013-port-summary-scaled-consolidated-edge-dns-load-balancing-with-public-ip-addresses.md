---
title: 'Lync Server 2013: riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici'
description: 'Lync Server 2013: Consolidated Edge di riepilogo delle porte, bilanciamento del carico DNS con indirizzi IP pubblici.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8090435485b4b6a183702a608b139cec91ae26a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563922"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="62404-103">Riepilogo delle porte-perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62404-103">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62404-104">_**Ultimo argomento modificato:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="62404-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="62404-105">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="62404-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="62404-106">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="62404-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="62404-107">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="62404-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="62404-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="62404-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="62404-109">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="62404-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="62404-110">**Rete perimetrale aziendale per Edge consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici**</span><span class="sxs-lookup"><span data-stu-id="62404-110">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="62404-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="62404-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="62404-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="62404-112">Port and Protocol Details</span></span>

<span data-ttu-id="62404-113">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="62404-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="62404-p103">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.</span><span class="sxs-lookup"><span data-stu-id="62404-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="62404-116">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici: interfaccia esterna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="62404-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62404-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="62404-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="62404-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="62404-118">Source IP address</span></span></th>
<th><span data-ttu-id="62404-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="62404-119">Destination IP address</span></span></th>
<th><span data-ttu-id="62404-120">Note</span><span class="sxs-lookup"><span data-stu-id="62404-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62404-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="62404-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="62404-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-122">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-123">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="62404-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="62404-124">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="62404-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="62404-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="62404-126">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-127">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-128">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="62404-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-129">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="62404-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="62404-130">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-131">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-132">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="62404-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-133">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="62404-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="62404-134">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-135">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-136">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="62404-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-137">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-138">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-139">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-140">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="62404-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-141">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-142">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-143">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-144">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="62404-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-145">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-146">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-147">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-148">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="62404-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-149">Web Conferencing/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-149">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-150">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-151">Indirizzo IP pubblico del servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-152">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="62404-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="62404-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="62404-154">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-154">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-155">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-156">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62404-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="62404-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="62404-158">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-159">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-160">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="62404-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="62404-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="62404-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-162">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-163">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-164">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="62404-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="62404-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="62404-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-166">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-167">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-168">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="62404-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="62404-170">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-171">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-172">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="62404-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="62404-173">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="62404-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="62404-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-175">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-176">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-177">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-179">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-180">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-181">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-183">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-184">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="62404-186">Riepilogo firewall per topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici: interfaccia interna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="62404-186">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62404-187">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="62404-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="62404-188">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="62404-188">Source IP address</span></span></th>
<th><span data-ttu-id="62404-189">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="62404-189">Destination IP address</span></span></th>
<th><span data-ttu-id="62404-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="62404-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62404-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="62404-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="62404-192">Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP del pool Front end che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="62404-192">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="62404-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-194">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="62404-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-196">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="62404-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="62404-197">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-198">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-201">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="62404-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="62404-202">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="62404-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="62404-204">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="62404-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="62404-205">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-206">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="62404-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="62404-208">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="62404-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="62404-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-210">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="62404-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-212">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-214">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="62404-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-216">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-218">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="62404-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="62404-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="62404-220">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="62404-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="62404-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-222">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="62404-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="62404-224">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-224">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-226">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="62404-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="62404-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="62404-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-228">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-230">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="62404-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="62404-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="62404-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-232">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="62404-234">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="62404-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="62404-235">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="62404-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62404-236">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="62404-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="62404-237">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="62404-237">Source IP address</span></span></th>
<th><span data-ttu-id="62404-238">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="62404-238">Destination IP address</span></span></th>
<th><span data-ttu-id="62404-239">Note</span><span class="sxs-lookup"><span data-stu-id="62404-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62404-240">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-241">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="62404-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-242">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-243">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="62404-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="62404-244">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="62404-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62404-245">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="62404-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="62404-246">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="62404-246">Source IP address</span></span></th>
<th><span data-ttu-id="62404-247">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="62404-247">Destination IP address</span></span></th>
<th><span data-ttu-id="62404-248">Note</span><span class="sxs-lookup"><span data-stu-id="62404-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62404-249">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-250">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="62404-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="62404-251">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-252">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="62404-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-253">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="62404-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="62404-254">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-255">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="62404-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="62404-256">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="62404-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-257">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="62404-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="62404-258">Client</span><span class="sxs-lookup"><span data-stu-id="62404-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="62404-259">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-260">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="62404-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="62404-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="62404-262">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-263">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="62404-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="62404-264">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="62404-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="62404-266">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-267">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="62404-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="62404-268">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="62404-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="62404-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="62404-270">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="62404-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="62404-271">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="62404-272">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="62404-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="62404-273">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="62404-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62404-274">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="62404-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="62404-275">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="62404-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="62404-276">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="62404-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="62404-277">Commenti</span><span class="sxs-lookup"><span data-stu-id="62404-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62404-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="62404-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="62404-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-279">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-280">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-281">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="62404-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="62404-282">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="62404-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62404-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="62404-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="62404-284">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="62404-285">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-285">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-286">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="62404-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="62404-287">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="62404-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62404-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="62404-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="62404-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="62404-289">Any</span></span></p></td>
<td><p><span data-ttu-id="62404-290">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="62404-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="62404-291">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="62404-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

