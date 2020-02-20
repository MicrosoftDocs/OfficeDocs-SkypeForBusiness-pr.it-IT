---
title: Fasi della migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Fasi della migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

In Lync Server 2013, è possibile definire i siti della rete che contengono componenti di Lync Server 2013. Un sito è un insieme di computer connessi tramite una rete ad alta velocità e a bassa latenza, ad esempio una singola rete locale (LAN) o due reti connesse tramite una rete in fibra ottica ad alta velocità.

Un *pool Front End* è un gruppo di Front End Server configurati in modo identico che collaborano per offrire servizi a un gruppo comune di utenti. Un pool garantisce scalabilità e funzionalità di failover per gli utenti. Ogni server in un pool deve eseguire uno o più ruoli del server identici. Un server Standard Edition, disegnato per organizzazioni di piccole dimensioni, definisce anche un pool e viene eseguito su un server singolo. In questo modo è possibile disporre di una funzionalità di Lync Server 2013 per un costo minore, ma non fornisce una vera soluzione a disponibilità elevata.

Nelle fasi seguenti viene descritto il processo di migrazione del pool da Lync Server 2010 a Lync Server 2013. Nel caso di più siti che includono più pool, per ogni singolo pool sarà necessario adottare questo approccio in più fasi.

1.  [Fase 1: pianificare la migrazione da Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: preparazione per la migrazione](phase-2-prepare-for-migration.md)

3.  [Fase 3: distribuire il pool pilota di Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: aggiungere il server perimetrale di Lync Server 2013 al pool pilota](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

