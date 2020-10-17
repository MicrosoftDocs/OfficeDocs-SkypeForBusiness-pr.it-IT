---
title: Riepilogo delle porte-server perimetrale consolidato in scala con i dispositivi di bilanciamento del carico hardware
description: Port Summary-Edge consolidato in scala con i dispositivi di bilanciamento del carico hardware.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564592"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="02a6d-103">Riepilogo delle porte-perimetro consolidato con bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02a6d-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02a6d-104">_**Ultimo argomento modificato:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="02a6d-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="02a6d-105">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="02a6d-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="02a6d-106">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="02a6d-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="02a6d-107">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="02a6d-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="02a6d-108">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="02a6d-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="02a6d-109">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="02a6d-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="02a6d-110">**Server perimetrale consolidato in scala con bilanciamento del carico hardware**</span><span class="sxs-lookup"><span data-stu-id="02a6d-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="02a6d-111">![Porte e protocolli della rete perimetrale del server Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Porte e protocolli della rete perimetrale del server Edge")</span><span class="sxs-lookup"><span data-stu-id="02a6d-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="02a6d-112">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="02a6d-112">Port and Protocol Details</span></span>

<span data-ttu-id="02a6d-113">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="02a6d-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="02a6d-p103">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.</span><span class="sxs-lookup"><span data-stu-id="02a6d-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="02a6d-116">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: interfaccia esterna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="02a6d-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02a6d-117">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="02a6d-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="02a6d-118">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="02a6d-118">Source IP address</span></span></th>
<th><span data-ttu-id="02a6d-119">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="02a6d-119">Destination IP address</span></span></th>
<th><span data-ttu-id="02a6d-120">Note</span><span class="sxs-lookup"><span data-stu-id="02a6d-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-121">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="02a6d-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="02a6d-122">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-123">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-124">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="02a6d-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-125">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="02a6d-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="02a6d-126">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-127">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-127">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-128">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="02a6d-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-129">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="02a6d-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="02a6d-130">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-131">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-132">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="02a6d-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-133">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="02a6d-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="02a6d-134">Indirizzo IP del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-135">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-135">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-136">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02a6d-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-137">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="02a6d-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="02a6d-138">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-139">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-140">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="02a6d-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-141">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="02a6d-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="02a6d-142">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-142">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-143">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-144">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="02a6d-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-145">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="02a6d-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="02a6d-146">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-146">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-147">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-148">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="02a6d-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-149">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="02a6d-150">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-151">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-151">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-152">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="02a6d-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="02a6d-153">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="02a6d-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-154">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="02a6d-155">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-155">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-156">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-157">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-158">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-159">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-159">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-160">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-161">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-162">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-163">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-164">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-164">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-165">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="02a6d-166">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: nodo interno dell'interfaccia 1 e nodo 2</span><span class="sxs-lookup"><span data-stu-id="02a6d-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02a6d-167">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="02a6d-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="02a6d-168">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="02a6d-168">Source IP address</span></span></th>
<th><span data-ttu-id="02a6d-169">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="02a6d-169">Destination IP address</span></span></th>
<th><span data-ttu-id="02a6d-170">Note</span><span class="sxs-lookup"><span data-stu-id="02a6d-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="02a6d-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="02a6d-172">Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP virtuale del pool Front end che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="02a6d-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-173">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-174">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="02a6d-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="02a6d-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-176">Qualsiasi (può essere definito come l'IP o il pool del server front end server che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="02a6d-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-177">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-178">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="02a6d-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="02a6d-180">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="02a6d-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-181">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-182">Traffico delle conferenze Web dalla distribuzione interna all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="02a6d-184">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="02a6d-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-185">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-186">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="02a6d-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-188">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="02a6d-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-189">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-190">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="02a6d-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="02a6d-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="02a6d-192">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-192">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-193">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-194">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="02a6d-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="02a6d-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="02a6d-196">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-196">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-197">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-198">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="02a6d-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="02a6d-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="02a6d-200">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-200">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-201">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-202">Controller del servizio di registrazione centralizzato utilizzando Lync Server Management Shell e i cmdlet del servizio di registrazione centralizzato, i comandi della riga di comando di ClsController (ClsController.exe) o gli agenti (ClsAgent.exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="02a6d-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02a6d-203">I dispositivi di bilanciamento del carico hardware presentano requisiti specifici quando vengono distribuiti per garantire la disponibilità e il bilanciamento del carico per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02a6d-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="02a6d-204">I requisiti sono definiti nella figura e nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="02a6d-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="02a6d-205">I fornitori di terze parti possono utilizzare una terminologia diversa per i requisiti definiti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="02a6d-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="02a6d-206">Sarà necessario eseguire il mapping dei requisiti di Lync Server alle caratteristiche e alle opzioni di configurazione fornite dal fornitore del dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="02a6d-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="02a6d-207">Quando si configurano i dispositivi di bilanciamento del carico hardware, considerare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="02a6d-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="02a6d-208">SNAT (Source Network Address Translation) può essere configurato sul bilanciamento del carico hardware (HLB) per il servizio Access Edge e il servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="02a6d-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="02a6d-209">SNAT non può essere configurato nel servizio A/V Edge – il servizio A/V Edge deve rispondere con l'indirizzo del server reale, non con l'IP virtuale di HLB (VIP), per l'attraversamento semplice di UDP su NAT (STUN)/Traversal utilizzando Relay NAT (turno)/Federation turno (FTURN) per funzionare correttamente</span><span class="sxs-lookup"><span data-stu-id="02a6d-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="02a6d-210">Se il client invia una richiesta a HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="02a6d-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="02a6d-211">Se il client invia una richiesta al server perimetrale, è necessario che la risposta venga restituita dall'IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="02a6d-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="02a6d-212">Gli indirizzi IP pubblici vengono utilizzati su ogni interfaccia del server e sui VIP di HLB e i requisiti dell'indirizzo IP pubblico sono N + 1, dove esiste un indirizzo IP pubblico per ogni interfaccia del server reale e uno per ogni VIP di HLB.</span><span class="sxs-lookup"><span data-stu-id="02a6d-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="02a6d-213">Se si dispone di 2 server perimetrali nel pool, vengono ottenuti 9 indirizzi IP pubblici, in cui vengono utilizzati 3 per i VIP di HLB e uno per ogni interfaccia server perimetrale (un totale di sei per i server)</span><span class="sxs-lookup"><span data-stu-id="02a6d-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="02a6d-214">Per il servizio Access Edge e il servizio Web Conferencing Edge (e l'utilizzo di NAT su HLB) il client contatta il VIP, il VIP cambia l'indirizzo IP di origine dal client al proprio indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="02a6d-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="02a6d-215">L'interfaccia del server indirizza l'indirizzo del mittente al VIP, il VIP cambia l'indirizzo di origine dall'indirizzo IP dell'interfaccia del server e invia il pacchetto al client</span><span class="sxs-lookup"><span data-stu-id="02a6d-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="02a6d-216">Per il servizio A/V Edge, il VIP non deve modificare l'indirizzo IP di origine e l'indirizzo del server reale viene restituito direttamente al client: non è possibile configurare NAT su HLB per il traffico AV</span><span class="sxs-lookup"><span data-stu-id="02a6d-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="02a6d-217">Se il client invia una richiesta al VIP di HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="02a6d-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="02a6d-218">Se il client invia una richiesta all'IP del server perimetrale, la risposta deve tornare dall'IP del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="02a6d-219">Per AV, il firewall esterno manterrà l'indirizzo IP pubblico del server reale per tutti i pacchetti</span><span class="sxs-lookup"><span data-stu-id="02a6d-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="02a6d-220">Una volta stabilito, il client per la comunicazione del servizio a/V Edge è al server reale, non a HLB</span><span class="sxs-lookup"><span data-stu-id="02a6d-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="02a6d-221">Perimetro interno ai server e ai client interni devono essere instradati e le route permanenti sono impostate per tutte le reti interne che ospitano server o client</span><span class="sxs-lookup"><span data-stu-id="02a6d-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="02a6d-222">Il VIP del servizio Access Edge di HLB agirà come il gateway predefinito per ogni interfaccia server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="02a6d-223">Per ulteriori informazioni sulla pianificazione e la funzionalità NAT, fare riferimento ai <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisiti hardware per il bilanciamento del carico per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02a6d-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="02a6d-224">![Dettagli relativi a porte e protocolli del server perimetrale](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Dettagli relativi a porte e protocolli del server perimetrale")</span><span class="sxs-lookup"><span data-stu-id="02a6d-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="02a6d-225">Impostazioni delle porte esterne necessarie per il server perimetrale consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali dell'interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="02a6d-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02a6d-226">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="02a6d-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="02a6d-227">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="02a6d-227">Source IP address</span></span></th>
<th><span data-ttu-id="02a6d-228">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="02a6d-228">Destination IP address</span></span></th>
<th><span data-ttu-id="02a6d-229">Note</span><span class="sxs-lookup"><span data-stu-id="02a6d-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="02a6d-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="02a6d-231">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-231">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-232">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="02a6d-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-233">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="02a6d-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="02a6d-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="02a6d-235">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="02a6d-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-236">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-236">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-237">Il servizio proxy XMPP invia traffico ai contatti XMPP nelle federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="02a6d-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-238">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-239">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-239">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-240">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="02a6d-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-241">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="02a6d-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-242">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="02a6d-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="02a6d-243">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-243">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-244">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="02a6d-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-245">SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="02a6d-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-246">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="02a6d-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="02a6d-247">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="02a6d-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-248">Partner federato</span><span class="sxs-lookup"><span data-stu-id="02a6d-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="02a6d-249">SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="02a6d-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-250">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="02a6d-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-251">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-251">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-252">Indirizzo VIP pubblico del servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-253">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="02a6d-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-254">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="02a6d-255">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-255">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-256">Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-257">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-258">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-259">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-259">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-260">Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="02a6d-261">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="02a6d-262">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: IP virtuale dell'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="02a6d-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02a6d-263">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="02a6d-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="02a6d-264">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="02a6d-264">Source IP address</span></span></th>
<th><span data-ttu-id="02a6d-265">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="02a6d-265">Destination IP address</span></span></th>
<th><span data-ttu-id="02a6d-266">Note</span><span class="sxs-lookup"><span data-stu-id="02a6d-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-267">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="02a6d-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="02a6d-268">Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</span><span class="sxs-lookup"><span data-stu-id="02a6d-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-269">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-270">Traffico SIP in uscita (da amministratore, indirizzo IP virtuale del pool di Director, Front End Server o indirizzo IP virtuale del pool Front End) a VIP Edge interno</span><span class="sxs-lookup"><span data-stu-id="02a6d-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-271">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="02a6d-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="02a6d-272">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-273">Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</span><span class="sxs-lookup"><span data-stu-id="02a6d-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-274">Traffico SIP in ingresso (per il server Director, l'indirizzo IP virtuale del pool di Director, l'indirizzo IP virtuale front-end o il pool Front End) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="02a6d-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="02a6d-276">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="02a6d-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="02a6d-277">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-278">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="02a6d-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="02a6d-280">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-280">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-281">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-282">Percorso preferito per trasferimenti multimediali A/V tra utenti interni ed esterni</span><span class="sxs-lookup"><span data-stu-id="02a6d-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02a6d-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-284">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-284">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-285">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-286">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="02a6d-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02a6d-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="02a6d-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="02a6d-288">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="02a6d-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="02a6d-289">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="02a6d-289">Any</span></span></p></td>
<td><p><span data-ttu-id="02a6d-290">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="02a6d-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

