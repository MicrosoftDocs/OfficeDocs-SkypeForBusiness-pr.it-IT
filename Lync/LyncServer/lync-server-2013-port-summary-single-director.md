---
title: 'Lync Server 2013: riepilogo delle porte-singolo server Director'
description: 'Lync Server 2013: riepilogo delle porte-singolo server Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566372"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="51296-103">Riepilogo delle porte-singolo Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51296-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51296-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="51296-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="51296-105">I requisiti delle porte del firewall per un singolo Director sono costituiti dalle porte che vengono utilizzate per stabilire la comunicazione con il server Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="51296-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="51296-106">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="51296-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="51296-107">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="51296-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="51296-108">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="51296-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="51296-109">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="51296-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="51296-110">Porte e protocolli del singolo Director per le definizioni del firewall</span><span class="sxs-lookup"><span data-stu-id="51296-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51296-111">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="51296-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="51296-112">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="51296-112">Source IP address</span></span></th>
<th><span data-ttu-id="51296-113">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="51296-113">Destination IP address</span></span></th>
<th><span data-ttu-id="51296-114">Note</span><span class="sxs-lookup"><span data-stu-id="51296-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51296-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="51296-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="51296-116">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="51296-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-117">Director</span><span class="sxs-lookup"><span data-stu-id="51296-117">Director</span></span></p></td>
<td><p><span data-ttu-id="51296-118">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="51296-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51296-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="51296-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="51296-120">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="51296-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-121">Director</span><span class="sxs-lookup"><span data-stu-id="51296-121">Director</span></span></p></td>
<td><p><span data-ttu-id="51296-122">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="51296-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51296-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="51296-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="51296-124">Director</span><span class="sxs-lookup"><span data-stu-id="51296-124">Director</span></span></p></td>
<td><p><span data-ttu-id="51296-125">Front End Server o pool Front End</span><span class="sxs-lookup"><span data-stu-id="51296-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="51296-126">Comunicazione tra server tra il Director e il front end server</span><span class="sxs-lookup"><span data-stu-id="51296-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51296-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="51296-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="51296-128">Client interni</span><span class="sxs-lookup"><span data-stu-id="51296-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="51296-129">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="51296-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="51296-130">Il Director fornisce servizi Web ai client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="51296-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51296-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="51296-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="51296-132">Client interni</span><span class="sxs-lookup"><span data-stu-id="51296-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="51296-133">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="51296-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="51296-134">Il Director fornisce servizi Web ai client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="51296-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51296-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="51296-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="51296-136">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="51296-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-137">Director</span><span class="sxs-lookup"><span data-stu-id="51296-137">Director</span></span></p></td>
<td><p><span data-ttu-id="51296-138">Comunicazione SIP dal server perimetrale al Director e front end server.</span><span class="sxs-lookup"><span data-stu-id="51296-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51296-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="51296-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="51296-140">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="51296-140">Any</span></span></p></td>
<td><p><span data-ttu-id="51296-141">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="51296-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-142">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="51296-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51296-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="51296-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="51296-144">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="51296-144">Any</span></span></p></td>
<td><p><span data-ttu-id="51296-145">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="51296-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-146">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="51296-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51296-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="51296-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="51296-148">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="51296-148">Any</span></span></p></td>
<td><p><span data-ttu-id="51296-149">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="51296-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="51296-150">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="51296-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

