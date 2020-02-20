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
ms.openlocfilehash: 751d8cbbb4ab7a10ca468c0156e14a45c065fd25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="ef6c1-102">Nuova funzionalità trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef6c1-102">New trunk feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef6c1-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ef6c1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ef6c1-104">In Microsoft Lync Server 2013, è possibile definire più trunk tra un Mediation Server e un gateway.</span><span class="sxs-lookup"><span data-stu-id="ef6c1-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="ef6c1-105">Microsoft Lync Server 2010 è consentito solo per un singolo trunk tra un Mediation Server e un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ef6c1-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="ef6c1-106">Questa funzionalità offre la flessibilità necessaria per definire ulteriori trunk.</span><span class="sxs-lookup"><span data-stu-id="ef6c1-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="ef6c1-107">Un trunk è un'associazione logica tra un FQDN del Mediation Server e una porta di attesa e un FQDN del gateway PSTN e una porta di attesa.</span><span class="sxs-lookup"><span data-stu-id="ef6c1-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="ef6c1-108">Questa nuova funzionalità consente di semplificare la definizione trunk per la resilienza (in cui è possibile utilizzare più Mediation Server per instradare le chiamate allo stesso gateway PSTN), per l'interoperabilità PBX, in cui è possibile utilizzare più trunk con criteri associati diversi e IP-PBX e Mediation Server e per le configurazioni trunk SIP in cui Mediation Server in siti diversi dispongono di trunk SIP per il vettore a cui fa riferimento lo stesso nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="ef6c1-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ef6c1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef6c1-109">See Also</span></span>


[<span data-ttu-id="ef6c1-110">Nuove funzionalità di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef6c1-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

