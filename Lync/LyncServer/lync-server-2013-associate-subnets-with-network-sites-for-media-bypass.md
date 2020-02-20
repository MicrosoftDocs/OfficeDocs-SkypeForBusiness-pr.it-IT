---
title: 'Lync Server 2013: associare subnet a siti di rete per il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for media bypass
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48184244
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74f007accc53158a1f541dbe4ac6aa821cd8be4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0a8ae-102">Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a8ae-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a8ae-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0a8ae-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a8ae-104">In questo argomento si presuppone che siano state configurate impostazioni globali per la funzionalità Media Bypass e che siano stati configurati l'area di rete e i siti di rete per tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0a8ae-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="0a8ae-p101">Ogni subnet della rete deve essere associata a un sito di rete specifico. Le informazioni della subnet, infatti, vengono utilizzate per determinare il sito di rete in cui si trova un endpoint. Quando sono note le posizioni di entrambe le parti di una sessione, il bypass multimediale consente di determinare dove inviare gli elementi multimediali per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="0a8ae-p101">Every subnet in your network must be associated with a specific network site. This is because subnet information is used to determine the network site on which an endpoint is located. When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="0a8ae-108">Per il bypass multimediale non esistono requisiti speciali per l'associazione di subnet a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="0a8ae-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="0a8ae-109">Per creare un'associazione tra le subnet e i siti di rete nella topologia, seguire le procedure illustrate in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="0a8ae-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="0a8ae-110">Passaggi successivi: creare profili di criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="0a8ae-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="0a8ae-p103">Dopo aver associato le subnet ai siti di rete per il bypass multimediale, è necessario creare uno o più profili di criteri di larghezza di banda per suddividere le subnet tra quelle con connettività di buon livello e quelle senza, ai fini del bypass multimediale. Tutte le subnet in un'area di rete con siti di rete che non hanno limiti di larghezza di banda dispongono di connettività di buon livello e possono pertanto utilizzare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="0a8ae-p103">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass. All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="0a8ae-113">Per le procedure per la configurazione dei profili dei criteri di larghezza di banda, vedere [create Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0a8ae-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

