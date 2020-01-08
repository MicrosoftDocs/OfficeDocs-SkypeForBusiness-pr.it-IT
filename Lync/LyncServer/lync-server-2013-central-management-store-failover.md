---
title: "Lync Server 2013: Failover dell'archivio di gestione centrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Failover dell'archivio di gestione centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

L'archivio di gestione centrale contiene i dati di configurazione relativi a server e servizi nella distribuzione di Lync 2013. Offre un solido spazio di archiviazione schematizzato dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync 2013. Convalida inoltre i dati per garantire la coerenza della configurazione.

Ogni distribuzione di Lync include un unico Central Management store, ospitato dal server back-end di un pool Front-end.

Quando si stabilisce l'associazione di un pool che include il pool che ospita l'archivio di gestione centrale, nel pool di backup è configurato un database di backup di Central Management store e i servizi di Central Management store sono installati in entrambi i pool. In qualsiasi momento, uno dei due database di Central Management store è lo schema attivo, mentre l'altro è in standby. Il contenuto viene replicato dal servizio di backup da master attivo in standby.

Durante un failover del pool che include i pool che ospitano Central Management store, l'amministratore deve avere esito negativo su Central Management Store prima di non superare il pool Front-end.

Una volta riparato il disastro, non è necessario eseguire il failover dell'Central Management store. Dopo il ripristino, l'archivio di gestione centrale nel pool di backup originale può rimanere come master attivo.

Gli obiettivi di progettazione per il failover di Central Management store sono di 5 minuti per l'obiettivo del tempo di recupero (RTO) e di 5 minuti per l'obiettivo del punto di ripristino (RPO).

</div>

<span> </span>

</div>

</div>

</div>

