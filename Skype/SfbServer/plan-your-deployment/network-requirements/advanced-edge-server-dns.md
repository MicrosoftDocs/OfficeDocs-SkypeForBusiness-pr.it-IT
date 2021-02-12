---
title: Pianificazione avanzata del DNS dei server perimetrali per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Riepilogo: esaminare gli scenari per le opzioni di distribuzione di Skype for Business Server. Se si desidera un singolo server o si preferisce un pool di server con DNS o HLB, questo argomento dovrebbe essere utile.'
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825326"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Pianificazione avanzata del DNS dei server perimetrali per Skype for Business Server
 
**Riepilogo:** Esaminare gli scenari per le opzioni di distribuzione di Skype for Business Server. Se si desidera un singolo server o si preferisce un pool di server con DNS o HLB, questo argomento dovrebbe essere utile.
  
Quando si tratta di pianificazione DNS (Domain Name System) per Skype for Business Server, ci sono molti fattori che possono prendere la decisione. Se la struttura di dominio dell'organizzazione è già presente, potrebbe essere necessario esaminare come procedere. Inizieremo con gli argomenti disponibili di seguito:
  
- [Procedura dettagliata di individuazione dei servizi da parte dei client Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configurazione automatica senza DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Ripristino di emergenza DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [Bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Procedura dettagliata di individuazione dei servizi da parte dei client Skype for Business
<a name="WalkthroughOfSkype"> </a>

I client Skype for Business sono simili alle versioni precedenti dei client Lync nel modo in cui trovano e accedono ai servizi in Skype for Business Server. In questa sezione viene specificato in dettaglio il processo di percorso del server.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Si tratta di un record host A per il servizio di individuazione automatica nei servizi Web interni.* 
    
2. lyncdiscover.\<domain\>
    
     *Si tratta di un record host A per il servizio di individuazione automatica nei servizi Web esterni.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS interne.* 
    
4. _sip._tls.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS esterne.* 
    
5. sipinternal.\<domain\>
    
     *Si tratta di un record host A per il pool Front End o il Director, risolvibile solo nella rete interna.* 
    
6. sip.\<domain\>
    
     *Si tratta di un record host A per il pool Front End o il Director, risolvibile solo nella rete interna.* 
    
7. sipexternal.\<domain\>
    
     *Si tratta di un record host A per il servizio Access Edge, quando il client è esterno.* 
    
Il servizio di individuazione automatica è sempre il metodo preferito per la posizione del servizio e gli altri sono metodi di fallback.
  
> [!NOTE]
> Quando si creano record SRV, è importante ricordare che devono puntare a un DNS A (e AAAA se si utilizza l'indirizzamento IPv6) nello stesso dominio in cui viene creato il record DNS SRV. Ad esempio, se il record SRV è in contoso.com, il record A (e AAAA) a cui punta non può essere in fabrikam.com. 
  
Se si è propensi a farlo, è possibile configurare il dispositivo mobile per l'individuazione manuale dei servizi. Se si desidera eseguire questa operazione, ogni utente deve configurare le impostazioni dei dispositivi mobili con gli URI completi del servizio di individuazione automatica interno ed esterno, inclusi il protocollo e il percorso, come indicato di seguito:
  
- Per l'accesso esterno: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Per l'accesso interno: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
È consigliabile utilizzare l'individuazione automatica anziché l'individuazione manuale. Tuttavia, se stai eseguendo alcune operazioni di risoluzione dei problemi o test, le impostazioni manuali possono essere molto utili.
  
## <a name="split-brain-dns"></a>DNS split brain
<a name="SplitBrainDNS"> </a>

Si tratta di una configurazione DNS in cui si dispone di due zone DNS con lo stesso spazio dei nomi. La prima zona DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne.
  
Perché un'azienda dovrebbe farlo? Possono avere la necessità di usare lo stesso spazio dei nomi internamente ed esternamente, ma naturalmente questo farà in modo che molti record DNS SRV e A siano univoci per una zona o un'altra e, in caso di duplicazione, gli indirizzi IP associati a questi record saranno univoci.
  
Ciò presenta alcune sfide. Il più importante è che il DNS split brain non **è supportato per** i dispositivi mobili. Ciò è dovuto ai record DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve essere definito nel server DNS esterno, mentre LyncDiscoverInternal deve essere definito nel server DNS interno).
  
I record DNS per le aree interne ed esterne verranno elencati qui, ma è possibile trovare esempi dettagliati nella sezione relativa ai requisiti di ambiente dei server perimetrali.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questa tabella contoso.com contiene:
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per il pool Front End, il pool di server Director o il nome del pool di server Director e tutti i server interni che eseguono Skype for Business Server nella rete dell'organizzazione.
    
  - Record DNS A e AAAA (se si usa l'indirizzamento IPv6) per l'interfaccia interna perimetrale per ogni server perimetrale Skype for Business Server nella rete perimetrale.
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per l'interfaccia  interna di ogni server proxy inverso nella rete perimetrale (facoltativo per la gestione di un proxy inverso).
    
  - Dns A e AAAA (se si utilizza l'indirizzamento IPv6) e record SRV per la configurazione automatica del client Skype for Business Server interno **(facoltativo).**
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o record CNAME per l'individuazione automatica dei servizi Web di Skype for Business Server **(facoltativo).**
    
- Tutte le interfacce perimetrali interne di Skype for Business Server nella rete perimetrale usano questa zona DNS interna per risolvere le query da contoso.com.
    
- Tutti i server che eseguono Skype for Business Server e i client che eseguono Skype for Business Server nella rete aziendale, puntano ai server DNS interni per la risoluzione delle query a contoso.com oppure utilizzano il file Host in ogni server perimetrale ed elencano i record A e AAAA (se si usa l'indirizzamento IPv6) per il server dell'hop successivo (in particolare per il VIP del director o del pool di server Director) , VIP del pool Front End o server Standard Edition).
    
### <a name="external-dns"></a>DNS esterno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questa tabella contoso.com contiene:
    
  - DNS A e AAAA (se si usa l'indirizzamento IPv6) o record CNAME, per l'individuazione automatica dei servizi Web di Skype for Business Server. Questo è per l'uso con i dispositivi mobili.
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e record SRV per l'interfaccia esterna perimetrale di ogni server perimetrale di Skype for Business Server o vip con bilanciamento del carico hardware (HLB) nella rete perimetrale.
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) e record SRV per l'interfaccia esterna del server proxy inverso o (VIP per un pool di server proxy inversa) nella rete perimetrale.
    
  - Dns A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split brain
<a name="NoSplitBrainDNS"> </a>

Se non si usa il DNS split brain, la configurazione automatica interna dei client che eseguono Skype for Business non funzionerà a meno che non si utilizzi una delle soluzioni alternative disponibili qui. Perché? Poiché Skype for Business Server richiede che l'URI SIP dell'utente corrisponda al dominio del pool Front End designato per la configurazione automatica. Ciò non è cambiato rispetto alle versioni precedenti di Lync Server.
  
Pertanto, se si dispone di due domini SIP in uso, sono necessari questi record DNS SRV:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se un utente accede come bob@contoso.com, questo record funzionerà per la configurazione automatica, in quanto il dominio SIP dell'utente corrisponde al dominio del pool Front End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se un utente accede come alice@fabrikam.com, questo record funzionerà per la configurazione automatica del secondo dominio, anche in quanto il dominio SIP corrisponde al pool Front End per tale dominio.* 
    
Per approfondire l'esempio, non sarebbe possibile:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utente che accede come tim@litwareinc.com non funziona per la configurazione automatica, perché il suo dominio SIP (litwareinc.com) non corrisponde al dominio nel pool (fabrikam.com).* 
    
Ora che sappiamo tutto questo, se hai bisogno di un requisito automatico per i client Skype for Business senza DNS split brain, hai queste opzioni:
  
- **Oggetti Criteri di gruppo**
    
    È possibile utilizzare oggetti Criteri di gruppo (GPO) per popolare i valori del server corretti.
    
    > [!NOTE]
    > Questa opzione non abilita la configurazione automatica, ma automatizza la configurazione manuale. Se si usa questo approccio, i record SRV associati alla configurazione automatica non sono necessari. 
  
- **Zona interna corrispondente**
    
    Dovrai creare una zona nel DNS interno corrispondente alla zona DNS esterna (ad esempio, contoso.com) e quindi creare record DNS A (e AAAA se si usa l'indirizzamento IPv6) che corrispondono al pool di Skype for Business Server usato per la configurazione automatica.
    
    Ad esempio, se un utente si trova su pool01.contoso.net, ma accede a Skype for Business come bob@contoso.com, crea una zona DNS interna denominata contoso.com e al suo interno devi creare un record DNS A (e AAAA se viene usato l'indirizzamento IPv6) per pool01.contoso.com.
    
- **Area interna del punto di ancoraggio**
    
    Se la creazione di un'intera zona nel DNS interno non è un'opzione, è possibile creare zone pin-point (dedicate) corrispondenti ai record SRV necessari per la configurazione automatica e popolare tali aree utilizzando dnscmd.exe. Dnscmd.exe è necessario perché l'interfaccia utente DNS non supporta la creazione di zone di punti di ancoraggio.
    
    Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front End denominato pool01 contenente due Front End Server, nel DNS interno saranno necessarie le seguenti zone pin-point e record A:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    È possibile che nell'ambiente sia presente un secondo dominio SIP. In tal caso, nel DNS interno saranno necessarie le seguenti zone pin-point e record A:
    
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
> L'FQDN del pool Front End verrà visualizzato due volte, ma con due indirizzi IP diversi. Questo perché viene utilizzato il bilanciamento del carico DNS. Se viene utilizzato bilanciamento del carico di rete, sarà presente una sola voce del pool Front End. 
  
> [!NOTE]
> Inoltre, i valori fqdn del pool Front End cambiano tra gli esempi contoso.com e fabrikam.com, ma gli indirizzi IP rimangono gli stessi. Ciò è dovuto al fatto che gli utenti che e utilizzano l'accesso da uno dei domini SIP utilizzano lo stesso pool Front End per la configurazione automatica. 
  
## <a name="dns-disaster-recovery"></a>Ripristino di emergenza DNS
<a name="DNSDR"> </a>

Per configurare DNS per reindirizzare il traffico Web di Skype for Business Server ai siti di ripristino di emergenza e failover, è necessario utilizzare un provider DNS che supporta GeoDNS. È possibile configurare i record DNS per supportare il ripristino di emergenza, in modo che le funzionalità che utilizzano i servizi Web continuino anche in caso di insodit di un intero pool Front End. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di individuazione automatica, meet e accesso remoto.
  
È possibile definire e configurare record AAAA (Host AAAA) DNS aggiuntivi per la risoluzione interna ed esterna dei servizi Web presso il provider GeoDNS. I dettagli seguenti presuppongono che i pool associati, distribuiti geograficamente, e che il GeoDNS supportato dal **provider** abbia **DNS** round robin o sia configurato per l'uso di Pool1 come primario ed esere eseguito il fails over a Pool2 in caso di perdita di comunicazioni o interruzione dell'alimentazione.
  
Tutti i record DNS in questa tabella sono esempi.
  
|**Record GeoDNS**|**Record del pool**|**Record CNAME**|**Impostazioni DNS (selezionare un'opzione)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias da Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias da Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias da Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com alias da Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias da Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias da Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OPPURE** <br/> Usa primario, connettiti a secondario in caso di errore  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="DNSLB"> </a>

Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione (ad esempio, un client che esegue Skype for Business) tenta di connettersi a un server in un pool connettendosi a uno degli indirizzi IP restituiti dalla query del record DNS A e AAAA (se si usa l'indirizzamento IPv6) per l'FQDN del pool.
  
Ad esempio, se in un pool denominato pool01.contoso.com sono presenti tre Front End Server, si verifica quanto segue:
  
- I client che eseguono Skype for Business eseguono query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come segue (in un ordine):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Il client tenta di stabilire una connessione TCP a uno degli indirizzi IP. In caso di esito negativo, tenterà l'indirizzo IP successivo memorizzato nella cache dall'elenco.
    
- Se la connessione TCP ha esito positivo, il client negozia TLS per connettersi al registrar principale pool01.contoso.com.
    
- Se il client tenta tutte le voci memorizzate nella cache senza una connessione corretta, l'utente riceve una notifica che indica che al momento non sono disponibili server che eseguono Skype for Business Server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso dal round robin DNS (DNS RR), che in genere fa riferimento al bilanciamento del carico basandosi su DNS per assegnare un ordine diverso di indirizzi IP per i server del pool. In genere, dns RR abilita la distribuzione del carico, ma non consente di abilitare il failover. Ad esempio, se la connessione all'unico indirizzo IP restituito dalla query A (o AAAA DNS in uno scenario IPv6) non riesce, la connessione avrà esito negativo. Ciò rende la RR DNS meno affidabile del bilanciamento del carico basato su DNS. È comunque possibile utilizzare dns RR in combinazione con il bilanciamento del carico basato su DNS, se necessario. 
  
Il bilanciamento del carico DNS consente di:
  
- Bilanciamento del carico SIP da server a server nei server perimetrali.
    
- Bilanciamento del carico delle applicazioni UCAS (Unified Communication Application Services), ad esempio Operatore automatico conferencing, Response Group e Parcheggio di chiamata.
    
- Impedire nuove connessioni alle applicazioni UCAS (noto anche come svuotamento).
    
- Bilanciare il carico di tutto il traffico da client a server tra client e server perimetrali.
    
Non è possibile utilizzare il bilanciamento del carico DNS per:
  
- Traffico Web da client a server verso i Front End Server o un Director.
    
Per informazioni più approfondite su come viene selezionato un record DNS SRV quando i record DNS vengono restituiti da una query, il servizio Access Edge seleziona sempre il record con la priorità numerica più bassa e, se è necessario un tie breaker, il peso numerico più alto. Questo è coerente con la [documentazione della Internet Engineering Task Force.](https://www.ietf.org/rfc/rfc2782.txt)
  
Ad esempio, se il primo record DNS SRV ha un peso di 20 e una priorità di 40 e il secondo record DNS SRV ha un peso di 10 e una priorità di 50, verrà scelto il primo record perché ha la priorità inferiore di 40. La priorità viene sempre la prima e questo è l'host a cui un client sarà destinatario per primo. Cosa succede se sono presenti due destinazioni con la stessa priorità? 
  
In questo caso, viene considerato il peso. A pesi maggiori dovrebbe essere data un'alta probabilità, in questa circostanza, di essere selezionati. Gli amministratori DNS devono usare il peso 0 quando non è disponibile alcuna selezione di server da eseguire. In presenza di record contenenti pesi maggiori di 0, i record con peso 0 hanno una probabilità molto ridotta di portare selezionato.
  
Cosa succede quindi se più record DNS SRV con priorità e peso uguali vengono restituiti? In questo caso, il servizio Access Edge sceglierà prima il record SRV ottenuto dal server DNS.
  

