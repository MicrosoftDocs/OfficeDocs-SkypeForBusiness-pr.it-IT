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
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nuove funzionalità di ripristino di emergenza e disponibilità elevata in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-20_

Come in Lync Server 2010, la combinazione di disponibilità elevata (HA) di Lync Server 2013 si basa sulla ridondanza del server tramite pool. In caso di errore di un server che esegue un determinato ruolo, gli altri server del pool che eseguono lo stesso ruolo sopportano il carico del server in errore. Ciò vale per Front End Server, server perimetrali, Mediation Server e Director.

Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza, consentendo di associare pool Front end situati in due datacenter. Se uno dei pool associati viene premuto, un amministratore può eseguire il failover degli utenti da tale pool all'altro pool della coppia per fornire la continuazione del servizio. Questa funzionalità non richiede una costosa soluzione di rete o hardware, ad esempio le reti di archiviazione o i dischi condivisi.

Lync Server 2013 aggiunge anche la disponibilità elevata del server back-end. Si tratta di una topologia facoltativa in cui è possibile distribuire due server back-end per un pool Front end e configurare il mirroring SQL sincrono per tutti i database di Lync in esecuzione nei server back-end. È possibile scegliere se distribuire un server di controllo per il mirror.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

