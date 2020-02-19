---
title: 'Lync Server 2013: bilanciamento del carico DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d08c56e8b88f13a965f7ab24c8f497e01f10400
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Bilanciamento del carico DNS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-15_

Lync Server consente il bilanciamento del carico DNS, una soluzione software che può ridurre notevolmente il sovraccarico di amministrazione per il bilanciamento del carico sulla rete. Il bilanciamento del carico DNS bilancia il traffico di rete univoco per Lync Server, ad esempio il traffico SIP e il traffico multimediale.

Se si distribuisce il bilanciamento del carico DNS, il sovraccarico di amministrazione dell'organizzazione per i dispositivi di bilanciamento del carico hardware verrà ridotto a icona. È inoltre possibile eliminare la complessità legata alla risoluzione dei problemi relativi a una configurazione errata dei servizi di bilanciamento del carico per il traffico SIP. È anche possibile impedire le connessioni al server, per poter disconnettere i server. Il bilanciamento del carico DNS garantisce infine che i problemi dei servizi di bilanciamento del carico hardware non influiscano su elementi del traffico SIP, ad esempio il routing delle chiamate di base.

Se si utilizza il bilanciamento del carico DNS, è anche possibile acquistare servizi di bilanciamento del carico hardware a un costo più conveniente rispetto a quello da sostenere se si utilizzano servizi di bilanciamento del carico hardware per tutti i tipi di traffico. È consigliabile utilizzare i bilanciamento del carico che hanno superato i test di qualificazione per l'interoperabilità con Lync Server. Per informazioni dettagliate sul test di interoperabilità del bilanciamento del carico, vedere "Lync Server 2010 Load Balancer Partners" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).

Il bilanciamento del carico DNS è supportato per i pool Front End, i pool di server perimetrali, i pool di server Director e i pool di Mediation Server autonomi.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bilanciamento del carico DNS in pool Front End e pool di server Director

È possibile utilizzare il bilanciamento del carico DNS per il traffico SIP in pool Front End e pool di server Director. Dopo aver distribuito il bilanciamento del carico DNS, è comunque necessario utilizzare anche servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server. Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client nelle porte 443 e 80.

Sebbene siano comunque necessari servizi di bilanciamento del carico hardware per questi pool, la loro impostazione e l'amministrazione saranno principalmente relative al traffico HTTPS a cui gli amministratori dei servizi di bilanciamento del carico hardware sono abituati.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Bilanciamento del carico DNS e supporto di server e client precedenti

Il bilanciamento del carico DNS supporta il failover automatico solo per i server che eseguono Lync Server 2013 o Lync Server 2010 e per i client Lync 2013 e Lync 2010. Le versioni precedenti dei client e Office Communications Server possono ancora connettersi ai pool che eseguono il bilanciamento del carico DNS, ma se non possono stabilire una connessione con il primo server a cui si riferisce il bilanciamento del carico DNS, non sono in grado di eseguire il failover su un altro server del pool. .

Inoltre, se si utilizza la messaggistica unificata di Exchange, è necessario utilizzare almeno Exchange 2010 SP1 per ottenere supporto per il bilanciamento del carico DNS di Lync Server. Se si utilizza una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:

  - Riproduzione della segreteria telefonica VoIP aziendale nel telefono

  - Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange

Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director

Per la distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director è necessario eseguire due passaggi aggiuntivi relativi a FQDN e record DNS.

  - Un pool che utilizza il bilanciamento del carico DNS deve disporre di due nomi di dominio completi (FQDN): il nome di dominio completo del pool standard, che viene utilizzato dal bilanciamento del carico DNS (ad esempio pool01.contoso.com) e che viene risolto negli indirizzi IP fisici dei server del pool e un altro nome di dominio completo per i servizi Web del pool (ad esempio web01.contoso.com), che viene risolto nell'indirizzo IP virtuale del pool.
    
    In Generatore di topologie, se si desidera distribuire il bilanciamento del carico DNS per un pool, per creare questo FQDN supplementare per i servizi Web del pool è necessario selezionare la casella di controllo **Sostituisci FQDN pool di servizi Web interni** e digitare il nome di dominio completo, nella pagina **specificare gli URL dei servizi Web per il pool** .

  - Per supportare il nome di dominio completo utilizzato dal bilanciamento del carico DNS, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio pool01.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via). Includere solo gli indirizzi IP dei server attualmente distribuiti.
    
    <div>
    

    > [!WARNING]  
    > Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server. Se si sta distribuendo anche Director, l'FQDN dei servizi Web esterni definiti per qualsiasi server Director o di server Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front end o front-end. Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Bilanciamento del carico DNS in pool di server perimetrali

È possibile distribuire il bilanciamento del carico DNS in pool di server perimetrali. In tal caso, è necessario tenere presenti alcune considerazioni.

L'utilizzo del bilanciamento del carico DNS nei server perimetrali comporta una perdita della capacità di failover negli scenari seguenti:

  - Federazione con organizzazioni che eseguono versioni di Office Communications Server rilasciate prima di Lync Server 2010.

  - Scambio di messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblica AOLand\!Yahoo, oltre ai server e ai provider basati su XMPP, come Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk è attualmente l'unico partner XMPP supportato.</P>
    > <LI>
    > <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Questi scenari funzionano a condizione che tutti i server perimetrali nel pool siano in esecuzione, ma se un server perimetrale non è disponibile, tutte le richieste per questi scenari inviate a tale server avranno esito negativo, anziché essere instradate a un altro server perimetrale.

Se si utilizza la messaggistica unificata di Exchange, è necessario utilizzare almeno Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server su Edge. Se si utilizza una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:

  - Riproduzione della segreteria telefonica VoIP aziendale nel telefono

  - Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange

Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.

Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Distribuzione del bilanciamento del carico DNS in pool di server perimetrali

Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di server perimetrali, sono necessarie le voci DNS seguenti:

  - Per il servizio Access Edge, è necessaria una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge, ad esempio sip.contoso.com, nell'indirizzo IP del servizio Access Edge su uno dei server perimetrali del pool.

  - Per il servizio Web Conferencing Edge, è necessaria una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio, webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno dei server perimetrali del pool.

  - Per il servizio audio/video Edge, è necessaria una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio audio/video Edge (ad esempio, av.contoso.com) nell'indirizzo IP del servizio A/V Edge su uno dei server perimetrali nel pool.

Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di server perimetrali, è necessario aggiungere un record A DNS, che consente di risolvere il nome di dominio completo interno del pool di server perimetrali nell'indirizzo IP di ogni server del pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilizzo del bilanciamento del carico DNS in pool di Mediation Server

È possibile utilizzare il bilanciamento del carico DNS in pool di Mediation Server autonomi. Tutto il traffico SIP e multimediale viene bilanciato dal bilanciamento del carico DNS.

Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio, mediationpool1.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocco del traffico verso un server con bilanciamento del carico DNS

Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci degli indirizzi IP dal nome di dominio completo del pool. È necessario rimuovere anche la voce DNS per il computer.

Si noti che per il traffico da server a server, Lync Server 2013 utilizza il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Per bloccare un server dalla ricezione del traffico da server a server, è necessario rimuovere il server dalla topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

