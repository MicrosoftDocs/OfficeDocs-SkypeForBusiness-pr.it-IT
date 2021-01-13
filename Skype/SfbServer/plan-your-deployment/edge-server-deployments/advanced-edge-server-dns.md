---
title: Pianificazione DNS avanzata del server perimetrale per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: esaminare gli scenari per le opzioni di distribuzione di Skype for Business Server. Se si desidera un singolo server o si preferisce un pool di server con DNS o HLB, questo argomento dovrebbe essere di aiuto.'
ms.openlocfilehash: 8615e0111385163b73558e5b76130f670f5d2db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813826"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Pianificazione DNS avanzata del server perimetrale per Skype for Business Server
 
**Riepilogo:** Esaminare gli scenari per le opzioni di distribuzione di Skype for Business Server. Se si desidera un singolo server o si preferisce un pool di server con DNS o HLB, questo argomento dovrebbe essere di aiuto.
  
Quando si tratta di pianificazione DNS (Domain Name System) per Skype for Business Server, esistono numerosi fattori che possono rivestire la propria decisione. Se la struttura del dominio dell'organizzazione è già attiva, potrebbe essere necessario esaminare la modalità di esecuzione. Inizieremo con gli argomenti riportati di seguito:
  
- [Procedura dettagliata dei client Skype for business che individuano i servizi](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS split-brain](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configurazione automatica senza DNS split-brain](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Ripristino di emergenza DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [Bilanciamento del carico DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Procedura dettagliata dei client Skype for business che individuano i servizi
<a name="WalkthroughOfSkype"> </a>

I client Skype for business sono simili alle versioni precedenti dei client Lync in modalità di ricerca e accesso ai servizi in Skype for Business Server. In questa sezione viene illustrata la procedura del percorso del server.
  
1. LyncdiscoverInternal.\<domain\>
    
     *Si tratta di un record host a per il servizio di individuazione automatica sui servizi Web interni.* 
    
2. Lyncdiscover.\<domain\>
    
     *Si tratta di un record host a per il servizio di individuazione automatica sui servizi Web esterni.* 
    
3. _sipinternaltls _sipinternaltls._tcp.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS interne.* 
    
4. _sip _sip._tls.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS esterne.* 
    
5. sipinternal.\<domain\>
    
     *Si tratta di un record host a per il pool Front end o il server Director, risolvibile solo nella rete interna.* 
    
6. SIP.\<domain\>
    
     *Si tratta di un record host a per il pool Front end o il server Director, risolvibile solo nella rete interna.* 
    
7. sipexternal.\<domain\>
    
     *Si tratta di un record host a per il servizio Access Edge, quando il client è esterno.* 
    
Il servizio di individuazione automatica è sempre favorito poiché questo è il metodo preferito per il percorso del servizio e gli altri sono metodi di fallback.
  
> [!NOTE]
> Quando si creano record SRV, è importante ricordare che è necessario puntare a un DNS a (e AAAA se si utilizza l'indirizzamento IPv6) nello stesso dominio in cui viene creato il record DNS SRV. Ad esempio, se i record SRV sono in contoso.com, il record A (e AAAA) che punta a non può essere in fabrikam.com. 
  
Se si è inclini a farlo, è possibile impostare il dispositivo mobile per la ricerca manuale dei servizi. Se si desidera eseguire questa operazione, ogni utente deve configurare le impostazioni dei dispositivi mobili con gli URI del servizio di individuazione automatica interni ed esterni, inclusi il protocollo e il percorso, come indicato di seguito:
  
- Per l'accesso esterno: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/root
    
- Per l'accesso interno: https:// \<IntPoolFQDN\> /autodiscover/autodiscover.svc/root
    
È consigliabile utilizzare l'individuazione automatica anziché la ricerca manuale. Tuttavia, se si stanno eseguendo alcuni test o la risoluzione dei problemi, le impostazioni manuali possono essere molto utili.
  
## <a name="split-brain-dns"></a>DNS split-brain
<a name="SplitBrainDNS"> </a>

Si tratta di una configurazione DNS in cui si dispone di due aree DNS con lo stesso spazio dei nomi. La prima area DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne.
  
Perché una società dovrebbe procedere in questo modo? Potrebbe essere necessario utilizzare lo stesso spazio dei nomi internamente ed esternamente, ma naturalmente ciò comporterà la presenza di molti DNS SRV e di un record univoci in un'area o in un'altra e, in caso di duplicazione, gli indirizzi IP associati a questi record sarebbero univoci.
  
Questo presenta alcune sfide. La cosa più importante è che il DNS split-brain **non è supportato** per la mobilità. Ciò si verifica a causa dei record DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve essere definito sul server DNS esterno, mentre LyncDiscoverInternal deve essere definito nel server DNS interno).
  
Di seguito vengono elencati i record DNS per le aree interne ed esterne, ma è possibile trovare esempi dettagliati sulla sezione requisiti ambientali dei server perimetrali.
  
### <a name="internal-dns"></a>DNS interno

- Contiene un'area DNS chiamata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questo contoso.com interno contiene:
    
  - DNS A e AAAA (se si utilizzano i record di indirizzamento IPv6) per il pool Front End, il pool di server Director o il nome del pool di Director e tutti i server interni che eseguono Skype for business, nella rete dell'organizzazione.
    
  - DNS A e AAAA (se si utilizzano i record di indirizzamento IPv6) per l'interfaccia interna del server perimetrale per ogni server Edge di Skype for business.
    
  - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) record per l'interfaccia interna di ogni server proxy inverso nella rete perimetrale (che è **facoltativo** per la gestione di un proxy inverso).
    
  - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client Skype for Business Server interno ( **facoltativo** ).
    
  - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o i record CNAME per l'individuazione automatica dei servizi Web di Skype for Business Server ( **facoltativo** ).
    
- Tutte le interfacce Edge interne di Skype for Business Server nella rete perimetrale utilizzano questa area DNS interna per la risoluzione delle query in contoso.com.
    
- Tutti i server che eseguono Skype for Business Server e i client che eseguono Skype for Business Server nella rete aziendale, fanno riferimento ai server DNS interni per la risoluzione delle query in contoso.com oppure utilizzano il file host in ogni server perimetrale ed elencano i record A e AAAA (se si utilizzano gli indirizzi IPv6) per il server dell'hop successivo (in particolare per il VIP del Director o del pool , Il VIP del pool Front end o il server Standard Edition.
    
### <a name="external-dns"></a>DNS esterno

- Contiene un'area DNS chiamata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questo contoso.com esterno contiene:
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6), o record CNAME, per l'individuazione automatica dei servizi Web di Skype for Business Server. Questo è per l'utilizzo con i dispositivi mobili.
    
  - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna perimetrale di ogni VIP di Skype for Business Server Edge Server o hardware con bilanciamento del carico (HLB) nella rete perimetrale.
    
  - DNS A e AAAA (se si sta utilizzando l'indirizzamento IPv6) e i record SRV per l'interfaccia esterna del server proxy inverso o (VIP per un pool di server proxy inversi), nella rete perimetrale.
    
  - DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e i record SRV per la configurazione automatica del client Skype for Business Server ( **facoltativo** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split-brain
<a name="NoSplitBrainDNS"> </a>

Se non si usa il DNS split-brain, la configurazione automatica interna dei client che eseguono Skype for business non funzionerà a meno che non si utilizzi una delle soluzioni alternative disponibili in questo articolo. Perché? Poiché Skype for Business Server richiede l'URI SIP dell'utente in modo che corrisponda al dominio del pool Front End designato per la configurazione automatica. Questo non è cambiato dalle versioni precedenti di Lync Server.
  
Pertanto, se si dispone di due domini SIP in uso, è necessario questi record DNS SRV:
  
- _sipinternaltls _sipinternaltls._tcp. contoso. com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se un utente accede come bob@contoso.com, il record funzionerà per la configurazione automatica, in quanto il dominio SIP dell'utente corrisponde al dominio del pool Front End (contoso.com).* 
    
- _sipinternaltls _sipinternaltls._tcp. fabrikam. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se un utente accede come alice@fabrikam.com, il record funzionerà per la configurazione automatica del secondo dominio, perché il dominio SIP corrisponde al pool Front end per il dominio.* 
    
Per fare questo esempio, non funzionerebbe:
  
- _sipinternaltls _sipinternaltls._tcp. litwareinc. com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utente che accede come tim@litwareinc.com non funzionerà per la configurazione automatica, perché il suo dominio SIP (litwareinc.com) non corrisponde al dominio del pool (fabrikam.com).* 
    
Ora che sappiamo tutto questo, se è necessario un requisito automatico per i client Skype for business senza DNS split-brain, sono disponibili le seguenti opzioni:
  
- **Oggetti Criteri di gruppo**
    
    È possibile utilizzare gli oggetti Criteri di gruppo per popolare i valori del server corretti.
    
    > [!NOTE]
    > Questa opzione non Abilita la configurazione automatica, ma automatizza la configurazione manuale. Se si utilizza questo approccio, i record SRV associati alla configurazione automatica non sono necessari. 
  
- **Area interna corrispondente**
    
    È necessario creare un'area nel DNS interno che corrisponda alla zona DNS esterna (ad esempio, contoso.com) e quindi creare record DNS A (e AAAA se si utilizza l'indirizzamento IPv6) che corrispondono al pool di Skype for Business Server utilizzato per la configurazione automatica.
    
    Ad esempio, se si dispone di un utente ospitato in pool01.contoso.net, ma si accede a Skype for business come bob@contoso.com, creare una zona DNS interna denominata contoso.com e al suo interno è necessario creare un record DNS A (e AAAA se viene utilizzato l'indirizzamento IPv6) per pool01.contoso.com.
    
- **Area interna del pin-point**
    
    Se la creazione di un'intera area nel DNS interno non è un'opzione per l'utente, è possibile creare zone con pin-point (dedicate) corrispondenti ai record SRV necessari per la configurazione automatica e popolare tali aree utilizzando dnscmd.exe. Dnscmd.exe è necessario perché l'interfaccia utente DNS non supporta la creazione di aree a punti pin.
    
    Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front End denominato Pool01 che contiene due front end server, sarà necessario disporre delle seguenti aree di pin-point e di un record nel DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    È possibile che si disponga di un secondo dominio SIP nell'ambiente. In tal caso, è necessario disporre delle seguenti aree pin-point e di un record nel DNS interno:
    
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
> Verrà visualizzato il nome FQDN del pool Front End doppio, ma con due indirizzi IP diversi. Questo perché viene utilizzato il bilanciamento del carico DNS. Se viene utilizzato HLB, è presente una sola voce del pool Front end. 
  
> [!NOTE]
> Inoltre, i valori FQDN del pool Front End cambiano tra gli esempi contoso.com e fabrikam.com, ma gli indirizzi IP rimangono invariati. Ciò è dovuto al fatto che gli utenti che accedono da un dominio SIP utilizzeranno lo stesso pool Front end per la configurazione automatica. 
  
## <a name="dns-disaster-recovery"></a>Ripristino di emergenza DNS
<a name="DNSDR"> </a>

Per configurare il DNS in modo da reindirizzare il traffico Web di Skype for Business Server ai siti di ripristino di emergenza (DR) e di failover, è necessario utilizzare un provider DNS che supporti GeoDNS. È possibile configurare i record DNS per supportare il ripristino di emergenza, in modo che le funzionalità che utilizzano i servizi Web continuino anche se un intero pool Front-end viene interrotto. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di individuazione, riunione e accesso esterno.
  
È possibile definire e configurare i record host DNS aggiuntivi A (AAAA se si utilizza IPv6) per la risoluzione interna ed esterna dei servizi Web nel provider di GeoDNS. Nei dettagli seguenti si presuppone che i pool associati, distribuiti geograficamente e che il GeoDNS supportato **dal provider disponga** di Round Robin DNS **o** sia configurato per l'utilizzo di pool1 come principale e che non riesca a Pool2 in caso di perdita di comunicazioni o di interruzioni dell'alimentazione.
  
Tutti i record DNS di questa tabella sono esempi.
  
|**Record GeoDNS**|**Record del pool**|**Record CNAME**|**Impostazioni DNS (selezionare un'opzione)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com a Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin tra pool  <br/> **O** <br/> Utilizzo primario, connessione a secondario se si verifica un errore  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="DNSLB"> </a>

Il bilanciamento del carico DNS è in genere implementato a livello di applicazione. L'applicazione, ad esempio un client che esegue Skype for business, tenta di connettersi a un server in un pool collegandosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per il nome di dominio completo del pool.
  
Ad esempio, se sono presenti tre Front End Server in un pool denominato pool01.contoso.com, si verificherà quanto segue:
  
- Client che eseguono il DNS di query Skype for business per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come indicato di seguito (in un ordine):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Il client tenta di stabilire una connessione TCP a uno degli indirizzi IP. In caso di esito negativo, proverà il successivo indirizzo IP memorizzato nella cache da tale elenco.
    
- Se la connessione TCP ha esito positivo, il client negozia TLS per la connessione al servizio di registrazione principale su pool01.contoso.com.
    
- Se il client cerca tutte le voci memorizzate nella cache senza una connessione riuscita, l'utente riceve una notifica che non è disponibile al momento nessun server che esegue Skype for Business Server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso dal DNS round robin (RR DNS), che in genere si riferisce al bilanciamento del carico facendo affidamento sul DNS per fornire un diverso ordine di indirizzi IP per i server del pool. In genere, l'RR DNS attiva la distribuzione del carico, ma non consente di abilitare il failover. Ad esempio, se la connessione a un indirizzo IP restituito dalla query DNS A (o AAAA in uno scenario IPv6) ha esito negativo, la connessione avrà esito negativo. Che rende il record DNS meno affidabile rispetto al bilanciamento del carico basato su DNS. Se necessario, è comunque possibile utilizzare l'RR DNS insieme al bilanciamento del carico basato su DNS. 
  
È possibile utilizzare il bilanciamento del carico DNS per:
  
- Bilanciamento del carico SIP da server a server ai server perimetrali.
    
- Il bilanciamento del carico applica le applicazioni di servizi di comunicazione unificata (unificate), ad esempio operatore automatico conferenze, Response Group e parcheggio di chiamata.
    
- Impedire nuove connessioni alle applicazioni di unificate (note anche come svuotamento).
    
- Bilanciamento del carico tutto il traffico da client a server tra client e server perimetrali.
    
Non è possibile utilizzare il bilanciamento del carico DNS per:
  
- Traffico Web da client a server verso i Front End Server o un Director.
    
Per approfondire la modalità di selezione di un record DNS SRV quando i record DNS di mutiple vengono restituiti da una query, il servizio Access Edge sceglie sempre il record con la priorità numerica più bassa e, se è necessario un tie-breaker, il peso numerico più alto. Questo è coerente con la [documentazione di Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Ad esempio, se il primo record DNS SRV ha un peso di 20 e una priorità di 40 e il secondo record DNS SRV ha un peso di 10 e una priorità di 50, il primo record verrà scelto perché ha la priorità più bassa di 40. La priorità va sempre prima e questo è l'host che un client avrà come destinazione per primo. Che cosa succede se sono presenti due obiettivi con la stessa priorità? 
  
In tal caso, il peso viene considerato. I pesi maggiori devono avere una probabilità elevata, in questa circostanza, di essere selezionati. Gli amministratori DNS devono utilizzare il peso 0 quando non è presente alcuna selezione del server. In presenza di record che contengono pesi maggiori di 0, i record con peso 0 hanno una possibilità molto piccola di portare selezionata.
  
Quindi, cosa succede se sono presenti più record DNS SRV con priorità e peso uguali a quelli restituiti? In questa situazione, il servizio Access Edge sceglierà il record SRV ottenuto dal server DNS per primo.
  

