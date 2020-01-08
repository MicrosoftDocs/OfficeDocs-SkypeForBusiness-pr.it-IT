---
title: 'Lync Server 2013: Nuove funzionalità per la disponibilità elevata e il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e93e2265d401c6dca16f5c00c339fbdc893aba0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a>Nuove funzionalità per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-20_

Come in Lync Server 2010, lo schema di disponibilità elevata per Lync Server 2013 è basato sulla ridondanza del server tramite pooling. Se un server che esegue un determinato ruolo del server non riesce, gli altri server nel pool che esegue lo stesso ruolo accettano il carico del server. Questo vale per i server front-end, Edge Server, Mediation Server e direttori.

Lync Server 2013 aggiunge nuove misure per il ripristino di emergenza, consentendo di associare i pool Front-end situati in due centri dati. Se uno dei pool associati si abbassa, un amministratore può eseguire il failover degli utenti da tale pool all'altro pool nella coppia per ottenere la continuazione del servizio. Questa funzionalità non richiede costosi soluzioni hardware o di rete, come reti di archiviazione o dischi condivisi.

Lync Server 2013 aggiunge anche l'elevata disponibilità di back end server. Si tratta di una topologia facoltativa in cui si distribuiscono due server back-end per un pool Front-end e si configura il mirroring sincrono di SQL per tutti i database di Lync in uso nei server back-end. È possibile scegliere se distribuire un testimone per il mirror.

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

