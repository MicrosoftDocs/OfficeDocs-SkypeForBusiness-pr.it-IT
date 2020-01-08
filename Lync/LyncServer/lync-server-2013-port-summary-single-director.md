---
title: 'Lync Server 2013: Riepilogo delle porte - singolo server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5568a37093f161caef6717df5d3a3f09be6f18c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="aabf2-102">Riepilogo delle porte - singolo server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aabf2-102">Port summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aabf2-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="aabf2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="aabf2-104">I requisiti della porta firewall per un singolo Director sono costituiti dalle porte usate per stabilire la comunicazione con il Director dall'interfaccia interna o dalla rete interna del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="aabf2-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="aabf2-105">Per impostazione predefinita, Microsoft Lync Server 2013 prevede che le porte HTTP/TCP 8080 e HTTPS/TCP 4443 siano aperte dal proxy inverso al Director, oltre al pool Front end e al server front-end.</span><span class="sxs-lookup"><span data-stu-id="aabf2-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="aabf2-106">Inoltre, deve essere disponibile una comunicazione SIP (Session Initiation Protocol) dall'interfaccia interna del server perimetrale al Director e al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="aabf2-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="aabf2-107">Il protocollo SIP USA SIP/MTLS/TCP 5061 dall'Edge Server al pool Front end e front end server.</span><span class="sxs-lookup"><span data-stu-id="aabf2-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="aabf2-108">Deve essere creata anche una regola che consente la comunicazione SIP/MTLS/TCP 5061 da parte del Director, del pool Front end e del front end server all'interfaccia interna del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="aabf2-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="aabf2-109">Porte e protocolli per Director singole per le definizioni di firewall</span><span class="sxs-lookup"><span data-stu-id="aabf2-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aabf2-110">Ruolo/protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="aabf2-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="aabf2-111">Indirizzo IP di origine</span><span class="sxs-lookup"><span data-stu-id="aabf2-111">Source IP address</span></span></th>
<th><span data-ttu-id="aabf2-112">Indirizzo IP di destinazione</span><span class="sxs-lookup"><span data-stu-id="aabf2-112">Destination IP address</span></span></th>
<th><span data-ttu-id="aabf2-113">Note</span><span class="sxs-lookup"><span data-stu-id="aabf2-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aabf2-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="aabf2-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="aabf2-115">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="aabf2-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-116">Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-116">Director</span></span></p></td>
<td><p><span data-ttu-id="aabf2-117">Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="aabf2-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aabf2-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="aabf2-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="aabf2-119">Interfaccia interna del proxy inverso</span><span class="sxs-lookup"><span data-stu-id="aabf2-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-120">Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-120">Director</span></span></p></td>
<td><p><span data-ttu-id="aabf2-121">Inizialmente ricevuto dal lato esterno del proxy inverso, la comunicazione viene inviata ai servizi Web Director e front end server</span><span class="sxs-lookup"><span data-stu-id="aabf2-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aabf2-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="aabf2-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="aabf2-123">Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-123">Director</span></span></p></td>
<td><p><span data-ttu-id="aabf2-124">Server front-end o pool Front-End</span><span class="sxs-lookup"><span data-stu-id="aabf2-124">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="aabf2-125">Comunicazioni tra server tra il Director e il front end server</span><span class="sxs-lookup"><span data-stu-id="aabf2-125">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aabf2-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="aabf2-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="aabf2-127">Client interni</span><span class="sxs-lookup"><span data-stu-id="aabf2-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="aabf2-128">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-128">Director web services</span></span></p></td>
<td><p><span data-ttu-id="aabf2-129">Il Director offre servizi Web a client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="aabf2-129">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aabf2-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="aabf2-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="aabf2-131">Client interni</span><span class="sxs-lookup"><span data-stu-id="aabf2-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="aabf2-132">Servizi Web Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-132">Director web services</span></span></p></td>
<td><p><span data-ttu-id="aabf2-133">Il Director offre servizi Web a client interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="aabf2-133">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aabf2-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="aabf2-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="aabf2-135">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="aabf2-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-136">Director</span><span class="sxs-lookup"><span data-stu-id="aabf2-136">Director</span></span></p></td>
<td><p><span data-ttu-id="aabf2-137">Comunicazioni SIP dall'Edge Server al Director e al server front-end.</span><span class="sxs-lookup"><span data-stu-id="aabf2-137">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aabf2-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="aabf2-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="aabf2-139">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="aabf2-139">Any</span></span></p></td>
<td><p><span data-ttu-id="aabf2-140">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="aabf2-140">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-141">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="aabf2-141">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aabf2-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="aabf2-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="aabf2-143">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="aabf2-143">Any</span></span></p></td>
<td><p><span data-ttu-id="aabf2-144">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="aabf2-144">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-145">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="aabf2-145">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aabf2-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="aabf2-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="aabf2-147">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="aabf2-147">Any</span></span></p></td>
<td><p><span data-ttu-id="aabf2-148">Interfaccia interna del server perimetrale</span><span class="sxs-lookup"><span data-stu-id="aabf2-148">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="aabf2-149">Controller di servizio di registrazione centralizzato (ClsController. exe) o di comando Agent (ClasAgent. exe) e raccolta log</span><span class="sxs-lookup"><span data-stu-id="aabf2-149">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

