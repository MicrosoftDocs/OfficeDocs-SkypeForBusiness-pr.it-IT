---
title: 'Lync Server 2013: supporto per la disponibilità elevata e il ripristino di emergenza'
description: 'Lync Server 2013: supporto per la disponibilità elevata e il ripristino di emergenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552792"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="14cf4-103">Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14cf4-103">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14cf4-104">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="14cf4-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="14cf4-105">Lync Server 2013 garantisce una disponibilità elevata per la ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="14cf4-105">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="14cf4-106">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="14cf4-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="14cf4-107">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="14cf4-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="14cf4-108">Per informazioni dettagliate sui ruoli del server, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="14cf4-108">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="14cf4-109">Lync Server 2013 fornisce anche misure di ripristino di emergenza abilitando l'abbinamento del pool.</span><span class="sxs-lookup"><span data-stu-id="14cf4-109">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="14cf4-110">Se si distribuisce questa topologia, vengono designate coppie di pool Front End, in cui ogni pool si trova in un data center distinto e in un'area geografica separata.</span><span class="sxs-lookup"><span data-stu-id="14cf4-110">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="14cf4-111">Se uno dei pool o dei siti diventa inattivo, è possibile reindirizzare gli utenti che vi appartengono all'altro pool della coppia, provocando in questo modo un'interruzione minima del servizio.</span><span class="sxs-lookup"><span data-stu-id="14cf4-111">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="14cf4-112">Lync Server 2013 supporta anche la disponibilità elevata del server back-end.</span><span class="sxs-lookup"><span data-stu-id="14cf4-112">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="14cf4-113">Si tratta di una topologia facoltativa in cui è possibile distribuire due server back-end per un pool Front end e configurare il mirroring sincrono di SQL Server per tutti i database Lync in esecuzione nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="14cf4-113">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="14cf4-114">Per informazioni dettagliate sull'abbinamento dei pool e sul mirroring dei server back-end, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="14cf4-114">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="14cf4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14cf4-115">See Also</span></span>


[<span data-ttu-id="14cf4-116">Ruoli del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14cf4-116">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="14cf4-117">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14cf4-117">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

