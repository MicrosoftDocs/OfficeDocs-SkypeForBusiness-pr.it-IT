---
title: 'Lync Server 2013: nuova funzionalità trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 693b228eb0065375bd01cb9eedabed46ec1833a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="d66a9-102">Nuova funzionalità trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d66a9-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d66a9-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d66a9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d66a9-104">In Microsoft Lync Server 2013, è possibile definire più trunk tra un Mediation Server e un gateway.</span><span class="sxs-lookup"><span data-stu-id="d66a9-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="d66a9-105">Microsoft Lync Server 2010 è consentito solo per un singolo trunk tra un Mediation Server e un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d66a9-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="d66a9-106">Questa funzionalità offre la flessibilità necessaria per definire ulteriori trunk.</span><span class="sxs-lookup"><span data-stu-id="d66a9-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="d66a9-107">Un trunk è un'associazione logica tra un FQDN del Mediation Server e una porta di attesa e un FQDN del gateway PSTN e una porta di attesa.</span><span class="sxs-lookup"><span data-stu-id="d66a9-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="d66a9-108">Questa nuova funzionalità consente di semplificare la definizione trunk per la resilienza (in cui è possibile utilizzare più Mediation Server per instradare le chiamate allo stesso gateway PSTN), per l'interoperabilità PBX, in cui è possibile utilizzare più trunk con criteri associati diversi e IP-PBX e Mediation Server e per le configurazioni trunk SIP in cui Mediation Server in siti diversi dispongono di trunk SIP per il vettore a cui fa riferimento lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="d66a9-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d66a9-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d66a9-109">See Also</span></span>


[<span data-ttu-id="d66a9-110">Nuove funzionalità di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d66a9-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

