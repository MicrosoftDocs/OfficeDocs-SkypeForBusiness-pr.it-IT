---
title: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT
description: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT.
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
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564562"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="16a86-103">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16a86-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16a86-104">_**Ultimo argomento modificato:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="16a86-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="16a86-105">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="16a86-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="16a86-106">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="16a86-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="16a86-107">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="16a86-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="16a86-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="16a86-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="16a86-109">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="16a86-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="16a86-110">**Perimetro di rete per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="16a86-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="16a86-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="16a86-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="16a86-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="16a86-112">Port and Protocol Details</span></span>

<span data-ttu-id="16a86-113">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="16a86-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="16a86-114">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="16a86-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="16a86-115">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea, presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="16a86-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="16a86-116">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="16a86-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16a86-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="16a86-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="16a86-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="16a86-118">Source IP address</span></span></th>
<th><span data-ttu-id="16a86-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="16a86-119">Destination IP address</span></span></th>
<th><span data-ttu-id="16a86-120">Note</span><span class="sxs-lookup"><span data-stu-id="16a86-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16a86-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="16a86-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="16a86-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-122">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-123">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="16a86-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="16a86-124">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="16a86-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="16a86-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="16a86-126">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-127">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-128">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="16a86-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-129">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="16a86-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="16a86-130">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-131">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-132">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="16a86-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-133">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="16a86-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="16a86-134">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-135">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-136">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="16a86-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-137">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-138">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-139">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-140">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="16a86-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-141">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-142">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-143">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-144">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="16a86-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-145">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-146">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-147">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-148">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="16a86-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-149">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="16a86-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-150">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-151">Servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-152">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="16a86-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="16a86-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="16a86-154">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-155">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-156">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16a86-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="16a86-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="16a86-158">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-159">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-160">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="16a86-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="16a86-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="16a86-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-162">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-163">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-164">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="16a86-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="16a86-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="16a86-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-166">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-167">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-168">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="16a86-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="16a86-170">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-171">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-172">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="16a86-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="16a86-173">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="16a86-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="16a86-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-175">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-176">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-177">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-179">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-180">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-181">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-183">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-184">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="16a86-186">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="16a86-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16a86-187">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="16a86-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="16a86-188">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="16a86-188">Source IP address</span></span></th>
<th><span data-ttu-id="16a86-189">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="16a86-189">Destination IP address</span></span></th>
<th><span data-ttu-id="16a86-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="16a86-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16a86-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="16a86-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="16a86-192">Qualsiasi (può essere definito come IP Server Standard Edition, indirizzo IP del server Standard Edition o indirizzo IP del pool che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="16a86-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="16a86-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-194">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="16a86-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-196">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="16a86-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="16a86-197">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-198">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-201">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="16a86-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="16a86-202">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="16a86-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="16a86-204">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="16a86-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="16a86-205">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-206">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="16a86-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="16a86-208">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="16a86-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="16a86-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-210">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="16a86-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-212">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-214">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="16a86-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-216">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-218">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="16a86-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="16a86-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="16a86-220">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="16a86-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="16a86-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-222">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="16a86-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="16a86-224">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-224">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-226">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="16a86-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="16a86-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="16a86-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-228">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-230">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="16a86-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="16a86-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="16a86-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-232">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="16a86-234">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="16a86-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="16a86-235">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="16a86-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16a86-236">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="16a86-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="16a86-237">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="16a86-237">Source IP address</span></span></th>
<th><span data-ttu-id="16a86-238">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="16a86-238">Destination IP address</span></span></th>
<th><span data-ttu-id="16a86-239">Note</span><span class="sxs-lookup"><span data-stu-id="16a86-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16a86-240">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-241">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="16a86-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="16a86-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-242">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-243">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="16a86-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="16a86-244">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="16a86-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16a86-245">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="16a86-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="16a86-246">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="16a86-246">Source IP address</span></span></th>
<th><span data-ttu-id="16a86-247">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="16a86-247">Destination IP address</span></span></th>
<th><span data-ttu-id="16a86-248">Note</span><span class="sxs-lookup"><span data-stu-id="16a86-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16a86-249">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-250">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="16a86-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="16a86-251">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-252">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="16a86-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-253">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="16a86-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="16a86-254">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-255">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="16a86-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="16a86-256">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="16a86-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-257">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="16a86-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="16a86-258">Client</span><span class="sxs-lookup"><span data-stu-id="16a86-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="16a86-259">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-260">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="16a86-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="16a86-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="16a86-262">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-263">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16a86-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="16a86-264">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="16a86-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="16a86-266">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-267">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16a86-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="16a86-268">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16a86-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="16a86-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="16a86-270">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16a86-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="16a86-271">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="16a86-272">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="16a86-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="16a86-273">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="16a86-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="16a86-274">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="16a86-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="16a86-275">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="16a86-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="16a86-276">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="16a86-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="16a86-277">Commenti</span><span class="sxs-lookup"><span data-stu-id="16a86-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="16a86-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="16a86-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="16a86-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-279">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-280">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="16a86-281">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="16a86-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="16a86-282">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="16a86-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="16a86-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="16a86-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="16a86-284">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="16a86-285">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-285">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-286">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="16a86-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="16a86-287">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="16a86-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="16a86-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="16a86-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="16a86-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="16a86-289">Any</span></span></p></td>
<td><p><span data-ttu-id="16a86-290">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="16a86-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="16a86-291">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="16a86-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

