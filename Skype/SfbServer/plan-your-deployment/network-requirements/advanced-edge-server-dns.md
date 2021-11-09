---
title: Pianificazione avanzata del DNS dei server perimetrali per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: Visualizzare gli scenari per Skype for Business Server di distribuzione. Che si desideri un singolo server o si preferisca un pool di server con DNS o HLB, questo argomento dovrebbe essere utile.
ms.openlocfilehash: 2c9ea99ae8f5ae7c6151dc337bd5571d739ff549
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844109"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Pianificazione avanzata del DNS dei server perimetrali per Skype for Business Server
 
**Riepilogo:** Esaminare gli scenari per Skype for Business Server di distribuzione. Che si desideri un singolo server o si preferisca un pool di server con DNS o HLB, questo argomento dovrebbe essere utile.
  
Quando si tratta di pianificazione dns (Domain Name System) per Skype for Business Server, molti fattori possono essere determinanti per la decisione. Se la struttura di dominio dell'organizzazione è già in atto, potrebbe essere necessario esaminare come procedere. Inizieremo con gli argomenti trovati di seguito:
  
- [Procedura dettagliata di Skype for Business client che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configurazione automatica senza DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Ripristino di emergenza DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [Bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Procedura dettagliata di Skype for Business client che individuano i servizi
<a name="WalkthroughOfSkype"> </a>

Skype for Business client sono simili alle versioni precedenti dei client Lync nel modo in cui trovano e accedono ai servizi in Skype for Business Server. In questa sezione viene dettagliato il processo di percorso del server.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Si tratta di un record host A per il servizio di individuazione automatica nei servizi Web interni.* 
    
2. lyncdiscover.\<domain\>
    
     *Si tratta di un record host A per il servizio di individuazione automatica nei servizi Web esterni.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS interne.* 
    
4. _sip._tls.\<domain\>
    
     *Si tratta di un record SRV per le connessioni TLS esterne.* 
    
5. sipinternal.\<domain\>
    
     *Si tratta di un record host per il pool Front End o il Director, risolvibile solo nella rete interna.* 
    
6. sip.\<domain\>
    
     *Si tratta di un record host per il pool Front End o il Director, risolvibile solo nella rete interna.* 
    
7. sipexternal.\<domain\>
    
     *Si tratta di un record host A per il servizio Access Edge, quando il client è esterno.* 
    
Il servizio di individuazione automatica è sempre preferito perché è il metodo preferito per la posizione del servizio e gli altri sono metodi di fallback.
  
> [!NOTE]
> Quando si creano record SRV, è importante ricordare che devono puntare a un A DNS (e AAAA se si utilizza l'indirizzamento IPv6) nello stesso dominio in cui viene creato il record DNS SRV. Ad esempio, se si tratta di record SRV in contoso.com, il record A (e AAAA) a cui punta non può essere in fabrikam.com. 
  
Se si è propensi a farlo, è possibile configurare il dispositivo mobile per l'individuazione manuale dei servizi. Se si desidera eseguire questa operazione, ogni utente deve configurare le impostazioni del dispositivo mobile con gli URI del servizio di individuazione automatica interni ed esterni completi, inclusi il protocollo e il percorso, come indicato di seguito:
  
- Per l'accesso esterno: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Per l'accesso interno: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
È consigliabile utilizzare l'individuazione automatica anziché l'individuazione manuale. Tuttavia, se stai eseguendo alcuni test o risoluzione dei problemi, le impostazioni manuali possono essere utili.
  
## <a name="split-brain-dns"></a>DNS split brain
<a name="SplitBrainDNS"> </a>

Si tratta di una configurazione DNS in cui sono disponibili due zone DNS con lo stesso spazio dei nomi. La prima zona DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne.
  
Perché un'azienda dovrebbe farlo? Possono avere la necessità di utilizzare lo stesso spazio dei nomi internamente ed esternamente, ma naturalmente questo genererà molti record DNS SRV e A univoci per una zona o un'altra e, in caso di duplicazione, gli indirizzi IP associati a questi record saranno univoci.
  
Questa situazione presenta alcune sfide. Il più importante è che il DNS split brain non **è supportato per** dispositivi mobili. Ciò è dovuto ai record DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve essere definito nel server DNS esterno, mentre LyncDiscoverInternal deve essere definito nel server DNS interno).
  
I record DNS per le zone interne ed esterne verranno elencati qui, ma è possibile trovare esempi dettagliati nella sezione Requisiti ambientali dei server perimetrali.
  
### <a name="internal-dns"></a>DNS interno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questo contoso.com interno contiene:
    
  - Record A e AAAA DNS (se si utilizza l'indirizzamento IPv6) per il pool Front End, il nome del pool di server Director o del pool di server Director e tutti i server interni che eseguono Skype for Business Server nella rete dell'organizzazione.
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per l'interfaccia interna di Edge per ogni server perimetrale Skype for Business Server nella rete perimetrale.
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) per l'interfaccia  interna di ogni server proxy inverso nella rete perimetrale (facoltativo per la gestione di un proxy inverso).
    
  - Dns A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).
    
  - Record DNS A e AAAA (se si utilizza l'indirizzamento IPv6) o record CNAME per l'individuazione automatica dei servizi Web Skype for Business Server **(facoltativo).**
    
- Tutte le Skype for Business Server perimetrali interne nella rete perimetrale utilizzano questa zona DNS interna per la risoluzione delle query contoso.com.
    
- Tutti i server che eseguono Skype for Business Server e i client che eseguono Skype for Business Server nella rete aziendale, puntano ai server DNS interni per la risoluzione delle query su contoso.com oppure utilizzano il file Host in ogni server perimetrale ed elencano i record A e AAAA (se si utilizza l'indirizzamento IPv6) per il server hop successivo (in particolare per il server Director o il pool di server Director)  VIP, VIP del pool Front End o edizione Standard server).
    
### <a name="external-dns"></a>DNS esterno

- Contiene una zona DNS denominata (ad esempio) contoso.com, per la quale è autorevole.
    
- Questa tabella contoso.com contiene:
    
  - DNS A and AAAA (if you're using IPv6 addressing) or CNAME records, for automatic discovery of Skype for Business Server web services. Questo è per l'uso con dispositivi mobili.
    
  - Dns A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.
    
  - Dns A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.
    
  - Dns A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configurazione automatica senza DNS split brain
<a name="NoSplitBrainDNS"> </a>

Se non si utilizza dns split brain, la configurazione automatica interna dei client che eseguono Skype for Business non funzionerà a meno che non si utilizzi una delle soluzioni alternative disponibili qui. Perché? Poiché Skype for Business Server'URI SIP dell'utente deve corrispondere al dominio del pool Front End designato per la configurazione automatica. Questa impostazione non è stata modificata rispetto alle versioni precedenti di Lync Server.
  
Pertanto, se sono in uso due domini SIP, sono necessari questi record DNS SRV:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se un utente accede come bob@contoso.com, questo record funzionerà per la configurazione automatica, poiché il dominio SIP dell'utente corrisponde al dominio del pool Front End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se un utente accede come alice@fabrikam.com, questo record funzionerà per la configurazione automatica del secondo dominio, perché il dominio SIP corrisponde al pool Front End per tale dominio.* 
    
Per approfondire l'esempio, non funziona:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Un utente che accede come tim@litwareinc.com non funziona per la configurazione automatica, perché il dominio SIP (litwareinc.com) non corrisponde al dominio nel pool (fabrikam.com).* 
    
Ora che sappiamo tutto questo, se è necessario un requisito automatico per i client Skype for Business senza DNS split brain, sono disponibili queste opzioni:
  
- **Oggetti Criteri di gruppo (GPO)**
    
    È possibile utilizzare oggetti Criteri di gruppo (GPO) per popolare i valori del server corretti.
    
    > [!NOTE]
    > Questa opzione non abilita la configurazione automatica, ma automatizza la configurazione manuale. Se si usa questo approccio, i record SRV associati alla configurazione automatica non sono necessari. 
  
- **Zona interna corrispondente**
    
    È necessario creare nel DNS interno una zona corrispondente alla zona DNS esterna (ad esempio, contoso.com) e quindi creare record DNS A (e AAAA se si utilizza l'indirizzamento IPv6) che corrispondono al pool di Skype for Business Server utilizzato per la configurazione automatica.
    
    Ad esempio, se un utente si trova su pool01.contoso.net, ma accede a Skype for Business come bob@contoso.com, crea una zona DNS interna denominata contoso.com e al suo interno devi creare un record A DNS (e AAAA se viene utilizzato l'indirizzamento IPv6) per pool01.contoso.com.
    
- **Area interna pin-point**
    
    Se la creazione di un'intera zona nel DNS interno non è un'opzione, è possibile creare zone pin-point (dedicate) che corrispondono ai record SRV necessari per la configurazione automatica e popolare tali zone utilizzando dnscmd.exe. Dnscmd.exe è necessario perché l'interfaccia utente DNS non supporta la creazione di zone pin-point.
    
    Ad esempio, se il dominio SIP è contoso.com e si dispone di un pool Front End denominato pool01 contenente due Front End Server, nel DNS interno saranno necessarie le seguenti zone di punti di ancoraggio e record A:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    È possibile che nell'ambiente sia presente un secondo dominio SIP. In tal caso, nel DNS interno sono necessarie le seguenti zone pin-point e record A:
    
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
> L'FQDN del pool Front End verrà visualizzato due volte, ma con due indirizzi IP diversi. Questo perché viene utilizzato il bilanciamento del carico DNS. Se si usa il bilanciamento del carico di rete, sarà presente una sola voce del pool Front End. 
  
> [!NOTE]
> Inoltre, i valori fqdn del pool Front End cambiano tra gli esempi contoso.com e fabrikam.com, ma gli indirizzi IP rimangono gli stessi. Ciò è dovuto al fatto che gli utenti che amberanno da uno dei due domini SIP utilizzano lo stesso pool Front End per la configurazione automatica. 
  
## <a name="dns-disaster-recovery"></a>Ripristino di emergenza DNS
<a name="DNSDR"> </a>

Per configurare DNS per reindirizzare Skype for Business Server web ai siti di ripristino di emergenza e failover, è necessario utilizzare un provider DNS che supporti GeoDNS. È possibile configurare i record DNS per supportare il ripristino di emergenza, in modo che le funzionalità che utilizzano i servizi Web continuino anche se un intero pool Front End non è più in funzione. Questa funzionalità di ripristino di emergenza supporta gli URL semplici di individuazione automatica, meet e accesso remoto.
  
È possibile definire e configurare record A (AAAA) host DNS aggiuntivi se si utilizza IPv6 per la risoluzione interna ed esterna dei servizi Web presso il provider GeoDNS. I dettagli seguenti presuppongono che i pool associati, geograficamente dislocati, e che geoDNS supportato dal **provider** abbia **DNS** round robin o sia configurato per l'utilizzo di Pool1 come primario ed esepari il pool2 in caso di perdita di comunicazioni o di interruzione dell'alimentazione.
  
Tutti i record DNS in questa tabella sono esempi.
  
|**Record GeoDNS**|**Record del pool**|**Record CNAME**|**Impostazioni DNS (selezionare un'opzione)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias a Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias a Pool2InternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias a Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias a Pool2ExternalWebFQDN.contoso.com  <br/> |Round robin tra pool  <br/> **OR** <br/> Usa principale, connettiti a secondario in caso di errore  <br/> |
   
## <a name="dns-load-balancing"></a>Bilanciamento del carico DNS
<a name="DNSLB"> </a>

Il bilanciamento del carico DNS viene in genere implementato a livello di applicazione. L'applicazione, ad esempio un client che esegue Skype for Business, tenta di connettersi a un server di un pool connettendosi a uno degli indirizzi IP restituiti dalla query di record DNS A e AAAA (se viene utilizzato l'indirizzamento IPv6) per il nome di dominio completo del pool.
  
Ad esempio, se in un pool denominato pool01.contoso.com sono presenti tre Front End Server, si verifica quanto segue:
  
- I client che Skype for Business eseguono query DNS per pool01.contoso.com. La query restituisce tre indirizzi IP e li memorizza nella cache come segue (in un ordine):
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- Il client tenta di stabilire una connessione TCP a uno degli indirizzi IP. In caso di esito negativo, tenterà l'indirizzo IP successivo memorizzato nella cache dall'elenco.
    
- Se la connessione TCP ha esito positivo, il client negozia TLS per connettersi al registrar principale pool01.contoso.com.
    
- Se il client tenta tutte le voci memorizzate nella cache senza una connessione corretta, l'utente riceve una notifica che indica che al momento non sono disponibili Skype for Business Server server.
    
> [!NOTE]
> Il bilanciamento del carico basato su DNS è diverso dal round robin DNS (DNS RR), che in genere si riferisce al bilanciamento del carico basandosi su DNS per assegnare un ordine diverso di indirizzi IP per i server nel pool. In genere, DNS RR abilita la distribuzione del carico, ma non consente di abilitare il failover. Ad esempio, se la connessione all'unico indirizzo IP restituito dalla query DNS A (o AAAA in uno scenario IPv6) ha esito negativo, la connessione avrà esito negativo. Ciò rende la RR DNS meno affidabile del bilanciamento del carico basato su DNS. È comunque possibile utilizzare DNS RR in combinazione con il bilanciamento del carico basato su DNS, se necessario. 
  
Il bilanciamento del carico DNS consente di:
  
- Bilanciamento del carico SIP da server a server nei server perimetrali.
    
- Bilanciamento del carico delle applicazioni UCAS (Unified Communication Application Services), ad esempio servizi di conferenza Operatore automatico, Response Group e Parcheggio di chiamata.
    
- Impedire nuove connessioni alle applicazioni UCAS (noto anche come drenaggio).
    
- Bilanciare il carico di tutto il traffico da client a server tra client e server perimetrali.
    
Non è possibile utilizzare il bilanciamento del carico DNS per:
  
- Traffico Web da client a server per i Front End Server o un Director.
    
Per informazioni più approfondite sulla selezione di un record DNS SRV quando più record DNS vengono restituiti da una query, il servizio Access Edge seleziona sempre il record con la priorità numerica più bassa e, se è necessario un tie-breaker, il peso numerico più alto. Ciò è coerente con la [documentazione relativa all'Internet Engineering Task Force.](https://www.ietf.org/rfc/rfc2782.txt)
  
Ad esempio, se il primo record DNS SRV ha un peso di 20 e una priorità di 40 e il secondo record DNS SRV ha un peso di 10 e una priorità di 50, verrà scelto il primo record perché ha la priorità inferiore di 40. La priorità viene sempre prima di tutto e questo è l'host a cui un client sarà destinatario per primo. Cosa succede se sono presenti due destinazioni con la stessa priorità? 
  
In tal caso, viene considerato il peso. A pesi maggiori dovrebbe essere data una probabilità elevata, in questa circostanza, di essere selezionati. Gli amministratori DNS devono utilizzare il peso 0 quando non è disponibile alcuna selezione di server da eseguire. In presenza di record contenenti pesi superiori a 0, i record con peso 0 hanno una probabilità molto ridotta di portare selezionato.
  
Quindi, cosa succede se più record DNS SRV con priorità e peso uguali vengono restituiti? In questo caso il servizio Access Edge sceglierà prima il record SRV ottenuto dal server DNS.
  

