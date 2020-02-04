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
ms.openlocfilehash: dd45daa964b51639c7fe1db3ff10e334e21641f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="93544-102">Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93544-102">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93544-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="93544-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93544-104">In questo argomento si presuppone che siano state configurate le impostazioni globali di bypass multimediale e che siano stati configurati i siti di rete e l'area network per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="93544-104">This topic assumes that you have configured media bypass global settings and that you have configured network region and network sites for media bypass.</span></span>



</div>

<span data-ttu-id="93544-105">Ogni subnet della rete deve essere associata a un sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="93544-105">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="93544-106">Il motivo è che le informazioni sulla subnet vengono usate per determinare il sito di rete in cui si trova un endpoint.</span><span class="sxs-lookup"><span data-stu-id="93544-106">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="93544-107">Quando sono note le posizioni di entrambe le parti di una sessione, il bypass multimediale può determinare dove inviare il supporto per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="93544-107">When the locations of both parties in a session are known, media bypass can determine where to send media for processing.</span></span>

<span data-ttu-id="93544-108">Il bypass multimediale non ha particolari requisiti per l'associazione delle subnet con i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="93544-108">Media bypass does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="93544-109">Per creare un'associazione tra le subnet e i siti di rete della topologia, seguire le procedure descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="93544-109">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

<div>

## <a name="next-steps-create-bandwidth-policy-profiles"></a><span data-ttu-id="93544-110">Passaggi successivi: creare profili dei criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="93544-110">Next Steps: Create Bandwidth Policy Profiles</span></span>

<span data-ttu-id="93544-111">Dopo aver associato le subnet con i siti di rete per il bypass multimediale, è necessario creare uno o più profili dei criteri di larghezza di banda che partizionano le subnet in quelle con una buona connettività e quelle senza, ai fini del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="93544-111">After you associate subnets with network sites for media bypass, you must create one or more bandwidth policy profiles that will partition subnets into those with good connectivity and those without, for the purposes of media bypass.</span></span> <span data-ttu-id="93544-112">Tutte le subnet all'interno di un'area di rete con siti di rete che non dispongono di vincoli di larghezza di banda hanno una buona connettività e, pertanto, tali subnet possono usare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="93544-112">All subnets within a network region with network sites that do not have bandwidth constraints have good connectivity, and, therefore, those subnets can use media bypass.</span></span>

<span data-ttu-id="93544-113">Per le procedure per configurare i profili dei criteri di larghezza di banda, vedere [creare profili dei criteri di larghezza di banda in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="93544-113">For procedures to configure bandwidth policy profiles, see [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

