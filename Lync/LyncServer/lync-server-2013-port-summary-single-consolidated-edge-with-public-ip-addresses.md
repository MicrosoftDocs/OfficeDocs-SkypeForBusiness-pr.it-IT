---
title: Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici
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
ms.openlocfilehash: f94ac852959ca440f09f8878a17c1e23f7698bd4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="e4a4e-102">Riepilogo delle porte-singolo server perimetrale consolidato con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4a4e-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4a4e-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e4a4e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e4a4e-104">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e4a4e-105">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="e4a4e-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e4a4e-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e4a4e-107">Le informazioni sulla pianificazione per il proxy inverso e la Federazione sono disponibili in [scenari per il proxy inverso in Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [la pianificazione per SIP, la Federazione XMPP e la messaggistica istantanea pubblica nelle sezioni di Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="e4a4e-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e4a4e-109">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e4a4e-110">**Rete perimetrale aziendale per un singolo perimetro consolidato con indirizzamento IP pubblico**</span><span class="sxs-lookup"><span data-stu-id="e4a4e-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="e4a4e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="e4a4e-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e4a4e-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="e4a4e-112">Port and Protocol Details</span></span>

<span data-ttu-id="e4a4e-113">È consigliabile aprire le porte necessarie per il supporto della funzionalità per la quale si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e4a4e-p103">Affinché l'accesso remoto funzioni con qualsiasi servizio perimetrale, è necessario consentire il flusso bidirezionale del traffico SIP, come mostrato nella figura relativa al traffico perimetrale in ingresso/in uscita. In altre parole, le funzionalità di messaggistica istantanea (IM), informazioni sulla presenza, Web Conferencing, audio/video (A/V) e federazione comportano l'uso della messaggistica SIP verso e dal servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="e4a4e-116">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP pubblici: interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="e4a4e-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4a4e-117">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e4a4e-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4a4e-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="e4a4e-118">Source IP address</span></span></th>
<th><span data-ttu-id="e4a4e-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="e4a4e-119">Destination IP address</span></span></th>
<th><span data-ttu-id="e4a4e-120">Notes</span><span class="sxs-lookup"><span data-stu-id="e4a4e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e4a4e-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-122">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-123">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-124">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="e4a4e-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e4a4e-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-126">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-128">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="e4a4e-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-129">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e4a4e-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-130">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-132">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-133">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e4a4e-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-134">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-135">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-136">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-137">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-138">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-139">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-140">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="e4a4e-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-141">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-142">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-143">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-144">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-145">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-146">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-147">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-148">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-149">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-150">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-151">Indirizzo IP pubblico del servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-152">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="e4a4e-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e4a4e-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-154">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-155">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-156">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e4a4e-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-158">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-160">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e4a4e-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e4a4e-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-162">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-162">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-163">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-164">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e4a4e-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-166">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-166">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-167">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-168">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-170">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-171">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-171">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-172">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e4a4e-173">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-175">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-175">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-176">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-177">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-179">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-179">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-180">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-181">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-183">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-184">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-184">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-185">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="e4a4e-186">Riepilogo del firewall per un singolo server perimetrale consolidato con indirizzi IP pubblici: interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="e4a4e-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4a4e-187">Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e4a4e-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4a4e-188">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="e4a4e-188">Source IP address</span></span></th>
<th><span data-ttu-id="e4a4e-189">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="e4a4e-189">Destination IP address</span></span></th>
<th><span data-ttu-id="e4a4e-190">Commenti</span><span class="sxs-lookup"><span data-stu-id="e4a4e-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e4a4e-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-192">Qualsiasi (può essere definito come IP Server Standard Edition, indirizzo IP del server Standard Edition o indirizzo IP del pool che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-194">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="e4a4e-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-196">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo IP del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-197">IP del server perimetrale o pool che contiene l'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="e4a4e-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-198">Traffico SIP in uscita (da Director, indirizzo IP del pool Director, Front End Server o indirizzo IP del pool Front End) all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-201">Qualsiasi (può essere definito come amministratore, indirizzo IP del pool di server Director, indirizzo del pool Front end o front end)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-202">Traffico SIP in ingresso (per il server Director, l'indirizzo IP del pool di Director, l'indirizzo IP del pool Front end o il front end) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e4a4e-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-204">Qualsiasi (può essere definito come indirizzo IP front end server o ogni indirizzo IP di front end server in un pool Front End)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-205">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-206">Traffico Web Conferencing da front end server o ogni Front End Server se in un pool, per l'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e4a4e-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-208">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-209">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-210">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-212">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-212">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-213">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-214">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e4a4e-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-216">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-216">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-217">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-218">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="e4a4e-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-220">Qualsiasi (può essere definito come l'indirizzo IP del server front end o il pool che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-221">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-222">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e4a4e-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-224">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-224">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-225">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-226">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="e4a4e-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e4a4e-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-228">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-228">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-229">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-230">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="e4a4e-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e4a4e-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-232">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-232">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-233">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-234">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="e4a4e-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="e4a4e-235">Riepilogo firewall per la federazione</span><span class="sxs-lookup"><span data-stu-id="e4a4e-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4a4e-236">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="e4a4e-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4a4e-237">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="e4a4e-237">Source IP address</span></span></th>
<th><span data-ttu-id="e4a4e-238">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="e4a4e-238">Destination IP address</span></span></th>
<th><span data-ttu-id="e4a4e-239">Notes</span><span class="sxs-lookup"><span data-stu-id="e4a4e-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-240">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-241">Indirizzo IP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="e4a4e-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-242">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-243">Per connettività per messaggistica istantanea pubblica e federata tramite SIP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e4a4e-244">Riepilogo firewall - connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="e4a4e-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4a4e-245">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e4a4e-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4a4e-246">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="e4a4e-246">Source IP address</span></span></th>
<th><span data-ttu-id="e4a4e-247">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="e4a4e-247">Destination IP address</span></span></th>
<th><span data-ttu-id="e4a4e-248">Notes</span><span class="sxs-lookup"><span data-stu-id="e4a4e-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-249">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-250">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="e4a4e-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-251">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-252">Per connettività di messaggistica istantanea pubblica e federata con SIP
</span><span class="sxs-lookup"><span data-stu-id="e4a4e-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-253">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e4a4e-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-254">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-255">Partner per la connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="e4a4e-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-256">Per connettività di messaggistica istantanea pubblica e federata con SIP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-257">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e4a4e-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-258">Client</span><span class="sxs-lookup"><span data-stu-id="e4a4e-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-259">Servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-260">Traffico SIP client-server per l'accesso utente esterno</span><span class="sxs-lookup"><span data-stu-id="e4a4e-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e4a4e-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-262">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-263">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4a4e-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-264">Utilizzato per le sessioni A/V con Windows Live Messenger se è configurata la connettività per messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-266">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-267">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4a4e-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-268">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4a4e-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e4a4e-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-270">Client Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4a4e-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-271">Servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-272">Obbligatorio per la connettività per messaggistica istantanea pubblica con Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e4a4e-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e4a4e-273">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4a4e-274">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="e4a4e-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e4a4e-275">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="e4a4e-276">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="e4a4e-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e4a4e-277">Commenti</span><span class="sxs-lookup"><span data-stu-id="e4a4e-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e4a4e-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-279">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-280">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-281">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e4a4e-282">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="e4a4e-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4a4e-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e4a4e-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-284">Indirizzo IP dell'interfaccia del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-285">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-285">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-286">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e4a4e-287">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="e4a4e-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4a4e-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e4a4e-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="e4a4e-289">Any</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-290">Ogni IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="e4a4e-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e4a4e-291">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end all'indirizzo IP interno del server perimetrale o all'indirizzo IP interno di ogni membro del pool perimetrale</span><span class="sxs-lookup"><span data-stu-id="e4a4e-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

