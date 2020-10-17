---
title: 'Lync Server 2013: riepilogo delle porte-bilanciamento del carico DNS e bilancio di HLB'
description: 'Lync Server 2013: riepilogo delle porte-bilanciamento del carico DNS e dei carichi di HLB.'
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
ms.openlocfilehash: be2e8204e792fd9c4718cb9171e90784af2d0104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543132"
---
# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="638ad-103">Riepilogo delle porte-bilanciamento del carico DNS e del caricamento in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="638ad-103">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="638ad-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="638ad-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="638ad-105">I requisiti delle porte del firewall per un singolo Director sono costituiti dalle porte che vengono utilizzate per stabilire la comunicazione con il server Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="638ad-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="638ad-106">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="638ad-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="638ad-107">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="638ad-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="638ad-108">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="638ad-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="638ad-109">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="638ad-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="638ad-110">Porte e protocolli del singolo Director per le definizioni del firewall</span><span class="sxs-lookup"><span data-stu-id="638ad-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="638ad-111">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="638ad-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="638ad-112">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="638ad-112">Source IP address</span></span></th>
<th><span data-ttu-id="638ad-113">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="638ad-113">Destination IP address</span></span></th>
<th><span data-ttu-id="638ad-114">Note</span><span class="sxs-lookup"><span data-stu-id="638ad-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="638ad-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="638ad-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="638ad-116">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="638ad-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="638ad-117">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="638ad-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="638ad-118">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="638ad-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638ad-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="638ad-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="638ad-120">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="638ad-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="638ad-121">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="638ad-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="638ad-122">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web del Director HLB VIP e front end server.</span><span class="sxs-lookup"><span data-stu-id="638ad-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638ad-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="638ad-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="638ad-124">Director</span><span class="sxs-lookup"><span data-stu-id="638ad-124">Director</span></span></p></td>
<td><p><span data-ttu-id="638ad-125">Pool Front end o front end server</span><span class="sxs-lookup"><span data-stu-id="638ad-125">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="638ad-126">Comunicazione tra server tra il VIP di HLB del regista e il front end server o front end server.</span><span class="sxs-lookup"><span data-stu-id="638ad-126">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638ad-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="638ad-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="638ad-128">Client interni</span><span class="sxs-lookup"><span data-stu-id="638ad-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="638ad-129">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="638ad-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="638ad-130">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="638ad-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638ad-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="638ad-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="638ad-132">Client interni</span><span class="sxs-lookup"><span data-stu-id="638ad-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="638ad-133">VIP del bilanciamento del carico hardware del server Director</span><span class="sxs-lookup"><span data-stu-id="638ad-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="638ad-134">Il Director fornisce servizi Web ai client interni e esterni.</span><span class="sxs-lookup"><span data-stu-id="638ad-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638ad-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="638ad-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="638ad-136">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="638ad-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="638ad-137">Director</span><span class="sxs-lookup"><span data-stu-id="638ad-137">Director</span></span></p></td>
<td><p><span data-ttu-id="638ad-138">Comunicazione SIP dal server perimetrale al Director, oltre ai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="638ad-138">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638ad-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="638ad-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="638ad-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="638ad-140">Any</span></span></p></td>
<td><p><span data-ttu-id="638ad-141">Director</span><span class="sxs-lookup"><span data-stu-id="638ad-141">Director</span></span></p></td>
<td><p><span data-ttu-id="638ad-142">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="638ad-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="638ad-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="638ad-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="638ad-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="638ad-144">Any</span></span></p></td>
<td><p><span data-ttu-id="638ad-145">Director</span><span class="sxs-lookup"><span data-stu-id="638ad-145">Director</span></span></p></td>
<td><p><span data-ttu-id="638ad-146">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="638ad-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="638ad-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="638ad-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="638ad-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="638ad-148">Any</span></span></p></td>
<td><p><span data-ttu-id="638ad-149">Director</span><span class="sxs-lookup"><span data-stu-id="638ad-149">Director</span></span></p></td>
<td><p><span data-ttu-id="638ad-150">Comandi di controllo del servizio di registrazione centralizzato (ClsController.exe) o di Agent (ClsAgent.exe) e raccolta di registri</span><span class="sxs-lookup"><span data-stu-id="638ad-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

