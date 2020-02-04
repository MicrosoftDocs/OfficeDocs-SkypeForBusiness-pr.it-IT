---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per il monitoraggio"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 102735e7a8149edcb858b30644197553f5392c1e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definizione dei requisiti dell'organizzazione per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

La razionalizzazione della distribuzione e dell'installazione del monitoraggio in Microsoft Lync Server 2013 ha anche semplificato i processi necessari per definire i requisiti dell'organizzazione per il monitoraggio. Tuttavia, sono ancora numerosi i problemi principali che devono essere risolti prima di iniziare l'installazione e la configurazione di Lync Server 2013:

**Quali tipi di dati si desidera monitorare?** Lync Server 2013 consente di monitorare due diversi tipi di dati: i dati di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE). La registrazione dei dettagli delle chiamate consente di tenere traccia dell'uso delle funzionalità di Lync Server, ad esempio chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Queste informazioni consentono di sapere quali funzionalità di Lync Server vengono usate (e quali non sono) e forniscono anche informazioni su quando queste caratteristiche vengono usate. La qualità dei dati sulle esperienze consente di mantenere un record della qualità delle chiamate audio e video effettuate nella propria organizzazione, inclusi elementi come il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto).

Se si sceglie di abilitare il monitoraggio in Lync Server 2013, è possibile abilitare sia il monitoraggio CDR che il controllo QoE oppure si può scegliere di abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Supponiamo ad esempio che gli utenti usino solo la messaggistica istantanea e i trasferimenti di file e non effettuino chiamate audio o video. In questo caso, è possibile che venga attivato il monitoraggio QoE. Allo stesso modo, Lync Server facilita l'attivazione e la disabilitazione del monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, potresti scegliere di distribuire il monitoraggio, ma lasci inizialmente il monitoraggio QoE disabilitato. Se gli utenti iniziano a riscontrare problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e usare questi dati per risolvere i problemi e risolverli.

Non esiste alcun vantaggio particolare (o svantaggio) per installare il monitoraggio contemporaneamente all'installazione di Lync Server e all'installazione del monitoraggio dopo l'installazione di Lync Server. Il punto da tenere presente è che, prima di installare il monitoraggio, è necessario selezionare un computer per ospitare l'archivio di monitoraggio del backend e una versione supportata di SQL Server deve essere installata e configurata nel computer prima di poter usare il computer per il monitoraggio . Se SQL Server è già installato in un computer e il computer è pronto per l'uso, è possibile installare il monitoraggio contemporaneamente all'installazione di Lync Server. Se non si dispone di un computer back-end, è possibile procedere con l'installazione di Lync Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

**Quando si vuole installare il monitoraggio?** Il monitoraggio può essere installato e configurato contemporaneamente all'installazione e alla configurazione di Lync Server 2013; la distribuzione guidata di Lync Server ti offre l'opportunità di associare i pool Front-end a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo l'installazione di Lync Server stesso; Questa operazione può essere eseguita usando generatore di topologie per associare i pool e i server front-end a un database di monitoraggio e quindi pubblicare la topologia riveduta.

**Quanti database di monitoraggio backend sono necessari?** Un singolo database di monitoraggio può supportare decine di migliaia di utenti (per Microsoft Lync Server 2010 è stato valutato che un database collocato per il monitoraggio e l'archiviazione potrebbe supportare gli utenti di 240.000). Inoltre, un singolo database di monitoraggio può essere usato da più pool Front-end. Se sono presenti tre pool di front-end nell'organizzazione, è possibile associare tutti e tre i pool allo stesso archivio backend.

Questo significa semplicemente che, per molte organizzazioni, la capacità del database non sarà il fattore decisivo per determinare il numero di database di monitoraggio backend che saranno necessari. Una considerazione più importante potrebbe invece essere la velocità della rete. Supponiamo di avere tre pool Front-End, ma uno di questi pool si trova in una connessione di rete lenta. In questo caso, potresti voler usare due database di monitoraggio: un database per il servizio dei due pool con la connessione di rete buona e un database separato per il servizio del pool con la connessione di rete più lenta.

Quando si pianifica l'infrastruttura di monitoraggio, tenere presente che Lync Server 2013 supporta l'uso dei database mirror. "Mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede in un server diverso. Ogni volta che i dati vengono scritti in un database primario, anche i dati vengono scritti nel database mirror. Se il database primario deve avere esito negativo o in caso contrario diventa non disponibile, è possibile eseguire il failover del database mirror usando un semplice comando di PowerShell per Lync Server. Ad esempio:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Questo è importante per scopi di pianificazione semplicemente perché il mirroring richiederà di raddoppiare il numero di database necessario: oltre a ogni database principale è necessario un secondo database per fungere da mirror.

**I siti di Lync Server necessitano di configurazioni di monitoraggio personalizzate?** Quando si installa Lync Server 2013 si installano anche raccolte globali di impostazioni di configurazione CDR e QoE; Queste raccolte globali offrono la possibilità di applicare le stesse impostazioni CDR e QoE all'intera organizzazione. In molti casi, questo sarà sufficiente: spesso si vorrà, ad esempio, avere il monitoraggio CDR abilitato per tutti gli utenti.

Tuttavia, potrebbero esserci anche momenti in cui si vogliono applicare impostazioni diverse a siti diversi. Ad esempio, è possibile usare sia il monitoraggio CDR che QoE nel sito Redmond, ma usare solo il monitoraggio CDR nel sito di Dublino. Allo stesso modo, potresti voler mantenere i dati di monitoraggio per 60 giorni nel sito Redmond, ma devi solo mantenere questo tipo di dati per 30 giorni nel sito di Dublino. Lync Server 2013 consente di creare raccolte separate di impostazioni di configurazione CDR e QoE nell'ambito del sito. che consente di gestire ogni sito in modo diverso. (Questo include sia l'abilitazione che la disabilitazione del monitoraggio, nonché la configurazione delle impostazioni di gestione, ad esempio il periodo di conservazione dei dati).

Tieni presente che puoi prendere questa decisione prima di distribuire il monitoraggio o dopo la distribuzione del monitoraggio. Ad esempio, puoi distribuire il monitoraggio e quindi gestire l'intera organizzazione usando le impostazioni globali. Se in seguito si cambia idea, è possibile creare una raccolta distinta di impostazioni per, ad esempio, il sito Redmond e quindi usare queste impostazioni per gestire il monitoraggio di Redmond. Le impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale. Se si cambia idea, è possibile semplicemente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale delle impostazioni verrà applicata automaticamente a tale sito.

</div>

<span> </span>

</div>

</div>

</div>

