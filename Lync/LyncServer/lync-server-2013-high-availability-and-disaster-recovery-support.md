---
title: 'Lync Server 2013: supporto per la disponibilità elevata e il ripristino di emergenza'
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
ms.openlocfilehash: f8c526f83929fafe9e61078b3ddb55fa9cc9d5f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a>Supporto per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-25_

Lync Server 2013 garantisce una disponibilità elevata per la ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director. Per informazioni dettagliate sui ruoli del server, vedere [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).

Lync Server 2013 fornisce anche misure di ripristino di emergenza abilitando l'abbinamento del pool. Se si distribuisce questa topologia, vengono designate coppie di pool Front End, in cui ogni pool si trova in un data center distinto e in un'area geografica separata. Se uno dei pool o dei siti diventa inattivo, è possibile reindirizzare gli utenti che vi appartengono all'altro pool della coppia, provocando in questo modo un'interruzione minima del servizio.

Lync Server 2013 supporta anche la disponibilità elevata del server back-end. Si tratta di una topologia facoltativa in cui è possibile distribuire due server back-end per un pool Front end e configurare il mirroring sincrono di SQL Server per tutti i database Lync in esecuzione nei server back-end.

Per informazioni dettagliate sull'abbinamento dei pool e sul mirroring dei server back-end, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

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

