---
title: Requisiti per il bilanciamento del carico per Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Riepilogo: rivedere le considerazioni di bilanciamento del carico prima di implementare Skype for Business Server.'
ms.openlocfilehash: 199c93528d89786573bdac16077f1e32feb1fe6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802046"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisiti per il bilanciamento del carico per Skype for Business
 
**Riepilogo:** Esaminare le considerazioni di bilanciamento del carico prima di implementare Skype for Business Server.
  
Il bilanciamento del carico distribuisce il traffico tra i server in un pool. Se si hanno pool Front-End, pool di Mediation Server o pool di Edge Server, è necessario distribuire il bilanciamento del carico per questi pool.
  
Skype for Business Server supporta due tipi di soluzioni di bilanciamento del carico per il traffico tra client e server: bilanciamento del carico DNS (Domain Name System) e bilanciamento del carico hardware (spesso abbreviato in HLB). Il bilanciamento del carico DNS offre diversi vantaggi, tra cui l'amministrazione più semplice, la risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico di Skype for Business Server da qualsiasi potenziale problema di bilanciamento del carico hardware.
  
Decidere autonomamente quale soluzione di bilanciamento del carico è appropriata per ogni pool della distribuzione, ma tieni presente le restrizioni seguenti: 
  
- L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS su un'interfaccia e un bilanciamento del carico hardware dall'altro.
    
- Alcuni tipi di traffico richiedono un bilanciamento del carico hardware. Ad esempio, il traffico HTTP richiede un bilanciamento del carico hardware invece del bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.
    
Se si sceglie di usare il bilanciamento del carico DNS per un pool, ma occorre comunque implementare il bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei dispositivi di bilanciamento del carico hardware è notevolmente semplificata. Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice perché gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS. Per informazioni dettagliate, vedere [bilanciamento del carico DNS](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Per il traffico da server a server, Skype for Business Server usa il bilanciamento del carico che supporta la topologia. I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico. 
  
Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisiti relativi al servizio di bilanciamento del carico hardware

La topologia di Edge consolidato di Skype for Business Server è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni che si federano principalmente con altre organizzazioni che usano Skype for Business Server o Lync Server. Se è necessaria una disponibilità elevata per uno degli scenari seguenti, è necessario usare un bilanciamento del carico hardware nei pool di Edge Server per gli elementi seguenti: 
  
- Federazione con organizzazioni che usano Office Communications Server 2007 R2 o Office Communications Server 2007
    
- Messaggistica unificata di Exchange per utenti remoti con messaggistica unificata di Exchange prima di Exchange 2010 con SP1
    
- Connettività agli utenti di messaggistica istantanea pubblica
    
> [!IMPORTANT]
> L'uso del bilanciamento del carico DNS su un'interfaccia e il bilanciamento del carico hardware dall'altro non è supportato. È necessario usare il bilanciamento del carico hardware per entrambe le interfacce o il bilanciamento del carico DNS per entrambi. 
  
> [!NOTE]
> Se si usa un sistema di bilanciamento del carico hardware, il servizio di bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per il bilanciamento del carico solo del traffico verso i server che esegue Access Edge e il servizio A/V Edge. Non può caricare il bilanciamento del traffico verso il servizio Web Conferencing Edge interno o il servizio proxy XMPP interno. 
  
> [!NOTE]
> Il protocollo DSR (Direct Server Return) NAT non è supportato con Skype for Business Server. 
  
Per determinare se il dispositivo di bilanciamento del carico hardware supporta le funzionalità necessarie per Skype for Business Server, vedere [infrastruttura per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisiti di bilanciamento del carico hardware per i server perimetrali che utilizzano il servizio A/V Edge

Di seguito sono riportati i requisiti di bilanciamento del carico hardware per Edge Server che esegue il servizio A/V Edge:
  
- Disattivare TCP nagling per le porte interne ed esterne 443. Nagling è il processo di combinazione di diversi piccoli pacchetti in un singolo pacchetto più grande per una trasmissione più efficiente.
    
- Disattivare TCP nagling per l'intervallo di porte esterne 50.000-59.999. 
    
- Non usare NAT sul firewall interno o esterno. 
    
- L'interfaccia interna del bordo deve essere in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di essi deve essere disabilitato. 
    
- L'interfaccia esterna dell'Edge Server che usa il servizio A/V Edge deve usare indirizzi IP instradabili pubblicamente e nessuna traduzione NAT o Port in uno degli indirizzi IP esterni di Edge. 
    
- Il bilanciamento del carico non deve modificare l'indirizzo di origine del client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Altri requisiti di bilanciamento del carico hardware

I requisiti di affinità basati su cookie sono notevolmente ridotti in Skype for Business Server for Web Services. Se si sta distribuendo Skype for Business Server e non si conservano i server front end di Lync Server 2010 o i pool Front-End, non è necessaria la persistenza basata su cookie. Se tuttavia si mantengono temporaneamente o definitivamente tutti i server front-end di Lync Server 2010 o i pool Front-End, è comunque possibile usare la persistenza basata su cookie mentre viene distribuita e configurata per Lync Server 2010. 
  
> [!NOTE]
> **Se si decide di usare l'affinità basata su cookie anche se la distribuzione non lo richiede**, non c'è alcun impatto negativo. 
  
Per le distribuzioni che **non useranno** l'affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true. In questo modo verrà inoltrato l'URL originale.
    
Per le distribuzioni **che** utilizzeranno l'affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 4443 impostare **Inoltra intestazione host** su true. In questo modo verrà inoltrato l'URL originale.
    
- Il cookie di bilanciamento del carico hardware non deve essere contrassegnato httpOnly
    
- Il cookie di bilanciamento del carico hardware non deve avere una data di scadenza
    
- Il cookie di bilanciamento del carico hardware deve essere denominato **MS-WSMan** (questo è il valore previsto per i servizi Web e non può essere modificato)
    
- Il cookie di bilanciamento del carico hardware deve essere impostato in tutte le risposte HTTP per cui la richiesta HTTP in arrivo non ha un cookie, indipendentemente dal fatto che una risposta HTTP precedente alla stessa connessione TCP abbia già ottenuto un cookie. Se il bilanciamento del carico ottimizza l'inserimento del cookie per eseguire una sola volta per ogni connessione TCP, non deve essere usata l'ottimizzazione.
    
> [!NOTE]
> Le tipiche configurazioni di bilanciamento del carico hardware usano l'affinità degli indirizzi di origine e la durata di una sessione TCP di 20 minuti, che va bene per i client Lync Server e Lync 2013, perché lo stato della sessione viene gestito tramite l'utilizzo del client e/o l'interazione tra applicazioni. 
  
Se si distribuiscono dispositivi mobili, il dispositivo di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste all'interno di una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).
  
> [!CAUTION]
> Se si distribuiscono dispositivi mobili, il dispositivo di bilanciamento del carico hardware deve essere in grado di caricare individualmente il bilanciamento di ogni richiesta all'interno di una connessione TCP. Le più recenti app per dispositivi mobili Apple iOS richiedono Transport Layer Security (TLS) versione 1,2.  
  
> [!CAUTION]
> Per informazioni dettagliate sui dispositivi di bilanciamento del carico hardware di terze parti, vedere [infrastruttura per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
Di seguito sono riportati i requisiti di bilanciamento del carico hardware per i servizi Web Director e front end pool:
  
- Per i VIP dei servizi Web interni, imposta Source_addr persistenza (porta interna 80, 443) sul servizio di bilanciamento del carico hardware. Per Skype for Business Server, Source_addr persistenza indica che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server per mantenere lo stato della sessione.
    
- Usare il timeout di inattività TCP di 1800 secondi.
    
- Nel firewall tra il proxy inverso e il bilanciamento del carico hardware del pool hop successivo creare una regola per consentire HTTPS: traffico sulla porta 4443, dal proxy inverso al bilanciamento del carico hardware. Il bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Riepilogo dei requisiti di affinità di bilanciamento del carico hardware

|**Posizione client/utente**|**Requisiti di affinità FQDN servizi Web esterni**|**Requisiti di affinità FQDN servizi Web interni**|
|:-----|:-----|:-----|
|Lync Web App (utenti interni ed esterni)  <br/> Dispositivo mobile (utenti interni ed esterni)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Lync Web App (solo utenti esterni)  <br/> Dispositivo mobile (utenti interni ed esterni)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Lync Web App (solo utenti interni)  <br/> Dispositivo mobile (non distribuito)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoraggio della porta per i dispositivi di bilanciamento del carico hardware

Puoi definire il monitoraggio della porta sui dispositivi di bilanciamento del carico hardware per determinare quando i servizi specifici non sono più disponibili a causa di problemi hardware o comunicazioni. Ad esempio, se il servizio server front-end (RTCSRV) si arresta perché il server front-end o il pool Front-end non riesce, il monitoraggio di HLB dovrebbe interrompere anche la ricezione del traffico sui servizi Web. Puoi implementare il monitoraggio della porta in HLB per monitorare le operazioni seguenti:
  
**Pool di utenti del server front-end-interfaccia interna di HLB**

|**IP virtuale/porta**|**Porta nodi**|**Nodo macchina/monitor**|**Profilo di persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<Web\>pool-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-end  <br/> 5061  <br/> |Fonte  <br/> |HTTPS  <br/> |
|\<Web\>pool-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-end  <br/> 5061  <br/> |Fonte  <br/> |HTTP  <br/> |
   
**Pool di utenti del server front-end-interfaccia esterna di HLB**

|**IP virtuale/porta**|**Porta nodi**|**Nodo macchina/monitor**|**Profilo di persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>del pool  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Nessuno  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>del pool  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Nessuno  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server consente il bilanciamento del carico DNS, una soluzione software in grado di ridurre notevolmente il sovraccarico di amministrazione per il bilanciamento del carico nella rete. Il bilanciamento del carico DNS bilancia il traffico di rete univoco per Skype for Business Server, ad esempio il traffico SIP e il traffico multimediale.
  
Se si distribuisce il bilanciamento del carico DNS, il sovraccarico di amministrazione dell'organizzazione per i dispositivi di bilanciamento del carico hardware verrà ridotto a icona. Inoltre, la risoluzione dei problemi complessi relativi alla configurazione errata dei bilanciatori di carichi per il traffico SIP verrà eliminata. È anche possibile impedire le connessioni del server in modo da poter prendere i server offline. Il bilanciamento del carico DNS garantisce inoltre che i problemi di bilanciamento del carico hardware non influiscono sugli elementi del traffico SIP, ad esempio il routing delle chiamate di base.

Il diagramma seguente mostra un esempio che include il bilanciamento del carico DNS interno ed esterno: 
  
**Diagramma reticolare Edge con indirizzi IPv4 pubblici**

![esempio di diagramma reticolare DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se si usa il bilanciamento del carico DNS, potrebbe essere anche possibile acquistare i dispositivi di bilanciamento del carico hardware a costo inferiore rispetto a quelli usati per tutti i tipi di traffico. È consigliabile usare i bilanciatori di carico che hanno superato i test di qualifica di interoperabilità con Skype for Business Server. Per informazioni dettagliate sui test di interoperabilità del bilanciamento del carico, vedere [partner di bilanciamento del carico di Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). Il contenuto si applica a Skype for Business Server.
  
Il bilanciamento del carico DNS è supportato per i pool Front-End, i pool di Edge Server, i pool di Director e i pool di Mediation Server autonomi.
  
Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione (ad esempio, un client che esegue Skype for business) Cerca di connettersi a un server in un pool connettendosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si usa l'indirizzamento IPv6) per il nome di dominio completo del pool. 
  
Se ad esempio sono presenti tre server front-end in un pool denominato pool01.contoso.com, si verificheranno le operazioni seguenti:
  
- Client che eseguono Skype for business query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (non necessariamente in questo ordine):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Il client cerca di stabilire una connessione TCP (Transmission Control Protocol) a uno degli indirizzi IP. Se l'operazione non riesce, il client tenterà l'indirizzo IP successivo nella cache.
    
- Se la connessione TCP riesce, il client negozia TLS per connettersi al registrar principale in pool01.contoso.com.
    
- Se il client prova tutte le voci memorizzate nella cache senza una connessione corretta, l'utente riceverà una notifica che non sono attualmente disponibili server che usano Skype for Business Server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso da DNS round robin (DNS RR) che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per specificare un ordine diverso di indirizzi IP corrispondenti ai server in un pool. In genere il record DNS consente solo la distribuzione del carico, ma non Abilita il failover. Ad esempio, se la connessione a un indirizzo IP restituito dal DNS A e AAAA (se si usa l'indirizzamento IPv6) non riesce, la connessione non riesce. Di conseguenza, il round robin DNS è meno attendibile del bilanciamento del carico basato su DNS. È possibile usare DNS round robin insieme al bilanciamento del carico DNS. 
  
Il bilanciamento del carico DNS viene usato per le operazioni seguenti:
  
- Bilanciamento del carico del SIP da server a server per gli Edge Server
    
- Bilanciamento del carico delle applicazioni UCAS (Unified Communications Application Services) come l'operatore automatico di conferenza, il gruppo di risposta e il parcheggio delle chiamate
    
- Impedire le nuove connessioni alle applicazioni di UCAS (nota anche come "drenante")
    
- Bilanciamento del carico di tutto il traffico da client a server tra client e Edge Server
    
Non è possibile usare il bilanciamento del carico DNS per gli elementi seguenti:
  
- Traffico Web da client a server a server Director o front end
    
Bilanciamento del carico DNS e traffico federativo:
  
Se più record DNS vengono restituiti da una query SRV DNS, il servizio Edge di Access sceglie sempre il record SRV DNS con la priorità numerica più bassa e il peso numerico più alto. Il documento Internet Engineering Task Force "un RR DNS per specificare la posizione dei servizi (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifica che se sono definiti più record SRV DNS, viene usata prima la priorità e quindi Weight. Ad esempio DNS SRV record A ha un peso di 20 e una priorità di 40 e DNS SRV record B ha un peso di 10 e la priorità di 50. Verrà selezionato il record SRV DNS A con priorità 40. Le regole seguenti si applicano alla selezione del record SRV DNS:
  
- La priorità viene considerata per prima. Un client deve tentare di contattare l'host di destinazione definito dal record SRV DNS con la priorità di numerazione più bassa che può raggiungere. Le destinazioni con la stessa priorità devono essere provate in un ordine definito dal campo peso.
    
- Il campo peso specifica un peso relativo per le voci con la stessa priorità. I pesi più grandi dovrebbero avere una probabilità di essere selezionata proporzionalmente più alta. Gli amministratori DNS dovrebbero usare il peso 0 quando non è presente alcuna selezione del server. In presenza di record che contengono pesi superiori a 0, i record con peso 0 dovrebbero avere una probabilità molto piccola di essere selezionati.
    
Se vengono restituiti più record SRV DNS con priorità e peso uguali, il servizio Access Edge selezionerà il record SRV ricevuto per primo dal server DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bilanciamento del carico DNS nei pool di front end e nei pool di Director

È possibile usare il bilanciamento del carico DNS per il traffico SIP nei pool di front end e nei pool di Director. Con il bilanciamento del carico DNS distribuito, è comunque necessario usare anche i dispositivi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server. Il bilanciamento del carico hardware viene usato per il traffico HTTPS dai client sulle porte 443 e 80. 
  
Anche se hai ancora bisogno di bilanciamento del carico hardware per questi pool, la loro configurazione e l'amministrazione saranno principalmente per il traffico HTTPS, a cui sono abituati gli amministratori dei dispositivi di bilanciamento del carico hardware.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Bilanciamento del carico DNS e supporto di client e server meno recenti

Il bilanciamento del carico DNS supporta il failover automatico solo per i server che utilizzano Skype for Business Server o Lync Server 2010 e per i client Lync 2013 e Skype for business. Le versioni precedenti di client e Office Communications Server possono comunque connettersi ai pool in cui è in esecuzione il bilanciamento del carico DNS, ma se non riescono a stabilire una connessione al primo server a cui si riferisce il bilanciamento del carico DNS, non riescono a eseguire il failover su un altro server nel pool . 
  
Inoltre, se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2010 SP1 per ottenere il supporto per il bilanciamento del carico DNS per Skype for Business Server. Se si usa una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:
  
- Riproduzione della segreteria telefonica aziendale sul telefono
    
- Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange
    
Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Distribuzione del bilanciamento del carico DNS nei pool di front-end e di Director
<a name="BK_FE_Dir"> </a>

La distribuzione di bilanciamento del carico DNS nei pool di front end e nei pool di Director richiede di eseguire alcuni passaggi aggiuntivi con FQDN e record DNS.
  
- Un pool che usa il bilanciamento del carico DNS deve avere due nomi di dominio completi: il nome di dominio completo del pool normale usato dal bilanciamento del carico DNS, ad esempio pool01.contoso.com, e viene risolto nell'IPs fisico dei server del pool e un altro nome di dominio completo per i servizi Web del pool, ad esempio web01.contoso.com), che viene risolto nell'indirizzo IP virtuale del pool. 
    
    In Generatore di topologia, se si vuole distribuire il bilanciamento del carico DNS per un pool, per creare il nome di dominio completo aggiuntivo per i servizi Web del pool, è necessario selezionare la casella di controllo **Sostituisci il nome FQDN del pool di servizi Web interni** e digitare il nome di dominio completo nella pagina **specifica gli URL dei servizi Web per questo pool** .
    
- Per supportare il nome di dominio completo usato dal bilanciamento del carico DNS, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio pool01.contoso.com, agli indirizzi IP di tutti i server del pool (ad es. 192.168.1.1, 192.168.1.2 e così via). Dovresti includere solo gli indirizzi IP dei server attualmente distribuiti.
    
    > [!CAUTION]
    > Se si hanno più di un pool Front end o un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come **pool01.contoso.com**, non è possibile usare **pool01.contoso.com** per un altro pool Front-end o front end server. Se si sta distribuendo anche Directors, l'FQDN dei servizi Web esterni definiti per qualsiasi pool di Director o Director deve essere univoco da qualsiasi altro pool di Director o Director, nonché da qualsiasi pool Front-end o front end server. Se decidi di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, Director o pool di Director.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Bilanciamento del carico DNS nei pool di Edge Server
<a name="BK_Edge"> </a>

È possibile distribuire il bilanciamento del carico DNS nei pool di Edge Server. In questo caso, è necessario tenere conto di alcune considerazioni.
  
L'uso del bilanciamento del carico DNS nei server perimetrali causa una perdita di capacità di failover negli scenari seguenti:
  
- Federazione con organizzazioni che utilizzano versioni di Skype for Business Server rilasciate prima di Lync Server 2010.
    
- Scambio di messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblica AOL e Yahoo!, oltre a provider e server basati su XMPP, come Google Talk, attualmente l'unico partner XMPP supportato.
    
Questi scenari funzionano fintanto che tutti i server perimetrali nel pool sono in esecuzione, ma se un server perimetrale non è disponibile, le richieste di questi scenari che verranno inviate non avranno esito positivo, invece di eseguire il routing a un altro Edge Server.
  
 Se si usa la messaggistica unificata di Exchange, è necessario usare un minimo di Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS Skype for Business Server su Edge. Se si usa una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi scenari di messaggistica unificata di Exchange:
  
- Riproduzione della segreteria telefonica aziendale sul telefono
    
- Trasferimento di chiamate da un operatore automatico di messaggistica unificata di Exchange
    
Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.
  
L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Distribuzione del bilanciamento del carico DNS nei pool di Edge Server

Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di Edge Server, sono necessarie le seguenti voci DNS:
  
- Per il servizio Access Edge è necessaria una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge, ad esempio sip.contoso.com, all'indirizzo IP del servizio Access Edge in uno degli Edge Server del pool.
    
- Per il servizio Web Conferencing Edge è necessario immettere una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno degli Edge Server del pool.
    
- Per il servizio Edge audio/video è necessario immettere una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Edge audio/video, ad esempio av.contoso.com, all'indirizzo IP del servizio A/V Edge in uno degli Edge Server del pool.
    
Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di Edge Server, è necessario aggiungere un record DNS, che risolve il nome di dominio completo interno del pool di Edge Server con l'indirizzo IP di ogni server nel pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Uso del bilanciamento del carico DNS nei pool di Mediation Server
<a name="BK_Mediation"> </a>

È possibile usare il bilanciamento del carico DNS nei pool di Mediation Server autonomi. Tutto il traffico SIP e multimediale è bilanciato dal bilanciamento del carico DNS.
  
Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio mediationpool1.contoso.com, agli indirizzi IP di tutti i server del pool, ad esempio 192.168.1.1, 192.168.1.2 e così via.
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloccare il traffico a un server con il bilanciamento del carico DNS
<a name="BK_Mediation"> </a>

Se si usa il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere semplicemente le voci di indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer. 
  
Tieni presente che per il traffico da server a server Skype for Business Server usa il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata in Central Management store per ottenere i nomi di dominio completi dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Per impedire a un server di ricevere il traffico da server a server, è necessario rimuovere il server dalla topologia. 
  

