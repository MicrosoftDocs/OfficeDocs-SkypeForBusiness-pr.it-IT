---
title: Pianificazione DNS avanzata di Edge Server per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Riepilogo: scenari di revisione per le opzioni di distribuzione di Skype for Business Server. Questo argomento dovrebbe essere utile se si vuole un singolo server o si preferisce un pool di server con DNS o HLB.'
ms.openlocfilehash: c1a5cc793cde46c1334d88dfcbd430922f0b7c32
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887645"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Pianificazione DNS avanzata di Edge Server per Skype for Business Server
 
**Riepilogo:** Scenari di revisione per le opzioni di distribuzione di Skype for Business Server. Questo argomento dovrebbe essere utile se si vuole un singolo server o si preferisce un pool di server con DNS o HLB.
  
Per quanto riguarda la pianificazione DNS (Domain Name System) per Skype for Business Server, sono presenti molti fattori che potrebbero rientrare nella tua decisione. Se la struttura del dominio dell'organizzazione è già in vigore, potrebbe essere necessario rivederla come procedere. Inizieremo con gli argomenti riportati di seguito:
  
- [Procedura dettagliata di individuazione dei servizi per i client Skype for business](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS split-brain](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configurazione automatica senza DNS split-brain](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Ripristino di emergenza DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [Bilanciamento del carico DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Procedura dettagliata di individuazione dei servizi per i client Skype for business
<a name="WalkthroughOfSkype"> </a>

I client Skype for business sono simili alle versioni precedenti dei client Lync nel modo in cui trovano e accedono ai servizi in Skype for Business Server. Questa sezione descrive in dettaglio il processo di posizione del server.
  
1. lyncdiscoverinternal. \<dominio\>
    
     *Si tratta di un record host per il servizio di individuazione automatica dei servizi Web interni.* 
    
2. Lyncdiscover. \<dominio\>
    
     *Si tratta di un record host per il servizio di individuazione automatica dei servizi Web esterni.* 
    
3. _sipinternaltls. _tcp. \<dominio\>
    
     *Si tratta di un record SRV per le connessioni TLS interne.* 
    
4. _sip. _tls. \<dominio\>
    
     *Si tratta di un record SRV per le connessioni TLS esterne.* 
    
5. sipinternal. \<dominio\>
    
     *Si tratta di un record host per il pool o il Director front-end, risolvibile solo nella rete interna.* 
    
6. SIP. \<dominio\>
    
     *Si tratta di un record host per il pool o il Director front-end, risolvibile solo nella rete interna.* 
    
7. sipexternal. \<dominio\>
    
     *Si tratta di un record host per il servizio Access Edge, quando il client è esterno.* 
    
Il servizio di individuazione automatica è sempre favorito perché è il metodo preferito per la posizione del servizio e gli altri sono metodi di fallback.
  
> [!NOTE]
> Quando si creano record SRV, è importante ricordare che devono puntare a un DNS a (e AAAA se si usa l'indirizzamento IPv6) nello stesso dominio in cui è stato creato il record SRV DNS. Ad esempio, se il record SRV è in contoso.com, il record A (e AAAA) punta a non può essere in fabrikam.com. 
  
Se si è inclini a farlo, è possibile impostare il dispositivo mobile per l'individuazione manuale dei servizi. In questo caso, ogni utente deve configurare le impostazioni del dispositivo mobile con gli URI del servizio di individuazione automatica interni ed esterni, inclusi il protocollo e il percorso, come indicato di seguito:
  
- Per l'accesso esterno:\<https://\>ExtPoolFQDN/Autodiscover/autodiscoverservice.svc/root
    
- Per l'accesso interno:\<https://\>IntPoolFQDN/autodiscover/autodiscover.svc/root
    
Ti consigliamo di usare l'individuazione automatica anziché l'individuazione manuale. Ma se si stanno eseguendo alcuni test o risoluzione dei problemi, le impostazioni manuali possono essere molto utili.
  
## <a name="split-brain-dns"></a>DNS split-brain
<a name="SplitBrainDNS"> </a>

Si tratta di una configurazione DNS in cui sono presenti due aree DNS con lo stesso spazio dei nomi. La prima area DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne.
  
Perché una società può eseguire questa operazione? Possono avere un requisito per usare lo stesso spazio dei nomi internamente e esternamente, ma ovviamente questo porterà molti DNS SRV e un record a essere univoci per una zona o un'altra e dove c'è una duplicazione, gli indirizzi IP associati a questi record sarebbero univoci.
  
Questo presenta alcune sfide. La cosa più importante è che il DNS split-brain **non è supportato** per la mobilità. A causa dei record DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve essere definito nel server DNS esterno, mentre LyncDiscoverInternal deve essere definito nel server DNS interno).
  
Verranno elencati i record DNS per le aree interne ed esterne, ma è possibile trovare esempi dettagliati nella sezione requisiti ambientali di Edge Server.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questo contoso.com interno contiene:
    
  - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per il pool di front-end, il pool di Director o il nome del pool di Director e tutti i server interni con Skype for Business Server nella rete dell'organizzazione.
    
  - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per l'interfaccia interna di Edge per ogni server Edge di Skype for Business Server nella rete perimetrale.
    
  - DNS A e AAAA (se si usano i record di indirizzamento IPv6) per l'interfaccia interna di ogni server proxy inverso nella rete perimetrale ( **facoltativo** per la gestione di un proxy inverso).
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client Skype for Business Server interno ( **facoltativo** ).
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) o CNAME Records per l'individuazione automatica dei servizi Web di Skype for Business Server ( **facoltativo** ).
    
- Tutte le interfacce Edge interne di Skype for Business Server nella rete perimetrale utilizzano questa zona DNS interna per la risoluzione delle query in contoso.com.
    
- Tutti i server che eseguono Skype for Business Server e i client che eseguono Skype for Business Server nella rete aziendale, puntano ai server DNS interni per la risoluzione delle query in contoso.com oppure usano il file host in ogni server perimetrale ed elencano A e AAAA (se si sta usando Indirizzi IPv6) record per il server hop successivo (in particolare per il VIP del pool Director o Director, il VIP del pool Front-end o il server Standard Edition).
    
### <a name="external-dns"></a>DNS esterno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questo contoso.com esterno contiene:
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) o CNAME Records per l'individuazione automatica dei servizi Web di Skype for Business Server. Questo è per l'uso con mobilità.
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna Edge di ogni VIP di Skype for Business Server Edge Server o di HLB (hardware load balanced) nella rete perimetrale.
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna del server proxy inverso o (VIP per un pool di server proxy inverso), nella rete perimetrale.
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) e i record SRV per la configurazione automatica client di Skype for Business Server ( **facoltativo** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split-brain
<a name="NoSplitBrainDNS"> </a>

Se non si usa il DNS split-brain, la configurazione automatica interna dei client che usano Skype for business non funziona a meno che non si stia usando una delle soluzioni alternative disponibili. Perché no? Poiché Skype for Business Server richiede che l'URI SIP dell'utente corrisponda al dominio del pool Front-End designato per la configurazione automatica. Questa operazione non è cambiata rispetto alle versioni precedenti di Lync Server.
  
Quindi, se si usano due domini SIP in uso, è necessario questi record SRV DNS:
  
- _sipinternaltls. _tcp. contoso. com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se un utente accede come bob@contoso.com, questo record funzionerebbe per la configurazione automatica, dato che il dominio SIP dell'utente corrisponde al dominio del pool Front-End (contoso.com).* 
    
- _sipinternaltls. _tcp. fabrikam. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se un utente accede come alice@fabrikam.com, questo record funzionerebbe per la configurazione automatica del secondo dominio, anche in questo caso perché il dominio SIP corrisponde al pool Front-end per il dominio.* 
    
Per eseguire l'esempio più avanti, non funzionerebbe:
  
- _sipinternaltls. _tcp. litwareinc. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utente che effettua l'accesso come tim@litwareinc.com non funziona per la configurazione automatica, perché il proprio dominio SIP (litwareinc.com) non corrisponde al dominio nel pool (fabrikam.com).* 
    
Quindi, ora che sappiamo tutto questo, se hai bisogno di requisiti automatici per i clienti Skype for business senza DNS split-brain, hai queste opzioni:
  
- **Oggetti Criteri di gruppo**
    
    Puoi usare gli oggetti Criteri di gruppo per popolare i valori del server corretti.
    
    > [!NOTE]
    > Questa opzione non consente la configurazione automatica, ma automatizza la configurazione manuale. Se questo approccio viene usato, i record SRV associati alla configurazione automatica non sono obbligatori. 
  
- **Zona interna corrispondente**
    
    È necessario creare una zona nel DNS interno che corrisponda alla zona DNS esterna, ad esempio contoso.com, e quindi creare record DNS A (e AAAA se si usa l'indirizzo IPv6) che corrispondono al pool di Skype for Business Server usato per l'automazione configurazione.
    
    Ad esempio, se si ha un utente ospitato in pool01.contoso.net, ma si accede a Skype for business come bob@contoso.com, creare una zona DNS interna denominata contoso.com e al suo interno è necessario creare un record DNS A (e AAAA se l'indirizzo IPv6 viene usato) per pool01.contoso.com.
    
- **Zona interna con pin-point**
    
    Se la creazione di un'intera area nel DNS interno non è un'opzione per l'utente, è possibile creare aree con pin point (dedicate) che corrispondono ai record SRV necessari per la configurazione automatica e popolare tali aree tramite Dnscmd. exe. Dnscmd. exe è necessario perché l'interfaccia utente DNS non supporta la creazione di aree con punti pin.
    
    Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front-End denominato Pool01 che contiene due server front-end, sono necessarie le seguenti aree di punti pin e un record nel DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Potresti avere un secondo dominio SIP nell'ambiente. In questo caso, è necessario disporre delle aree di punti pin seguenti e di un record nel DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Verrà visualizzato il nome di dominio completo del pool di front end, ma con due indirizzi IP diversi. Questo perché viene usato il bilanciamento del carico DNS. Se viene usato HLB, c'è solo una singola voce del pool Front-end. 
  
> [!NOTE]
> Inoltre, i valori FQDN del pool di front end cambiano tra gli esempi contoso.com e fabrikam.com, ma gli indirizzi IP rimangono invariati. Il motivo è che gli utenti che accedono da un dominio SIP useranno lo stesso pool Front-end per la configurazione automatica. 
  
## <a name="dns-disaster-recovery"></a>Ripristino di emergenza DNS
<a name="DNSDR"> </a>

Per configurare il DNS per reindirizzare il traffico Web di Skype for Business Server ai siti di disaster recover (DR) e failover, è necessario usare un provider DNS che supporti GeoDNS. È possibile configurare i record DNS per supportare il ripristino di emergenza, in modo che le caratteristiche che usano i servizi Web continuino anche se un intero pool Front-End scende. Questa funzionalità DR supporta gli URL semplici di individuazione, riunione e accesso esterno.
  
Si definiscono e si configurano altri record host DNS a (AAAA If using IPv6) per la risoluzione interna ed esterna dei servizi Web presso il provider di GeoDNS. I dettagli seguenti presumono che i pool associati, distribuiti geograficamente e che il GeoDNS supportato **dal provider** dispongano di Round Robin DNS **o** siano configurati per l'uso di pool1 come primari e non vengano rientrati in Pool2 in caso di perdita di comunicazioni o di interruzioni di corrente.
  
Tutti i record DNS in questa tabella sono esempi.
  
|**Record GeoDNS**|**Record del pool**|**Record CNAME**|**Impostazioni DNS (selezionare un'opzione)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin tra i pool  <br/> **OPPURE** <br/> USA primaria, Connetti a secondario se si verifica un errore  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="DNSLB"> </a>

Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione (ad esempio, un client che esegue Skype for business) Cerca di connettersi a un server in un pool connettendosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si usa l'indirizzamento IPv6) per il nome di dominio completo del pool.
  
Se ad esempio sono presenti tre server front-end in un pool denominato pool01.contoso.com, si verificheranno le operazioni seguenti:
  
- Client che eseguono Skype for business query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (in un ordine):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Il client cerca di stabilire una connessione TCP a uno degli indirizzi IP. Se l'operazione non riesce, cercherà l'indirizzo IP successivo memorizzato nella cache da tale elenco.
    
- Se la connessione TCP riesce, il client negozia TLS per connettersi al registrar principale in pool01.contoso.com.
    
- Se il client cerca tutte le voci memorizzate nella cache senza una connessione riuscita, l'utente riceve una notifica che non è disponibile al momento nessun server che esegue Skype for Business Server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso da DNS round robin (DNS RR), che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per assegnare un ordine diverso agli indirizzi IP per i server nel pool. In genere, DNS RR Abilita la distribuzione del carico, ma non consente di abilitare il failover. Se ad esempio la connessione all'indirizzo IP restituito dalla query DNS A (o AAAA in uno scenario IPv6) non riesce, la connessione non riuscirà. Che rende il record DNS meno affidabile del bilanciamento del carico basato su DNS. È comunque possibile usare il record DNS in combinazione con il bilanciamento del carico basato su DNS, se necessario. 
  
Si usa il bilanciamento del carico DNS per:
  
- Bilanciamento del carico SIP da server a server per gli Edge Server.
    
- Bilanciamento del carico delle applicazioni UCAS (Unified Communication Application Services), come l'operatore automatico di conferenza, il gruppo di risposte e il parcheggio delle chiamate.
    
- Impedire le nuove connessioni alle applicazioni di UCAS (note anche come svuotamento).
    
- Bilanciamento del carico tutto il traffico client-server tra client e Edge Server.
    
Non è possibile usare il bilanciamento del carico DNS per:
  
- Traffico Web da client a server ai server front-end o a un amministratore.
    
Per approfondire il modo in cui un record SRV DNS è selezionato quando i record DNS di mutiple vengono restituiti da una query, il servizio di Access Edge seleziona sempre il record con la priorità numerica più bassa e, se è necessario un tie-breaker, il peso numerico più elevato. Ciò è coerente con la [documentazione di Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Ad esempio, se il primo record SRV DNS ha un peso di 20 e una priorità di 40, mentre il secondo record SRV DNS ha un peso di 10 e una priorità di 50, verrà scelto il primo record perché ha la priorità inferiore di 40. La priorità passa sempre prima e questo è l'host che verrà destinato prima a un cliente. Cosa fare se sono presenti due obiettivi con la stessa priorità? 
  
In questo caso, il peso viene considerato. I pesi più grandi dovrebbero avere una probabilità elevata, in questa circostanza, di essere selezionati. Gli amministratori DNS dovrebbero usare il peso 0 quando non è presente alcuna selezione del server. In presenza di record che contengono pesi superiori a 0, i record con peso 0 hanno una probabilità molto piccola di apportare la selezione.
  
Quindi, cosa succede se più record SRV DNS con priorità uguale e peso come restituiti? In questa situazione, il servizio Access Edge sceglierà il record SRV ottenuto dal server DNS per primo.
  

