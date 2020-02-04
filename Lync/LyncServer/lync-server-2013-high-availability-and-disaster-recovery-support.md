---
title: 'Lync Server 2013: Supporto per la disponibilità elevata e il ripristino di emergenza'
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
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

Lync Server 2013 offre una disponibilità elevata tramite la ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server. Questo vale per i server front-end, Edge Server, Mediation Server e direttori. Per informazioni dettagliate sui ruoli del server, vedere [ruoli del server in Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 offre anche misure per il ripristino di emergenza abilitando l'associazione del pool. Se si distribuisce questa topologia, verranno designate coppie di pool Front-End, con ogni pool in una coppia che si trova in un centro dati separato e in un'area geografica separata. Se si abbassa un pool o un sito, è possibile reindirizzare gli utenti di tale pool a usare l'altro pool nella coppia, con l'interruzione minima del servizio.

Lync Server 2013 supporta inoltre l'elevata disponibilità del server back-end. Si tratta di una topologia facoltativa in cui si distribuiscono due server back-end per un pool Front-end e si configura il mirroring sincrono di SQL Server per tutti i database Lync in uso nei server back-end.

Per informazioni dettagliate sull'associazione del pool e il mirroring del server back-end, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

<div>

## <a name="see-also"></a>Vedere anche


[Ruoli del server in Lync Server 2013](lync-server-2013-server-roles.md)  
[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

