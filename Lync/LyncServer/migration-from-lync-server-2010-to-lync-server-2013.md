---
title: Migrazione da Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Migrazione da Lync Server 2010 a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Negli argomenti di questa sezione viene illustrata la procedura di migrazione da Lync Server 2010 a Lync Server 2013.

<div>


> [!IMPORTANT]  
> Questo documento descrive i passaggi in genere necessari per completare ogni fase della migrazione. Non affronta tutte le possibili topologie di distribuzione legacy o ogni possibile scenario di migrazione. Di conseguenza, potrebbe non essere necessario eseguire ogni passaggio descritto oppure potrebbe essere necessario eseguire passaggi aggiuntivi, a seconda della distribuzione. Questo documento offre anche esempi di passaggi di verifica. Questi passaggi di verifica vengono forniti per aiutarti a capire cosa è necessario cercare per verificare che ogni fase venga completata correttamente durante la migrazione. Adattare questi passaggi di verifica al processo di migrazione specifico.



</div>

Questa guida fornisce informazioni specifiche per l'aggiornamento della distribuzione esistente. Non spiega come cambiare la topologia esistente. Questa guida non riguarda l'implementazione delle nuove caratteristiche. Quando una procedura dettagliata è documentata in un'altra posizione, questa guida indica la sezione documento o documento appropriata.

Questo documento definisce i termini specificati nell'elenco seguente.

  - *migrazione*  
    Spostamento della distribuzione della produzione da una versione precedente di Lync Server 2010 a Lync Server 2013.

<!-- end list -->

  - *aggiornamento*  
    Installazione di una versione più recente del software in un server o un computer client.

<!-- end list -->

  - *coesistenza*  
    Ambiente temporaneo che esiste durante la migrazione quando alcune funzionalità sono state migrate in Lync Server 2013 e altre funzionalità restano ancora in una versione precedente di Lync Server 2010.

<!-- end list -->

  - *interoperabilità*  
    La capacità della distribuzione di funzionare correttamente durante il periodo di coesistenza.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Operazioni preliminari alla migrazione](before-you-begin-the-migration.md)

  - [Fase 1: pianificare la migrazione da Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Fase 2: preparare la migrazione](phase-2-prepare-for-migration.md)

  - [Fase 3: distribuire Lync Server 2013 Pilot pool](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Fase 4: trasferire gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Fase 5: aggiungere Lync Server 2013 Edge Server al pool pilota](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Fase 6: passare dalla distribuzione pilota alla produzione](phase-6-move-from-pilot-deployment-into-production.md)

  - [Fase 7: completare le attività successive alla migrazione](phase-7-complete-post-migration-tasks.md)

  - [Fase 8: rimuovere le autorizzazioni dei pool legacy](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

