---
title: Riepilogo DNS-Federazione XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49105655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff58998ef9114baeb7dc7c6462ca0ebaae114f10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="620f3-102">Riepilogo DNS-Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f3-102">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="620f3-103">_**Argomento Ultima modifica:** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="620f3-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="620f3-104">Per configurare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, è possibile creare due record DNS (Domain Name System) in un server DNS esterno che risolverà i record nel servizio Edge di Access del server perimetrale o del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="620f3-104">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two Domain Name System (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="620f3-105">Riepilogo DNS per il protocollo di messaggistica e presenza estensibile</span><span class="sxs-lookup"><span data-stu-id="620f3-105">DNS Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="620f3-106">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="620f3-106">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="620f3-107">FQDN</span><span class="sxs-lookup"><span data-stu-id="620f3-107">FQDN</span></span></th>
<th><span data-ttu-id="620f3-108">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="620f3-108">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="620f3-109">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="620f3-109">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="620f3-110">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="620f3-110">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="620f3-111">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="620f3-111">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="620f3-112">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="620f3-112">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="620f3-113">Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="620f3-113">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="620f3-114">Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="620f3-114">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="620f3-115">Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</span><span class="sxs-lookup"><span data-stu-id="620f3-115">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="620f3-116">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="620f3-116">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="620f3-117">xmpp.contoso.com (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="620f3-117">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="620f3-118">Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="620f3-118">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="620f3-119">Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="620f3-119">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="620f3-120">In genere, il record SRV creato punterà al record host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="620f3-120">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="620f3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="620f3-121">See Also</span></span>


[<span data-ttu-id="620f3-122">Configurazione della federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f3-122">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  


[<span data-ttu-id="620f3-123">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="620f3-123">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

