---
title: 'Lync Server 2013: pianificazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef077c82a273a480977a21ca1e2e8b14043cae46
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="01e6d-102">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01e6d-103">_**Ultimo argomento modificato:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="01e6d-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="01e6d-104">Le informazioni contenute in questo argomento riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="01e6d-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="01e6d-105">Il routing in base alla posizione rende possibile limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="01e6d-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="01e6d-106">Il routing in base alla posizione è parte dell'infrastruttura di VoIP aziendale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01e6d-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="01e6d-107">Il routing in base alla posizione è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate da Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="01e6d-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="01e6d-108">Applica le regole di autorizzazione delle chiamate per stabilire se le chiamate possono essere instradate a endpoint PBX o PSTN in base alla posizione geografica del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="01e6d-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01e6d-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="01e6d-109">In This Section</span></span>

  - [<span data-ttu-id="01e6d-110">Panoramica del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="01e6d-111">Linee guida per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="01e6d-112">Scenari per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="01e6d-113">Considerazioni tecniche per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="01e6d-114">Supporto per client e server per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="01e6d-115">Funzionalità non supportate dal routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="01e6d-116">Processo di distribuzione per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="01e6d-117">Routing in base alla posizione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01e6d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e6d-118">See Also</span></span>


[<span data-ttu-id="01e6d-119">Pianificazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01e6d-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

