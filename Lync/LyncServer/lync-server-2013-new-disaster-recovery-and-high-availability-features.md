---
title: 'Lync Server 2013: nuove funzionalità di ripristino di emergenza e disponibilità elevata'
description: 'Lync Server 2013: nuove funzionalità di ripristino di emergenza e disponibilità elevata.'
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
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578862"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="a9148-103">Nuove funzionalità di ripristino di emergenza e disponibilità elevata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9148-103">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9148-104">_**Ultimo argomento modificato:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="a9148-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="a9148-105">Come in Lync Server 2010, la combinazione di disponibilità elevata (HA) di Lync Server 2013 si basa sulla ridondanza del server tramite pool.</span><span class="sxs-lookup"><span data-stu-id="a9148-105">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="a9148-106">In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore.</span><span class="sxs-lookup"><span data-stu-id="a9148-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a9148-107">Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.</span><span class="sxs-lookup"><span data-stu-id="a9148-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="a9148-108">Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza, consentendo di associare pool Front end situati in due datacenter.</span><span class="sxs-lookup"><span data-stu-id="a9148-108">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="a9148-109">Se uno dei pool associati viene premuto, un amministratore può eseguire il failover degli utenti da tale pool all'altro pool della coppia per fornire la continuazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="a9148-109">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="a9148-110">Questa funzionalità non richiede una costosa soluzione di rete o hardware, ad esempio le reti di archiviazione o i dischi condivisi.</span><span class="sxs-lookup"><span data-stu-id="a9148-110">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="a9148-111">Lync Server 2013 aggiunge anche la disponibilità elevata del server back-end.</span><span class="sxs-lookup"><span data-stu-id="a9148-111">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="a9148-112">Si tratta di una topologia facoltativa in cui è possibile distribuire due server back-end per un pool Front end e configurare il mirroring SQL sincrono per tutti i database di Lync in esecuzione nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="a9148-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="a9148-113">È possibile scegliere se distribuire un server di controllo per il mirror.</span><span class="sxs-lookup"><span data-stu-id="a9148-113">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a9148-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9148-114">See Also</span></span>


[<span data-ttu-id="a9148-115">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9148-115">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

