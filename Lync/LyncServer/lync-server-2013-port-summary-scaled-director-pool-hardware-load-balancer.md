---
title: 'Lync Server 2013: riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware'
description: 'Lync Server 2013: riassunto delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564552"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="ab167-103">Riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ab167-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab167-104">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ab167-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ab167-105">I requisiti delle porte del firewall per un pool di server Director sono costituiti dalle porte utilizzate per stabilire la comunicazione con il Director dall'interfaccia interna del server perimetrale o dall'interfaccia interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="ab167-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="ab167-106">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="ab167-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="ab167-107">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="ab167-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ab167-108">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="ab167-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ab167-109">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="ab167-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="ab167-110">Porte director e protocollo per le definizioni firewall</span><span class="sxs-lookup"><span data-stu-id="ab167-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab167-111">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ab167-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ab167-112">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ab167-112">Source IP address</span></span></th>
<th><span data-ttu-id="ab167-113">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ab167-113">Destination IP address</span></span></th>
<th><span data-ttu-id="ab167-114">Note</span><span class="sxs-lookup"><span data-stu-id="ab167-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab167-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="ab167-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="ab167-116">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab167-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ab167-117">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ab167-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ab167-118">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</span><span class="sxs-lookup"><span data-stu-id="ab167-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab167-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="ab167-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="ab167-120">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ab167-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ab167-121">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ab167-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ab167-122">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</span><span class="sxs-lookup"><span data-stu-id="ab167-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab167-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="ab167-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="ab167-124">Director</span><span class="sxs-lookup"><span data-stu-id="ab167-124">Director</span></span></p></td>
<td><p><span data-ttu-id="ab167-125">Front End Server o pool Front End</span><span class="sxs-lookup"><span data-stu-id="ab167-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="ab167-126">Comunicazione tra server tra il direttore di HLB VIP e i Front End Server</span><span class="sxs-lookup"><span data-stu-id="ab167-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab167-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="ab167-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="ab167-128">Client interni</span><span class="sxs-lookup"><span data-stu-id="ab167-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ab167-129">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ab167-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ab167-130">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="ab167-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab167-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="ab167-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="ab167-132">Client interni</span><span class="sxs-lookup"><span data-stu-id="ab167-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ab167-133">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ab167-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ab167-134">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="ab167-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab167-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="ab167-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="ab167-136">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ab167-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ab167-137">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ab167-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ab167-138">Comunicazione SIP dal server perimetrale al Director e front end server.</span><span class="sxs-lookup"><span data-stu-id="ab167-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab167-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ab167-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ab167-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ab167-140">Any</span></span></p></td>
<td><p><span data-ttu-id="ab167-141">Director</span><span class="sxs-lookup"><span data-stu-id="ab167-141">Director</span></span></p></td>
<td><p><span data-ttu-id="ab167-142">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ab167-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab167-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ab167-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ab167-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ab167-144">Any</span></span></p></td>
<td><p><span data-ttu-id="ab167-145">Director</span><span class="sxs-lookup"><span data-stu-id="ab167-145">Director</span></span></p></td>
<td><p><span data-ttu-id="ab167-146">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ab167-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab167-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ab167-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ab167-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ab167-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ab167-149">Director</span><span class="sxs-lookup"><span data-stu-id="ab167-149">Director</span></span></p></td>
<td><p><span data-ttu-id="ab167-150">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ab167-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

