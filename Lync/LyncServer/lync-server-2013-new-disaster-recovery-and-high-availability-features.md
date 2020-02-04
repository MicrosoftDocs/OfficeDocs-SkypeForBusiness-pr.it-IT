---
title: 'Lync Server 2013: Nuove funzionalità per la disponibilità elevata e il ripristino di emergenza'
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
ms.openlocfilehash: aabac29c5e866c4bfeff8ad79d392578d52ba650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="6fe39-102">Nuove funzionalità per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe39-102">New disaster recovery and high availability features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fe39-103">_**Argomento Ultima modifica:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="6fe39-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="6fe39-104">Come in Lync Server 2010, lo schema di disponibilità elevata per Lync Server 2013 è basato sulla ridondanza del server tramite pooling.</span><span class="sxs-lookup"><span data-stu-id="6fe39-104">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="6fe39-105">Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server.</span><span class="sxs-lookup"><span data-stu-id="6fe39-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="6fe39-106">Questo vale per i server front-end, Edge Server, Mediation Server e direttori.</span><span class="sxs-lookup"><span data-stu-id="6fe39-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="6fe39-107">Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza, consentendo di associare i pool Front-end situati in due centri dati.</span><span class="sxs-lookup"><span data-stu-id="6fe39-107">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="6fe39-108">Se uno dei pool associati si abbassa, un amministratore può eseguire il failover degli utenti da tale pool all'altro pool nella coppia per ottenere la continuazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6fe39-108">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="6fe39-109">Questa funzionalità non richiede costosi soluzioni hardware o di rete, come reti di archiviazione o dischi condivisi.</span><span class="sxs-lookup"><span data-stu-id="6fe39-109">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="6fe39-110">Lync Server 2013 aggiunge anche l'elevata disponibilità di back end server.</span><span class="sxs-lookup"><span data-stu-id="6fe39-110">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="6fe39-111">Si tratta di una topologia facoltativa in cui si distribuiscono due server back-end per un pool Front-end e si configura il mirroring sincrono di SQL per tutti i database di Lync in uso nei server back-end.</span><span class="sxs-lookup"><span data-stu-id="6fe39-111">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="6fe39-112">È possibile scegliere se distribuire un testimone per il mirror.</span><span class="sxs-lookup"><span data-stu-id="6fe39-112">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6fe39-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fe39-113">See Also</span></span>


[<span data-ttu-id="6fe39-114">Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe39-114">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

