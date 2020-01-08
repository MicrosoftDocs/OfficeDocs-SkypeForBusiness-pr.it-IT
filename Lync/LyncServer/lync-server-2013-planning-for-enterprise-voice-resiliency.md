---
title: 'Lync Server 2013: Pianificazione della resilienza di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66bba2fe6f53198fcc1e1fc423423e02d46ac8b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="db330-102">Pianificazione della resilienza di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db330-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db330-103">_**Argomento Ultima modifica:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="db330-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="db330-104">La resilienza vocale si riferisce alla capacità degli utenti di continuare a effettuare e ricevere chiamate se un sito centrale che ospita Lync Server 2013 non è disponibile, sia tramite un errore WAN (Wide Area Network) che con un'altra causa.</span><span class="sxs-lookup"><span data-stu-id="db330-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="db330-105">Se un sito centrale non riesce, il servizio VoIP aziendale deve continuare senza interruzioni attraverso il failover continuo in un sito di backup.</span><span class="sxs-lookup"><span data-stu-id="db330-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="db330-106">In caso di errore WAN, le chiamate del sito di succursale devono essere reindirizzate a un gateway PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="db330-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="db330-107">In questa sezione viene illustrata la pianificazione della resilienza vocale in caso di errori WAN o del sito centrale.</span><span class="sxs-lookup"><span data-stu-id="db330-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db330-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="db330-108">In This Section</span></span>

  - [<span data-ttu-id="db330-109">Pianificazione della resilienza vocale del sito centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db330-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="db330-110">Pianificazione della resilienza vocale del sito di succursale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db330-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

