---
title: 'Lync Server 2013: Topologia di riferimento per le organizzazioni di medie dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41a003bd87e4dc8b85e78946a5ce870f3f6dd045
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologia di riferimento per Lync Server 2013 per le organizzazioni di medie dimensioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

La topologia di riferimento con elevata disponibilità e un singolo centro dati è progettata per un'organizzazione di piccole e medie dimensioni con un sito centrale. La topologia esatta nel diagramma seguente è per un'organizzazione di utenti di 20.000.

**Topologia di riferimento per le organizzazioni medie**

![Topologia di riferimento per la]topologia di riferimento del diagramma centro dati singolo(images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "per il diagramma centro dati")

  - **Accogliere più utenti aggiungendo altri server front-end.**    La topologia esatta in questo diagramma include tre server front-end per consentire il supporto per gli utenti di 20.000. Se si dispone di un singolo sito centrale e di più utenti, è possibile aggiungere semplicemente altri server front-end al pool. Il numero massimo di utenti per pool è 80.000, con dodici server front-end.
    
    Tuttavia, la singola topologia del sito può supportare ancora più utenti aggiungendo un altro pool Front end al sito.

  - **Potrebbe essere aggiunto il ripristino di emergenza.**    Per questa organizzazione, la disponibilità elevata per i servizi di Lync Server è una caratteristica necessaria, ma il ripristino di emergenza non lo è. Il pool di server front-end distribuiti offre una disponibilità elevata.
    
    Se si vuole aggiungere un'abilità di ripristino di emergenza, è possibile valutare la possibilità di creare un altro Data Center e aggiungere un altro pool di front-end e associarlo al pool Front-End nel Data Center corrente. In caso di un disastro che influisce sul pool principale, gli amministratori potrebbero non eseguire il failover degli utenti nel pool di backup.

  - **I server back**   -end vengono speculati per ottenere una disponibilità più elevata per le funzionalità utente di base, l'organizzazione ha distribuito una coppia speculare di server back-end per ogni pool Front-end. Questa è una nuova opzione di topologia per Lync Server 2013 ed è facoltativa. È possibile scegliere di distribuire un singolo server back-end.

  - **Opzioni di database del server di monitoraggio.**    Questa organizzazione ha implementato il monitoraggio per garantire la qualità delle chiamate vocali aziendali e delle conferenze a/V. Il monitoraggio viene distribuito in tutti i server front-end e il database di monitoraggio è collocato con i server back-end. Supportiamo anche le topologie in cui il database di monitoraggio si trova in un server separato.

  - **Disponibilità**    elevata in questa organizzazione di esempio con gli utenti di 20.000, solo un server perimetrale sarebbe sufficiente per le prestazioni. Tuttavia, esiste un pool di due server perimetrali distribuiti per ottenere una disponibilità elevata.

  - **Opzioni di distribuzione del sito di succursale.**    L'organizzazione in questa topologia ha distribuito VoIP aziendale come soluzione vocale. Il sito di succursale 1 non ha un collegamento WAN (Wide Area Network) resiliente al sito centrale, quindi ha un Survivable Branch Appliance distribuito per gestire molte caratteristiche di Lync Server nel caso in cui il collegamento WAN al sito centrale venga abbasso. Il sito della filiale 2 ha tuttavia un collegamento WAN resiliente, quindi è necessario solo un gateway PSTN (Public Switched Telephone Network). Il gateway PSTN distribuito supporta il bypass multimediale, quindi non è necessario alcun Mediation Server nel sito della filiale 2. Per informazioni dettagliate sulla scelta della distribuzione in un sito di succursale, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.

  - **Bilanciamento del carico DNS.**    Il pool di server front-end pool andEdge, con bilanciamento del carico DNS per il traffico SIP distribuito. In questo modo, viene eliminata la necessità di un bilanciamento del carico hardware per gli Edge Server e si riduce significativamente la configurazione e la manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, poiché i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

  - **Distribuzione della messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Lync Server.
    
    Per informazioni dettagliate sulla messaggistica unificata di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server di Office Web Apps.** È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web. Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web. Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **I server perimetrali sono consigliati.**    Anche se la distribuzione di un server perimetrale non è necessaria, è consigliabile per qualsiasi dimensione della distribuzione. Puoi massimizzare l'investimento di Lync Server distribuendo un server perimetrale per garantire il servizio agli utenti al di fuori dei firewall dell'organizzazione. I vantaggi includono i seguenti:
    
      - Gli utenti dell'organizzazione possono usare le funzionalità di Lync Server, se lavorano da casa o sono fuori strada.
    
      - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.
    
      - Se si ha un partner, un fornitore o un'organizzazione di clienti che usa anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione. La distribuzione di Lync Server riconoscerebbe quindi gli utenti di tale organizzazione federata, con una migliore collaborazione.
    
      - Gli utenti possono scambiare messaggi istantanei con utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live, AOL\!, Yahoo e Google Talk. Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
        > <LI>
        > <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
        > <LI>
        > <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>

        
        </div>

  - **Gli amministratori possono essere aggiunti.**    Se l'organizzazione ha voluto aiutare ad aumentare la sicurezza dagli attacchi Denial of Service, potrebbe anche distribuire un pool di direttori. Un amministratore è un ruolo del server facoltativo separato in Lync Server che non ospita gli account utente o offre servizi di conferenza o presenza. Funge da server hop interno successivo a cui un Edge Server instrada il traffico SIP in ingresso destinato ai server interni. Il direttore esegue la pre-autenticazione delle richieste in ingresso e le reindirizza al server o al pool Home dell'utente. La pre-autenticazione presso il Director consente di eliminare le richieste da account utente sconosciuto alla distribuzione. Un amministratore consente di isolare i server front-end da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.

  - **È consigliabile System Center Operations Manager.**   È consigliabile monitorare l'integrità della distribuzione di Lync Server per garantire la disponibilità dei servizi per gli utenti finali. È possibile monitorare Lync con il Management Pack di System Center Operations Manager per Lync disponibile come download gratuito da Microsoft. Con Lync Management Pack è possibile ottenere avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare la funzionalità Lync end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi della distribuzione prima che gli utenti finali li sperimentino.

</div>

<span> </span>

</div>

</div>

</div>

