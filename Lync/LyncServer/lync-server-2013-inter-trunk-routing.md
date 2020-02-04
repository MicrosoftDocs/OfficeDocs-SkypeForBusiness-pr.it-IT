---
title: 'Lync Server 2013: routing tra trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="99b82-102">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99b82-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b82-103">_**Argomento Ultima modifica:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="99b82-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="99b82-104">Lync Server 2013 offre la gestione delle sessioni di base tramite il supporto del routing intertrunk.</span><span class="sxs-lookup"><span data-stu-id="99b82-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="99b82-105">Questa nuova funzionalità consente a Lync Server di concedere funzionalità di controllo delle chiamate ai sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="99b82-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="99b82-106">Il routing intertrunk può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="99b82-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="99b82-107">Allo stesso modo, Lync Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra telefoni PBX dai diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99b82-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="99b82-108">Nella figura seguente viene illustrato Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99b82-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="99b82-109">![Diagramma delle connessioni tra Lync Server e gateway PSTN/IP-PBX](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Diagramma delle connessioni tra Lync Server e gateway PSTN/IP-PBX")</span><span class="sxs-lookup"><span data-stu-id="99b82-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="99b82-110">Nella figura seguente viene illustrato Lync Server 2013 che connette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="99b82-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="99b82-111">![Diagramma delle interconnessioni tra Lync Server e sistemi IP-PAX](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramma delle interconnessioni tra Lync Server e sistemi IP-PAX")</span><span class="sxs-lookup"><span data-stu-id="99b82-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

