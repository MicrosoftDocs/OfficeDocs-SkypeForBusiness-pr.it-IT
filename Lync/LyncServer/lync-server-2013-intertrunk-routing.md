---
title: 'Lync Server 2013: Routing tra trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="b139f-102">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b139f-102">Intertrunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b139f-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b139f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b139f-104">Lync Server 2013 può connettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="b139f-104">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="b139f-105">Analogamente, Lync Server 2013 può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b139f-105">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="b139f-106">Questa caratteristica di routing intertrunk può essere configurata usando il cmdlet Lync Server Management Shell, **Set-CsTrunkConfiguration**, con il nuovo parametro PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="b139f-106">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="b139f-107">Questo parametro specifica il set di record di utilizzo PSTN da usare.</span><span class="sxs-lookup"><span data-stu-id="b139f-107">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="b139f-108">Un trunk usa questo uso PSTN per determinare una route e per instradare tutte le chiamate in arrivo di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="b139f-108">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="b139f-109">Il diagramma seguente illustra Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b139f-109">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="b139f-110">**Routing intertrunk tra gateway e IP PBX**</span><span class="sxs-lookup"><span data-stu-id="b139f-110">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="b139f-111">![Lync Server che connette il gateway PSTN/IP-PBX schema](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server che connette il portale PSTN/IP-PBX")</span><span class="sxs-lookup"><span data-stu-id="b139f-111">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="b139f-112">Il diagramma seguente illustra Lync Server 2013 che interconnette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b139f-112">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="b139f-113">**Routing intertrunk tra due IP PBX**</span><span class="sxs-lookup"><span data-stu-id="b139f-113">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="b139f-114">![Lync Server Interconnecting IP-Pax System Diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server Interconnecting IP-Pax System Diagram")</span><span class="sxs-lookup"><span data-stu-id="b139f-114">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

