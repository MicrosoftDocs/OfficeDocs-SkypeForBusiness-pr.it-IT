---
title: Migrazione da Office Communications Server 2007 R2 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624891658fb925fbc2522e98f8b216e535d2bf0c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Migrazione da Office Communications Server 2007 R2 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Negli argomenti di questa sezione viene illustrato il processo di migrazione da Office Communications Server 2007 R2 a Lync Server 2013

<div>


> [!IMPORTANT]  
> Questo documento descrive i passaggi normalmente necessari per eseguire ogni fase della migrazione. Non sono descritti tutti gli scenari di migrazione o tutte le topologie di distribuzione legacy possibili. Per questi motivi, potrebbe non essere necessario eseguire tutti i passaggi descritti oppure potrebbero servirne altri, a seconda della distribuzione. Nel documento sono inoltre disponibili alcuni esempi dei passaggi di verifica, forniti allo scopo di illustrare quali aspetti ed elementi considerare per assicurarsi che ogni fase venga completata correttamente, man mano che si procede nella migrazione. Adattare tali passaggi di verifica allo specifico processo di migrazione.



</div>

Questa guida include informazioni specifiche per l'aggiornamento della distribuzione esistente e non spiega come modificare la topologia esistente. Non viene descritta l'implementazione delle nuove caratteristiche. Se una procedura dettagliata è descritta altrove, in questa guida vengono forniti riferimenti al documento o alla sezione del documento appropriato.

Nel documento vengono utilizzati termini specifici, con le definizioni seguenti.

  - *migrazione*  
    Spostamento della distribuzione di produzione da una versione precedente di Office Communications Server 2007 R2 a Lync Server 2013.

<!-- end list -->

  - *aggiornamento*  
    Installare una versione più recente del software in un computer server o client.

<!-- end list -->

  - *coesistenza*  
    Ambiente temporaneo esistente durante la migrazione, quando è stata eseguita la migrazione di alcune funzionalità a Lync Server 2013 e altre funzionalità rimangono ancora in una versione precedente di Office Communications Server 2007 R2.

<!-- end list -->

  - *interoperabilità*  
    Capacità della distribuzione di operare in modo corretto durante il periodo di coesistenza.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Prima di iniziare la migrazione](before-you-begin-the-migration_1.md)

  - [Fasi della migrazione](migration-phases_1.md)

  - [Fase 1: pianificare la migrazione da Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Fase 2: preparazione per la migrazione](phase-2-prepare-for-migration_1.md)

  - [Fase 3: distribuire il pool pilota di Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Fase 4: unire le topologie](phase-4-merge-topologies.md)

  - [Fase 5: configurare il pool pilota](phase-5-configure-the-pilot-pool.md)

  - [Fase 6: spostare gli utenti nel pool pilota](phase-6-move-users-to-the-pilot-pool.md)

  - [Fase 7: aggiungere il server perimetrale di Lync Server 2013 al pool pilota](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 8: passare dalla distribuzione pilota alla produzione](phase-8-move-from-pilot-deployment-into-production.md)

  - [Fase 9: completare le attività successive alla migrazione](phase-9-complete-post-migration-tasks.md)

  - [Fase 10: rimuovere il sito legacy](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

