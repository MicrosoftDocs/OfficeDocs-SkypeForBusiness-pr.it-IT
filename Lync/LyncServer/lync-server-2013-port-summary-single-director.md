---
title: 'Lync Server 2013: riepilogo delle porte-singolo server Director'
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
ms.openlocfilehash: 95ae1ada828ea4ad3c6bdd2c863333c911635ff8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8a53a-102">Riepilogo delle porte-singolo Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a53a-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a53a-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8a53a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8a53a-104">I requisiti delle porte del firewall per un singolo Director sono costituiti dalle porte che vengono utilizzate per stabilire la comunicazione con il server Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="8a53a-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="8a53a-105">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al server Director, nonché il pool Front end e il front end.</span><span class="sxs-lookup"><span data-stu-id="8a53a-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="8a53a-106">Inoltre, deve essere presente una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="8a53a-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8a53a-107">Il protocollo SIP utilizza SIP/MTLS/TCP 5061 dal server perimetrale al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="8a53a-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="8a53a-108">È anche necessario creare una regola che consenta la comunicazione SIP/MTLS/TCP 5061 del server Director, del pool Front end e del front end server fino all'interfaccia interna di Edge.</span><span class="sxs-lookup"><span data-stu-id="8a53a-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="8a53a-109">Porte e protocolli del singolo Director per le definizioni del firewall</span><span class="sxs-lookup"><span data-stu-id="8a53a-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a53a-110">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="8a53a-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8a53a-111">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="8a53a-111">Source IP address</span></span></th>
<th><span data-ttu-id="8a53a-112">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="8a53a-112">Destination IP address</span></span></th>
<th><span data-ttu-id="8a53a-113">Notes</span><span class="sxs-lookup"><span data-stu-id="8a53a-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a53a-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="8a53a-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="8a53a-115">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8a53a-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-116">Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-116">Director</span></span></p></td>
<td><p><span data-ttu-id="8a53a-117">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="8a53a-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a53a-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="8a53a-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="8a53a-119">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8a53a-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-120">Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-120">Director</span></span></p></td>
<td><p><span data-ttu-id="8a53a-121">Inizialmente ricevuta dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="8a53a-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a53a-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="8a53a-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="8a53a-123">Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-123">Director</span></span></p></td>
<td><p><span data-ttu-id="8a53a-124">Front End Server o pool Front End</span><span class="sxs-lookup"><span data-stu-id="8a53a-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="8a53a-125">Comunicazione tra server tra il Director e il front end server</span><span class="sxs-lookup"><span data-stu-id="8a53a-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a53a-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="8a53a-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="8a53a-127">Client interni</span><span class="sxs-lookup"><span data-stu-id="8a53a-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8a53a-128">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8a53a-129">Il Director fornisce servizi Web ai client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="8a53a-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a53a-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="8a53a-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="8a53a-131">Client interni</span><span class="sxs-lookup"><span data-stu-id="8a53a-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="8a53a-132">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="8a53a-133">Il Director fornisce servizi Web ai client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="8a53a-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a53a-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="8a53a-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="8a53a-135">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="8a53a-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-136">Director</span><span class="sxs-lookup"><span data-stu-id="8a53a-136">Director</span></span></p></td>
<td><p><span data-ttu-id="8a53a-137">Comunicazione SIP dal server perimetrale al Director e front end server.</span><span class="sxs-lookup"><span data-stu-id="8a53a-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a53a-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8a53a-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8a53a-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="8a53a-139">Any</span></span></p></td>
<td><p><span data-ttu-id="8a53a-140">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="8a53a-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-141">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="8a53a-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a53a-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8a53a-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8a53a-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="8a53a-143">Any</span></span></p></td>
<td><p><span data-ttu-id="8a53a-144">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="8a53a-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-145">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="8a53a-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a53a-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8a53a-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8a53a-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="8a53a-147">Any</span></span></p></td>
<td><p><span data-ttu-id="8a53a-148">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="8a53a-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8a53a-149">Comandi e raccolta dei log del controller (ClsController.exe) o dell'agente (ClasAgent.exe) del servizio di registrazione centralizzato</span><span class="sxs-lookup"><span data-stu-id="8a53a-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

