---
title: Failover dell'archivio di gestione centrale di Lync Server 2013
description: Failover dell'archivio di gestione centrale di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2960a55d6bdc49e00bf22997bc53946d4770fde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544372"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Failover dell'archivio di gestione centrale in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

L'archivio di gestione centrale contiene i dati di configurazione relativi a server e servizi nella distribuzione di Lync 2013. Fornisce un'archiviazione schematizzato e robusta dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync 2013. Convalida inoltre i dati per garantire la coerenza della configurazione.

Ogni distribuzione di Lync include un archivio di gestione centrale, ospitato dal server back-end di un pool Front end.

Quando si stabilisce una coppia di pool che include il pool che ospita l'archivio di gestione centrale, nel pool di backup è configurato un database dell'archivio di gestione centrale di backup e i servizi dell'archivio di gestione centrale sono installati in entrambi i pool. In qualsiasi momento, uno dei due database dell'archivio di gestione centrale è il master attivo e l'altro è una modalità standby. Il contenuto viene replicato dal servizio di backup dal master attivo in quello in standby.

Durante un failover del pool che include i pool che ospitano l'archivio di gestione centrale, l'amministratore deve eseguire il failover dell'archivio di gestione centrale prima di eseguire il failback del pool Front end.

Dopo aver ripristinato il disastro, non è necessario eseguire il failover dell'archivio di gestione centrale. Dopo il ripristino, l'archivio di gestione centrale nel pool di backup originale può rimanere come master attivo.

Gli obiettivi di progettazione per il failover dell'archivio di gestione centrale sono di 5 minuti per l'obiettivo del tempo di ripristino (RTO) e di 5 minuti per l'obiettivo del punto di ripristino (RPO).

</div>

<span> </span>

</div>

</div>

</div>

