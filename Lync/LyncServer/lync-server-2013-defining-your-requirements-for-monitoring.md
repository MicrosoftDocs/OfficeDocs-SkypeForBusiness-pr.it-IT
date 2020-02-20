---
title: 'Lync Server 2013: definizione dei requisiti per il monitoraggio'
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
ms.openlocfilehash: c1e2464eef960f91ecd8e7d8fc8fb71da7ab3a73
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definizione dei requisiti per il monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

L'ottimizzazione della distribuzione e dell'installazione del monitoraggio in Microsoft Lync Server 2013 ha inoltre semplificato i processi coinvolti nella definizione dei requisiti dell'organizzazione per il monitoraggio. Tuttavia, esistono ancora alcuni problemi principali che devono essere risolti prima di iniziare a installare e configurare Lync Server 2013:

**Che tipo di dati si desidera monitorare?** Lync Server 2013 consente di monitorare due diversi tipi di dati, ovvero dati di registrazione dettagli chiamata (CDR) e dati QoE (Quality of Experience). La registrazione dettagli chiamata consente di monitorare l'utilizzo delle funzionalità di Lync Server, ad esempio le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Queste informazioni consentono di sapere quali funzionalità di Lync Server vengono utilizzate (e quali non sono) e fornisce anche informazioni su quando vengono utilizzate queste funzionalità. La qualità dei dati di utilizzo consente di mantenere una registrazione della qualità delle chiamate audio e video eseguite nell'organizzazione, inclusi il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "jitter" (differenze nel ritardo dei pacchetti).

Se si sceglie di abilitare il monitoraggio in Lync Server 2013, è possibile abilitare sia il monitoraggio del CDR che il monitoraggio QoE oppure è possibile scegliere di abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Si supponga, ad esempio, che gli utenti utilizzino solo la messaggistica istantanea e i trasferimenti di file e non effettuino chiamate audio o video. In tal caso, è possibile che venga attivato il monitoraggio QoE. Analogamente, Lync Server facilita l'abilitazione e la disabilitazione del monitoraggio dopo la distribuzione del monitoraggio. Ad esempio, è possibile scegliere di distribuire il monitoraggio ma lasciare inizialmente il monitoraggio QoE disabilitato. Se gli utenti iniziano a riscontrare problemi con le chiamate audio o video, è possibile abilitare il monitoraggio QoE e utilizzare tali dati per risolvere i problemi e risolverli.

Non vi sono vantaggi particolari (o svantaggi) per l'installazione del monitoraggio contemporaneamente all'installazione di Lync Server e all'installazione del monitoraggio dopo l'installazione di Lync Server. Il punto da tenere in considerazione consiste nel fatto che, prima di installare il monitoraggio, è necessario selezionare un computer per ospitare l'archivio di monitoraggio di back-end e una versione supportata di SQL Server deve essere installata e configurata in tale computer prima che il computer possa essere utilizzato per il monitoraggio . Se SQL Server è stato già installato in un computer e il computer è pronto per l'uso, è possibile installare il monitoraggio nello stesso momento in cui si installa Lync Server. Se non si dispone di un computer back-end pronto, è possibile procedere con l'installazione di Lync Server da solo, quindi installare il monitoraggio ogni volta che il computer back-end è pronto per l'uso.

**Quando si desidera installare il monitoraggio?** È possibile installare e configurare il monitoraggio nello stesso momento in cui si installa e si configura Lync Server 2013; la distribuzione guidata di Lync Server offrirà la possibilità di associare i pool Front end a un database di monitoraggio durante l'installazione. In alternativa, è possibile installare il monitoraggio dopo l'installazione di Lync Server stesso. a tale scopo, è possibile utilizzare il generatore di topologie per associare i pool Front end e i server a un database di monitoraggio e quindi pubblicare la topologia riveduta.

**Quanti database di monitoraggio back-end sono necessari?** Un singolo database di monitoraggio può supportare decine di migliaia di utenti (per Microsoft Lync Server 2010, è stato valutato che un database collocato per il monitoraggio e l'archiviazione potrebbe supportare gli utenti di 240.000). Inoltre, un singolo database di monitoraggio può essere utilizzato da più pool Front end. Se nell'organizzazione sono presenti tre pool Front End, è possibile associare tutti e tre i pool allo stesso archivio back-end.

Ciò significa semplicemente che, per molte organizzazioni, la capacità del database non sarà il fattore decisivo quando si determina il numero di database di monitoraggio back-end necessari. Invece, una considerazione più importante potrebbe essere la velocità della rete. Si supponga di disporre di tre pool Front End, ma uno di questi pool si trova in una connessione di rete lenta. In tal caso, è possibile utilizzare due database di monitoraggio: un database per il servizio dei due pool con la connessione di rete valida e un database separato per il servizio del pool con la connessione di rete più lenta.

Quando si pianifica l'infrastruttura di monitoraggio, è necessario tenere in considerazione anche che Lync Server 2013 supporta l'utilizzo dei database mirror. "Mirroring del database" consente di gestire contemporaneamente due copie di un database, con ogni database che risiede in un server diverso. Ogni volta che i dati vengono scritti in un database primario, anche gli stessi dati vengono scritti nel database mirror. Se il database primario deve avere esito negativo o altrimenti diventare non disponibile, è possibile eseguire il failover del database mirror utilizzando un semplice comando di PowerShell per Lync Server. Ad esempio:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

Questo è importante per la pianificazione, semplicemente perché il mirroring richiederà di raddoppiare il numero di database necessari: in aggiunta a ogni database primario, sarà necessario un secondo database per fungere da mirror.

**I siti di Lync Server devono disporre di configurazioni di monitoraggio personalizzate?** Quando si installa Lync Server 2013, vengono installate anche raccolte globali di impostazioni di configurazione di CDR e QoE. Queste raccolte globali offrono la possibilità di applicare le stesse impostazioni CDR e QoE all'intera organizzazione. In molti casi, questo sarà sufficiente: spesso, ad esempio, si vorrà dire che il monitoraggio CDR è abilitato per tutti gli utenti.

Tuttavia, è possibile che si verifichino anche momenti in cui si desidera applicare impostazioni diverse a siti diversi. Ad esempio, se si desidera utilizzare il monitoraggio CDR e QoE nel sito Redmond, è possibile utilizzare solo il monitoraggio di registrazione dettagli chiamata nel sito di Dublino. Analogamente, potrebbe essere necessario mantenere i dati di monitoraggio per 60 giorni nel sito Redmond, ma è sufficiente mantenere questo tipo di dati per 30 giorni nel sito di Dublino. Lync Server 2013 consente di creare raccolte separate di impostazioni di configurazione CDR e QoE nell'ambito del sito. che consente di gestire ogni sito in modo diverso. Questo include sia l'abilitazione e la disabilitazione del monitoraggio, sia la configurazione delle impostazioni di gestione, ad esempio la durata di conservazione dei dati.

Tenere presente che è possibile prendere questa decisione prima di distribuire il monitoraggio o dopo aver distribuito il monitoraggio. Ad esempio, è possibile distribuire il monitoraggio e quindi gestire l'intera organizzazione utilizzando le impostazioni globali. Se in seguito si cambia idea, è possibile creare una raccolta distinta di impostazioni per, ad esempio, il sito Redmond e quindi utilizzare tali impostazioni per gestire il monitoraggio di Redmond. (Le impostazioni applicate nell'ambito del sito hanno sempre la precedenza sulle impostazioni applicate nell'ambito globale). Se si cambia idea, è possibile semplicemente eliminare le impostazioni di configurazione applicate al sito Redmond. Quando viene rimossa una raccolta di impostazioni del sito, la raccolta globale di impostazioni verrà applicata automaticamente a tale sito.

</div>

<span> </span>

</div>

</div>

</div>

