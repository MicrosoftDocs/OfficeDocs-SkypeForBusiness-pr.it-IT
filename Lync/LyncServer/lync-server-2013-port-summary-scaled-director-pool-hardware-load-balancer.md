---
title: 'Lync Server 2013: riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware'
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
ms.openlocfilehash: 18c0957d66d9b877a67819b8fd8d46d4e614cdad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f87d7-102">Riepilogo delle porte-pool di server Director con scalabilità orizzontale, bilanciamento del carico hardware in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f87d7-102">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f87d7-103">_**Ultimo argomento modificato:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="f87d7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="f87d7-104">I requisiti delle porte del firewall per un pool di server Director sono costituiti dalle porte utilizzate per stabilire la comunicazione con il Director dall'interfaccia interna del server perimetrale o dall'interfaccia interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f87d7-104">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="f87d7-105">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="f87d7-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="f87d7-106">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="f87d7-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="f87d7-107">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="f87d7-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="f87d7-108">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="f87d7-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="f87d7-109">Porte director e protocollo per le definizioni firewall</span><span class="sxs-lookup"><span data-stu-id="f87d7-109">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f87d7-110">Ruolo/Protocollo/TCP o UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="f87d7-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f87d7-111">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="f87d7-111">Source IP address</span></span></th>
<th><span data-ttu-id="f87d7-112">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="f87d7-112">Destination IP address</span></span></th>
<th><span data-ttu-id="f87d7-113">Notes</span><span class="sxs-lookup"><span data-stu-id="f87d7-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f87d7-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="f87d7-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="f87d7-115">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f87d7-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="f87d7-116">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="f87d7-117">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</span><span class="sxs-lookup"><span data-stu-id="f87d7-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f87d7-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="f87d7-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="f87d7-119">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="f87d7-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="f87d7-120">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="f87d7-121">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e Front End Servers.</span><span class="sxs-lookup"><span data-stu-id="f87d7-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f87d7-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="f87d7-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="f87d7-123">Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-123">Director</span></span></p></td>
<td><p><span data-ttu-id="f87d7-124">Front End Server o pool Front End</span><span class="sxs-lookup"><span data-stu-id="f87d7-124">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="f87d7-125">Comunicazione tra server tra il direttore di HLB VIP e i Front End Server</span><span class="sxs-lookup"><span data-stu-id="f87d7-125">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f87d7-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="f87d7-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="f87d7-127">Client interni</span><span class="sxs-lookup"><span data-stu-id="f87d7-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="f87d7-128">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="f87d7-129">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="f87d7-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f87d7-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="f87d7-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="f87d7-131">Client interni</span><span class="sxs-lookup"><span data-stu-id="f87d7-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="f87d7-132">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="f87d7-133">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="f87d7-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f87d7-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="f87d7-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="f87d7-135">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="f87d7-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f87d7-136">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-136">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="f87d7-137">Comunicazione SIP dal server perimetrale al Director e front end server.</span><span class="sxs-lookup"><span data-stu-id="f87d7-137">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f87d7-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="f87d7-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="f87d7-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="f87d7-139">Any</span></span></p></td>
<td><p><span data-ttu-id="f87d7-140">Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-140">Director</span></span></p></td>
<td><p><span data-ttu-id="f87d7-141">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="f87d7-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f87d7-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="f87d7-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="f87d7-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="f87d7-143">Any</span></span></p></td>
<td><p><span data-ttu-id="f87d7-144">Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-144">Director</span></span></p></td>
<td><p><span data-ttu-id="f87d7-145">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="f87d7-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f87d7-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="f87d7-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="f87d7-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="f87d7-147">Any</span></span></p></td>
<td><p><span data-ttu-id="f87d7-148">Director</span><span class="sxs-lookup"><span data-stu-id="f87d7-148">Director</span></span></p></td>
<td><p><span data-ttu-id="f87d7-149">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="f87d7-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

