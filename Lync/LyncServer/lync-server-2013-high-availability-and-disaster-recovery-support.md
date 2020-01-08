---
title: 'Lync Server 2013: Supporto per la disponibilità elevata e il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="2e7c5-102">Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e7c5-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e7c5-103">_**Argomento Ultima modifica:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="2e7c5-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="2e7c5-104">Lync Server 2013 offre una disponibilità elevata tramite la ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="2e7c5-105">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="2e7c5-106">Questo vale per i server front-end, Edge Server, Mediation Server e direttori.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="2e7c5-107">Per informazioni dettagliate sui ruoli del server, vedere [ruoli del server in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2e7c5-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="2e7c5-108">Lync Server 2013 offre anche misure per il ripristino di emergenza abilitando l'associazione del pool.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="2e7c5-109">Se si distribuisce questa topologia, verranno designate coppie di pool Front-End, con ogni pool in una coppia che si trova in un centro dati separato e in un'area geografica separata.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="2e7c5-110">Se si abbassa un pool o un sito, è possibile reindirizzare gli utenti di tale pool a usare l'altro pool nella coppia, con l'interruzione minima del servizio.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="2e7c5-111">Lync Server 2013 supporta inoltre l'elevata disponibilità del server back-end.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="2e7c5-112">Si tratta di una topologia facoltativa in cui si distribuiscono due server back-end per un pool Front-end e si configura il mirroring sincrono di SQL Server per tutti i database Lync in uso nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="2e7c5-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="2e7c5-113">Per informazioni dettagliate sull'associazione del pool e il mirroring del server back-end, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="2e7c5-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2e7c5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e7c5-114">See Also</span></span>


[<span data-ttu-id="2e7c5-115">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e7c5-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="2e7c5-116">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e7c5-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

