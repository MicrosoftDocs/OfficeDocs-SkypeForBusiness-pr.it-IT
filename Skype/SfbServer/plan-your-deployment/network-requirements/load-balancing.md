---
title: Requisiti di bilanciamento del carico per Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Riepilogo: esaminare le considerazioni sul bilanciamento del carico prima di implementare Skype for Business Server.'
---

# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisiti di bilanciamento del carico per Skype for Business
 
**Riepilogo:** Esaminare le considerazioni sul bilanciamento del carico prima di implementare Skype for Business Server.
  
Il bilanciamento del carico distribuisce il traffico tra i server di un pool. Se si dispone di pool Front End, pool Mediation Server o pool di server perimetrali, è necessario distribuire il bilanciamento del carico per tali pool.
  
Skype for Business Server supporta due tipi di soluzioni di bilanciamento del carico per il traffico da client a server: il bilanciamento del carico DNS (Domain Name System) e il bilanciamento del carico hardware (spesso abbreviato come HLB). Il bilanciamento del carico DNS offre diversi vantaggi, tra cui un'amministrazione più semplice, una risoluzione dei problemi più efficiente e la possibilità di isolare gran parte del traffico Skype for Business Server da potenziali problemi di bilanciamento del carico hardware.
  
Decidere la soluzione di bilanciamento del carico appropriata per ogni pool della distribuzione, ma tenere presenti le restrizioni seguenti: 
  
- Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware nell'altra.
    
- Alcuni tipi di traffico richiedono un servizio di bilanciamento del carico hardware. Il traffico HTTP richiede, ad esempio, un servizio di bilanciamento del carico hardware anziché il bilanciamento del carico DNS. Il bilanciamento del carico DNS non funziona con il traffico Web da client a server.
    
Se si sceglie di utilizzare il bilanciamento del carico DNS per un pool, ma è comunque necessario implementare servizi di bilanciamento del carico hardware per il traffico, ad esempio il traffico HTTP, l'amministrazione dei servizi di bilanciamento del carico hardware risulta notevolmente semplificata. Ad esempio, la configurazione del servizio di bilanciamento del carico hardware sarà più semplice in quanto gestirà solo il traffico HTTP e HTTPS, mentre tutti gli altri protocolli verranno gestiti dal bilanciamento del carico DNS. Per informazioni dettagliate, vedere [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Per il traffico da server a server, Skype for Business Server il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere gli FQDN dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Gli amministratori non devono configurare o gestire questo tipo di bilanciamento del carico. 
  
Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci dell'indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisiti del servizio di bilanciamento del carico hardware

La Skype for Business Server topologia perimetrale consolidata con scalabilità orizzontale è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni federate principalmente con altre organizzazioni che utilizzano Skype for Business Server o Lync Server. Se è richiesta la disponibilità elevata per uno degli scenari seguenti, sarà necessario utilizzare un dispositivo di bilanciamento del carico hardware nei pool di server perimetrali nei casi seguenti: 
  
- Federazione con organizzazioni che utilizzano Office Communications Server 2007 R2 o Office Communications Server 2007
    
- Exchange messaggistica unificata per gli utenti remoti che Exchange messaggistica unificata prima di Exchange 2010 con SP1
    
- Connettività con utenti di messaggistica istantanea pubblica
    
> [!IMPORTANT]
> Non è possibile usare il bilanciamento del carico DNS in un'interfaccia e il bilanciamento del carico hardware in un'altra. È necessario usare lo stesso tipo di bilanciamento del carico per entrambe le interfacce, in quanto non è supportata una combinazione dei due tipi. 
  
> [!NOTE]
> Se si usa un servizio di bilanciamento del carico hardware, il bilanciamento del carico distribuito per le connessioni con la rete interna deve essere configurato per bilanciare il carico solo del traffico verso i server che eseguono i servizi Access Edge e A/V Edge. Non è possibile bilanciare il carico del traffico verso il servizio Web Conferencing Edge interno o il servizio del proxy XMPP interno. 
  
> [!NOTE]
> Il nat DSR (Direct Server Return) non è supportato con Skype for Business Server. 
  
Per determinare se il servizio di bilanciamento del carico hardware supporta le funzionalità necessarie richieste da Skype for Business Server, vedere [Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisiti dei servizi di bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge

Di seguito sono riportati i requisiti di bilanciamento del carico hardware per i server perimetrali che eseguono il servizio A/V Edge:
  
- Disattivare il nagling TCP per le porte 443 interne ed esterne. Per nagling si intende il processo di combinazione di più pacchetti di piccole dimensioni in un singolo pacchetto di dimensioni maggiori per una trasmissione più efficiente.
    
- Disattivare il nagling TCP per l'intervallo di porte esterne 50.000 - 59.999. 
    
- Non utilizzare NAT nel firewall interno o esterno. 
    
- L'interfaccia interna perimetrale deve trovarsi in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di esse deve essere disabilitato. 
    
- L'interfaccia esterna del server perimetrale che esegue il servizio A/V Edge deve utilizzare indirizzi IP instradabili pubblicamente e nessuna conversione NAT o porta su uno degli indirizzi IP esterni perimetrali. 
    
- Il servizio di bilanciamento del carico non deve modificare l'indirizzo di origine del client.
    
### <a name="other-hardware-load-balancer-requirements"></a>Altri requisiti del servizio di bilanciamento del carico hardware

I requisiti di affinità basati su cookie sono notevolmente Skype for Business Server per i servizi Web. Se si distribuisce Skype for Business Server e non vengono mantenuti i Front End Server o i pool Front End di Lync Server 2010, non è necessaria la persistenza basata su cookie. Tuttavia, se si manterranno temporaneamente o definitivamente i Front End Server di Lync Server 2010 o i pool Front End, si continuerà a utilizzare la persistenza basata su cookie quando viene distribuita e configurata per Lync Server 2010. 
  
> [!NOTE]
> **La decisione di usare l'affinità basata sui cookie anche se la distribuzione non la richiede** non determina un impatto negativo. 
  
Per le distribuzioni in cui l'affinità basata sui cookie **non verrà usata**:
  
- Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.
    
Per le distribuzioni in cui l'affinità basata sui cookie **verrà usata**:
  
- Nella regola di pubblicazione del proxy inverso per la porta 4443, impostare **Forward host header** su True in modo da assicurarsi che l'URL originale venga inoltrato.
    
- Il cookie del bilanciamento del carico hardware NON DEVE essere contrassegnato come httpOnly
    
- Per il bilanciamento del carico hardware NON DEVE essere impostata una data di scadenza
    
- Il cookie del bilanciamento del carico hardware DEVE essere denominato **MS-WSMAN** ovvero il valore, non modificabile, previsto dai servizi Web
    
- Il cookie del bilanciamento del carico hardware DEVE essere impostato in ogni risposta HTTP per la quale la richiesta HTTP in arrivo non presentava un cookie, indipendentemente dal fatto che una precedente risposta HTTP nella stessa connessione TCP abbia già ottenuto un cookie. Se il bilanciamento del carico ottimizza l'inserimento del cookie in modo che venga eseguito una sola volta per ogni connessione TCP, tale ottimizzazione NON DEVE essere usata
    
> [!NOTE]
> Le configurazioni tipiche del servizio di bilanciamento del carico hardware utilizzano l'affinità degli indirizzi di origine e una durata della sessione TCP di 20 minuti, che va bene per i client Lync Server e Lync 2013 perché lo stato della sessione viene mantenuto tramite l'utilizzo del client e/o l'interazione delle applicazioni. 
  
Se si distribuiscono dispositivi mobili, il servizio di bilanciamento del carico hardware deve essere in grado di bilanciare il carico delle singole richieste in una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).
  
> [!CAUTION]
> Se si distribuiscono dispositivi mobili, il servizio di bilanciamento del carico hardware deve essere in grado di bilanciare singolarmente il carico di ogni richiesta all'interno di una connessione TCP. Le applicazioni per dispositivi mobili Apple iOS più recenti richiedono TLS (Transport Layer Security) versione 1.2.  
  
> [!CAUTION]
> Per informazioni dettagliate sui servizi di bilanciamento del carico hardware di terze parti, vedere [Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).  
  
Vengono riportati di seguito i requisiti dei servizi di bilanciamento del carico hardware per i servizi Web dei pool di server Director e Front End:
  
- Per gli IP virtuali dei servizi Web interni, impostare la persistenza Source_addr (porta interna 80, 443) nel servizio di bilanciamento del carico hardware. Ad Skype for Business Server, Source_addr persistenza significa che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server per mantenere lo stato sessione.
    
- Impostare il timeout di inattività TCP su 1800 secondi.
    
- Nel firewall tra il proxy inverso e il servizio di bilanciamento del carico hardware del pool di hop successivo, creare una regola per consentire il traffico https: sulla porta 4443, dal proxy inverso al servizio di bilanciamento del carico hardware. Il servizio di bilanciamento del carico hardware deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Riepilogo dei requisiti per l'affinità del servizio di bilanciamento del carico hardware

|**Posizione client/utente**|**Requisiti per l'affinità FQDN dei servizi Web esterni**|**Requisiti per l'affinità FQDN dei servizi Web interni**|
|:-----|:-----|:-----|
|Lync Web App (utenti interni ed esterni)  <br/> Dispositivo mobile (utenti interni ed esterni)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Lync Web App (solo utenti esterni)  <br/> Dispositivo mobile (utenti interni ed esterni)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Lync Web App (solo utenti interni)  <br/> Dispositivo mobile (non distribuito)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoraggio delle porte per i servizi di bilanciamento del carico hardware

Il monitoraggio delle porte viene definito nei servizi di bilanciamento del carico hardware per stabilire quando determinati servizi non sono più disponibili a causa di un errore hardware o delle comunicazioni. Ad esempio, se il servizio Front End Server (RTCSRV) si interrompe a causa di un errore del Front End Server o del pool Front End, anche il monitoraggio del bilanciamento del carico di rete dovrebbe interrompere la ricezione del traffico nei servizi Web. Il monitoraggio delle porte viene implementato nel servizio HLB per monitorare quanto segue:
  
**Pool di utenti front-end server - Interfaccia interna HLB**

|**IP virtuale/Porta**|**Porta nodo**|**Computer/Monitor nodo**|**Profilo persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front End  <br/> 5061  <br/> |Origine  <br/> |HTTPS  <br/> |
|\<pool\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front End  <br/> 5061  <br/> |Origine  <br/> |HTTP  <br/> |
   
**Pool di utenti front-end server - Interfaccia esterna HLB**

|**IP virtuale/Porta**|**Porta nodo**|**Computer/Monitor nodo**|**Profilo persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front End  <br/> 5061  <br/> |Nessuna  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front End  <br/> 5061  <br/> |Nessuna  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server il bilanciamento del carico DNS, una soluzione software in grado di ridurre notevolmente l'overhead amministrativo per il bilanciamento del carico nella rete. Il bilanciamento del carico DNS bilancia il traffico di rete univoco Skype for Business Server, ad esempio il traffico SIP e il traffico multimediale.
  
Se si distribuisce il bilanciamento del carico DNS, l'overhead di amministrazione dell'organizzazione per i servizi di bilanciamento del carico hardware verrà ridotto al minimo. È inoltre possibile eliminare la complessità legata alla risoluzione dei problemi relativi a una configurazione errata dei servizi di bilanciamento del carico per il traffico SIP. È anche possibile impedire le connessioni al server, per poter disconnettere i server. Il bilanciamento del carico DNS garantisce infine che i problemi dei servizi di bilanciamento del carico hardware non influiscano su elementi del traffico SIP, ad esempio il routing delle chiamate di base.

Il diagramma seguente mostra un esempio che include il bilanciamento del carico DNS sia interno che esterno: 
  
**Diagramma della rete perimetrale con indirizzi IPv4 pubblici**

![esempio di diagramma di rete DNS.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se si utilizza il bilanciamento del carico DNS, è anche possibile acquistare servizi di bilanciamento del carico hardware a un costo più conveniente rispetto a quello da sostenere se si utilizzano servizi di bilanciamento del carico hardware per tutti i tipi di traffico. È consigliabile usare servizi di bilanciamento del carico che hanno superato i test di qualificazione dell'interoperabilità con Skype for Business Server. Per informazioni dettagliate sui test di interoperabilità del servizio di bilanciamento del carico, vedere [Lync Server 2010 Load Balancer Partners](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). Il contenuto si applica a Skype for Business Server.
  
Il bilanciamento del carico DNS è supportato per i pool Front End, i pool di server perimetrali, i pool di server Director e i pool di Mediation Server autonomi.
  
Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione, ad esempio un client che esegue Skype for Business, tenta di connettersi a un server di un pool connettendosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si usa l'indirizzamento IPv6) per il nome di dominio completo (FQDN) del pool. 
  
Ad esempio, se in un pool denominato pool01.contoso.com sono presenti tre server front-end, si verifica quanto segue:
  
- I client che Skype for Business eseguono query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache nel modo seguente (non necessariamente in questo ordine):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- Il client tenta di stabilire una connessione TCP (Transmission Control Protocol) a uno degli indirizzi IP. In caso di esito negativo, il client tenta l'indirizzo IP successivo nella cache.
    
- Se la connessione TCP ha esito positivo, il client negozia TLS per connettersi al registrar principale pool01.contoso.com.
    
- Se il client tenta tutte le voci memorizzate nella cache senza una connessione corretta, all'utente viene notificato che al momento non sono disponibili Skype for Business Server server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso dal round robin DNS (DNS RR), che in genere si riferisce al bilanciamento del carico basandosi su DNS per fornire un ordine diverso di indirizzi IP corrispondenti ai server di un pool. RR DNS in genere abilita solo la distribuzione del carico, ma non abilita il failover. Ad esempio, se la connessione all'unico indirizzo IP restituito dalla query DNS A e AAAA (se si utilizza l'indirizzamento IPv6) ha esito negativo, la connessione ha esito negativo. Pertanto, il round robin DNS di per sé è meno affidabile del bilanciamento del carico basato su DNS. È possibile utilizzare il round robin DNS insieme al bilanciamento del carico DNS. 
  
Il bilanciamento del carico DNS viene utilizzato per gli elementi seguenti:
  
- Bilanciamento del carico SIP da server a server nei server perimetrali
    
- Bilanciamento del carico Applicazioni UCAS (Unified Communications Application Services), ad esempio servizi di Operatore automatico conferenza, Response Group e Parcheggio di chiamata
    
- Impedire nuove connessioni alle applicazioni UCAS (noto anche come "drenaggio")
    
- Bilanciamento del carico di tutto il traffico da client a server tra client e server perimetrali
    
Non è possibile utilizzare il bilanciamento del carico DNS per gli elementi seguenti:
  
- Traffico Web da client a server verso Director o Front End Server
    
Bilanciamento del carico DNS e traffico federato:
  
Se più record DNS vengono restituiti da una query DNS SRV, il servizio Access Edge seleziona sempre il record DNS SRV con la priorità numerica più bassa e il peso numerico più alto. Il documento internet Engineering Task Force "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifica che se sono definiti più record DNS SRV, viene innanzitutto utilizzata la priorità, quindi il peso. Ad esempio, il record DNS SRV A ha un peso di 20 e una priorità di 40 e il record DNS SRV B ha un peso di 10 e una priorità di 50. Verrà selezionato il record DNS SRV A con priorità 40. Alla selezione dei record DNS SRV si applicano le regole seguenti:
  
- La priorità viene considerata per prima. Un client DEVE tentare di contattare l'host di destinazione definito dal record DNS SRV con la priorità numerata più bassa che può raggiungere. Le destinazioni con la stessa priorità devono essere tentate in un ordine definito dal campo peso.
    
- Il campo peso specifica un peso relativo per le voci con la stessa priorità. A pesi maggiori deve essere data una probabilità proporzionalmente superiore di essere selezionata. Gli amministratori DNS DEVONO utilizzare il peso 0 quando non è disponibile alcuna selezione di server da eseguire. In presenza di record contenenti pesi maggiori di 0, i record con peso 0 dovrebbero avere una probabilità molto ridotta di essere selezionati.
    
Se vengono restituiti più record DNS SRV con priorità e peso uguali, il servizio Access Edge selezionerà il record SRV ricevuto per primo dal server DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bilanciamento del carico DNS in pool Front End e pool di server Director

È possibile utilizzare il bilanciamento del carico DNS per il traffico SIP in pool Front End e pool di server Director. Dopo aver distribuito il bilanciamento del carico DNS, è comunque necessario utilizzare anche servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTPS da client a server. Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client nelle porte 443 e 80. 
  
Sebbene siano comunque necessari servizi di bilanciamento del carico hardware per questi pool, la loro impostazione e l'amministrazione saranno principalmente relative al traffico HTTPS a cui gli amministratori dei servizi di bilanciamento del carico hardware sono abituati.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Bilanciamento del carico DNS e supporto di server e client precedenti

Il bilanciamento del carico DNS supporta il failover automatico solo per i server che eseguono Skype for Business Server o Lync Server 2010 e per lync 2013 e Skype for Business client. Le versioni precedenti dei client e di Office Communications Server possono comunque connettersi ai pool che eseguono il bilanciamento del carico DNS, ma se non riescono a stabilire una connessione al primo server a cui fa riferimento il bilanciamento del carico DNS, non possono eseguire il failover a un altro server del pool. 
  
Inoltre, se si utilizza la messaggistica unificata Exchange, è necessario utilizzare almeno Exchange 2010 SP1 per ottenere il supporto per il bilanciamento del carico DNS Skype for Business Server dns. Se si utilizza una versione precedente di Exchange, gli utenti non avranno funzionalità di failover per questi Exchange di messaggistica unificata:
  
- Riproduzione della Enterprise vocale sul telefono
    
- Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange
    
Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director
<a name="BK_FE_Dir"> </a>

Per la distribuzione del bilanciamento del carico DNS in pool Front End e pool di server Director è necessario eseguire due passaggi aggiuntivi relativi a FQDN e record DNS.
  
- Un pool che utilizza il bilanciamento del carico DNS deve avere due FQDN: l'FQDN del pool normale utilizzato dal bilanciamento del carico DNS (ad esempio pool01.contoso.com) e viene risolto negli INDIRIZZI IP fisici dei server del pool e un altro FQDN per i servizi Web del pool (ad esempio web01.contoso.com), che si risolve in indirizzo IP virtuale del pool. 
    
    In Generatore di topologie, se si desidera distribuire il bilanciamento del carico DNS per un pool, per creare questo FQDN aggiuntivo per i servizi Web del pool è necessario selezionare la casella di controllo Ignora FQDN pool di servizi **Web** interni e digitare il nome di dominio completo nella pagina Specificare gli URL **dei servizi Web** per il pool.
    
- Per supportare il nome di dominio completo utilizzato dal bilanciamento del carico DNS, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio pool01.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via). Includere solo gli indirizzi IP dei server attualmente distribuiti.
    
    > [!CAUTION]
    > Se si dispone di più pool Front End o Front End Server, il nome di dominio completo dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce il nome di dominio completo dei servizi Web esterni di un Front End Server **come pool01.contoso.com**, non è possibile utilizzare **pool01.contoso.com per un** altro pool Front End o Front End Server. Se si distribuiscono anche Director, il nome di dominio completo dei servizi Web esterni definito per qualsiasi server Director o pool di server Director deve essere univoco da qualsiasi altro server Director o pool di server Director, nonché da qualsiasi pool Front End o Front End Server. Se si decide di sostituire i servizi Web interni con un fqdn autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Bilanciamento del carico DNS in pool di server perimetrali
<a name="BK_Edge"> </a>

È possibile distribuire il bilanciamento del carico DNS in pool di server perimetrali. In tal caso, è necessario tenere presenti alcune considerazioni.
  
L'utilizzo del bilanciamento del carico DNS nei server perimetrali comporta una perdita della capacità di failover negli scenari seguenti:
  
- Federazione con organizzazioni che eseguono versioni di Skype for Business Server rilasciate prima di Lync Server 2010.
    
- Lo scambio di messaggi istantanei con gli utenti dei servizi di messaggistica istantanea pubblica AOL e Yahoo!, oltre ai provider e ai server basati su XMPP, come Google Talk, attualmente è l'unico partner XMPP supportato.
    
Questi scenari funzionano a condizione che tutti i server perimetrali nel pool siano in esecuzione, ma se un server perimetrale non è disponibile, tutte le richieste per questi scenari inviate a tale server avranno esito negativo, anziché essere instradate a un altro server perimetrale.
  
 Se si utilizza la Exchange di messaggistica unificata, è necessario utilizzare almeno Exchange 2013 per ottenere il supporto per il bilanciamento del carico DNS Skype for Business Server server perimetrale. Se si utilizza una versione precedente di Exchange, gli utenti remoti non avranno funzionalità di failover per questi Exchange di messaggistica unificata:
  
- Riproduzione della Enterprise vocale sul telefono
    
- Trasferimento delle chiamate da un Operatore automatico messaggistica unificata di Exchange
    
Tutti gli altri scenari di messaggistica unificata di Exchange funzioneranno correttamente.
  
Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Distribuzione del bilanciamento del carico DNS in pool di server perimetrali

Per distribuire il bilanciamento del carico DNS nell'interfaccia esterna del pool di server perimetrali, sono necessarie le voci DNS seguenti:
  
- Per il servizio Access Edge, è necessaria una voce per ogni server del pool. Ogni voce deve risolvere il nome di dominio completo del servizio Access Edge (ad esempio, sip.contoso.com) nell'indirizzo IP del servizio Access Edge in uno dei server perimetrali del pool.
    
- Per il servizio Web Conferencing Edge, è necessaria una voce per ogni server del pool. Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge (ad esempio, webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge in uno dei server perimetrali del pool.
    
- Per il servizio Audio/Video Edge, è necessaria una voce per ogni server del pool. Ogni voce deve risolvere il nome di dominio completo del servizio Audio/Video Edge (ad esempio, av.contoso.com) nell'indirizzo IP del servizio A/V Edge in uno dei server perimetrali del pool.
    
Per distribuire il bilanciamento del carico DNS nell'interfaccia interna del pool di server perimetrali, è necessario aggiungere un record A DNS, che consente di risolvere il nome di dominio completo interno del pool di server perimetrali nell'indirizzo IP di ogni server del pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Utilizzo del bilanciamento del carico DNS in pool di Mediation Server
<a name="BK_Mediation"> </a>

È possibile utilizzare il bilanciamento del carico DNS in pool di Mediation Server autonomi. Tutto il traffico SIP e multimediale viene bilanciato dal bilanciamento del carico DNS.
  
Per distribuire il bilanciamento del carico DNS in un pool di Mediation Server, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio, mediationpool1.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blocco del traffico verso un server con bilanciamento del carico DNS
<a name="BK_Mediation"> </a>

Se si utilizza il bilanciamento del carico DNS ed è necessario bloccare il traffico verso un computer specifico, non è sufficiente rimuovere solo le voci dell'indirizzo IP dall'FQDN del pool. È necessario rimuovere anche la voce DNS per il computer. 
  
Si noti che per il traffico da server a server, Skype for Business Server il bilanciamento del carico in grado di riconoscere la topologia. I server leggono la topologia pubblicata nell'archivio di gestione centrale per ottenere gli FQDN dei server nella topologia e distribuiscono automaticamente il traffico tra i server. Per impedire a un server di ricevere traffico da server a server, è necessario rimuovere il server dalla topologia. 
