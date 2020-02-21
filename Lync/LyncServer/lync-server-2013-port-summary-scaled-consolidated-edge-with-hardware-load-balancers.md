---
title: Riepilogo delle porte-server perimetrale consolidato in scala con i dispositivi di bilanciamento del carico hardware
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
ms.openlocfilehash: e6af913a6be7b92a7a640a2e06537197ba21351c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="ba9db-102">Riepilogo delle porte-perimetro consolidato con bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba9db-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba9db-103">_**Ultimo argomento modificato:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="ba9db-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="ba9db-104">La funzionalità Lync Server 2013, Edge Server descritta in questa architettura dello scenario è molto simile a quella che è stata implementata in Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ba9db-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ba9db-105">L'aggiunta più evidente è la voce della porta **5269 su TCP** per il protocollo XMPP (Extensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="ba9db-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ba9db-106">Lync Server 2013 consente di distribuire facoltativamente un proxy XMPP nel server perimetrale o nel pool perimetrale e nel server gateway XMPP nel server front-end o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="ba9db-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="ba9db-107">Oltre a IPv4, il server perimetrale supporta ora IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba9db-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ba9db-108">Per maggiore chiarezza, solo IPv4 viene utilizzato in questi scenari.</span><span class="sxs-lookup"><span data-stu-id="ba9db-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ba9db-109">**Server perimetrale consolidato in scala con bilanciamento del carico hardware**</span><span class="sxs-lookup"><span data-stu-id="ba9db-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="ba9db-110">![Porte e protocolli della rete perimetrale del server Edge](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Porte e protocolli della rete perimetrale del server Edge")</span><span class="sxs-lookup"><span data-stu-id="ba9db-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ba9db-111">Informazioni dettagliate sulle porte e sui protocolli</span><span class="sxs-lookup"><span data-stu-id="ba9db-111">Port and Protocol Details</span></span>

<span data-ttu-id="ba9db-112">È consigliabile aprire solo le porte necessarie per supportare le funzionalità per cui si fornisce l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ba9db-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ba9db-p103">Per il corretto funzionamento dell'accesso remoto per qualsiasi servizio perimetrale, è obbligatorio che sia consentito il flusso bidirezionale del traffico SIP, come illustrato nella figura Traffico perimetrale in ingresso/in uscita. In altre parole, la messaggistica SIP da e al servizio Access Edge è coinvolta nella messaggistica istantanea, nella presenza, nelle conferenze Web, nell'audio/video (A/V) e nella federazione.</span><span class="sxs-lookup"><span data-stu-id="ba9db-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="ba9db-115">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: interfaccia esterna – nodo 1 e nodo 2 (esempio)</span><span class="sxs-lookup"><span data-stu-id="ba9db-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba9db-116">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba9db-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba9db-117">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba9db-117">Source IP address</span></span></th>
<th><span data-ttu-id="ba9db-118">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba9db-118">Destination IP address</span></span></th>
<th><span data-ttu-id="ba9db-119">Notes</span><span class="sxs-lookup"><span data-stu-id="ba9db-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ba9db-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ba9db-121">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-122">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-123">Revoca di certificati/controllo CRL e recupero</span><span class="sxs-lookup"><span data-stu-id="ba9db-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-124">Accesso/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ba9db-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ba9db-125">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-126">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-127">Query DNS su TCP</span><span class="sxs-lookup"><span data-stu-id="ba9db-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-128">Accesso/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ba9db-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ba9db-129">Indirizzo IP pubblico del servizio Access Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-130">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-130">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-131">Query DNS su UDP</span><span class="sxs-lookup"><span data-stu-id="ba9db-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba9db-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba9db-133">Indirizzo IP del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-134">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-135">Necessario per la Federazione con partner che eseguono Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba9db-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba9db-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba9db-137">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-138">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-139">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ba9db-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba9db-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba9db-141">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-142">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-143">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba9db-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba9db-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba9db-145">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-145">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-146">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-147">Obbligatorio solo per la Federazione con partner che eseguono Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba9db-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba9db-149">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-150">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-150">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-151">3478 in uscita viene utilizzato per determinare la versione del server perimetrale in cui è in comunicazione Lync Server e anche per il traffico multimediale proveniente dal server Edge Server-Edge.</span><span class="sxs-lookup"><span data-stu-id="ba9db-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ba9db-152">Obbligatorio per la Federazione con Lync Server 2010, Windows Live Messenger e Office Communications Server 2007 R2, nonché se più pool di server perimetrali sono distribuiti all'interno di una società.</span><span class="sxs-lookup"><span data-stu-id="ba9db-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba9db-154">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-155">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-156">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-158">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-159">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-160">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-162">Indirizzo IP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-163">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-164">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="ba9db-165">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: nodo interno dell'interfaccia 1 e nodo 2</span><span class="sxs-lookup"><span data-stu-id="ba9db-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba9db-166">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba9db-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba9db-167">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba9db-167">Source IP address</span></span></th>
<th><span data-ttu-id="ba9db-168">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba9db-168">Destination IP address</span></span></th>
<th><span data-ttu-id="ba9db-169">Notes</span><span class="sxs-lookup"><span data-stu-id="ba9db-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ba9db-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ba9db-171">Qualsiasi (può essere definito come indirizzo front end server o indirizzo IP virtuale del pool Front end che esegue il servizio gateway XMPP)</span><span class="sxs-lookup"><span data-stu-id="ba9db-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-172">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-173">Traffico XMPP in uscita dal servizio gateway XMPP in esecuzione nel front end server o nel pool Front End</span><span class="sxs-lookup"><span data-stu-id="ba9db-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ba9db-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-175">Qualsiasi (può essere definito come l'IP o il pool del server front end server che contiene l'archivio di gestione centrale)</span><span class="sxs-lookup"><span data-stu-id="ba9db-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-176">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-177">Replica delle modifiche dall'archivio di gestione centrale al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ba9db-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ba9db-179">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="ba9db-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-180">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-181">Traffico delle conferenze Web dalla distribuzione interna all'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba9db-183">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="ba9db-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-184">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-185">Percorso preferito per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="ba9db-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-187">Qualsiasi (può essere definito come IP del server Director, IP virtuale o Pool IP del front end)</span><span class="sxs-lookup"><span data-stu-id="ba9db-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-188">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-189">Percorso di fallback per il trasferimento multimediale A/V tra gli utenti interni ed esterni, Survivable Branch Appliance o Survivable Branch Server se non è possibile stabilire la comunicazione UDP, viene utilizzato TCP per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="ba9db-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ba9db-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ba9db-191">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-191">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-192">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-193">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ba9db-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ba9db-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ba9db-195">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-195">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-196">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-197">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ba9db-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ba9db-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ba9db-199">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-199">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-200">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-201">Controller del servizio di registrazione centralizzato utilizzando i cmdlet di Lync Server Management Shell e del servizio di registrazione centralizzata, i comandi della riga di comando di ClsController (ClsController. exe) o dell'agente (ClsAgent. exe) e la raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ba9db-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba9db-202">I dispositivi di bilanciamento del carico hardware presentano requisiti specifici quando vengono distribuiti per garantire la disponibilità e il bilanciamento del carico per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba9db-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="ba9db-203">I requisiti sono definiti nella figura e nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba9db-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="ba9db-204">I fornitori di terze parti possono utilizzare una terminologia diversa per i requisiti definiti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ba9db-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="ba9db-205">Sarà necessario eseguire il mapping dei requisiti di Lync Server alle caratteristiche e alle opzioni di configurazione fornite dal fornitore del dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="ba9db-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="ba9db-206">Quando si configurano i dispositivi di bilanciamento del carico hardware, considerare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba9db-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="ba9db-207">SNAT (Source Network Address Translation) può essere configurato sul bilanciamento del carico hardware (HLB) per il servizio Access Edge e il servizio Web Conferencing Edge</span><span class="sxs-lookup"><span data-stu-id="ba9db-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="ba9db-208">SNAT non può essere configurato nel servizio A/V Edge – il servizio A/V Edge deve rispondere con l'indirizzo del server reale, non con l'IP virtuale di HLB (VIP), per l'attraversamento semplice di UDP su NAT (STUN)/Traversal utilizzando Relay NAT (turno)/Federation turno (FTURN) per funzionare correttamente</span><span class="sxs-lookup"><span data-stu-id="ba9db-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="ba9db-209">Se il client invia una richiesta a HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="ba9db-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="ba9db-210">Se il client invia una richiesta al server perimetrale, è necessario che la risposta venga restituita dall'IP del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="ba9db-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="ba9db-211">Gli indirizzi IP pubblici vengono utilizzati su ogni interfaccia del server e sui VIP di HLB e i requisiti dell'indirizzo IP pubblico sono N + 1, dove esiste un indirizzo IP pubblico per ogni interfaccia del server reale e uno per ogni VIP di HLB.</span><span class="sxs-lookup"><span data-stu-id="ba9db-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="ba9db-212">Se si dispone di 2 server perimetrali nel pool, vengono ottenuti 9 indirizzi IP pubblici, in cui vengono utilizzati 3 per i VIP di HLB e uno per ogni interfaccia server perimetrale (un totale di sei per i server)</span><span class="sxs-lookup"><span data-stu-id="ba9db-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="ba9db-213">Per il servizio Access Edge e il servizio Web Conferencing Edge (e l'utilizzo di NAT su HLB) il client contatta il VIP, il VIP cambia l'indirizzo IP di origine dal client al proprio indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="ba9db-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="ba9db-214">L'interfaccia del server indirizza l'indirizzo del mittente al VIP, il VIP cambia l'indirizzo di origine dall'indirizzo IP dell'interfaccia del server e invia il pacchetto al client</span><span class="sxs-lookup"><span data-stu-id="ba9db-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="ba9db-215">Per il servizio A/V Edge, il VIP non deve modificare l'indirizzo IP di origine e l'indirizzo del server reale viene restituito direttamente al client: non è possibile configurare NAT su HLB per il traffico AV</span><span class="sxs-lookup"><span data-stu-id="ba9db-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="ba9db-216">Se il client invia una richiesta al VIP di HLB, la risposta deve tornare dal VIP di HLB</span><span class="sxs-lookup"><span data-stu-id="ba9db-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="ba9db-217">Se il client invia una richiesta all'IP del server perimetrale, la risposta deve tornare dall'IP del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="ba9db-218">Per AV, il firewall esterno manterrà l'indirizzo IP pubblico del server reale per tutti i pacchetti</span><span class="sxs-lookup"><span data-stu-id="ba9db-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="ba9db-219">Una volta stabilito, il client per la comunicazione del servizio a/V Edge è al server reale, non a HLB</span><span class="sxs-lookup"><span data-stu-id="ba9db-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="ba9db-220">Perimetro interno ai server e ai client interni devono essere instradati e le route permanenti sono impostate per tutte le reti interne che ospitano server o client</span><span class="sxs-lookup"><span data-stu-id="ba9db-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="ba9db-221">Il VIP del servizio Access Edge di HLB agirà come il gateway predefinito per ogni interfaccia server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ba9db-222">Per ulteriori informazioni sulla pianificazione e la funzionalità NAT, fare riferimento ai <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisiti hardware per il bilanciamento del carico per Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ba9db-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ba9db-223">![Dettagli relativi a porte e protocolli del server perimetrale](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Dettagli relativi a porte e protocolli del server perimetrale")</span><span class="sxs-lookup"><span data-stu-id="ba9db-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="ba9db-224">Impostazioni delle porte esterne necessarie per il server perimetrale consolidato in scala, bilanciamento del carico hardware: indirizzi IP virtuali dell'interfaccia esterna</span><span class="sxs-lookup"><span data-stu-id="ba9db-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba9db-225">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba9db-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba9db-226">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba9db-226">Source IP address</span></span></th>
<th><span data-ttu-id="ba9db-227">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba9db-227">Destination IP address</span></span></th>
<th><span data-ttu-id="ba9db-228">Notes</span><span class="sxs-lookup"><span data-stu-id="ba9db-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba9db-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba9db-230">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-230">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-231">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="ba9db-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-232">Il servizio proxy XMPP accetta il traffico dai contatti XMPP in federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="ba9db-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba9db-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba9db-234">Servizio proxy XMPP (condivide l'indirizzo IP con il servizio Access Edge)</span><span class="sxs-lookup"><span data-stu-id="ba9db-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-235">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-235">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-236">Il servizio proxy XMPP invia traffico ai contatti XMPP nelle federazioni XMPP definite</span><span class="sxs-lookup"><span data-stu-id="ba9db-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-237">Accesso/SIP (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-238">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-238">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-239">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="ba9db-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-240">Traffico SIP client-server per l'accesso degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="ba9db-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-241">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba9db-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba9db-242">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-242">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-243">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="ba9db-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-244">SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba9db-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-245">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba9db-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba9db-246">Indirizzo VIP pubblico del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="ba9db-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-247">Partner federato</span><span class="sxs-lookup"><span data-stu-id="ba9db-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="ba9db-248">SIP signaling, federato e la connettività di messaggistica istantanea pubblica con SIP</span><span class="sxs-lookup"><span data-stu-id="ba9db-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-249">/TCP/443 di Web Conferencing/PSOM (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba9db-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-250">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-250">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-251">Indirizzo VIP pubblico del servizio Web Conferencing Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-252">File multimediali Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="ba9db-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba9db-254">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-254">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-255">Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-256">Negoziazione STUN/TURN dei candidati su UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-258">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-258">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-259">Indirizzo VIP pubblico del servizio A/V Edge Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ba9db-260">Negoziazione STUN/TURN dei candidati su TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="ba9db-261">Riepilogo del firewall per il server perimetrale consolidato in scala, bilanciamento del carico hardware: IP virtuale dell'interfaccia interna</span><span class="sxs-lookup"><span data-stu-id="ba9db-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba9db-262">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba9db-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba9db-263">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ba9db-263">Source IP address</span></span></th>
<th><span data-ttu-id="ba9db-264">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ba9db-264">Destination IP address</span></span></th>
<th><span data-ttu-id="ba9db-265">Notes</span><span class="sxs-lookup"><span data-stu-id="ba9db-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-266">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba9db-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba9db-267">Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</span><span class="sxs-lookup"><span data-stu-id="ba9db-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-268">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-269">Traffico SIP in uscita (da amministratore, indirizzo IP virtuale del pool di Director, Front End Server o indirizzo IP virtuale del pool Front End) a VIP Edge interno</span><span class="sxs-lookup"><span data-stu-id="ba9db-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-270">Accesso/SIP (MTLS)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba9db-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba9db-271">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-272">Qualsiasi (può essere definito come amministratore, indirizzo IP virtuale del pool di server Director, indirizzo IP virtuale del pool Front end o front-end)</span><span class="sxs-lookup"><span data-stu-id="ba9db-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-273">Traffico SIP in ingresso (per il server Director, l'indirizzo IP virtuale del pool di Director, l'indirizzo IP virtuale front-end o il pool Front End) dall'interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ba9db-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ba9db-275">Qualsiasi (può essere definito come indirizzo IP front end server o indirizzo IP del pool Front end o un Survivable Branch Appliance o Survivable Branch Server con questo server perimetrale)</span><span class="sxs-lookup"><span data-stu-id="ba9db-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ba9db-276">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-277">Autenticazione degli utenti A/V (servizio di autenticazione A/V) dall'indirizzo IP di front end server o del pool Front end o da un Survivable Branch Appliance o Survivable Branch Server che utilizza questo server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba9db-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba9db-279">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-279">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-280">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-281">Percorso preferito per trasferimenti multimediali A/V tra utenti interni ed esterni</span><span class="sxs-lookup"><span data-stu-id="ba9db-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba9db-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-283">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-283">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-284">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-285">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="ba9db-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba9db-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba9db-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba9db-287">Interfaccia VIP interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ba9db-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ba9db-288">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ba9db-288">Any</span></span></p></td>
<td><p><span data-ttu-id="ba9db-289">Percorso di fallback per il trasferimento multimediale A/V tra utenti interni ed esterni se non è possibile stabilire la comunicazione UDP. TCP viene utilizzato per il trasferimento di file e la condivisione del desktop</span><span class="sxs-lookup"><span data-stu-id="ba9db-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

