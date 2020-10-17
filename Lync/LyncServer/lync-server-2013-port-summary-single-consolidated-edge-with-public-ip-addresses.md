---
title: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici
description: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici.
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566402"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="648ce-103">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="648ce-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="648ce-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="648ce-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="648ce-105">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="648ce-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="648ce-106">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="648ce-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="648ce-107">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="648ce-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="648ce-108">Le informazioni sulla pianificazione per il proxy inverso e la Federazione sono disponibili in [scenari per il proxy inverso in Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [la pianificazione per SIP, la Federazione XMPP e la messaggistica istantanea pubblica nelle sezioni di Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="648ce-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="648ce-109">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="648ce-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="648ce-110">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="648ce-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="648ce-111">**Rete perimetrale aziendale per un singolo perimetro consolidato con indirizzamento IP pubblico**</span><span class="sxs-lookup"><span data-stu-id="648ce-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="648ce-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="648ce-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="648ce-113">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="648ce-113">Port and Protocol Details</span></span>

<span data-ttu-id="648ce-114">È consigliabile aprire le porte necessarie per il supporto della funzionalità per la quale si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="648ce-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="648ce-p103">Affinché l'accesso remoto funzioni con qualsiasi servizio perimetrale, è necessario consentire il flusso bidirezionale del traffico SIP, come mostrato nella figura relativa al traffico perimetrale in ingresso/in uscita. In altre parole, le funzionalità di messaggistica istantanea (IM), informazioni sulla presenza, Web Conferencing, audio/video (A/V) e federazione comportano l'uso della messaggistica SIP verso e dal servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="648ce-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="648ce-117">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP pubblici: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="648ce-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648ce-118">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="648ce-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="648ce-119">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="648ce-119">Source IP address</span></span></th>
<th><span data-ttu-id="648ce-120">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="648ce-120">Destination IP address</span></span></th>
<th><span data-ttu-id="648ce-121">Note</span><span class="sxs-lookup"><span data-stu-id="648ce-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648ce-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="648ce-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="648ce-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-123">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-124">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="648ce-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="648ce-125">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="648ce-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="648ce-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="648ce-127">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-128">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-128">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-129">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="648ce-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-130">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="648ce-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="648ce-131">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-132">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-133">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="648ce-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-134">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="648ce-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="648ce-135">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-136">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-136">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-137">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="648ce-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-138">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-139">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-140">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-141">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="648ce-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-142">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-143">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-144">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-145">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="648ce-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-146">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-147">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-148">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-149">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="648ce-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-150">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="648ce-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-151">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-151">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-152">Indirizzo IP pubblico del servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-153">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="648ce-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-154">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="648ce-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="648ce-155">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-156">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-156">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-157">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="648ce-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-158">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="648ce-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="648ce-159">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-160">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-160">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-161">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="648ce-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-162">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="648ce-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="648ce-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-163">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-164">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-165">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="648ce-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-166">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="648ce-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="648ce-167">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-167">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-168">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-169">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="648ce-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-170">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="648ce-171">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-172">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-172">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-173">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="648ce-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="648ce-174">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="648ce-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-175">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="648ce-176">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-176">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-177">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-178">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-179">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-180">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-180">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-181">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-182">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-183">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-184">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-185">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-185">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-186">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="648ce-187">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP pubblici: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="648ce-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648ce-188">Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="648ce-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="648ce-189">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="648ce-189">Source IP address</span></span></th>
<th><span data-ttu-id="648ce-190">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="648ce-190">Destination IP address</span></span></th>
<th><span data-ttu-id="648ce-191">Commenti</span><span class="sxs-lookup"><span data-stu-id="648ce-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648ce-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="648ce-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="648ce-193">Qualsiasi (può essere definito come IP Server Standard Edition, indirizzo IP del server Standard Edition o indirizzo IP del pool che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="648ce-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="648ce-194">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-195">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="648ce-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-197">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="648ce-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="648ce-198">IP del server perimetrale o pool che contiene l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="648ce-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-199">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-201">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-202">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="648ce-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="648ce-203">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="648ce-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="648ce-205">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="648ce-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="648ce-206">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-207">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="648ce-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="648ce-209">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="648ce-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="648ce-210">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-211">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="648ce-213">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-213">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-214">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-215">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="648ce-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-217">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-217">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-218">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-219">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="648ce-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="648ce-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="648ce-221">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="648ce-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="648ce-222">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-223">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="648ce-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="648ce-225">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-225">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-226">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-227">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="648ce-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="648ce-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="648ce-229">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-229">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-230">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-231">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="648ce-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="648ce-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="648ce-233">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-233">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-234">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="648ce-235">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="648ce-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="648ce-236">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="648ce-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648ce-237">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="648ce-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="648ce-238">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="648ce-238">Source IP address</span></span></th>
<th><span data-ttu-id="648ce-239">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="648ce-239">Destination IP address</span></span></th>
<th><span data-ttu-id="648ce-240">Note</span><span class="sxs-lookup"><span data-stu-id="648ce-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648ce-241">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-242">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="648ce-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-243">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-243">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-244">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="648ce-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="648ce-245">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="648ce-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648ce-246">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="648ce-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="648ce-247">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="648ce-247">Source IP address</span></span></th>
<th><span data-ttu-id="648ce-248">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="648ce-248">Destination IP address</span></span></th>
<th><span data-ttu-id="648ce-249">Note</span><span class="sxs-lookup"><span data-stu-id="648ce-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648ce-250">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-251">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="648ce-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="648ce-252">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-253">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="648ce-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-254">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="648ce-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="648ce-255">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-256">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="648ce-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="648ce-257">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="648ce-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-258">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="648ce-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="648ce-259">Client</span><span class="sxs-lookup"><span data-stu-id="648ce-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="648ce-260">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-261">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="648ce-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-262">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="648ce-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="648ce-263">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-264">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="648ce-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="648ce-265">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="648ce-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-266">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="648ce-267">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-268">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="648ce-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="648ce-269">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="648ce-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-270">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="648ce-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="648ce-271">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="648ce-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="648ce-272">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="648ce-273">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="648ce-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="648ce-274">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="648ce-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="648ce-275">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="648ce-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="648ce-276">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="648ce-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="648ce-277">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="648ce-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="648ce-278">Commenti</span><span class="sxs-lookup"><span data-stu-id="648ce-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="648ce-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="648ce-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="648ce-280">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-280">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-281">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-282">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="648ce-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="648ce-283">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="648ce-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="648ce-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="648ce-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="648ce-285">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="648ce-286">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-286">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-287">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="648ce-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="648ce-288">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="648ce-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="648ce-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="648ce-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="648ce-290">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="648ce-290">Any</span></span></p></td>
<td><p><span data-ttu-id="648ce-291">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="648ce-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="648ce-292">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="648ce-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

