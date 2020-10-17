---
title: Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol)
description: Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9508bc8b9fbcca6fb6a37478def258a9fa52c373
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543092"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="4d98f-103">Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d98f-103">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d98f-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="4d98f-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="4d98f-105">Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuito nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono inoltre la comunicazione dal server perimetrale al partner federato XMPP.</span><span class="sxs-lookup"><span data-stu-id="4d98f-105">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="4d98f-106">Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="4d98f-106">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="4d98f-107">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="4d98f-107">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d98f-108">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="4d98f-108">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="4d98f-109">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="4d98f-109">Source (IP address)</span></span></th>
<th><span data-ttu-id="4d98f-110">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="4d98f-110">Destination (IP address)</span></span></th>
<th><span data-ttu-id="4d98f-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="4d98f-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d98f-112">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4d98f-112">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4d98f-113">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="4d98f-113">Any</span></span></p></td>
<td><p><span data-ttu-id="4d98f-114">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="4d98f-114">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4d98f-115">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="4d98f-115">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4d98f-116">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="4d98f-116">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d98f-117">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="4d98f-117">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="4d98f-118">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="4d98f-118">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="4d98f-119">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="4d98f-119">Any</span></span></p></td>
<td><p><span data-ttu-id="4d98f-120">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="4d98f-120">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="4d98f-121">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="4d98f-121">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d98f-122">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="4d98f-122">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="4d98f-123">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="4d98f-123">Any</span></span></p></td>
<td><p><span data-ttu-id="4d98f-124">IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="4d98f-124">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="4d98f-125">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="4d98f-125">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d98f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d98f-126">See Also</span></span>


[<span data-ttu-id="4d98f-127">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="4d98f-127">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="4d98f-128">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d98f-128">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

