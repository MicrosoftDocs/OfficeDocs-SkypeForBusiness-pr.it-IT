---
title: 'Lync Server 2013: riepilogo delle porte-bilanciamento del carico DNS e bilancio di HLB'
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
ms.openlocfilehash: 3e6175f83e1cea20e21ed25c372849c0e6b80b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="ffa90-102">Riepilogo delle porte-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffa90-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffa90-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ffa90-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ffa90-104">I requisiti delle porte del firewall per un singolo Director sono costituiti dalle porte che vengono utilizzate per stabilire la comunicazione con il server Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="ffa90-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="ffa90-105">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="ffa90-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="ffa90-106">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ffa90-107">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="ffa90-108">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="ffa90-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="ffa90-109">Porte e protocolli del singolo Director per le definizioni del firewall</span><span class="sxs-lookup"><span data-stu-id="ffa90-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffa90-110">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ffa90-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ffa90-111">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="ffa90-111">Source IP address</span></span></th>
<th><span data-ttu-id="ffa90-112">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="ffa90-112">Destination IP address</span></span></th>
<th><span data-ttu-id="ffa90-113">Notes</span><span class="sxs-lookup"><span data-stu-id="ffa90-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffa90-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="ffa90-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="ffa90-115">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ffa90-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ffa90-116">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ffa90-117">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffa90-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="ffa90-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="ffa90-119">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ffa90-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="ffa90-120">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ffa90-121">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffa90-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="ffa90-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="ffa90-123">Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-123">Director</span></span></p></td>
<td><p><span data-ttu-id="ffa90-124">Pool Front end o front end server</span><span class="sxs-lookup"><span data-stu-id="ffa90-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="ffa90-125">Comunicazione tra server tra il VIP di HLB del regista e il front end server o front end server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffa90-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="ffa90-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="ffa90-127">Client interni</span><span class="sxs-lookup"><span data-stu-id="ffa90-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ffa90-128">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ffa90-129">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="ffa90-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffa90-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="ffa90-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="ffa90-131">Client interni</span><span class="sxs-lookup"><span data-stu-id="ffa90-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="ffa90-132">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="ffa90-133">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="ffa90-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffa90-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="ffa90-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="ffa90-135">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="ffa90-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ffa90-136">Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-136">Director</span></span></p></td>
<td><p><span data-ttu-id="ffa90-137">Comunicazione SIP dal server perimetrale al Director, oltre ai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="ffa90-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffa90-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ffa90-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ffa90-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ffa90-139">Any</span></span></p></td>
<td><p><span data-ttu-id="ffa90-140">Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-140">Director</span></span></p></td>
<td><p><span data-ttu-id="ffa90-141">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ffa90-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffa90-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ffa90-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ffa90-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ffa90-143">Any</span></span></p></td>
<td><p><span data-ttu-id="ffa90-144">Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-144">Director</span></span></p></td>
<td><p><span data-ttu-id="ffa90-145">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ffa90-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffa90-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ffa90-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ffa90-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="ffa90-147">Any</span></span></p></td>
<td><p><span data-ttu-id="ffa90-148">Director</span><span class="sxs-lookup"><span data-stu-id="ffa90-148">Director</span></span></p></td>
<td><p><span data-ttu-id="ffa90-149">Comandi del controller del servizio di registrazione centralizzato (ClsController. exe) o dell'agente (ClsAgent. exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="ffa90-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

