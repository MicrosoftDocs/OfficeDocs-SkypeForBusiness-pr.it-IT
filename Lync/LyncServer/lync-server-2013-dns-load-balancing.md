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
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>Bilanciamento del carico DNS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-15_

Lync Server Abilita il bilanciamento del carico DNS, una soluzione software che consente di ridurre notevolmente il sovraccarico di amministrazione per il bilanciamento del carico nella rete. Il bilanciamento del carico DNS bilancia il traffico di rete univoco per Lync Server, ad esempio il traffico SIP e il traffico multimediale.

Se si distribuisce il bilanciamento del carico DNS, il sovraccarico di amministrazione dell'organizzazione per i dispositivi di bilanciamento del carico hardware verrà ridotto a icona. Inoltre, la risoluzione dei problemi complessi relativi alla configurazione errata dei bilanciatori di carichi per il traffico SIP verrà eliminata. È anche possibile impedire le connessioni del server in modo da poter prendere i server offline. Il bilanciamento del carico DNS garantisce inoltre che i problemi di bilanciamento del carico hardware non influiscono sugli elementi del traffico SIP, ad esempio il routing delle chiamate di base.

Se si usa il bilanciamento del carico DNS, potrebbe essere anche possibile acquistare i dispositivi di bilanciamento del carico hardware a costo inferiore rispetto a quelli usati per tutti i tipi di traffico. È consigliabile usare i bilanciatori di carico che hanno superato i test di qualifica di interoperabilità con Lync Server. Per informazioni dettagliate sui test di interoperabilità del bilanciamento del carico, vedere "partner di bilanciamento del carico [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)di Lync Server 2010".

Il bilanciamento del carico DNS è supportato per i pool Front-End, i pool di Edge Server, i pool di Director e i pool di Mediation Server autonomi.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bilanciamento del carico DNS nei pool di front end e nei pool di Director

È possibile usare il bilanciamento del carico DNS per il traffico SIP nei pool di front end e nei pool di Director. Con il bilanciamento del carico DNS distribuito, è comunque necessario usare anche i dispositivi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server. Il bilanciamento del carico hardware viene usato per il traffico HTTPS dai client sulle porte 443 e 80.

Anche se hai ancora bisogno di bilanciamento del carico hardware per questi pool, la loro configurazione e l'amministrazione saranno principalmente per il traffico HTTPS, a cui sono abituati gli amministratori dei dispositivi di bilanciamento del carico hardware.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Bilanciamento del carico DNS e supporto di client e server meno recenti

Il bilanciamento del carico DNS supporta il failover automatico solo per i server che utilizzano Lync Server 2013 o Lync Server 2010 e per i client Lync 2013 e Lync 2010. Le versioni precedenti di client e Office Communications Server possono comunque connettersi ai pool in cui è in esecuzione il bilanciamento del carico DNS, ma se non riescono a stabilire una connessione al primo server a cui si riferisce il bilanciamento del carico DNS, non riescono a eseguire il failover su un altro server nel pool .

Inoltre, se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2010 SP1 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server. Se si usa una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:

  - Riproduzione della segreteria telefonica aziendale sul telefono

  - Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange

Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Distribuzione del bilanciamento del carico DNS nei pool di front-end e di Director

La distribuzione di bilanciamento del carico DNS nei pool di front end e nei pool di Director richiede di eseguire alcuni passaggi aggiuntivi con FQDN e record DNS.

  - Un pool che usa il bilanciamento del carico DNS deve avere due nomi di dominio completi: il nome di dominio completo del pool normale usato dal bilanciamento del carico DNS, ad esempio pool01.contoso.com, e viene risolto nell'IPs fisico dei server del pool e un altro nome di dominio completo per i servizi Web del pool, ad esempio web01.contoso.com), che viene risolto nell'indirizzo IP virtuale del pool.
    
    In Generatore di topologia, se si vuole distribuire il bilanciamento del carico DNS per un pool, per creare il nome di dominio completo aggiuntivo per i servizi Web del pool, è necessario selezionare la casella di controllo **Sostituisci il nome FQDN del pool di servizi Web interni** e digitare il nome di dominio completo nella pagina **specifica gli URL dei servizi Web per questo pool** .

  - Per supportare il nome di dominio completo usato dal bilanciamento del carico DNS, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio pool01.contoso.com, agli indirizzi IP di tutti i server del pool (ad es. 192.168.1.1, 192.168.1.2 e così via). Dovresti includere solo gli indirizzi IP dei server attualmente distribuiti.
    
    <div>
    

    > [!WARNING]  
    > Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>Bilanciamento del carico DNS nei pool di Edge Server

È possibile distribuire il bilanciamento del carico DNS nei pool di Edge Server. In questo caso, è necessario tenere conto di alcune considerazioni.

L'uso del bilanciamento del carico DNS nei server perimetrali causa una perdita di capacità di failover negli scenari seguenti:

  - Federazione con organizzazioni che utilizzano versioni di Office Communications Server rilasciate prima di Lync Server 2010.

  - Scambio di messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblica AOLand\!Yahoo, oltre a provider e server basati su XMPP, come Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk è attualmente l'unico partner XMPP supportato.</P>
    > <LI>
    > <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P></LI></UL>

    
    </div>

Questi scenari funzionano fintanto che tutti i server perimetrali nel pool sono in esecuzione, ma se un server perimetrale non è disponibile, le richieste di questi scenari che verranno inviate non avranno esito positivo, invece di eseguire il routing a un altro Edge Server.

Se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS di Lync Server sul bordo. Se si usa una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:

  - Riproduzione della segreteria telefonica aziendale sul telefono

  - Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange

Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.

L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Distribuzione del bilanciamento del carico DNS nei pool di Edge Server

Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di Edge Server, sono necessarie le seguenti voci DNS:

  - Per il servizio Access Edge è necessaria una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge, ad esempio sip.contoso.com, all'indirizzo IP del servizio Access Edge in uno degli Edge Server del pool.

  - Per il servizio Web Conferencing Edge è necessario immettere una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno degli Edge Server del pool.

  - Per il servizio Edge audio/video è necessario immettere una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Edge audio/video, ad esempio av.contoso.com, all'indirizzo IP del servizio A/V Edge in uno degli Edge Server del pool.

Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di Edge Server, è necessario aggiungere un record DNS, che risolve il nome di dominio completo interno del pool di Edge Server con l'indirizzo IP di ogni server nel pool.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Uso del bilanciamento del carico DNS nei pool di Mediation Server

È possibile usare il bilanciamento del carico DNS nei pool di Mediation Server autonomi. Tutto il traffico SIP e multimediale è bilanciato dal bilanciamento del carico DNS.

Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio mediationpool1.contoso.com, agli indirizzi IP di tutti i server del pool, ad esempio 192.168.1.1, 192.168.1.2 e così via.

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloccare il traffico a un server con il bilanciamento del carico DNS

Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer.

Tieni presente che per il traffico da server a server, Lync Server 2013 usa il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Per impedire a un server di ricevere il traffico da server a server, è necessario rimuovere il server dalla topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

