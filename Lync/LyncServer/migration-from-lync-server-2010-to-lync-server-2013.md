---
title: Migrazione da Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cab7ac790d08a848cb90a609720c237c4c20062
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migrazione da Lync Server 2010 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Negli argomenti di questa sezione viene illustrato il processo di migrazione da Lync Server 2010 a Lync Server 2013.

<div>


> [!IMPORTANT]  
> Questo documento descrive i passaggi normalmente necessari per eseguire ogni fase della migrazione. Non sono descritti tutti gli scenari di migrazione o tutte le topologie di distribuzione legacy possibili. Per questi motivi, potrebbe non essere necessario eseguire tutti i passaggi descritti oppure potrebbero servirne altri, a seconda della distribuzione. Nel documento sono inoltre disponibili alcuni esempi dei passaggi di verifica, forniti allo scopo di illustrare quali aspetti ed elementi considerare per assicurarsi che ogni fase venga completata correttamente, man mano che si procede nella migrazione. Adattare tali passaggi di verifica allo specifico processo di migrazione.



</div>

Questa guida include informazioni specifiche per l'aggiornamento della distribuzione esistente e non spiega come modificare la topologia esistente. Non viene descritta l'implementazione delle nuove caratteristiche. Se una procedura dettagliata è descritta altrove, in questa guida vengono forniti riferimenti al documento o alla sezione del documento appropriato.

Nel documento vengono utilizzati termini specifici, con le definizioni seguenti.

  - *migrazione*  
    Spostamento della distribuzione di produzione da una versione precedente di Lync Server 2010 a Lync Server 2013.

<!-- end list -->

  - *aggiornamento*  
    Installare una versione più recente del software in un computer server o client.

<!-- end list -->

  - *coesistenza*  
    Ambiente temporaneo esistente durante la migrazione, quando è stata eseguita la migrazione di alcune funzionalità a Lync Server 2013 e altre funzionalità rimangono ancora in una versione precedente di Lync Server 2010.

<!-- end list -->

  - *interoperabilità*  
    Capacità della distribuzione di operare in modo corretto durante il periodo di coesistenza.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Prima di iniziare la migrazione](before-you-begin-the-migration.md)

  - [Fase 1: pianificare la migrazione da Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: preparazione per la migrazione](phase-2-prepare-for-migration.md)

  - [Fase 3: distribuire il pool pilota di Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: aggiungere il server perimetrale di Lync Server 2013 al pool pilota](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

