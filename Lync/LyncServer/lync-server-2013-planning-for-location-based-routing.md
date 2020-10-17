---
title: 'Lync Server 2013: pianificazione del routing Location-Based'
description: 'Lync Server 2013: pianificazione del routing per Location-Based.'
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
ms.openlocfilehash: 894a596e998fe07b97ad7911441eced670ba85b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553082"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2f9ee-103">Pianificazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-103">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f9ee-104">_**Ultimo argomento modificato:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="2f9ee-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="2f9ee-105">Le informazioni contenute in questo argomento riguardano gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-105">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="2f9ee-106">Location-Based routing rende possibile limitare il routing delle chiamate tra endpoint VoIP e endpoint PSTN in base alla posizione delle parti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-106">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="2f9ee-107">Location-Based routing è parte dell'infrastruttura di VoIP aziendale di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-107">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="2f9ee-108">Location-Based routing è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate tramite Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-108">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="2f9ee-109">Applica le regole di autorizzazione delle chiamate per stabilire se le chiamate possono essere instradate a endpoint PBX o PSTN in base alla posizione geografica del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-109">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f9ee-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="2f9ee-110">In This Section</span></span>

  - [<span data-ttu-id="2f9ee-111">Panoramica del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-111">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-112">Linee guida per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-112">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-113">Scenari per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-113">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-114">Considerazioni tecniche per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-114">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-115">Supporto per client e server per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-115">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-116">Funzionalità non supportate dal routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-116">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-117">Processo di distribuzione per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-117">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="2f9ee-118">Routing in base alla posizione per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-118">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f9ee-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f9ee-119">See Also</span></span>


[<span data-ttu-id="2f9ee-120">Pianificazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f9ee-120">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

