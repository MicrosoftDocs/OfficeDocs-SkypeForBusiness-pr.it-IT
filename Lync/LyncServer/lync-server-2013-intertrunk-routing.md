---
title: 'Lync Server 2013: routing tra trunk'
description: 'Lync Server 2013: routing tra trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553142"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="cf3cc-103">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf3cc-103">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf3cc-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="cf3cc-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="cf3cc-105">Lync Server 2013 può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate provenienti da un telefono PBX possano essere instradate alla rete PSTN e che le chiamate PSTN in arrivo possano essere instradate a un telefono PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="cf3cc-105">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="cf3cc-106">Analogamente, Lync Server 2013 può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-106">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="cf3cc-107">Questa funzionalità di routing intertrunk può essere configurata utilizzando il cmdlet di Lync Server Management Shell, **Set-CsTrunkConfiguration**, con il nuovo parametro PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-107">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="cf3cc-108">Questo parametro specifica l'insieme di record di utilizzo PSTN da applicare.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-108">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="cf3cc-109">Un trunk si basa su questo utilizzo PSTN per determinare una route e per instradare tutte le chiamate in arrivo di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-109">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="cf3cc-110">Nel diagramma seguente viene illustrato Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-110">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="cf3cc-111">**Routing tra trunk tra gateway e IP-PBX**</span><span class="sxs-lookup"><span data-stu-id="cf3cc-111">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="cf3cc-112">![Lync Server che connette il diagramma gateway PSTN/IP-PBX](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server che connette il diagramma gateway PSTN/IP-PBX")</span><span class="sxs-lookup"><span data-stu-id="cf3cc-112">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="cf3cc-113">Nel diagramma seguente viene illustrato Lync Server 2013 che interconnette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="cf3cc-113">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="cf3cc-114">**Routing tra trunk tra due sistemi IP-PBX**</span><span class="sxs-lookup"><span data-stu-id="cf3cc-114">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="cf3cc-115">![Diagramma dei sistemi IP-PAX per la connessione di Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramma dei sistemi IP-PAX per la connessione di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="cf3cc-115">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

