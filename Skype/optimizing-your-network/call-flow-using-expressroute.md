---
title: Flusso delle chiamate con ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.
ms.openlocfilehash: 757dc1c918a6d7a78cc636fa5269ce8cad334909
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="call-flow-using-expressroute"></a>Flusso delle chiamate con ExpressRoute

[] Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.
  
Se si sta distribuendo Skype Business online come parte di Office 365, Skype per Business Server ibrido o Skype per Business Cloud connettore Edition, è necessario comprendere la comunicazione tra Skype per client di Business e i server e il flusso delle chiamate in modo è in modo efficace può pianificare, distribuire, operazioni e risolvere i Skype per i servizi in linea aziendale. 
  
## <a name="call-flow-overview"></a>Panoramica sul flusso delle chiamate

In questo documento vengono descritti la rete segmenti che possono portare i dati per le chiamate flussi e aiuta a comprendere il tipo di traffico resterà locali alla propria rete rispetto al traffico trasferiti tramite Internet o ExpressRoute. Conoscere il tipo di traffico utilizza ExpressRoute consente di valutare i vantaggi che l'azienda riceverà tramite ExpressRoute, nonché consente di comprendere la Guida alla distribuzione ExpressRoute per convalidare e risolvere i problemi della distribuzione dopo aver deciso Per utilizzare ExpressRoute.
  
Sui flussi delle chiamate qui descritti può influire una serie di fattori che puoi controllare, come regole firewall, configurazione NAT, proxy e configurazione dei router. In questo documento si suppone che siano state applicate le impostazioni consigliate. Tali impostazioni consigliate sono descritte in:
  
- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Panoramica di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)
    
- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)
    
Il programma di installazione e le configurazioni che non sono seguita la procedura di installazione disponibile nella documentazione relativa alla precedente possono avere flussi di chiamate diverso rispetto a quelle che è stata documentate. Inoltre, è possibile familiarità con problemi di configurazione, ad esempio le route di rete non ottimale e asimmetrica o protocolli di trasporto non ottimali. Routing asimmetrica è un fattore importante ogni volta che interessa ExpressRoute, poiché ExpressRoute introduce un secondo percorso a Office 365, che consente di creare la possibilità di una route che utilizzi Internet unidirezionale e un altro percorso utilizzato ExpressRoute in altra direzione. Ciò può causare un traffico sono bloccato nella direzione restituita se l'attraversamento un firewall.
  
## <a name="network-segments-and-traffic-types"></a>Segmenti di rete e tipi di traffico

### <a name="network-segments"></a>Segmenti di rete

Prima di illustrare il flusso delle chiamate, dobbiamo definire alcuni termini che ti aiuteranno a comprendere i segmenti di rete e i tipi di elementi multimediali utilizzati in Skype for Business online. 
  
I diagrammi di flusso chiamata riportata di seguito mostra quattro segmenti di rete diversa, ognuno dei quali vengono gestiti da diverse organizzazioni (la rete interna, il provider di servizi e i partner peering Internet e Microsoft) con diversi caratteristiche di prestazioni. Per indicazioni sugli obiettivi di prestazioni di rete, vedere [qualità multimediale e le prestazioni di connettività di rete in Skype Business online](media-quality-and-network-connectivity-performance.md).
  
Di seguito puoi vedere ciascun segmento di rete di cui parleremo.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **La rete** Questo è il segmento di rete che fa parte della rete generale che è possibile controllare e gestire. Sono incluse tutte le connessioni all'interno delle sedi se via cavo o wireless tra office edifici, su centri dati locali e le connessioni al provider Internet o ExpressRoute partner.
  
In genere, il bordo della rete con uno o più DMZ con firewall e/o server proxy, quale applicare criteri di protezione dell'organizzazione e che consente solo alcune il traffico di rete impostato e configurato. Poiché è gestire questa rete, è possibile specificare direttamente le prestazioni della rete ed è consigliabile che aver completato le valutazioni di rete per convalidare le prestazioni sia all'interno dei siti della rete e dalla rete di Skype per le aziende In linea. Per verificare i requisiti di prestazioni, vedere [qualità multimediale e le prestazioni di connettività di rete in Skype Business online](media-quality-and-network-connectivity-performance.md).
  
 **Internet** Questo è il segmento di rete che fa parte dell'intera rete che verrà utilizzata da utenti che si connettono a Skype Business online all'esterno della rete e viene utilizzati per tutte le connessioni quando ExpressRoute non è configurato. Internet e tutte le connessioni non vengono gestite dall'utente o Microsoft, in modo che le prestazioni e i percorsi di routing non è possibile determinare e ciò avrà un impatto maggiore nel flusso di chiamate e qualità globali.
  
 **ExpressRoute** Questo è il segmento di rete che fa parte della rete generale in grado di offrire una connessione dedicata, privata a Microsoft network. Questa opzione è consigliata per la connessione alla rete Microsoft network (Office 365 centri dati) per tutti i carichi di lavoro che dipendono velocità di rete e le prestazioni, ad esempio Skype per le comunicazioni in tempo reale in linea di Business. ExpressRoute delle connessioni tra la rete e l'utilizzo di rete Microsoft [provider di connettività ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) per fornire una rete privata e gestita 99,9% tempo di attività e supporto per la qualità del servizio (QoS) che possono migliorare le prestazioni per i segnali multimediali in tempo reale durante i periodi di congestione della rete.
  
 **Microsoft network** Questo è il segmento di rete che fa parte dell'intera rete che supporta i servizi di Office 365. Sono incluse tutte le comunicazioni tra i server Online per Office 365. Ciò potrebbe includere il traffico attraversa il backbone di rete di Microsoft e verrà trasmessi tra regioni geografiche.
  
### <a name="types-of-traffic"></a>Tipi di traffico

Il traffico di rete per Skype Business online può essere suddiviso in due categorie principali, indicate come percorsi distinti nel flusso delle chiamate:
  
 **Multimediali in tempo reale** dati incapsulati all'interno di RTP (Real-time Transport Protocol) e supporta l'audio, video, condivisione di applicazioni e carichi di lavoro di trasferimento file. In generale, il traffico multimediale è elevata latenza e minuscole, in modo che il traffico per rendere il percorso più diretto possibili e sono state introdotte latenza superiore per l'utilizzo UDP come protocollo di trasporto layer perché utilizzando TCP.
  
 **Segnalazione** è il collegamento di comunicazione tra il client e server, o altri client in cui vengono utilizzati per controllare le attività (ad esempio, quando viene avviata una chiamata) e deliver messaggi immediati. La maggior parte dei traffico di segnalazione utilizza il protocollo SIP, anche se alcuni client di utilizzare interfacce REST basato su HTTP. Per rendere più semplice, si sta valutando la possibilità di un'ampia gamma di segnalazione che può avvenire tramite connessioni HTTP e HTTPS o TLS in questo tipo di traffico. È importante comprendere che tale traffico è molto meno sensibile alla latenza, ma possono causare interruzioni del servizio o i timeout di chiamata se la latenza tra gli endpoint supera alcuni secondi.
  
Destinazioni di questo tipo di traffico si trovano in [Office 365 URL e intervalli di indirizzi IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per tutti i servizi di Office 365. Per ogni URL indica se la parte del traffico può attraversare il ExpressRoute per Office 365. Per i diagrammi che illustrano Internet viene ancora utilizzato per la parte del traffico quando è abilitata la ExpressRoute, vedere [ExpressRoute Azure per Office 365](http://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). È importante tenere presente che anche gli URL elencati come instradabili su ExpressRoute anche instradabili su Internet. Ciò significa che in alcuni scenari, la determinazione su che verrà utilizzato Internet o ExpressRoute dipende dalla posizione del client e la configurazione del server proxy e firewall. È inoltre importante tenere presente che poiché non tutti gli URL associate a Office 365 siano in grado di utilizzare ExpressRoute, è necessaria una connessione Internet, anche se si ExpressRoute da un partner ExpressRoute. 
  
Traffico che può essere inviato solo tramite Internet include dipendenze Internet comuni, ad esempio elenchi di revoche di certificati (CRL), le ricerche DNS e la risoluzione dei nomi, gli URL di servizi condivisi di Office 365, ad esempio per l'interfaccia di amministrazione di Office 365 e alcuni non in tempo reale caratteristiche di comunicazione di Skype per Business Online, ad esempio telemetria e la federazione per l'interoperabilità con Skype consumer, come supporto ben trasmesso per trasmettere riunione Skype. Per prendere decisioni, vedere [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) per ulteriori considerazioni durante la pianificazione del routing di rete.
  
## <a name="principles-for-call-flows-with-skype-for-business"></a>Principi dei flussi delle chiamate con Skype for Business

Prima di entrare nei dettagli di scenari di flussi delle chiamate specifici, esistono sei principi generali che ti aiutano a comprendere i flussi delle chiamate per Skype for Business.
  
1. Skype per conferenza Business è ospitato nella stessa area in cui si trova l'organizzatore della conferenza. Questa è nel cloud di Office 365 se l'organizzatore è un utente in linea o in un data center locali se l'organizzatore della riunione è un utente locale.
    
2. Il traffico multimediale inviato da un client a una conferenza ospitata sempre di accedere al server che ospita la conferenza. Può trattarsi di un server locali all'interno di un centro dati che gestiscono o Online all'interno dell'area di Office 365. Tuttavia, un server perimetrale viene sempre utilizzato per il flusso multimediale per le conferenze Online.
    
3. Il traffico multimediale per le chiamate peer-to-peer effettua il percorso più diretto disponibile. Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile a causa di un blocco del traffico da parte del firewall o per altri motivi, il traffico verrà inoltrato da uno o più server perimetrali.
    
4. Il traffico di segnalazione viene sempre diretto verso il server che ospita l'utente, sia online o locale. Se non è possibile connettersi direttamente al server front end, verrà utilizzato un server perimetrale.
    
5. Gli utenti che partecipano a una conferenza ospitata online utilizzeranno sempre un server perimetrale (o due, se richiesto dalle configurazioni del firewall client).
    
6. Gli utenti che partecipano a una conferenza ospitata localmente in genere non useranno un server perimetrale se la connessione avviene dall'interno della stessa rete che contiene la distribuzione locale, e utilizzeranno uno o due server perimetrali quando la connessione avviene dall'esterno della rete. 
    
Per ulteriori informazioni su ulteriori informazioni sul percorso multimediale che sia selezionata, vedere [ICE - connettività multimediale perimetrale](https://aka.ms/AVEdge). Sebbene questo video su Lync Server 2013, i principi e i protocolli comunque valide per Skype per le aziende.
  
## <a name="skype-for-business-call-flows-with-expressroute"></a>Flussi delle chiamate di Skype for Business con ExpressRoute

Dopo aver creato una conoscenza di quattro segmenti di rete diversa e alcuni principi generali per Skype per flussi di chiamate Business, è possibile utilizzare che informazioni utili per comprendere quali Skype per il traffico Business attraversato un ExpressRoute segmento di rete.
  
In generale, il traffico di rete attraverserà la connessione ExpressRoute se un endpoint è nella tua rete e l'altro endpoint è nel centro dati Office 365. Ciò includerà il traffico di segnalazione tra client e server, il traffico multimediale utilizzato durante le conferenze telefoniche, o le chiamate peer-to-peer che utilizzano un server perimetrale online.
  
Il traffico non attraversano la connessione ExpressRoute se entrambi i punti finali sono in grado di comunicare direttamente tramite internet o si trovano all'interno della rete. Ciò include multimediali per le chiamate peer-to-peer, il traffico proveniente da Internet indirizzato a una distribuzione locale o tutto il traffico tra Internet e dei server perimetrali di Office 365. Un esempio di questo oggetto è un utente che accede a una conferenza Online da un albergo.
  
## <a name="basic-skype-for-business-call-flow"></a>Flusso delle chiamate di base di Skype for Business

Per aiutarti ad applicare i principi generali dei flussi delle chiamate Skype for Business descritti in precedenza, la seguente sessione di questo articolo presenta diversi diagrammi di riferimento. Non si tratta di un elenco completo di tutti i flussi delle chiamate possibili, ma serve per aiutarti ad applicare i principi illustrati in precedenza. In aggiunta, gli scenari nei diagrammi sono stati scelti per trattare tipi di distribuzione comuni quali Skype for Business online, Business Server Hybrid, Business Cloud Connector Edition e, in un caso speciale, Skype Meeting Broadcast.
  
> [!NOTE]
> Un sottoinsieme del traffico utilizzato da Skype per Business non instradabile su ExpressRoute e avrà sempre un percorso Internet. Fare riferimento agli [intervalli di indirizzi IP e gli URL di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare gli URL che possono essere coinvolti.
  
### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Chiamate peer-to-peer per gli utenti di Office 365 da all'interno della rete dei clienti
<a name="bk_Figure2"> </a>

Per le chiamate peer-to-peer, il traffico multimediale effettua il percorso più diretto verso la destinazione. Tuttavia, il traffico di segnalazione è diretto a un centro dati Office 365 dove è ospitato l'utente online. Poiché entrambi gli utenti si trovano sulla stessa rete WAN e nulla impedisce ai client di comunicare direttamente, il flusso dell'elemento multimediale avviene direttamente tra essi. Il traffico di segnalazione per entrambi gli utenti attraversa la connessione ExpressRoute destinata al centro dati di ciascuna organizzazione. Per il flusso delle chiamate di questo scenario, guarda qui.
  
 **Flusso delle chiamate peer-to-peer**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utente online sulla tua rete che partecipa a una conferenza ospitata online
<a name="bk_Figure3"> </a>

Nell'esempio peer-to-peer, il traffico multimediale viene sempre il percorso più diretto alla destinazione. Tuttavia, per una conferenza in linea, la destinazione è nel cloud di Office 365. Ciò significa che il traffico multimediale per tutti gli utenti di partecipare alla conferenza all'interno della rete attraversato connessione ExpressRoute e il traffico di segnalazione passa al cloud di Office 365. Nella figura riportata di seguito vengono indicati che multimediali e segnali attraversato connessione ExpressRoute per un utente all'interno della rete e attraversato direttamente Internet per utenti connessi a Internet dall'esterno della rete, ad esempio da una coffee reparto o un hotel.
  
Tenere presente che il percorso di una conferenza viene definito dall'organizzatore della riunione e non da parte dei partecipanti. Ciò significa che se le riunioni pianificate da un'analisi in locale, il traffico multimediale non scorrere verso il cloud di Office 365 ExpressRoute, ma in realtà attraversano Internet al datacenter locali dell'organizzatore della riunione.
  
La destinazione degli elementi multimediali per le conferenze online sarà un centro dati interno al cloud Office 365, ma il centro dati potrebbe trovarsi in una diversa regione geografica rispetto agli utenti che partecipano alla conferenza. Ciò è possibile in uno dei due casi riportati di seguito:
  
- Se l'organizzatore della riunione proviene da un'azienda diversa rispetto ai partecipanti, e la relativa organizzazione è ospitata in una località geografica o paese/regione diversa.
    
- Se un utente partecipa da un paese o una regione diversa rispetto alla posizione dell'organizzazione dell'azienda, sia per il fatto che l'azienda è una multinazionale o che l'utente è in viaggio.
    
La buona notizia sull'utilizzo di ExpressRoute in questo scenario è che con il componente aggiuntivo premium ExpressRoute, dati di seguito il percorso ExpressRoute passa automaticamente tra backbone di Microsoft indipendentemente dall'area geografica dell'organizzatore della riunione Data Center dell'organizzazione.
  
 **Flusso delle chiamate di un utente online con riunione online**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Partecipare a una conferenza ospitata da un utente locale in una distribuzione Business Server Hybrid
<a name="bk_Figure3"> </a>

Tenere presente che i server per conferenze che supportano le conferenze ospitate sono determinati da cui è assegnato l'organizzatore della riunione. In questo scenario verrà flusso multimediale per tutti gli utenti di partecipare a una conferenza pianificata da un utente locale in una distribuzione ibrida a un datacenter in locale. Verrà stabilita segnalazione per gli utenti disponibili Online tramite organizzazione nel Cloud Office 365, mentre media tenterà di una connessione diretta. In questo scenario, poiché entrambi gli utenti si connettono da all'interno della rete, una connessione diretta multimediale è possibile, in modo ExpressRoute viene utilizzata solo per la segnalazione del traffico per l'utente disponibile in linea. Se un utente disponibile in linea si connette da Internet, l'oggetto multimediale può attraversare ExpressRoute se un server perimetrale Online viene utilizzato per la connessione.
  
 **Flusso delle chiamate per una conferenza ospitata da un utente Business Server Hybrid**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Server perimetrale locale con conferenze ospitate su Office 365
<a name="bk_Figure5"> </a>

Quando un join utente ibrida un Online ospitato conferenza, è possibile sapere che segnalazione e multimediali verranno destinato nel cloud di Office 365 e dopo l'utente partecipa da Internet, in genere un percorso internet diretto sarebbe da eseguire. Tuttavia, in alcuni casi, ad esempio a causa di restrizioni di firewall, un percorso Internet diretto non è disponibile. In questo caso, un server perimetrale locale può inoltrare il traffico multimediale, che fa sì che il traffico multimediale tornare alla rete locale prima di passare a commutazione di circuito ExpressRoute nel cloud di Office 365.
  
 **Utente locale che partecipa a una conferenza telefonica online utilizzando un server perimetrale locale**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Utilizzo [Skype per Business Online Cloud connettore Edition](https://aka.ms/CloudConnectorInstaller) offre una connettività PSTN utilizzando le risorse locali, ad esempio un trunk SIP o un gateway PSTN o utilizzare un dispositivo hardware minimo per l'integrazione con Skype per le aziende. Con Cloud connettore Edition, gli utenti sono ospitati in linea e agiscono come utenti Online normali quando non comportano la chiamata dei piani. Segnalazione per gli scenari PSTN verrà viaggi tra il client e il cloud attraverso una connessione ExpressRoute se è disponibile e il traffico multimediale rimanga entro la rete WAN. In questo caso, la segnalazione viene al cloud di Office 365 e termina con il connettore Cloud.
  
 **Chiamata PSTN tramite il sistema telefonico in Office 365 e connettore Cloud**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype Meeting Broadcast con utenti che partecipano da una rete del cliente
<a name="bk_Figure6"> </a>

Trasmissione riunione Skype è una speciale utilizzare case, costituito da una riunione di due parti con ogni parte con profili di trasporto di rete diversa. La prima parte e quella che più ti interessano da un punto di vista delle prestazioni di rete, è la riunione interna. Questa è la parte in tempo reale della riunione che include uno o più endpoint client connessione al server per conferenze nel cloud di Office 365. Dati trasmessi utilizzando questa parte della riunione sono esattamente come illustrato nell'esempio precedente, con un accesso a utenti di Office 365 e conferenza in linea. 
  
Che cosa rende univoco Skype riunione trasmissione sia che la riunione viene distribuita tra un numero elevato di partecipanti alla conferenza utilizzando una trasmissione del servizio di flusso. La trasmissione del servizio di flusso non instradabile su ExpressRoute, ma utilizza Internet con il supporto facoltativo dei servizi (contenuti CDN Network). È utile di riconoscono che il flusso di trasmissione sia un flusso multimediale unidirezionale perché i partecipanti rimanga in attesa, ma non contattare e supporta il buffer, in modo da essere molto meno riservata per problemi di prestazioni di rete, ad esempio latenza, la perdita di pacchetti e l'instabilità. Invece di ottimizzare il traffico di trasmissione per questi problemi, è ottimizzato per l'utilizzo della larghezza di banda dal momento che esiste potenzialmente un numero molto elevato di partecipanti ricevere i flussi di dati multimediali.
  
 **Skype Meeting Broadcast con utenti della rete del cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## <a name="call-flow-patterns-by-deployment-type"></a>Modelli di flusso delle chiamate per tipo di distribuzione

Con più comuni chiamare esempi flusso precedenti e una conoscenza dei principi generali che controllano i modelli di traffico, tabelle riportate di seguito vengono riepilogati dei modelli di traffico per una combinazione di grandi dimensioni degli scenari di distribuzione e utilizzo. Queste tabelle non acquisiscono tutte le combinazioni possibili di flussi di chiamate, ma devono contribuire a comprendere ulteriormente i principi generali di flusso di chiamate.
  
Dati di trasmissione e viene elencati locale per l'organizzazione. non non lasciare la rete di clienti, Internet o ExpressRoute. I formati elencati di seguito si basano sulle impostazioni di rete più comuni, ad esempio firewall, la federazione e Internet e si presuppongono che tutte le organizzazioni necessarie per più partecipanti o federati flussi dispongano ExpressRoute. In pratica, con diverse impostazioni potrebbe causare modelli di traffico diversi rispetto a quelle elencate di seguito.
  
### <a name="call-flows-for-skype-for-business-online"></a>Flussi delle chiamate per Skype for Business online

Skype per gli scenari di utilizzo Business Online coinvolgere gli utenti che si trovano in linea e possono essere chiamata dalla rete interna o Internet. Server locali non fanno parte di questi scenari, in modo che tutti i servizi di conferenza o dal supporto correlate PSTN fluisce nel cloud di Office 365 e gli utenti in linea di Edge server saranno anch'essi nel cloud.
  
 **Riepilogo dei flussi delle chiamate per Skype for Business online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla tua rete.  <br/> |ExpressRoute  <br/> |locale  <br/> |[Chiamate peer-to-peer per gli utenti di Office 365 da all'interno della rete dei clienti](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chiamate peer-to-peer  <br/> |Due client, uno sulla rete (interna) e altri client su Internet (esterno).  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Internet  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Da Internet al server perimetrale Office 365.  <br/> |[Chiamate peer-to-peer per gli utenti di Office 365 da all'interno della rete dei clienti](call-flow-using-expressroute.md#bk_Figure2) <br/> |Si presuppone che tale firewall connessioni dirette blocchi tra i client, che richiede un server perimetrale in linea. Il traffico proveniente da utente interno nel server perimetrale Online segue percorso simile a quella per conferencing server per la conferenza telefonica.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, uno sulla tua rete (interno) e uno presso l'utente online sulla rete dell'organizzazione federata (federato).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente  <br/> |Il client è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a conferenze dall'utente in Internet  <br/> |Client si trova nel server Internet e di conferenza in cloud di Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza ospitata da un server locale di un'altra azienda  <br/> |Il client è sulla tua rete e il server delle conferenze è in un centro dati di terze parti.  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Poiché il server delle conferenze che ospita la conferenza si trova su una rete locale di un cliente diverso, attraverso il cloud Microsoft non passerà alcun dato.  <br/> |
|Chiamata PSTN  <br/> |Client nella rete cliente e server sistema telefonico in cloud di Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chiamata PSTN  <br/> |Client nei server Internet e di sistema telefonico in cloud di Office 365  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |I contenuti multimediali e segnali viene flow al datacenter di Office 365. Poiché l'endpoint client è su Internet, tutti i dati fluisce al datacenter Microsoft tramite Internet (anche se un server perimetrale Online è necessario per la connettività).  <br/> |
   
> [!NOTE]
> ExpressRoute verrà utilizzato sul percorso multimediale da un utente presente nella rete aziendale per un Server Edge in linea, ma non verrà utilizzato se si utilizza il server perimetrale per la distribuzione locale del cliente. 
  
### <a name="call-flows-for-skype-for-business-hybrid"></a>Flussi delle chiamate per Skype for Business Hybrid

Flussi di chiamate ibrida vengono applicate quando si dispone di un Skype per la distribuzione aziendale che include almeno alcuni utenti che sono ospitati in locale. I flussi di chiamate in questa sezione includono entrambe le conferenze locali e chiamate peer-to-peer o PSTN con almeno un utente del server locale.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla rete del cliente e ospitati localmente  <br/> |Locale  <br/> |locale  <br/> |[Chiamate peer-to-peer per gli utenti di Office 365 da all'interno della rete dei clienti](call-flow-using-expressroute.md#bk_Figure2) <br/> |Poiché gli utenti sono ospitati localmente, il flusso del traffico di segnalazione avviene localmente verso il centro dati locale anziché verso il cloud Office 365.  <br/> |
|Chiamate peer-to-peer  <br/> |Due client, che si connettono entrambi dalla rete del cliente. Uno è ospitato online, mentre l'altro è ospitato localmente.  <br/> |Utente online: ExpressRoute  <br/> Utente locale: locale  <br/> |locale  <br/> |[Chiamate peer-to-peer per gli utenti di Office 365 da all'interno della rete dei clienti](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo l'utente ospitato localmente invia il traffico di segnalazione al cloud Office 365.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, un utente locale sulla rete del cliente (interno) e un utente online presso la rete dell'azienda federata (federato).  <br/> |Utente interno: locale  <br/> Utente federato: ExpressRoute  <br/> |Internet o ExpressRoute (dipende se viene utilizzato un server perimetrale online o locale)  <br/> |[Utente online sulla rete partecipa alla conferenza che è ospitato in linea](call-flow-using-expressroute.md#bk_Figure3) e parte del [server perimetrale locali con Office 365 ospitati conferenze](call-flow-using-expressroute.md#bk_Figure5) (per il traffico multimediale). <br/> |Si presuppone un firewall connessioni dirette blocchi tra i client, che richiedono Online Edge server. Negoziazione ICE offrirà i server Edge locali (dall'utente locale) per la connettività sia Online (dall'utente in linea).  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente (conferenza pianificata dall'utente online)  <br/> |L'utente locale è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Risorse server per la conferenza telefonica definite dall'organizzatore della riunione. In questo caso, è stata pianificata da un utente in linea, in modo che le risorse sono nel cloud di Office 365.  <br/> |
|Chiamata PSTN  <br/> |Utente locale sulla tua rete e centro dati Skype for Business locale.  <br/> |Locale  <br/> |Locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scenario simile a quello per l'uso di Cloud Connector Edition, eccetto per il fatto che l'utente è ospitato localmente, quindi il traffico di segnalazione rimane all'interno della tua rete.  <br/> |
   
### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flussi delle chiamate per Skype for Business con Cloud Connector

Gli utenti che effettuano la connessione a Cloud Connector Edition sono tutti ospitati online. Ciò significa che la conferenza sarà online, e il traffico di segnalazione segue gli stessi modelli degli utenti online. Per gli scenari diversi da quelli delle chiamate PSTN, il flusso delle chiamate sarà esattamente quello descritto in precedenza per Skype for Business online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamata PSTN  <br/> |Utente online sulla tua rete che utilizza Cloud Connector Edition.  <br/> |locale  <br/> |locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chiamata PSTN  <br/> |Utente online che utilizza Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinazione di [server perimetrali locali con Office 365 ospitati conferenze](call-flow-using-expressroute.md#bk_Figure5) e [PSTN di chiamata tramite Skype per Business Cloud connettore Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Gli utenti Internet effettueranno la connessione attraverso il server perimetrale incluso in Cloud Connector, mentre Cloud Connector effettuerà la connessione alla rete PSTN.  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Documentazione ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)
