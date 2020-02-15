---
title: Topologia di riferimento per Lync Server 2013 per organizzazioni di grandi dimensioni con più data center
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
ms.openlocfilehash: 3a0be5b144b7476ecdca2a2cf3c4694a81910092
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>Topologia di riferimento per Lync Server 2013 in organizzazioni di grandi dimensioni con più data center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

La topologia di riferimento per un'organizzazione di grandi dimensioni con il supporto di più Data Center è per tutte le dimensioni dell'organizzazione con più di un sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di 50.000 utenti, con 20.000 utenti nel sito centrale A, 20.000 nel sito centrale B. e un totale di 10.000 nel sito centrale C e nei siti di succursale. Il tipo di topologia illustrato in questo diagramma è in grado di ospitare organizzazioni con qualsiasi numero di utenti.

Oltre alla disponibilità elevata fornita dai pool di front end server, questa topologia aggiunge il supporto per il ripristino di emergenza. I pool Front end nei siti centrali A e B sono abbinati tra loro. Se uno di questi pool si sposta verso il basso, l'amministratore può spostare i servizi per gli utenti coinvolti nel pool associato nel sito inalterato.

Questa topologia è illustrata in più diagrammi, con una panoramica prima seguita da visualizzazioni dettagliate dei siti centrali.

**Panoramica della topologia di riferimento per organizzazioni di grandi dimensioni con più data center**

![Topologia di riferimento per più data center](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "Topologia di riferimento per più data center")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale A**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale B**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**Topologia di riferimento per le organizzazioni di grandi dimensioni: visualizzazione dettagliata del sito centrale C**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **I pool Front End sono associati per abilitare il ripristino di emergenza.**    I pool Front end del sito a e del sito B sono abbinati tra loro, per fornire il supporto per il ripristino di emergenza. Se il pool di un sito ha esito negativo, l'amministratore può eseguire il failover degli utenti da tale sito al pool Front end associato nell'altro sito, con un minimo di interruzioni del servizio per gli utenti. Ognuno di questi due pool Front end dispone di sei server, che sono sufficienti per tutti gli utenti di 40.000 in entrambi i pool in caso di failover. Per ulteriori informazioni, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **I server back**   -end sono rispecchiati per garantire una disponibilità elevata per le funzionalità utente di base, nell'organizzazione è stata distribuita una coppia di server back-end per ogni pool Front end. Si tratta di una topologia facoltativa ed è possibile scegliere di distribuire un singolo server back-end.

  - **Utilizzo del server Standard Edition in un sito di succursale.**    Questa organizzazione considera il sito C come un sito di succursale perché ha solo 600 dipendenti. Tuttavia, gli utenti hanno molte conferenze A/V tra di loro. Se è stato distribuito in Lync Server come sito di succursale, il supporto per queste conferenze verrebbe eseguito attraverso la rete WAN (Wide Area Network) da e verso un sito centrale in cui è stato distribuito un server front-end. Per evitare questo carico di larghezza di banda potenziale, sono state installate una coppia di server Standard Edition in questo sito, che ospiterà queste conferenze. Poiché i server Standard Edition sono installati in questa posizione, Lync Server per definizione lo considera un sito centrale e viene trattato come tale in Generatore di topologie e nello strumento di pianificazione.
    
    Solo un server Standard Edition sarebbe sufficiente per le prestazioni, ma l'organizzazione ha distribuito due e abbinato insieme per garantire una disponibilità elevata nel caso in cui un server venisse abbassato.
    
    Anche se il sito C è considerato un sito centrale, non è necessario distribuire i server perimetrali. In questo esempio, il sito C utilizzerà i server perimetrali distribuiti nel sito A.

  - **Monitoraggio e archiviazione**   questa organizzazione ha implementato sia il monitoraggio che l'archiviazione. Quando si distribuisce il monitoraggio o l'archiviazione, viene eseguito in tutti i Front End Server. I database per queste funzionalità possono essere collocati con il database back-end o in un server separato. Questa organizzazione ha individuato i database in un server separato dai server back-end, nel sito centrale B. I database qui ricevono il monitoraggio e l'archiviazione dei dati dai Front End Server in tutti i siti.

  - **Opzioni di distribuzione di siti di succursale.**    Questa organizzazione ha in realtà oltre 50 siti di succursale, solo tre dei quali sono mostrati nei diagrammi dettagliati. I siti di succursale 1 e 3 non dispongono di un collegamento WAN resiliente al sito centrale, quindi dispongono di Survivable Branch Appliance distribuite per fornire servizi di telefonia nel caso in cui il collegamento WAN al sito centrale venga premuto. Il sito di succursale 2 ha tuttavia un collegamento WAN resiliente, quindi è necessario solo un gateway PSTN (Public Switched Telephone Network). Il gateway PSTN distribuito supporta il bypass multimediale, quindi non è necessario alcun Mediation Server nel sito di succursale B. Per informazioni dettagliate sulla scelta delle operazioni da installare in un sito di succursale, vedere [Planning for Enterprise Voice resilienzy in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) nella documentazione relativa alla pianificazione.

  - **Trunking SIP e Mediation Server.**    Si noti che nel sito centrale B, Mediation Server non è collocato con i Front End Server. Questo perché Mediation Server autonomo è consigliato per i siti che utilizzano il trunking SIP. Nella maggior parte delle altre istanze, si consiglia di collocare Mediation Server con Front End Server. Per informazioni dettagliate sulle topologie di Mediation Server, vedere [componenti e topologie per Mediation Server in Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) nella documentazione relativa alla pianificazione.

  - **La chat persistente viene distribuita.**    In questa organizzazione sono stati distribuiti i server necessari per abilitare la chat persistente. Sono stati distribuiti più front end server di chat persistente per gestire il carico per il numero di utenti nel pool e per garantire una disponibilità elevata. Ha inoltre implementato la conformità per la chat persistente e ha individuato l'archivio di chat persistente e l'archivio di conformità di Persistent Chat su server distinti. Tali archivi potevano essere collocati e possono anche essere collocati con il server back-end, ma questa organizzazione ha scelto di separarli per garantire prestazioni migliori.

  - **Bilanciamento del carico DNS.**    Pool Front end e pool di server perimetrali,. In questo modo viene eliminata la necessità di disporre di dispositivi di bilanciamento del carico hardware per l'interfaccia interna dei server perimetrali e diminuisce significativamente la quantità di tempo necessario per l'installazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, in quanto il carico hardware Gli equilibristi sono necessari solo per il traffico HTTP. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

  - **Distribuzione della messaggistica unificata di Exchange.**   Lync Server è compatibile con le distribuzioni *locali* della messaggistica unificata di Exchange e la messaggistica unificata di Exchange *ospitata* . Nel sito centrale A è incluso un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Lync Server. La funzionalità di messaggistica unificata di Exchange per Lync Server viene eseguita nel pool Front end.
    
    Il sito centrale B utilizza Exchange ospitato, quindi anche la funzionalità del server Messaggistica unificata di Exchange è ospitata.
    
    Per informazioni dettagliate sulla messaggistica UNIFICAta di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server Office Web Apps.**   È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. È possibile distribuire una singola farm di server Office Web Apps in un sito che utilizza il traffico proveniente da tutti i siti oppure distribuirlo in ogni sito. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **È possibile aggiungere i Director.**   Se l'organizzazione ha voluto aumentare la sicurezza contro gli attacchi Denial of Service, potrebbe anche distribuire un pool di Director. Un Director è un ruolo del server facoltativo separato in Lync Server che non ospita account utente o che fornisce servizi di conferenza o presenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue la preautenticazione delle richieste in ingresso e le reindirizza al pool o al server Home dell'utente. La preautenticazione nel server Director consente di eliminare le richieste provenienti da account utente sconosciuti alla distribuzione. Un amministratore consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director.

  - **System Center Operations Manager è distribuito.**   Si consiglia di monitorare l'integrità della distribuzione di Lync Server per garantire la disponibilità del servizio per gli utenti finali. È possibile monitorare Lync con System Center Operations Manager Management Pack per Lync che è disponibile come download gratuito da Microsoft. Con Lync Management Pack, è possibile ottenere in modo proattivo gli avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare la funzionalità di Lync end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi relativi alla distribuzione prima che vengano sperimentati dagli utenti finali.
    
    L'organizzazione ha distribuito un server System Center Operations Manager in ogni sito centrale.

</div>

<span> </span>

</div>

</div>

</div>

