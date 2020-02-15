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
ms.openlocfilehash: 587b908cbbff1b69f04fa285fd60a18c28992efb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="17c80-102">Routing tra trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17c80-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17c80-103">_**Ultimo argomento modificato:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="17c80-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="17c80-104">Lync Server 2013 fornisce la gestione delle sessioni di base tramite il supporto del routing tra trunk.</span><span class="sxs-lookup"><span data-stu-id="17c80-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="17c80-105">Questa nuova funzionalità consente a Lync Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="17c80-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="17c80-106">Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="17c80-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="17c80-107">Analogamente, Lync Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="17c80-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="17c80-108">Nella figura seguente viene illustrato Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="17c80-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="17c80-109">![Lync Server che connette il diagramma gateway PSTN/IP-PBX](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server che connette il diagramma gateway PSTN/IP-PBX")</span><span class="sxs-lookup"><span data-stu-id="17c80-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="17c80-110">Nella figura seguente viene illustrato Lync Server 2013 che collega due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="17c80-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="17c80-111">![Diagramma dei sistemi IP-PAX per la connessione di Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramma dei sistemi IP-PAX per la connessione di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="17c80-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

