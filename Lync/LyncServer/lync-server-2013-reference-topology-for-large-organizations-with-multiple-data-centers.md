---
title: 'Lync Server 2013: Topologia di riferimento per organizzazioni di grandi dimensioni con più data center'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d9edde5ab097f3244919d6dd2c572b4a1dc112
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologia di riferimento per Lync Server 2013 per organizzazioni di grandi dimensioni con più data center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

La topologia di riferimento per un'organizzazione di grandi dimensioni con il supporto di più centri dati è per tutte le dimensioni dell'organizzazione con più di un sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di utenti di 50.000, con 20.000 utenti nel sito centrale A, 20.000 presso il sito centrale B. e un totale di 10.000 presso il sito centrale C e i siti di succursale. Il tipo di topologia illustrato in questo diagramma può ospitare le organizzazioni con un numero qualsiasi di utenti.

Oltre alla disponibilità elevata fornita dai pool di server front-end, questa topologia aggiunge il supporto per il ripristino di emergenza. I pool Front-end dei siti centrali A e B sono associati tra loro. Se uno di questi pool scende, l'amministratore può spostare i servizi per gli utenti interessati nel pool associato al sito non interessato.

Questa topologia è illustrata in più diagrammi, con una panoramica seguita da visualizzazioni dettagliate dei siti centrali.

**Panoramica della topologia di riferimento per le organizzazioni di grandi dimensioni con più centri dati**

![Topologia di riferimento per più data center](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologia di riferimento per più data center")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **I pool Front-End sono associati per consentire il ripristino di emergenza.**    I pool Front-end del sito a e del sito B sono associati tra loro per consentire il supporto per il ripristino di emergenza. Se il pool di un sito non riesce, l'amministratore può eseguire il failover degli utenti da tale sito al pool Front-end associato dell'altro sito, con un minimo di interruzioni dei servizi per gli utenti. Ognuno di questi due pool Front-end include sei server, che sono sufficienti per tutti gli utenti di 40.000 in entrambi i pool in caso di failover. Per altre informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **I server back**   -end vengono speculati per ottenere una disponibilità più elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia speculare di server back-end per ogni pool Front-end. Si tratta di una topologia facoltativa e si può scegliere di distribuire un singolo server back-end.

  - **Uso di server standard in un sito di succursale.**    Questa organizzazione considera il sito C come sito di succursale perché ha solo 600 dipendenti. Tuttavia, gli utenti hanno molte conferenze A/V tra di loro. Se è stata distribuita in Lync Server come sito di succursale, il supporto per queste conferenze verrebbe eseguito attraverso la rete WAN da un sito centrale con un server front-end distribuito. Per evitare questo potenziale carico di larghezza di banda, hanno installato una coppia di server standard in questo sito, che ospiterà queste conferenze. E dato che i server standard sono installati, Lync Server per definizione lo considera un sito centrale e viene trattato come tale in Generatore di topologie e nello strumento di pianificazione.
    
    Solo un server Standard Edition sarebbe sufficiente per le prestazioni, ma l'organizzazione ha distribuito due e li ha associati per ottenere una disponibilità elevata nel caso in cui un server scendesse.
    
    Anche se il sito C è considerato un sito centrale, non è necessario distribuire i server perimetrali. In questo esempio, il sito C utilizzerà gli Edge Server distribuiti nel sito A.

  - **Il monitoraggio e l'archiviazione di**questa organizzazione ha implementato sia il monitoraggio che l'archiviazione.    Quando si distribuisce il monitoraggio o l'archiviazione, viene eseguito in ogni server front-end. I database per queste funzionalità possono essere collocati nel database di back-end o in un server separato. Questa organizzazione ha individuato questi database in un server separato dai server back-end, nel sito centrale B. I database qui ricevono il monitoraggio e l'archiviazione dei dati dai server front-end in tutti i siti.

  - **Opzioni di distribuzione del sito di succursale.**    Questa organizzazione ha in realtà oltre 50 siti di succursale, solo tre dei quali sono mostrati nei diagrammi dettagliati. I siti di succursale 1 e 3 non hanno un collegamento WAN resiliente al sito centrale, in modo che abbiano gli elettrodomestici Survivable Branch distribuiti per consentire il servizio telefonico nel caso in cui il collegamento WAN al sito centrale vada giù. Il sito della filiale 2 ha tuttavia un collegamento WAN resiliente, quindi è necessario solo un gateway PSTN (Public Switched Telephone Network). Il gateway PSTN distribuito supporta il bypass multimediale, quindi non è necessario alcun Mediation Server nel sito della filiale B. Per informazioni dettagliate sulla scelta della procedura di installazione in un sito di succursale, vedere [pianificazione della resilienza di Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.

  - **Trunking SIP e Mediation Server.**    Si noti che nel sito centrale B, Mediation Server non è collocato con i server front-end. Questo avviene perché Mediation Server autonomo è consigliato per i siti che usano il trunking SIP. Nella maggior parte delle altre istanze ti consigliamo di collocare Mediation Server con Front End Server. Per informazioni dettagliate sulle topologie di Mediation Server, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

  - **La chat persistente viene distribuita.**    Questa organizzazione ha distribuito i server necessari per abilitare la chat persistente. Ha distribuito più server front-end della chat persistente per gestire il carico per il numero di utenti nel pool e per ottenere una disponibilità elevata. Ha inoltre implementato la conformità per la chat persistente e ha individuato l'Archivio Chat persistente e l'archivio conformità della chat persistente in server distinti. Questi archivi potrebbero essere collocati e possono essere collocati anche con il server back-end, ma questa organizzazione ha scelto di separarli per ottenere prestazioni migliori.

  - **Bilanciamento del carico DNS.**    Pool Front-end e pool Edge Server. In questo modo, viene eliminata l'esigenza di usare il bilanciamento del carico hardware per l'interfaccia interna di Edge Server e si riduce significativamente la quantità di tempo necessario per la configurazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, come il caricamento hardware Gli equilibristi sono necessari solo per il traffico HTTP. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

  - **Distribuzione della messaggistica unificata di Exchange.**   Lync Server funziona sia con le distribuzioni *locali* della messaggistica unificata di Exchange che con la messaggistica unificata di Exchange *ospitata* . Il sito centrale A include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Lync Server. La funzionalità di messaggistica unificata di Exchange per Lync Server viene eseguita nel pool Front-end.
    
    Il sito centrale B usa Exchange ospitata, quindi ospita anche la funzionalità del server Messaggistica unificata di Exchange.
    
    Per informazioni dettagliate sulla messaggistica unificata di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server di Office Web Apps.**   È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. È possibile distribuire una singola farm di Office Web Apps in un sito che serve traffico da tutti i siti o distribuirlo in ogni sito. Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web. Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Gli amministratori possono essere aggiunti.**   Se l'organizzazione vuole aumentare la sicurezza dagli attacchi Denial of Service, potrebbe anche distribuire un pool di direttori. Un amministratore è un ruolo del server facoltativo separato in Lync Server che non ospita gli account utente o offre servizi di conferenza o presenza. Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni. Il direttore esegue la pre-autenticazione delle richieste in ingresso e le reindirizza al server o al pool Home dell'utente. La pre-autenticazione presso il Director consente di eliminare le richieste da account utente sconosciuto alla distribuzione. Un amministratore consente di isolare i server front-end da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.

  - **System Center Operations Manager viene distribuito.**   È consigliabile monitorare l'integrità della distribuzione di Lync Server per garantire la disponibilità dei servizi per gli utenti finali. È possibile monitorare Lync con il Management Pack di System Center Operations Manager per Lync disponibile come download gratuito da Microsoft. Con Lync Management Pack è possibile ottenere avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare la funzionalità Lync end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi della distribuzione prima che gli utenti finali li sperimentino.
    
    Questa organizzazione ha distribuito un server System Center Operations Manager in ogni sito centrale.

</div>

<span> </span>

</div>

</div>

</div>

