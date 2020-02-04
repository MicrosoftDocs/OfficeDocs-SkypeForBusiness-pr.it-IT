---
title: 'Lync Server 2013: connessioni SIP dirette'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5cd00033eeccc855cd5ff10b6a2bee6f78da1d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="72400-102">Connessioni SIP dirette in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72400-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72400-103">_**Argomento Ultima modifica:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="72400-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="72400-104">È possibile usare *connessioni SIP dirette* per connettere Lync Server a una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72400-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="72400-105">IP-PBX (per informazioni dettagliate, vedere [Opzioni di distribuzione SIP dirette in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="72400-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="72400-106">Un gateway PSTN (per informazioni dettagliate, vedere [Opzioni di distribuzione del gateway PSTN in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="72400-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="72400-107">Per implementare una connessione SIP diretta, è necessario seguire essenzialmente gli stessi passaggi di distribuzione che si vuole implementare in un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="72400-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="72400-108">In entrambi i casi, la connessione viene implementata usando l'interfaccia esterna di un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="72400-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="72400-109">L'unica differenza è che si connettono trunk SIP a un'entità esterna, ad esempio un gateway ITSP, e si connettono connessioni SIP dirette a un'entità interna all'interno della rete locale, ad esempio un IP-PBX o un gateway PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="72400-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="72400-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="72400-110">In This Section</span></span>

  - [<span data-ttu-id="72400-111">Opzioni di distribuzione SIP diretta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72400-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="72400-112">Opzioni di distribuzione di gateway PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72400-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

