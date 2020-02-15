---
title: Lync Server 2013 tempo di ripristino per il failover del pool e il failback del pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tempo di ripristino per il failover del pool e il failback del pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-10_

Per il failover e il failback dei pool, l'obiettivo tecnico relativo al tempo di ripristino è di 30 minuti. Si tratta del tempo necessario per l'esecuzione del failover dopo che gli amministratori hanno determinano l'esistenza di un'emergenza e hanno avviato le procedure di failover. Non include il tempo necessario agli amministratori per valutare la situazione e prendere decisioni né quello impiegato dagli utenti per ripetere l'accesso dopo il completamento del failover.

Per il failover e il failback del pool, l'obiettivo tecnico relativo al punto di ripristino è pari a 30 minuti. Questo valore rappresenta la misura temporale dei dati che potrebbero essere persi a causa dell'emergenza, in virtù della latenza della replica del servizio di backup. Ad esempio, se un pool scende alle 10:00 A.M. e il RPO è di 30 minuti, i dati vengono scritti nel pool tra 9:30 A.M. e 10:00 potrebbe non essere stato replicato nel pool di backup e verrebbe perso.

Tutti i numeri degli obiettivi relativi al tempo e al punto di ripristino riportati in questo documento presuppongono che i due data center si trovino nella medesima area geografica con trasporto ad alta velocità e bassa latenza tra i siti. Questi numeri sono misurati per un pool con 40.000 utenti attivi contemporaneamente e 200.000 utenti abilitati per Lync rispetto a un modello utente predefinito in cui non è presente alcun backlog nella replica dei dati. Le cifre sono soggette a modifiche a seconda dei test e della convalida delle prestazioni.

</div>

<span> </span>

</div>

</div>

</div>

