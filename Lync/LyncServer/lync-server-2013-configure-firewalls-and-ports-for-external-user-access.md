---
title: "Lync Server 2013: configurare firewall e porte per l'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 514c93cff5d3050ae94d1057b57fb703e92696ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="5393a-102">Configurare firewall e porte per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5393a-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5393a-103">_**Ultimo argomento modificato:** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="5393a-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="5393a-104">Per configurare firewall e porte, è necessario configurarli per i server perimetrali, i server proxy inversi e possibilmente i dispositivi di bilanciamento del carico hardware (per una distribuzione con scalabilità implementata in cui non viene utilizzato il bilanciamento del carico DNS).</span><span class="sxs-lookup"><span data-stu-id="5393a-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="5393a-105">In questa sezione vengono fornite informazioni sui requisiti di firewall e porte per tutti i componenti dei server perimetrali e sulla configurazione delle porte di firewall per i server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="5393a-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="5393a-106">Per informazioni dettagliate sulla configurazione delle porte per i server proxy inversi, vedere [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span><span class="sxs-lookup"><span data-stu-id="5393a-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="5393a-107">Se si distribuisce una topologia con scalabilità orizzontale e si utilizza il bilanciamento del carico hardware anziché il bilanciamento del carico DNS, vedere [scala consolidato Edge con dispositivi di bilanciamento del carico hardware in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) nella documentazione relativa alla pianificazione per informazioni dettagliate sulla configurazione delle porte per i dispositivi di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="5393a-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5393a-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5393a-108">See Also</span></span>


[<span data-ttu-id="5393a-109">Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5393a-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

