---
title: 'Lync Server 2013: nuove funzionalità di ripristino di emergenza e disponibilità elevata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7845f919f04985e67d6825b8722904a9158606b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="44caf-102">Nuove funzionalità di ripristino di emergenza e disponibilità elevata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44caf-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44caf-103">_**Ultimo argomento modificato:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="44caf-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="44caf-104">Come in Lync Server 2010, la combinazione di disponibilità elevata (HA) di Lync Server 2013 si basa sulla ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="44caf-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="44caf-105">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="44caf-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="44caf-106">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="44caf-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="44caf-107">Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza, consentendo di associare pool Front end situati in due datacenter.</span><span class="sxs-lookup"><span data-stu-id="44caf-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="44caf-108">Se uno dei pool associati viene premuto, un amministratore può eseguire il failover degli utenti da tale pool all'altro pool della coppia per fornire la continuazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="44caf-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="44caf-109">Questa funzionalità non richiede una costosa soluzione di rete o hardware, ad esempio le reti di archiviazione o i dischi condivisi.</span><span class="sxs-lookup"><span data-stu-id="44caf-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="44caf-110">Lync Server 2013 aggiunge anche la disponibilità elevata del server back-end.</span><span class="sxs-lookup"><span data-stu-id="44caf-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="44caf-111">Si tratta di una topologia facoltativa in cui è possibile distribuire due server back-end per un pool Front end e configurare il mirroring SQL sincrono per tutti i database di Lync in esecuzione nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="44caf-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="44caf-112">È possibile scegliere se distribuire un server di controllo per il mirror.</span><span class="sxs-lookup"><span data-stu-id="44caf-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="44caf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44caf-113">See Also</span></span>


[<span data-ttu-id="44caf-114">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44caf-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

