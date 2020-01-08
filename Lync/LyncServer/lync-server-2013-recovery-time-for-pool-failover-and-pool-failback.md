---
title: 'Lync Server 2013: Tempo di ripristino per il failover e il failback dei pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a746eb96de7b1e22291cf7a147851b313469bed5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Tempo di ripristino per il failover e il failback dei pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-10_

Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 30 minuti. Questo è il tempo necessario per il failover, dopo che gli amministratori hanno determinato che si è verificato un disastro e avviato le procedure di failover. Non include il tempo per gli amministratori di valutare la situazione e prendere una decisione, né include il tempo per cui gli utenti possono accedere di nuovo dopo il completamento del failover.

Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 30 minuti. Rappresenta la misura temporale dei dati che potrebbero essere persi a causa del disastro causato dalla latenza della replica del servizio di backup. Ad esempio, se un pool scende alle 10:00 A.M. e RPO è di 30 minuti, i dati vengono scritti nel pool tra 9:30 A.M. e 10:00. M. potrebbe non essere stato replicato nel pool di backup e andrebbe perduto.

Tutti i numeri di RTO e RPO in questo documento presuppongono che i due centri dati si trovino all'interno della stessa area geografica con il trasporto ad alta velocità e a bassa latenza tra i due siti. Questi numeri vengono misurati per un pool con 40.000 utenti attivi simultaneamente e 200.000 gli utenti abilitati per Lync rispetto a un modello di utente predefinito in cui non è presente alcun backlog nella replica dei dati. Sono soggetti a modifiche in base al test delle prestazioni e alla convalida.

</div>

<span> </span>

</div>

</div>

</div>

