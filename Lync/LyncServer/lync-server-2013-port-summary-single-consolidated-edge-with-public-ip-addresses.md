---
title: Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ad4d6dc9b7eda2e476068d5fae4a40d066a0d71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="a3726-102">Riepilogo delle porte - singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3726-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3726-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a3726-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a3726-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a3726-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a3726-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="a3726-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a3726-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="a3726-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="a3726-107">Le informazioni sulla pianificazione per il proxy inverso e la Federazione si trovano in [scenari per proxy inverso in Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica nelle sezioni di Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="a3726-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="a3726-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="a3726-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a3726-109">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="a3726-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a3726-110">**Rete perimetrale aziendale per singoli bordi consolidati con indirizzi IP pubblici**</span><span class="sxs-lookup"><span data-stu-id="a3726-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="a3726-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="a3726-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a3726-112">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="a3726-112">Port and Protocol Details</span></span>

<span data-ttu-id="a3726-113">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="a3726-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a3726-114">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentita per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="a3726-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="a3726-115">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="a3726-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="a3726-116">Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="a3726-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3726-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a3726-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3726-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a3726-118">Source IP address</span></span></th>
<th><span data-ttu-id="a3726-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3726-119">Destination IP address</span></span></th>
<th><span data-ttu-id="a3726-120">Note</span><span class="sxs-lookup"><span data-stu-id="a3726-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3726-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a3726-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a3726-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-122">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-123">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="a3726-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a3726-124">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="a3726-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a3726-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a3726-126">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-127">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-128">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="a3726-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a3726-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a3726-130">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-131">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-132">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="a3726-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a3726-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a3726-134">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-135">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-136">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="a3726-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-137">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-139">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-140">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="a3726-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-141">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-142">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-143">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-144">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="a3726-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-145">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-146">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-147">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-148">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="a3726-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-149">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-151">Indirizzo IP pubblico di Edge Server Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="a3726-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-152">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="a3726-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a3726-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3726-154">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-155">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-156">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3726-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a3726-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3726-158">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-159">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-160">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a3726-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a3726-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3726-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-162">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-163">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-164">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a3726-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a3726-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3726-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-166">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-167">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-168">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a3726-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3726-170">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-171">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-172">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="a3726-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a3726-173">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="a3726-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3726-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-175">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-176">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-177">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-179">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-180">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-181">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-183">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-184">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="a3726-186">Riepilogo del firewall per un singolo bordo consolidato con indirizzi IP pubblici: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="a3726-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3726-187">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a3726-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3726-188">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a3726-188">Source IP address</span></span></th>
<th><span data-ttu-id="a3726-189">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3726-189">Destination IP address</span></span></th>
<th><span data-ttu-id="a3726-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="a3726-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3726-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a3726-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a3726-192">Any (può essere definito come IP standard server, indirizzo IP del server Standard Edition o indirizzo IP del pool in cui è in uso il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="a3726-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a3726-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-194">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="a3726-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-196">Any (può essere definito come Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end)</span><span class="sxs-lookup"><span data-stu-id="a3726-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a3726-197">IP del server perimetrale o pool che contiene l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="a3726-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-198">Traffico SIP in uscita (da Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o pool di front-end) all'interfaccia interna del server Edge</span><span class="sxs-lookup"><span data-stu-id="a3726-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-201">Any (può essere definito come Director, indirizzo IP del pool di Director, Front End Server o indirizzo del pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="a3726-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="a3726-202">Traffico SIP in ingresso (per Director, indirizzo IP del pool di Director, indirizzo IP del server front-end o di front end) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a3726-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a3726-204">Any (può essere definito come indirizzo IP del server front-end o ogni indirizzo IP del server front-end in un pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="a3726-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="a3726-205">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-206">Traffico di Web Conferencing dal server front-end o da ogni server front-end se in un pool, all'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a3726-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a3726-208">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="a3726-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a3726-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-210">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3726-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-212">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-214">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="a3726-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-216">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-218">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="a3726-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a3726-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a3726-220">Any (può essere definito come indirizzo IP del server front-end o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="a3726-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a3726-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-222">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3726-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a3726-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a3726-224">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-224">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-226">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="a3726-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a3726-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a3726-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-228">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-230">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="a3726-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a3726-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a3726-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-232">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="a3726-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3726-234">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="a3726-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="a3726-235">Riepilogo del firewall per la Federazione</span><span class="sxs-lookup"><span data-stu-id="a3726-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3726-236">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a3726-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3726-237">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a3726-237">Source IP address</span></span></th>
<th><span data-ttu-id="a3726-238">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3726-238">Destination IP address</span></span></th>
<th><span data-ttu-id="a3726-239">Note</span><span class="sxs-lookup"><span data-stu-id="a3726-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3726-240">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-241">Indirizzo IP pubblico del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="a3726-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-242">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-243">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="a3726-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a3726-244">Riepilogo firewall-connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a3726-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3726-245">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a3726-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3726-246">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="a3726-246">Source IP address</span></span></th>
<th><span data-ttu-id="a3726-247">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="a3726-247">Destination IP address</span></span></th>
<th><span data-ttu-id="a3726-248">Note</span><span class="sxs-lookup"><span data-stu-id="a3726-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3726-249">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-250">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a3726-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a3726-251">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-252">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="a3726-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-253">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3726-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3726-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-255">Partner di connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="a3726-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a3726-256">Per la connettività di messaggistica istantanea federata e pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="a3726-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-257">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3726-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3726-258">Client</span><span class="sxs-lookup"><span data-stu-id="a3726-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="a3726-259">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-260">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="a3726-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a3726-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3726-262">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-263">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="a3726-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a3726-264">Usato per sessioni A/V con Windows Live Messenger se è configurata la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="a3726-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3726-266">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-267">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="a3726-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a3726-268">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a3726-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3726-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3726-270">Client di Messenger Live</span><span class="sxs-lookup"><span data-stu-id="a3726-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a3726-271">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="a3726-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a3726-272">Obbligatorio per la connettività di messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a3726-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a3726-273">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="a3726-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3726-274">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a3726-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3726-275">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="a3726-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="a3726-276">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="a3726-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a3726-277">Commenti</span><span class="sxs-lookup"><span data-stu-id="a3726-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3726-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a3726-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a3726-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-279">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-280">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="a3726-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-281">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="a3726-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a3726-282">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="a3726-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3726-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a3726-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a3726-284">Indirizzo IP dell'interfaccia del servizio Edge Server Edge</span><span class="sxs-lookup"><span data-stu-id="a3726-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a3726-285">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-285">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-286">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="a3726-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a3726-287">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="a3726-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3726-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a3726-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a3726-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="a3726-289">Any</span></span></p></td>
<td><p><span data-ttu-id="a3726-290">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="a3726-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="a3726-291">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool di Edge</span><span class="sxs-lookup"><span data-stu-id="a3726-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

