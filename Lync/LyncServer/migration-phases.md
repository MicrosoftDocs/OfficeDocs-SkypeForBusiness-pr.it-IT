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
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Fasi della migrazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

In Lync Server 2013 si definiscono i siti della rete che contengono componenti di Lync Server 2013. Un sito è un set di computer ben connessi da una rete a bassa latenza ad alta velocità, ad esempio una rete LAN (Local Area Network) o due reti connesse da una rete a fibre ottiche ad alta velocità.

Un *pool Front-End* è un set di server front-end configurati in modo identico e collaborano per creare servizi per un gruppo di utenti comune. Un pool offre funzionalità di scalabilità e failover per gli utenti. Ogni server in un pool deve eseguire un ruolo o ruoli del server identico. Un server Standard Edition, progettato per le piccole organizzazioni, definisce anche un pool ed è in esecuzione su un singolo server. In questo modo è possibile avere la funzionalità Lync Server 2013 per un costo inferiore, ma non offre una vera soluzione a elevata disponibilità.

Le fasi seguenti descrivono il processo di migrazione del pool da Lync Server 2010 a Lync Server 2013. Per più siti che contengono più pool, ogni singolo pool deve seguire questo approccio graduale.

1.  [Fase 1: pianificare la migrazione da Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)

3.  [Fase 3: distribuire Lync Server 2013 Pilot pool](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Fase 4: trasferire gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Fase 5: aggiungere Lync Server 2013 Edge Server al pool pilota](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)

8.  [Fase 8: rimuovere le autorizzazioni dei pool legacy](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

