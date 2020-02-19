---
title: 'Lync Server 2013: nuove funzionalità di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf51e5d06241ece778d5bdb6dc41691e64682f18
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42124409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="f0deb-102">Nuove funzionalità di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0deb-103">_**Ultimo argomento modificato:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="f0deb-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="f0deb-104">Lync Server 2013 introduce diverse nuove funzionalità di routing e gestione delle chiamate che migliorano VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f0deb-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="f0deb-105">Lync Server 2013 supporta più trunk tra Mediation Server e gateway.</span><span class="sxs-lookup"><span data-stu-id="f0deb-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="f0deb-106">Un *trunk* è un'associazione logica tra un numero di porta e un Mediation Server con un numero di porta e un gateway.</span><span class="sxs-lookup"><span data-stu-id="f0deb-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="f0deb-107">Questo significa che un Mediation Server può disporre di più trunk per diversi gateway e che un gateway può disporre di più trunk per i Mediation Server diversi.</span><span class="sxs-lookup"><span data-stu-id="f0deb-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="f0deb-108">Il routing tra trunk rende possibile per Lync Server 2013 interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) o per interconnettere più sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f0deb-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="f0deb-109">Lync Server 2013 funge da colla (ovvero l'interconnessione) tra diversi sistemi di telefonia.</span><span class="sxs-lookup"><span data-stu-id="f0deb-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="f0deb-110">Microsoft Lync Server 2013 apporta miglioramenti nelle aree di inoltro di chiamata, squillo simultaneo, gestione della segreteria telefonica e presentazione dell'ID chiamante.</span><span class="sxs-lookup"><span data-stu-id="f0deb-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="f0deb-111">Queste funzionalità arricchiscono l'esperienza di chiamata VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="f0deb-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="f0deb-112">Lync Server 2013 introduce i nuovi miglioramenti seguenti in VoIP aziendale:</span><span class="sxs-lookup"><span data-stu-id="f0deb-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="f0deb-113">Nuove funzionalità di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="f0deb-114">Nuova funzionalità ID chiamante in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="f0deb-115">Nuova funzionalità di segreteria telefonica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="f0deb-116">Nuova funzionalità trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="f0deb-117">Nuova funzionalità di intertrunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="f0deb-118">Nuove funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0deb-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

