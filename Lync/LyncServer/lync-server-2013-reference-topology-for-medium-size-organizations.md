---
title: Topologia di riferimento per Lync Server 2013 per le organizzazioni di medie dimensioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c35c0053ac775ae804b6d92cb84c0ef3d77b4208
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a>Topologia di riferimento per Lync Server 2013 in organizzazioni di medie dimensioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

La topologia di riferimento con disponibilità elevata e un solo data center è specifica per un'organizzazione di piccole-medie dimensioni con un unico sito centrale. La topologia esatta nel diagramma seguente è destinata a un'organizzazione di 20.000 utenti.

**Topologia di riferimento per le organizzazioni di medie dimensioni**

![Topologia di riferimento per un singolo diagramma Data Center](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Topologia di riferimento per un singolo diagramma Data Center")

  - **Ospitare più utenti aggiungendo più Front End Server.**    La topologia esatta in questo diagramma ha tre Front End Server per fornire il supporto per gli utenti di 20.000. Se si dispone di un singolo sito centrale e di più utenti, è sufficiente aggiungere più front end server al pool. Il numero massimo di utenti per pool è 80.000, con dodici front end server.
    
    Tuttavia, la topologia del sito singolo può supportare anche altri utenti aggiungendo un altro pool Front end al sito.

  - **È possibile aggiungere il ripristino di emergenza.**    Per questa organizzazione, la disponibilità elevata per i servizi di Lync Server è una funzionalità necessaria, ma il ripristino di emergenza non lo è. Il pool di front end server distribuiti garantisce una disponibilità elevata.
    
    Se si desidera aggiungere un'abilità di ripristino di emergenza, è possibile prendere in considerazione l'impostazione di un altro Data Center e l'aggiunta di un altro pool Front end e l'abbinamento con il pool Front End nel Data Center corrente. Quindi, se si è verificato un errore che influisce sul pool primario, gli amministratori possono eseguire il failover degli utenti nel pool di backup.

  - **I server back**   -end sono rispecchiati per garantire una disponibilità elevata per le funzionalità utente di base, nell'organizzazione è stata distribuita una coppia di server back-end per ogni pool Front end. Questa è una nuova opzione di topologia per Lync Server 2013 ed è facoltativa. È possibile scegliere di distribuire un singolo server back-end.

  - **Opzioni del database di Monitoring Server.**    Questa organizzazione ha implementato il monitoraggio per garantire la qualità delle chiamate vocali e delle conferenze audio/video aziendali. Il monitoraggio viene distribuito in tutti i Front End Server e il database di monitoraggio è collocato con i server back-end. È inoltre supportata la topologia in cui il database di monitoraggio si trova su un server separato.

  -     **Disponibilità elevata del server perimetrale** nell'organizzazione di esempio con 20.000 utenti, solo un server perimetrale sarebbe sufficiente per le prestazioni. Tuttavia, è presente un pool di due server perimetrali distribuiti per garantire la disponibilità elevata.

  - **Opzioni di distribuzione di siti di succursale.**    L'organizzazione in questa topologia ha Enterprise Voice distribuito come soluzione vocale. Il sito di succursale 1 non dispone di un collegamento WAN (Wide Area Network) resiliente al sito centrale, quindi ha un Survivable Branch Appliance distribuito per mantenere molte caratteristiche di Lync Server nel caso in cui il collegamento WAN al sito centrale venga inattivo. Nel Sito di succursale 2 invece è presente un collegamento WAN resiliente e pertanto è necessario solo un gateway PSTN (Public Switched Telephone Network). Poiché il gateway PSTN distribuito supporta il bypass multimediale, non sono necessari Mediation Server nel Sito di succursale 2. Per informazioni dettagliate sulla scelta delle operazioni da distribuire in un sito di succursale, vedere [pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) nella documentazione relativa alla pianificazione.

  - **Bilanciamento del carico DNS.**    Pool di server andEdge del pool Front End, con bilanciamento del carico DNS per il traffico SIP distribuito. In questo modo si evita di dover utilizzare dispositivi di bilanciamento del carico hardware per i server perimetrali, riducendo in modo significativo le attività di configurazione e manutenzione dei dispositivi di bilanciamento del carico hardware per gli altri pool, poiché i dispositivi di bilanciamento del carico hardware sono necessari solo per il traffico HTTP. Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.

  - **Distribuzione di Messaggistica unificata di Exchange.** Questa topologia di riferimento include un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Lync Server.
    
    Per informazioni dettagliate sulla messaggistica UNIFICAta di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.

  - **Server Office Web Apps.** È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web. Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **I server perimetrali sono consigliati.**    Anche se la distribuzione di un server perimetrale non è necessaria, è consigliabile per tutte le dimensioni della distribuzione. È possibile massimizzare l'investimento di Lync Server distribuendo un server perimetrale per fornire il servizio agli utenti attualmente esterni ai firewall dell'organizzazione. Tra i vantaggi derivanti dall'utilizzo di server perimetrali sono inclusi i seguenti:
    
      - Gli utenti dell'organizzazione possono utilizzare le funzionalità di Lync Server, se lavorano da casa o sono in viaggio.
    
      - Gli utenti possono invitare utenti esterni a partecipare alle riunioni.
    
      - Se si dispone di un partner, un fornitore o un'organizzazione del cliente che utilizza anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione. La distribuzione di Lync Server dovrebbe quindi riconoscere gli utenti provenienti da tale organizzazione federata, determinando una maggiore collaborazione.
    
      - Gli utenti possono scambiare messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live,\!AOL, Yahoo e Google Talk. Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
        > <LI>
        > <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
        > <LI>
        > <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>

        
        </div>

  - **È possibile aggiungere i Director.**    Se l'organizzazione ha voluto contribuire a migliorare la sicurezza contro gli attacchi Denial of Service, potrebbe anche distribuire un pool di Director. Un Director è un ruolo del server facoltativo separato in Lync Server che non ospita account utente o che fornisce servizi di conferenza o presenza. Funge da server hop successivo interno a cui un server perimetrale instrada il traffico SIP in ingresso destinato ai server interni. Il Director esegue la preautenticazione delle richieste in ingresso e le reindirizza al pool o al server Home dell'utente. La preautenticazione nel server Director consente di eliminare le richieste provenienti da account utente sconosciuti alla distribuzione. Un amministratore consente di isolare i Front End Server da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete viene inondata di traffico esterno non valido in un attacco di questo tipo, il traffico termina nel server Director.

  - **È consigliabile utilizzare System Center Operations Manager.**   Si consiglia di monitorare l'integrità della distribuzione di Lync Server per garantire la disponibilità del servizio per gli utenti finali. È possibile monitorare Lync con System Center Operations Manager Management Pack per Lync che è disponibile come download gratuito da Microsoft. Con Lync Management Pack, è possibile ottenere in modo proattivo gli avvisi in tempo reale quando si verificano problemi, eseguire transazioni sintetiche per testare la funzionalità di Lync end-to-end, ottenere report per la disponibilità del servizio e così via. Questo consente di rispondere in modo proattivo ai problemi relativi alla distribuzione prima che vengano sperimentati dagli utenti finali.

</div>

<span> </span>

</div>

</div>

</div>

