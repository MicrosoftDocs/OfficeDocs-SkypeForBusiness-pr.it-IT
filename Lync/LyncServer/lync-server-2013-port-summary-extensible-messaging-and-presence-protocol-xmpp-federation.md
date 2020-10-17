---
title: Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol)
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
ms.openlocfilehash: 5c8d7f99b4a7c72b9eb039fb7447397e711caa36
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527923"
---
# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="2b872-102">Riepilogo delle porte-Federazione di protocollo XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b872-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b872-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="2b872-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="2b872-104">Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuito nel server perimetrale consentono la comunicazione dal partner federato XMPP al server perimetrale e consentono inoltre la comunicazione dal server perimetrale al partner federato XMPP.</span><span class="sxs-lookup"><span data-stu-id="2b872-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="2b872-105">Una regola viene definita anche nel firewall con accesso interno dal front end server o dal pool Front end al server perimetrale o al pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="2b872-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="2b872-106">Riepilogo firewall per XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="2b872-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b872-107">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="2b872-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2b872-108">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="2b872-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="2b872-109">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="2b872-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="2b872-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b872-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b872-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="2b872-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="2b872-112">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b872-112">Any</span></span></p></td>
<td><p><span data-ttu-id="2b872-113">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="2b872-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="2b872-114">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="2b872-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="2b872-115">Consente la comunicazione con il proxy XMPP del server perimetrale da partner federati XMPP</span><span class="sxs-lookup"><span data-stu-id="2b872-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b872-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="2b872-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="2b872-117">Indirizzo IP dell'interfaccia del servizio Access Edge</span><span class="sxs-lookup"><span data-stu-id="2b872-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="2b872-118">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b872-118">Any</span></span></p></td>
<td><p><span data-ttu-id="2b872-119">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="2b872-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="2b872-120">Consente la comunicazione dal proxy XMPP del server perimetrale ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="2b872-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b872-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="2b872-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="2b872-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b872-122">Any</span></span></p></td>
<td><p><span data-ttu-id="2b872-123">IP dell'interfaccia del server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="2b872-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="2b872-124">Traffico XMPP interno dal gateway XMPP nel front end server o nel pool Front end al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="2b872-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b872-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b872-125">See Also</span></span>


[<span data-ttu-id="2b872-126">Esempio di configurazione XMPP in Lync Server 2013 – Federazione XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="2b872-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="2b872-127">Gestire i partner federati XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b872-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

