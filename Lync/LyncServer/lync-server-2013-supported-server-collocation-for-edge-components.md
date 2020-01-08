---
title: 'Lync Server 2013: Collocazione dei server supportata per i componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ad78cc1060c64181a75acefa21e64809e0d7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="913b7-102">Collocazione dei server supportata per i componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="913b7-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="913b7-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="913b7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="913b7-104">I servizi Edge di Access, Web Conferencing Edge service, A/V Edge e il servizio proxy XMPP sono collocati negli Edge Server.</span><span class="sxs-lookup"><span data-stu-id="913b7-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="913b7-105">I server seguenti includono le funzioni necessarie per l'accesso degli utenti esterni e devono essere distribuite come server dedicati:</span><span class="sxs-lookup"><span data-stu-id="913b7-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="913b7-106">Edge Server</span><span class="sxs-lookup"><span data-stu-id="913b7-106">Edge Server</span></span>

  - <span data-ttu-id="913b7-107">Director (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="913b7-107">Director (Optional)</span></span>

  - <span data-ttu-id="913b7-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="913b7-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="913b7-109">Non è necessario che il proxy inverso sia dedicato al servizio solo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="913b7-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="913b7-110">Ad esempio, puoi prestare servizi per pubblicare i servizi Web di Lync Server e contemporaneamente creare un sito Web pubblicato per un altro sito Web che non ha alcun impatto su Lync Server.</span><span class="sxs-lookup"><span data-stu-id="913b7-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="913b7-111">Se si dispone già di un server proxy inverso nella rete perimetrale per supportare altri servizi, è possibile usarlo per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="913b7-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

