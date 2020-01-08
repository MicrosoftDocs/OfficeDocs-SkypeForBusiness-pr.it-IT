---
title: 'Lync Server 2013: Considerazioni tecniche per il routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29187cf1a5cf99ae5312f655c924565f6a38a706
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="ab127-102">Considerazioni tecniche per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab127-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab127-103">_**Argomento Ultima modifica:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="ab127-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="ab127-104">Quando si pianifica il routing basato sulla posizione, è consigliabile considerare l'impatto sugli scenari seguenti.</span><span class="sxs-lookup"><span data-stu-id="ab127-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="ab127-105">Ripristino di emergenza</span><span class="sxs-lookup"><span data-stu-id="ab127-105">Disaster Recovery</span></span>

<span data-ttu-id="ab127-106">Durante un failover dal pool principale a un pool di backup e quando si ripristinano le normali operazioni nel pool principale, il routing basato sulla posizione rimane imposto in qualsiasi momento durante una procedura di emergenza e ripristino.</span><span class="sxs-lookup"><span data-stu-id="ab127-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="ab127-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ab127-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="ab127-108">La configurazione del routing basato sulla posizione ha un impatto sulla pianificazione della distribuzione dei gateway associati agli elettrodomestici Survivable Branch.</span><span class="sxs-lookup"><span data-stu-id="ab127-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="ab127-109">Il gateway associato alla SBA deve trovarsi nello stesso sito di rete dell'appliance Survivable Branch; in caso contrario, gli utenti residenti nell'appliance Survivable Branch non saranno autorizzati a inserire chiamate in uscita se è configurato il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="ab127-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="ab127-110">Quando la connessione WAN tra l'appliance Survivable Branch e il sito centrale è in calo, le restrizioni di routing basate sulla posizione restano applicate.</span><span class="sxs-lookup"><span data-stu-id="ab127-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab127-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab127-111">See Also</span></span>


[<span data-ttu-id="ab127-112">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab127-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

