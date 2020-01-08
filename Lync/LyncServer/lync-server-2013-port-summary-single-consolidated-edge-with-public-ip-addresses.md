---
title: Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="76247-102">Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76247-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76247-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="76247-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="76247-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="76247-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="76247-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="76247-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="76247-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="76247-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="76247-107">Le informazioni sulla pianificazione per il proxy inverso e la Federazione si trovano in [scenari per proxy inverso in Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica nelle sezioni di Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="76247-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="76247-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="76247-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="76247-109">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="76247-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="76247-110">**Rete perimetrale aziendale per singoli bordi consolidati con indirizzi IP pubblici**</span><span class="sxs-lookup"><span data-stu-id="76247-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="76247-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="76247-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="76247-112">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="76247-112">Port and Protocol Details</span></span>

<span data-ttu-id="76247-113">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="76247-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="76247-114">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentita per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="76247-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="76247-115">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="76247-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="76247-116">Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="76247-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76247-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="76247-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76247-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="76247-118">Source IP address</span></span></th>
<th><span data-ttu-id="76247-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="76247-119">Destination IP address</span></span></th>
<th><span data-ttu-id="76247-120">Note</span><span class="sxs-lookup"><span data-stu-id="76247-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76247-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76247-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76247-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-122">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-123">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="76247-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="76247-124">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="76247-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="76247-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="76247-126">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-127">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-128">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="76247-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="76247-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="76247-130">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-131">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-132">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="76247-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="76247-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="76247-134">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-135">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-136">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="76247-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-137">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-138">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-139">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-140">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="76247-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-141">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-142">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-143">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-144">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="76247-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-145">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-146">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-147">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-148">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="76247-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-149">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-150">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-151">Indirizzo IP pubblico di Edge Server Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="76247-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-152">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="76247-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="76247-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76247-154">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-155">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-156">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="76247-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="76247-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76247-158">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-159">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-160">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="76247-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="76247-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76247-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-162">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-163">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-164">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="76247-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="76247-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76247-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-166">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-167">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-168">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="76247-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76247-170">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-171">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-172">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="76247-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="76247-173">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="76247-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76247-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-175">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-176">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-177">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-179">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-180">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-181">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-183">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-184">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="76247-186">Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="76247-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76247-187">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="76247-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76247-188">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="76247-188">Source IP address</span></span></th>
<th><span data-ttu-id="76247-189">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="76247-189">Destination IP address</span></span></th>
<th><span data-ttu-id="76247-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="76247-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76247-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="76247-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="76247-192">Any (può essere definito come IP standard server, indirizzo IP del server Standard Edition o indirizzo IP del pool in cui è in uso il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="76247-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="76247-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-194">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="76247-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-196">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="76247-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="76247-197">IP del server perimetrale o pool che contiene l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="76247-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-198">Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</span><span class="sxs-lookup"><span data-stu-id="76247-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-201">Any (può essere definito come Director, indirizzo IP del pool di Director, Front End Server o indirizzo del pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="76247-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="76247-202">Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="76247-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="76247-204">Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="76247-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="76247-205">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-206">Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="76247-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="76247-208">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="76247-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="76247-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-210">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76247-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-212">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-214">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="76247-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-216">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-218">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="76247-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="76247-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="76247-220">Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="76247-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="76247-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-222">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="76247-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="76247-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="76247-224">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-224">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-226">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="76247-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="76247-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="76247-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-228">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-230">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="76247-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="76247-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="76247-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-232">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="76247-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="76247-234">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="76247-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="76247-235">Riepilogo del firewall per la Federazione</span><span class="sxs-lookup"><span data-stu-id="76247-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76247-236">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="76247-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76247-237">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="76247-237">Source IP address</span></span></th>
<th><span data-ttu-id="76247-238">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="76247-238">Destination IP address</span></span></th>
<th><span data-ttu-id="76247-239">Note</span><span class="sxs-lookup"><span data-stu-id="76247-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76247-240">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-241">Indirizzo IP pubblico del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="76247-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-242">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-243">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="76247-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="76247-244">Riepilogo firewall-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="76247-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76247-245">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="76247-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76247-246">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="76247-246">Source IP address</span></span></th>
<th><span data-ttu-id="76247-247">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="76247-247">Destination IP address</span></span></th>
<th><span data-ttu-id="76247-248">Note</span><span class="sxs-lookup"><span data-stu-id="76247-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76247-249">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-250">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="76247-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="76247-251">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-252">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="76247-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-253">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="76247-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="76247-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-255">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="76247-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="76247-256">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="76247-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-257">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="76247-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="76247-258">Client</span><span class="sxs-lookup"><span data-stu-id="76247-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="76247-259">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-260">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="76247-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="76247-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="76247-262">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-263">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="76247-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76247-264">Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="76247-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76247-266">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-267">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="76247-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76247-268">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="76247-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="76247-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="76247-270">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="76247-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="76247-271">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="76247-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="76247-272">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="76247-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="76247-273">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="76247-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76247-274">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="76247-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="76247-275">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="76247-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="76247-276">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="76247-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="76247-277">Commenti</span><span class="sxs-lookup"><span data-stu-id="76247-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76247-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76247-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76247-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-279">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-280">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="76247-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-281">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="76247-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="76247-282">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="76247-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76247-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="76247-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="76247-284">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="76247-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="76247-285">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-285">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-286">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="76247-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="76247-287">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="76247-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76247-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="76247-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="76247-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="76247-289">Any</span></span></p></td>
<td><p><span data-ttu-id="76247-290">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="76247-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="76247-291">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</span><span class="sxs-lookup"><span data-stu-id="76247-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

