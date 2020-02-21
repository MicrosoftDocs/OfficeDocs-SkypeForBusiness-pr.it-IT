---
title: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT
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
ms.openlocfilehash: 870732df847d589ebb24751977babc8182d79a3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9c320-102">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c320-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c320-103">_**Ultimo argomento modificato:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="9c320-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="9c320-104">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="9c320-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9c320-105">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="9c320-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9c320-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="9c320-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9c320-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="9c320-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9c320-108">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="9c320-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9c320-109">**Perimetro di rete per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT**</span><span class="sxs-lookup"><span data-stu-id="9c320-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="9c320-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="9c320-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9c320-111">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="9c320-111">Port and Protocol Details</span></span>

<span data-ttu-id="9c320-112">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="9c320-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9c320-113">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="9c320-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="9c320-114">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea, presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="9c320-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="9c320-115">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="9c320-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c320-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9c320-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c320-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9c320-117">Source IP address</span></span></th>
<th><span data-ttu-id="9c320-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9c320-118">Destination IP address</span></span></th>
<th><span data-ttu-id="9c320-119">Notes</span><span class="sxs-lookup"><span data-stu-id="9c320-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c320-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9c320-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9c320-121">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-122">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="9c320-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9c320-123">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="9c320-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9c320-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9c320-125">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-127">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="9c320-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-128">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9c320-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9c320-129">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-130">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-131">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="9c320-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-132">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9c320-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9c320-133">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-135">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="9c320-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-136">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-137">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-137">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-138">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-139">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="9c320-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-140">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-142">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-143">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9c320-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-144">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-145">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-146">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-146">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-147">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9c320-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-148">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="9c320-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-149">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-149">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-150">Servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-151">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="9c320-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9c320-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9c320-153">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-154">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-155">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c320-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9c320-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9c320-157">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-159">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="9c320-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9c320-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9c320-161">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-161">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-162">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-163">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9c320-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9c320-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9c320-165">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-166">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-167">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9c320-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9c320-169">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-170">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-170">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-171">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="9c320-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9c320-172">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="9c320-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9c320-174">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-175">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-176">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-178">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-179">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-180">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-182">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-183">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-183">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-184">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="9c320-185">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP privati tramite NAT: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="9c320-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c320-186">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9c320-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c320-187">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9c320-187">Source IP address</span></span></th>
<th><span data-ttu-id="9c320-188">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9c320-188">Destination IP address</span></span></th>
<th><span data-ttu-id="9c320-189">Commenti</span><span class="sxs-lookup"><span data-stu-id="9c320-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c320-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9c320-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9c320-191">Qualsiasi (può essere definito come IP Server Standard Edition, indirizzo IP del server Standard Edition o indirizzo IP del pool che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="9c320-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9c320-192">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-193">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="9c320-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-195">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="9c320-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9c320-196">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-197">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-199">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-200">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="9c320-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9c320-201">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9c320-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9c320-203">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="9c320-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9c320-204">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-205">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9c320-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9c320-207">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="9c320-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9c320-208">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-209">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9c320-211">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-211">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-212">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-213">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9c320-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-215">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-215">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-216">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-217">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="9c320-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9c320-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9c320-219">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="9c320-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9c320-220">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-221">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9c320-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9c320-223">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-223">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-224">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-225">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9c320-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9c320-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9c320-227">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-227">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-228">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-229">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9c320-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9c320-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9c320-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-231">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-232">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9c320-233">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="9c320-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9c320-234">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="9c320-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c320-235">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9c320-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c320-236">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9c320-236">Source IP address</span></span></th>
<th><span data-ttu-id="9c320-237">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9c320-237">Destination IP address</span></span></th>
<th><span data-ttu-id="9c320-238">Notes</span><span class="sxs-lookup"><span data-stu-id="9c320-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c320-239">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-240">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="9c320-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9c320-241">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-241">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-242">Per connettività per messaggistica istantanea pubblica e federata tramite SIP</span><span class="sxs-lookup"><span data-stu-id="9c320-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9c320-243">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9c320-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c320-244">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="9c320-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c320-245">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="9c320-245">Source IP address</span></span></th>
<th><span data-ttu-id="9c320-246">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="9c320-246">Destination IP address</span></span></th>
<th><span data-ttu-id="9c320-247">Notes</span><span class="sxs-lookup"><span data-stu-id="9c320-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c320-248">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-249">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9c320-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9c320-250">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-251">Per connettività di messaggistica istantanea pubblica e federata con SIP
</span><span class="sxs-lookup"><span data-stu-id="9c320-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-252">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9c320-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9c320-253">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-254">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="9c320-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9c320-255">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="9c320-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-256">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9c320-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9c320-257">Client</span><span class="sxs-lookup"><span data-stu-id="9c320-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="9c320-258">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-259">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="9c320-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="9c320-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9c320-261">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-262">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9c320-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9c320-263">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="9c320-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9c320-265">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-266">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9c320-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9c320-267">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9c320-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9c320-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9c320-269">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9c320-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9c320-270">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9c320-271">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="9c320-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9c320-272">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="9c320-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c320-273">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="9c320-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c320-274">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9c320-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="9c320-275">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="9c320-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9c320-276">Commenti</span><span class="sxs-lookup"><span data-stu-id="9c320-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c320-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9c320-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9c320-278">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-278">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-279">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9c320-280">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9c320-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9c320-281">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="9c320-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c320-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9c320-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9c320-283">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9c320-284">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-284">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-285">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="9c320-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9c320-286">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="9c320-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c320-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9c320-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9c320-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="9c320-288">Any</span></span></p></td>
<td><p><span data-ttu-id="9c320-289">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="9c320-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="9c320-290">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="9c320-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

