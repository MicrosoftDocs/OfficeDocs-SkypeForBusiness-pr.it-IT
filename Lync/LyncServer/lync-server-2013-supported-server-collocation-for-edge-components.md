---
title: 'Lync Server 2013: collocazione dei server supportata per i componenti perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e52d1c630bba8c93193c2e309d4d3299f45a6388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="52109-102">Collocazione dei server supportata per i componenti perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52109-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52109-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="52109-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="52109-104">Il servizio Access Edge, il servizio Web Conferencing Edge, il servizio A/V Edge e il servizio proxy XMPP sono collocati nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="52109-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="52109-105">I server seguenti forniscono le funzioni necessarie per l'accesso degli utenti esterni e devono essere distribuiti come server dedicati:</span><span class="sxs-lookup"><span data-stu-id="52109-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="52109-106">Server perimetrale</span><span class="sxs-lookup"><span data-stu-id="52109-106">Edge Server</span></span>

  - <span data-ttu-id="52109-107">Server Director (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="52109-107">Director (Optional)</span></span>

  - <span data-ttu-id="52109-108">Proxy inverso</span><span class="sxs-lookup"><span data-stu-id="52109-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52109-109">Non è necessario che il proxy inverso sia dedicato alla gestione di solo Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52109-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="52109-110">Ad esempio, è possibile fornire servizi per la pubblicazione dei servizi Web di Lync Server e fornire contemporaneamente un sito Web pubblicato per un altro sito Web che non ha alcun impatto su Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52109-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="52109-111">Se si dispone già di un server proxy inverso nella rete perimetrale per supportare altri servizi, è possibile utilizzarlo per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="52109-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

