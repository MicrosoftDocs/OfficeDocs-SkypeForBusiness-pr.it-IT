---
title: Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP privati tramite NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="ba957-102">Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba957-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba957-103">_**Argomento Ultima modifica:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="ba957-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="ba957-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ba957-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ba957-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="ba957-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ba957-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ba957-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="ba957-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba957-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ba957-108">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="ba957-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ba957-109">**Perimetro di rete per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="ba957-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="ba957-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ba957-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ba957-111">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="ba957-111">Port and Protocol Details</span></span>

<span data-ttu-id="ba957-112">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ba957-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ba957-113">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentito per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="ba957-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="ba957-114">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea, presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="ba957-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="ba957-115">Riepilogo del firewall per il singolo Edge consolidato con indirizzi IP privati tramite NAT: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="ba957-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba957-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba957-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba957-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba957-117">Source IP address</span></span></th>
<th><span data-ttu-id="ba957-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba957-118">Destination IP address</span></span></th>
<th><span data-ttu-id="ba957-119">Note</span><span class="sxs-lookup"><span data-stu-id="ba957-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba957-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba957-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba957-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-121">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-122">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="ba957-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ba957-123">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="ba957-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ba957-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ba957-125">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-127">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="ba957-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ba957-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ba957-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-130">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-131">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="ba957-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ba957-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ba957-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-135">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="ba957-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-136">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-137">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-137">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-138">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-139">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="ba957-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-140">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-143">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba957-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-144">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-145">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-146">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-146">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-147">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba957-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-148">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-150">Edge Server Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-151">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="ba957-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba957-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba957-153">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-155">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba957-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba957-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba957-157">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-159">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ba957-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba957-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba957-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-161">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-162">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-163">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba957-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba957-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba957-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-165">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-166">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-167">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba957-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba957-169">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-171">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="ba957-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ba957-172">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="ba957-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba957-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-175">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-176">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-179">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-180">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-182">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-183">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-183">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-184">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="ba957-185">Riepilogo del firewall per il singolo Edge consolidato con indirizzi IP privati tramite NAT: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="ba957-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba957-186">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba957-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba957-187">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba957-187">Source IP address</span></span></th>
<th><span data-ttu-id="ba957-188">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba957-188">Destination IP address</span></span></th>
<th><span data-ttu-id="ba957-189">Commenti</span><span class="sxs-lookup"><span data-stu-id="ba957-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba957-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ba957-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ba957-191">Any (può essere definito come IP standard server, indirizzo IP del server Standard Edition o indirizzo IP del pool in cui è in uso il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="ba957-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ba957-192">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-193">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="ba957-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-195">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="ba957-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba957-196">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-197">Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</span><span class="sxs-lookup"><span data-stu-id="ba957-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-199">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-200">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="ba957-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba957-201">Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba957-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ba957-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ba957-203">Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="ba957-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ba957-204">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-205">Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba957-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ba957-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ba957-207">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="ba957-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ba957-208">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-209">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba957-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba957-211">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-211">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-212">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-213">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ba957-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-215">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-215">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-216">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-217">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="ba957-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ba957-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ba957-219">Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="ba957-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ba957-220">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-221">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba957-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ba957-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ba957-223">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-223">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-224">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-225">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="ba957-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ba957-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ba957-227">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-227">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-228">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-229">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="ba957-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ba957-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ba957-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-231">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-232">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba957-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba957-233">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="ba957-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ba957-234">Riepilogo del firewall per la Federazione</span><span class="sxs-lookup"><span data-stu-id="ba957-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba957-235">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba957-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba957-236">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba957-236">Source IP address</span></span></th>
<th><span data-ttu-id="ba957-237">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba957-237">Destination IP address</span></span></th>
<th><span data-ttu-id="ba957-238">Note</span><span class="sxs-lookup"><span data-stu-id="ba957-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba957-239">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-240">Indirizzo IP pubblico del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="ba957-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba957-241">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-241">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-242">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba957-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ba957-243">Riepilogo firewall-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="ba957-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba957-244">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba957-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba957-245">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba957-245">Source IP address</span></span></th>
<th><span data-ttu-id="ba957-246">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba957-246">Destination IP address</span></span></th>
<th><span data-ttu-id="ba957-247">Note</span><span class="sxs-lookup"><span data-stu-id="ba957-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba957-248">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-249">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="ba957-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ba957-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-251">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba957-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-252">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba957-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba957-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-254">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="ba957-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ba957-255">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba957-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-256">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba957-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba957-257">Client</span><span class="sxs-lookup"><span data-stu-id="ba957-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba957-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-259">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="ba957-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba957-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba957-261">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-262">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="ba957-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba957-263">Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="ba957-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba957-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-266">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="ba957-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba957-267">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba957-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba957-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba957-269">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="ba957-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba957-270">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="ba957-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba957-271">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba957-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ba957-272">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="ba957-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba957-273">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba957-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba957-274">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="ba957-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="ba957-275">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="ba957-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ba957-276">Commenti</span><span class="sxs-lookup"><span data-stu-id="ba957-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba957-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba957-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba957-278">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-278">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-279">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="ba957-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ba957-280">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="ba957-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ba957-281">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="ba957-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba957-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba957-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba957-283">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="ba957-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ba957-284">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-284">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-285">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="ba957-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ba957-286">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="ba957-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba957-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ba957-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ba957-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba957-288">Any</span></span></p></td>
<td><p><span data-ttu-id="ba957-289">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="ba957-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ba957-290">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</span><span class="sxs-lookup"><span data-stu-id="ba957-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

