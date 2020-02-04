---
title: Riepilogo della porta-Federazione XMPP (Extensible Messaging and Presence Protocol)
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
ms.openlocfilehash: 0a18129fce98b3bb9bc613f4fc752daadfb6c5ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="85d4a-102">Riepilogo della porta-Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85d4a-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85d4a-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="85d4a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="85d4a-104">Le porte e i protocolli definiti per il proxy XMPP (Extensible Messaging and Presence Protocol) distribuiti nel server perimetrale consentono le comunicazioni dal partner federato XMPP al server perimetrale e consente inoltre la comunicazione da un server perimetrale alla XMPP partner federato.</span><span class="sxs-lookup"><span data-stu-id="85d4a-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="85d4a-105">Una regola viene definita anche nel firewall rivolto internamente dal server front-end o dal pool Front-end al server perimetrale o al pool Edge.</span><span class="sxs-lookup"><span data-stu-id="85d4a-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="85d4a-106">Riepilogo del firewall per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="85d4a-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85d4a-107">Protocollo/TCP o UDP/porta</span><span class="sxs-lookup"><span data-stu-id="85d4a-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="85d4a-108">Origine (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="85d4a-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="85d4a-109">Destinazione (indirizzo IP)</span><span class="sxs-lookup"><span data-stu-id="85d4a-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="85d4a-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="85d4a-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85d4a-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="85d4a-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="85d4a-112">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="85d4a-112">Any</span></span></p></td>
<td><p><span data-ttu-id="85d4a-113">Indirizzo IP dell'interfaccia del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="85d4a-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="85d4a-114">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="85d4a-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="85d4a-115">Consente la comunicazione al proxy XMPP di Edge Server da partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="85d4a-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85d4a-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="85d4a-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="85d4a-117">Indirizzo IP dell'interfaccia del servizio Edge di Access</span><span class="sxs-lookup"><span data-stu-id="85d4a-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="85d4a-118">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="85d4a-118">Any</span></span></p></td>
<td><p><span data-ttu-id="85d4a-119">Porta di comunicazione standard da server a server per XMPP.</span><span class="sxs-lookup"><span data-stu-id="85d4a-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="85d4a-120">Consente la comunicazione dal proxy XMPP di Edge Server ai partner XMPP federati</span><span class="sxs-lookup"><span data-stu-id="85d4a-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85d4a-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="85d4a-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="85d4a-122">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="85d4a-122">Any</span></span></p></td>
<td><p><span data-ttu-id="85d4a-123">IP dell'interfaccia server perimetrale interno</span><span class="sxs-lookup"><span data-stu-id="85d4a-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="85d4a-124">Traffico XMPP interno dal gateway XMPP nel server front-end o nel pool Front end al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="85d4a-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="85d4a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85d4a-125">See Also</span></span>


[<span data-ttu-id="85d4a-126">Esempio di configurazione XMPP in Lync Server 2013 - federazione di XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="85d4a-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="85d4a-127">Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85d4a-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

