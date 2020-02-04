---
title: 'Lync Server 2013: Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb594057977fbe39f6be6a9a9c678806d7e2d8dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="88125-102">Riepilogo delle porte - bilanciamento del carico DNS e bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88125-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88125-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="88125-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="88125-104">I requisiti della porta firewall per un singolo Director sono costituiti dalle porte usate per stabilire la comunicazione con il Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="88125-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="88125-105">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al Director, oltre al pool Front end e al server front-end.</span><span class="sxs-lookup"><span data-stu-id="88125-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="88125-106">Inoltre, deve essere disponibile una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="88125-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="88125-107">Il protocollo SIP USA SIP/MTLS/TCP 5061 dall'Edge Server al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="88125-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="88125-108">Deve essere creata anche una regola che consente la comunicazione SIP/MTLS/TCP 5061 da parte del Director, del pool Front end e del front end server all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="88125-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="88125-109">Porte e protocolli per Director singole per le definizioni di firewall</span><span class="sxs-lookup"><span data-stu-id="88125-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88125-110">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="88125-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="88125-111">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="88125-111">Source IP address</span></span></th>
<th><span data-ttu-id="88125-112">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="88125-112">Destination IP address</span></span></th>
<th><span data-ttu-id="88125-113">Note</span><span class="sxs-lookup"><span data-stu-id="88125-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88125-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="88125-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="88125-115">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="88125-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="88125-116">VIP di bilanciamento del carico hardware Director</span><span class="sxs-lookup"><span data-stu-id="88125-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="88125-117">Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata al Direttore servizi Web di HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="88125-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88125-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="88125-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="88125-119">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="88125-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="88125-120">VIP di bilanciamento del carico hardware Director</span><span class="sxs-lookup"><span data-stu-id="88125-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="88125-121">Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata al Direttore servizi Web di HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="88125-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88125-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="88125-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="88125-123">Director</span><span class="sxs-lookup"><span data-stu-id="88125-123">Director</span></span></p></td>
<td><p><span data-ttu-id="88125-124">Pool Front end o front end server</span><span class="sxs-lookup"><span data-stu-id="88125-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="88125-125">Comunicazioni tra server tra il Director HLB VIP e il front end server o Front End Servers.</span><span class="sxs-lookup"><span data-stu-id="88125-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88125-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="88125-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="88125-127">Client interni</span><span class="sxs-lookup"><span data-stu-id="88125-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="88125-128">VIP di bilanciamento del carico hardware Director</span><span class="sxs-lookup"><span data-stu-id="88125-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="88125-129">Il Director offre servizi Web a client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="88125-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88125-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="88125-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="88125-131">Client interni</span><span class="sxs-lookup"><span data-stu-id="88125-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="88125-132">VIP di bilanciamento del carico hardware Director</span><span class="sxs-lookup"><span data-stu-id="88125-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="88125-133">Il Director offre servizi Web a client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="88125-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88125-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="88125-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="88125-135">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="88125-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="88125-136">Director</span><span class="sxs-lookup"><span data-stu-id="88125-136">Director</span></span></p></td>
<td><p><span data-ttu-id="88125-137">Comunicare SIP dall'Edge Server al Director, oltre ai server front-end.</span><span class="sxs-lookup"><span data-stu-id="88125-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88125-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="88125-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="88125-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="88125-139">Any</span></span></p></td>
<td><p><span data-ttu-id="88125-140">Director</span><span class="sxs-lookup"><span data-stu-id="88125-140">Director</span></span></p></td>
<td><p><span data-ttu-id="88125-141">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="88125-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88125-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="88125-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="88125-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="88125-143">Any</span></span></p></td>
<td><p><span data-ttu-id="88125-144">Director</span><span class="sxs-lookup"><span data-stu-id="88125-144">Director</span></span></p></td>
<td><p><span data-ttu-id="88125-145">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="88125-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88125-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="88125-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="88125-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="88125-147">Any</span></span></p></td>
<td><p><span data-ttu-id="88125-148">Director</span><span class="sxs-lookup"><span data-stu-id="88125-148">Director</span></span></p></td>
<td><p><span data-ttu-id="88125-149">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClsAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="88125-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

