---
title: Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="dbca0-102">Riepilogo delle porte - topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbca0-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbca0-103">_**Argomento Ultima modifica:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="dbca0-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="dbca0-104">Le funzionalità di Lync Server 2013 e Edge Server descritte in questa architettura di scenario sono molto simili a quelle implementate in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dbca0-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="dbca0-105">L'aggiunta più evidente è la porta **5269 sulla voce TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="dbca0-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="dbca0-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nell'Edge Server o nel pool Edge e nel server gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="dbca0-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="dbca0-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="dbca0-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="dbca0-108">Per chiarezza, solo IPv4 viene usato negli scenari.</span><span class="sxs-lookup"><span data-stu-id="dbca0-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="dbca0-109">**Edge consolidato in scala con il bilanciamento del carico hardware**</span><span class="sxs-lookup"><span data-stu-id="dbca0-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="dbca0-110">Porte(images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "e protocolli di") rete perimetrale ![Edge server perimetrali e protocolli]</span><span class="sxs-lookup"><span data-stu-id="dbca0-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="dbca0-111">Dettagli sulla porta e sul protocollo</span><span class="sxs-lookup"><span data-stu-id="dbca0-111">Port and Protocol Details</span></span>

<span data-ttu-id="dbca0-112">È consigliabile aprire solo le porte necessarie per supportare la funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="dbca0-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="dbca0-113">Per l'accesso remoto al lavoro per qualsiasi servizio Edge, è obbligatorio che il traffico SIP sia consentito per il flusso bidirezionale, come illustrato nella figura del traffico Edge in ingresso/in uscita.</span><span class="sxs-lookup"><span data-stu-id="dbca0-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="dbca0-114">In un altro modo, la messaggistica SIP da e verso il servizio Access Edge è coinvolta in messaggistica istantanea (IM), presenza, Web Conferencing, audio/video (A/V) e Federazione.</span><span class="sxs-lookup"><span data-stu-id="dbca0-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="dbca0-115">Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: interfaccia esterna-nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="dbca0-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbca0-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="dbca0-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbca0-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="dbca0-117">Source IP address</span></span></th>
<th><span data-ttu-id="dbca0-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="dbca0-118">Destination IP address</span></span></th>
<th><span data-ttu-id="dbca0-119">Note</span><span class="sxs-lookup"><span data-stu-id="dbca0-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="dbca0-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="dbca0-121">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-122">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-123">Controllo e recupero di certificati revocati/CRL</span><span class="sxs-lookup"><span data-stu-id="dbca0-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="dbca0-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="dbca0-125">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-126">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-127">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="dbca0-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="dbca0-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="dbca0-129">Indirizzo IP pubblico del servizio Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-130">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-131">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="dbca0-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbca0-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbca0-133">Indirizzo IP del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-134">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-135">Obbligatorio per la Federazione con partner che gestiscono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbca0-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbca0-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbca0-137">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-138">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-139">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="dbca0-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbca0-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbca0-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-141">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-142">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-143">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="dbca0-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="dbca0-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="dbca0-145">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-145">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-146">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-147">Obbligatorio solo per la Federazione con partner che gestiscono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="dbca0-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbca0-149">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-150">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-151">3478 in uscita viene usato per determinare la versione di Edge Server in cui Lync Server sta comunicando e anche per il traffico multimediale da Edge Server-to-Edge Server.</span><span class="sxs-lookup"><span data-stu-id="dbca0-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="dbca0-152">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2 e anche se sono distribuiti più pool di Edge all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="dbca0-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbca0-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-154">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-155">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-156">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-158">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-159">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-160">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-162">Indirizzo IP pubblico del servizio Edge A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-163">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-164">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="dbca0-165">Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: nodo di interfaccia interno 1 e nodo 2</span><span class="sxs-lookup"><span data-stu-id="dbca0-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbca0-166">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="dbca0-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbca0-167">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="dbca0-167">Source IP address</span></span></th>
<th><span data-ttu-id="dbca0-168">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="dbca0-168">Destination IP address</span></span></th>
<th><span data-ttu-id="dbca0-169">Note</span><span class="sxs-lookup"><span data-stu-id="dbca0-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="dbca0-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="dbca0-171">Any (può essere definito come indirizzo del server front-end o indirizzo IP virtuale del pool Front-end che gestisce il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="dbca0-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-172">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-173">Traffico XMPP in uscita dal servizio gateway XMPP in uso sul server front-end o sul pool Front-End</span><span class="sxs-lookup"><span data-stu-id="dbca0-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="dbca0-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-175">Any (può essere definito come front end Server IP o pool che contiene l'Central Management store)</span><span class="sxs-lookup"><span data-stu-id="dbca0-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-176">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-177">Replica delle modifiche da Central Management store a Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="dbca0-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="dbca0-179">Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</span><span class="sxs-lookup"><span data-stu-id="dbca0-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-180">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-181">Traffico di Web Conferencing dalla distribuzione interna all'interfaccia Internal Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbca0-183">Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</span><span class="sxs-lookup"><span data-stu-id="dbca0-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-184">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-185">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-187">Any (può essere definito come IP Director, IP del server front end o IP virtuale del pool)</span><span class="sxs-lookup"><span data-stu-id="dbca0-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-188">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-189">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, TCP viene usato per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="dbca0-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="dbca0-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="dbca0-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-191">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-192">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-193">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="dbca0-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="dbca0-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="dbca0-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-195">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-196">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-197">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="dbca0-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="dbca0-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="dbca0-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-199">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-201">Controller di servizio di registrazione centralizzato con Lync Server Management Shell e cmdlet del servizio di registrazione centralizzato, comandi della riga di comando di ClsController (ClsController. exe) o Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="dbca0-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dbca0-202">I dispositivi di bilanciamento del carico hardware hanno requisiti specifici quando vengono distribuiti per consentire il bilanciamento del carico e della disponibilità per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dbca0-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="dbca0-203">I requisiti sono definiti nella figura e nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbca0-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="dbca0-204">I fornitori di terze parti possono usare terminologia diversa per i requisiti definiti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="dbca0-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="dbca0-205">Sarà necessario eseguire il mapping dei requisiti di Lync Server alle funzionalità e alle opzioni di configurazione fornite dal fornitore del dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="dbca0-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="dbca0-206">Quando si configurano i criteri di bilanciamento del carico hardware, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="dbca0-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="dbca0-207">La conversione di SNAT (Source Network Address Translation) può essere configurata nel servizio di bilanciamento del carico hardware (HLB) per Access Edge service e Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="dbca0-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="dbca0-208">SNAT non può essere configurato nell'A/V Edge service: l'A/V Edge service deve rispondere con l'indirizzo del server reale, non con l'IP virtuale di HLB (VIP), per l'attraversamento semplice di UDP su NAT (STUN)/Traversal l'uso di Relay NAT (TURN)/Federation TURN (FTURN) per funzionare correttamente</span><span class="sxs-lookup"><span data-stu-id="dbca0-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="dbca0-209">Se il cliente invia una richiesta a HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="dbca0-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="dbca0-210">Se il client invia una richiesta al bordo, la risposta deve tornare dall'IP del bordo</span><span class="sxs-lookup"><span data-stu-id="dbca0-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="dbca0-211">Gli indirizzi IP pubblici vengono usati per ogni interfaccia server e per i VIP di HLB e i requisiti per l'indirizzo IP pubblico sono N + 1, dove esiste un indirizzo IP pubblico per ogni interfaccia del server reale e uno per ogni VIP di HLB.</span><span class="sxs-lookup"><span data-stu-id="dbca0-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="dbca0-212">In cui sono presenti 2 server perimetrali nel pool, vengono visualizzati 9 indirizzi IP pubblici, in cui vengono usati 3 per i VIP di HLB e uno per ogni interfaccia Edge Server (un totale di sei per i server)</span><span class="sxs-lookup"><span data-stu-id="dbca0-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="dbca0-213">Per il servizio Access Edge e Web Conferencing Edge (e l'uso di NAT su HLB) il cliente contatta il VIP, il VIP cambia l'indirizzo IP di origine dal client al proprio indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="dbca0-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="dbca0-214">L'interfaccia del server indirizza l'indirizzo del mittente al VIP, il VIP cambia l'indirizzo di origine dall'indirizzo IP dell'interfaccia server e invia il pacchetto al client</span><span class="sxs-lookup"><span data-stu-id="dbca0-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="dbca0-215">Per il servizio A/V Edge, il VIP non deve cambiare l'indirizzo IP di origine e l'indirizzo del server reale viene restituito direttamente al client: non è possibile configurare il NAT in HLB per il traffico AV</span><span class="sxs-lookup"><span data-stu-id="dbca0-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="dbca0-216">Se il cliente invia una richiesta al VIP di HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="dbca0-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="dbca0-217">Se il client invia una richiesta all'IP del bordo, la risposta deve tornare dall'IP del bordo</span><span class="sxs-lookup"><span data-stu-id="dbca0-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="dbca0-218">Per AV, il firewall esterno manterrà l'indirizzo IP pubblico del server reale per tutti i pacchetti</span><span class="sxs-lookup"><span data-stu-id="dbca0-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="dbca0-219">Una volta stabilito, il client per comunicare con un servizio Edge a/V è il server reale, non il HLB</span><span class="sxs-lookup"><span data-stu-id="dbca0-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="dbca0-220">Il bordo interno ai server e ai client interni deve essere instradato e le route permanenti sono impostate per tutte le reti interne che ospitano server o client.</span><span class="sxs-lookup"><span data-stu-id="dbca0-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="dbca0-221">Il servizio VIP Access Edge di HLB fungerà da gateway predefinito per ogni interfaccia Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="dbca0-222">Per altre informazioni sulla pianificazione e la funzionalità NAT, vedere <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisiti di bilanciamento del carico hardware per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dbca0-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="dbca0-223">Dettagli sulle porte e i protocolli del server ![perimetrale]porte e(images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "protocolli")</span><span class="sxs-lookup"><span data-stu-id="dbca0-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="dbca0-224">Impostazioni della porta esterna necessarie per il bordo consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali di interfacce esterne</span><span class="sxs-lookup"><span data-stu-id="dbca0-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbca0-225">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="dbca0-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbca0-226">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="dbca0-226">Source IP address</span></span></th>
<th><span data-ttu-id="dbca0-227">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="dbca0-227">Destination IP address</span></span></th>
<th><span data-ttu-id="dbca0-228">Note</span><span class="sxs-lookup"><span data-stu-id="dbca0-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dbca0-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dbca0-230">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-230">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-231">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="dbca0-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-232">Il servizio proxy XMPP accetta il traffico da contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="dbca0-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="dbca0-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="dbca0-234">Servizio proxy XMPP (condivide l'indirizzo IP con Access Edge service)</span><span class="sxs-lookup"><span data-stu-id="dbca0-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-235">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-235">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-236">Il servizio proxy XMPP invia il traffico ai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="dbca0-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-237">Access/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-238">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-238">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-239">Indirizzo VIP pubblico del servizio Edge Access</span><span class="sxs-lookup"><span data-stu-id="dbca0-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-240">Traffico SIP da client a server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="dbca0-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-241">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbca0-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbca0-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-242">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-243">Indirizzo VIP pubblico del servizio Edge Access</span><span class="sxs-lookup"><span data-stu-id="dbca0-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-244">Segnalazione SIP, federati e connettività di messaggistica istantanea pubblica tramite SIP</span><span class="sxs-lookup"><span data-stu-id="dbca0-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-245">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbca0-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbca0-246">Indirizzo VIP pubblico del servizio Edge Access</span><span class="sxs-lookup"><span data-stu-id="dbca0-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-247">Partner federato</span><span class="sxs-lookup"><span data-stu-id="dbca0-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="dbca0-248">Segnalazione SIP, federati e connettività di messaggistica istantanea pubblica tramite SIP</span><span class="sxs-lookup"><span data-stu-id="dbca0-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-249">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-250">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-250">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-251">Indirizzo VIP pubblico di Edge Server Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="dbca0-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-252">Supporto per Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="dbca0-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbca0-254">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-254">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-255">Indirizzo VIP pubblico del servizio Edge A/V Edge</span><span class="sxs-lookup"><span data-stu-id="dbca0-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-256">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-258">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-258">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-259">Indirizzo VIP pubblico del servizio Edge A/V Edge</span><span class="sxs-lookup"><span data-stu-id="dbca0-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="dbca0-260">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="dbca0-261">Riepilogo del firewall per il bordo consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali di interfacce interne</span><span class="sxs-lookup"><span data-stu-id="dbca0-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbca0-262">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="dbca0-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="dbca0-263">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="dbca0-263">Source IP address</span></span></th>
<th><span data-ttu-id="dbca0-264">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="dbca0-264">Destination IP address</span></span></th>
<th><span data-ttu-id="dbca0-265">Note</span><span class="sxs-lookup"><span data-stu-id="dbca0-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-266">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbca0-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbca0-267">Any (può essere definito come amministratore, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del front end server o del pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="dbca0-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-268">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-269">Traffico SIP in uscita (da Director, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del server front-end o del pool Front-End) a VIP Edge interno</span><span class="sxs-lookup"><span data-stu-id="dbca0-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-270">Access/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="dbca0-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="dbca0-271">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-272">Any (può essere definito come amministratore, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del front end server o del pool Front-End)</span><span class="sxs-lookup"><span data-stu-id="dbca0-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-273">Traffico SIP in ingresso (a Director, indirizzo IP virtuale del pool di Director, indirizzo IP virtuale del server front-end o del pool Front-End) dall'interfaccia interna di Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="dbca0-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="dbca0-275">Any (può essere definito come indirizzo IP del server front-end o indirizzo IP del pool Front-end o un Survivable Branch Appliance o Survivable Branch Server con questo Edge Server)</span><span class="sxs-lookup"><span data-stu-id="dbca0-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="dbca0-276">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-277">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP del server front-end o del pool Front-end o da qualsiasi Appliance Survivable Branch o Survivable Branch Server con questo Edge Server</span><span class="sxs-lookup"><span data-stu-id="dbca0-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="dbca0-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="dbca0-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-279">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-280">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-281">Percorso preferito per il trasferimento multimediale A/V tra utenti interni ed esterni</span><span class="sxs-lookup"><span data-stu-id="dbca0-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbca0-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-283">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-283">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-284">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-285">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se non è possibile stabilire la comunicazione UDP, viene usato TCP per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="dbca0-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbca0-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="dbca0-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="dbca0-287">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="dbca0-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="dbca0-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dbca0-288">Any</span></span></p></td>
<td><p><span data-ttu-id="dbca0-289">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni se non è possibile stabilire la comunicazione UDP, viene usato TCP per il trasferimento di file e la condivisione desktop</span><span class="sxs-lookup"><span data-stu-id="dbca0-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

