---
title: "Flusso delle chiamate con ExpressRoute"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione."
---

# Flusso delle chiamate con ExpressRoute

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](413acb29-ad83-4393-9402-51d88e7561ab.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/413acb29-ad83-4393-9402-51d88e7561ab). 
  
Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.
  
Se si distribuisce Skype for Business Online come parte di Office 365, Skype for Business Server ibrido o Skype per Business Cloud connettore Edition, sarà necessario comprendere in modo le comunicazioni tra Skype for Business client e server e il flusso di chiamata è in modo efficace può pianificare, installare, operare e risolvere i problemi del Skype per Business Online services.
  
## Panoramica sul flusso delle chiamate

In questo documento vengono illustrati la rete segmenti che possono svolgere dati per le chiamate scorra e aiuta a capire quali il traffico rimarranno locali alla rete rispetto al traffico trasferiti tramite Internet o ExpressRoute. Conoscere il tipo di traffico utilizza ExpressRoute consente di valutare i vantaggi che riceverà la propria azienda tramite ExpressRoute, nonché consente di comprendere la Guida alla distribuzione ExpressRoute per convalidare e risolvere i problemi di distribuzione dopo aver deciso Per utilizzare ExpressRoute.
  
Sui flussi delle chiamate qui descritti può influire una serie di fattori che puoi controllare, come regole firewall, configurazione NAT, proxy e configurazione dei router. In questo documento si suppone che siano state applicate le impostazioni consigliate. Tali impostazioni consigliate sono descritte in:
  
- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Azure ExpressRoute per Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/)
    
Il programma di installazione e configurazioni che non la procedura di installazione disponibile nella documentazione indicata di seguito possono avere flussi chiamata diverso rispetto a quelle ottenute che sono state descritte di seguito. Inoltre, potrebbero risultare se stessi con problemi di configurazione, ad esempio route di rete asimmetrici e non ottimale o protocolli di trasporto non ottimale. Routing asimmetrici è importante ogni volta che interessa ExpressRoute, poiché ExpressRoute introduce un secondo percorso a Office 365, che consente di creare la possibilità di una route che utilizza Internet in un'unica direzione e un'altra route che utilizza ExpressRoute in altra direzione. Questo può comportare il traffico bloccato nella direzione restituita se scorre un firewall.
  
## Segmenti di rete e tipi di traffico

### Segmenti di rete

Prima di illustrare il flusso delle chiamate, dobbiamo definire alcuni termini che ti aiuteranno a comprendere i segmenti di rete e i tipi di elementi multimediali utilizzati in Skype for Business online. 
  
I diagrammi di flusso chiamata riportata di seguito mostra quattro segmenti di rete diversa, ognuno dei quali vengono gestite da organizzazioni diverse (rete interna, il provider di servizi e i partner peering Internet e Microsoft) differenti caratteristiche delle prestazioni. Per indicazioni sul destinazioni prestazioni di rete, fare riferimento alla [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
Di seguito puoi vedere ciascun segmento di rete di cui parleremo.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **La rete** Questo è il segmento di rete che fa parte della rete complessiva che è possibile controllare e gestire. Questo include tutte le connessioni all'interno delle sedi cablata o wireless tra edifici di office, al data center locale e le connessioni al provider di servizi Internet o ExpressRoute partner.
  
In genere, il bordo della rete è uno o più rete Perimetrale con firewall e/o il server proxy, quale applicare i criteri di sicurezza dell'organizzazione e di solo determinato il traffico di rete che è stato impostato e configurato. Perché è gestire la rete, è possibile controllare direttamente le prestazioni della rete e si consiglia aver completato le valutazioni di rete per convalidare prestazioni sia all'interno dei siti della rete e di rete per Skype for Business In linea. Per informazioni sui requisiti di prestazioni, vedere [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
 **Internet** Questo è il segmento di rete che fa parte della rete complessiva che verrà utilizzata dagli utenti che si connette a Skype for Business Online da fuori rete e viene utilizzati per tutte le connessioni quando non è configurato ExpressRoute. Internet e tutte le connessioni non sono gestite dall'utente o Microsoft, in modo che non è possibile determinare le prestazioni e percorsi di routing e si avrà il massimo impatto sul flusso di chiamate e sulla qualità complessiva.
  
 **ExpressRoute** Questo è il segmento di rete che fa parte della rete complessiva in grado di offrire una connessione dedicata, privata alla rete Microsoft. Questa è l'opzione consigliata per la connessione di rete alla rete Microsoft (Data Center di Office 365) per tutti i carichi di lavoro che dipendono dalla velocità della rete e le prestazioni, ad esempio Skype for Business Online comunicazione in tempo reale. ExpressRoute delle connessioni tra la rete e l'utilizzo di rete Microsoft[provider connettività ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) per fornire una rete privata e gestita con 99,9 inattività e il supporto di qualità del servizio (QoS) che migliorare le prestazioni per i file multimediali in tempo reale durante i periodi di eccessivo traffico sulla rete.
  
 **Rete di Microsoft** Questo è il segmento di rete che fa parte della rete complessiva che supporta i servizi di Office 365. Questo include tutte le comunicazioni tra server Online per Office 365. Può trattarsi di traffico che attraversa dorsale di rete Microsoft e trasmesse tra le aree geografiche.
  
### Tipi di traffico

Il traffico di rete per Skype for Business Online può essere suddiviso in due categorie, visualizzate come tracciati nel flusso di chiamata:
  
 **Elementi multimediali in tempo reale** dati racchiusa RTP (Real Transport Protocol) e supporta l'audio, video, la condivisione delle applicazioni e carichi di lavoro di trasferimento file. In generale, il traffico multimediale è altamente latenza riservata, in modo che il traffico per rendere il percorso più diretto possibile e per l'utilizzo UDP come protocollo di livello di trasporto perché utilizzando TCP introduce latenza superiore.
  
 **Segnalazione** è il collegamento di comunicazione tra il client e server, o altri client utilizzati per controllare le attività (ad esempio, quando viene avviata una chiamata) e recapita messaggi istantanei. Maggior parte del traffico segnalazione il protocollo SIP, anche se alcuni client di utilizzare interfacce resto basate su HTTP. Per rendere più semplice, si sta valutando la possibilità di una serie che segnala che può avvenire tramite connessioni HTTP e HTTPS o TLS in questo tipo di traffico. È importante comprendere che il traffico è molto meno sensibile a latenza, ma potrebbe causare interruzioni del servizio o di chiamarlo timeout se latenza tra i punti finali superiore alcuni secondi.
  
Le destinazioni per il traffico si trovano in [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per tutti i servizi di Office 365. Per ogni URL indica se la parte del traffico potrebbe scorrere il ExpressRoute per Office 365. Per i diagrammi che mostrano Internet viene ancora utilizzato per una parte del traffico quando è abilitata ExpressRoute, vedere[Azure ExpressRoute per Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). È importante tenere presente che anche URL elencati come routing su ExpressRoute anche routing tramite Internet. Questo significa che in alcuni casi la determinazione sulla che verrà utilizzata in Internet ExpressRoute varia in base alla posizione client e la configurazione del server proxy e firewall. È anche importante tenere presente che, poiché non tutti gli URL associati a Office 365 in grado di utilizzare ExpressRoute, è necessaria una connessione Internet, anche se si acquista ExpressRoute da un partner ExpressRoute.
  
Il traffico che può essere inviato solo via Internet include dipendenze Internet comuni, ad esempio degli elenchi di revoche di certificati (CRL), le ricerche DNS e la risoluzione dei nomi, gli URL di servizi condivisi di Office 365, ad esempio per l'interfaccia di amministrazione di Office 365 e alcune non-in tempo reale caratteristiche di comunicazione di Skype for Business Online, ad esempio telemetria e della federazione per l'interoperabilità con consumer di Skype, come ben elementi multimediali per cui trasmessi in streaming per Skype Meeting Broadcast. Per informazioni su come prendere decisioni, vedere [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) per altre considerazioni quando si pianifica il routing di rete.
  
## Principi dei flussi delle chiamate con Skype for Business

Prima di passare ai dettagli di specifico chiamare scenari di flusso, esistono sei principi generali che consentono di comprendere i flussi di chiamata per Skype for Business.
  
1. Skype per conferenza di lavoro è ospitato nella stessa area in cui è assegnato l'organizzatore della conferenza. Si tratta nel cloud di Office 365 se l'organizzatore non è un utente in linea o in un data center locale se l'organizzatore della riunione è un utente locale.
    
2. Media inviati da un client a una conferenza ospitata sempre del traffico nel server che ospita la conferenza. Può trattarsi di un server locale all'interno di un Data Center gestiti o su un server Online all'interno dell'area di Office 365. Tuttavia, un Edge server viene sempre utilizzato per il flusso di elementi multimediali per le conferenze in linea.
    
3. Il traffico multimediale per le chiamate peer-to-peer effettua il percorso più diretto disponibile. Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile a causa di un blocco del traffico da parte del firewall o per altri motivi, il traffico verrà inoltrato da uno o più server perimetrali.
    
4. Il traffico di segnalazione viene sempre diretto verso il server che ospita l'utente, sia online o locale. Se non è possibile connettersi direttamente al server front end, verrà utilizzato un server perimetrale.
    
5. Gli utenti che partecipano a una conferenza ospitata online utilizzeranno sempre un server perimetrale (o due, se richiesto dalle configurazioni del firewall client).
    
6. Gli utenti che partecipano a una conferenza ospitata localmente in genere non useranno un server perimetrale se la connessione avviene dall'interno della stessa rete che contiene la distribuzione locale, e utilizzeranno uno o due server perimetrali quando la connessione avviene dall'esterno della rete. 
    
Per ulteriori informazioni sul percorso media scelto, vedere [ICE - bordo Media connettività](https://aka.ms/AVEdge). Anche se questo video su Lync Server 2013, i principi e i protocolli anche per Skype for Business.
  
## Flussi delle chiamate di Skype for Business con ExpressRoute

Dopo aver creato la comprensione di quattro segmenti di rete diversa e alcuni principi generali per Skype per i flussi di chiamata Business, è possibile utilizzare che le informazioni utili per capire quali Skype per il traffico Business verranno scorrere un ExpressRoute segmento di rete.
  
In generale, il traffico di rete attraverserà la connessione ExpressRoute se un endpoint è nella tua rete e l'altro endpoint è nel centro dati Office 365. Ciò includerà il traffico di segnalazione tra client e server, il traffico multimediale utilizzato durante le conferenze telefoniche, o le chiamate peer-to-peer che utilizzano un server perimetrale online.
  
Il traffico non è possibile scorrere la connessione ExpressRoute se entrambi gli endpoint sono in grado di comunicare direttamente su internet o si trovano all'interno della rete. Ciò include supporto per le chiamate peer-to-peer, il traffico da Internet destinati a una distribuzione locale o tutto il traffico tra Internet e i server perimetrali di Office 365. Un esempio di questo è un utente partecipa a una conferenza in linea da un albergo.
  
## Flusso delle chiamate di base di Skype for Business

Per aiutarti ad applicare i principi generali dei flussi delle chiamate Skype for Business descritti in precedenza, la seguente sessione di questo articolo presenta diversi diagrammi di riferimento. Non si tratta di un elenco completo di tutti i flussi delle chiamate possibili, ma serve per aiutarti ad applicare i principi illustrati in precedenza. In aggiunta, gli scenari nei diagrammi sono stati scelti per trattare tipi di distribuzione comuni quali Skype for Business online, Business Server Hybrid, Business Cloud Connector Edition e, in un caso speciale, Skype Meeting Broadcast.
  
> [!NOTE]
> Un sottoinsieme del traffico utilizzato da Skype for Business non routing su ExpressRoute e si passerà sempre un percorso Internet. Consultare l' [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare l'URL che è possibile applicare.
  
### Chiamata peer-to-peer per utenti di Office 365 all'interno di rete dei clienti
<a name="bk_Figure2"> </a>

Per le chiamate peer-to-peer, il traffico multimediale effettua il percorso più diretto verso la destinazione. Tuttavia, il traffico di segnalazione è diretto a un centro dati Office 365 dove è ospitato l'utente online. Poiché entrambi gli utenti si trovano sulla stessa rete WAN e nulla impedisce ai client di comunicare direttamente, il flusso dell'elemento multimediale avviene direttamente tra essi. Il traffico di segnalazione per entrambi gli utenti attraversa la connessione ExpressRoute destinata al centro dati di ciascuna organizzazione. Per il flusso delle chiamate di questo scenario, guarda qui.
  
 **Flusso delle chiamate peer-to-peer**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### Utente online sulla tua rete che partecipa a una conferenza ospitata online
<a name="bk_Figure3"> </a>

Nell'esempio peer-to-peer, il traffico multimediale ha sempre il percorso più diretto alla relativa destinazione. Tuttavia, per una conferenza in linea, la destinazione è nel cloud di Office 365. Ciò significa che il traffico di elementi multimediali per tutti gli utenti a partecipare alla conferenza all'interno della rete verrà scorrere la connessione ExpressRoute e il traffico segnalazione percorre nel cloud di Office 365. L'immagine riportata di seguito vengono indicati che elementi multimediali e la segnalazione verrà scorrere la connessione di ExpressRoute per un utente all'interno della rete e verrà transita direttamente su Internet per gli utenti connessi a Internet dall'esterno della rete, ad esempio da un caffè reparto o albergo.
  
Tenere presente che il percorso di una conferenza è definito dall'organizzatore della riunione e non per i partecipanti. Ciò significa che se sono stata pianificata la riunione per un cliente in locale, il traffico multimediale non è possibile scorrere verso il cloud di Office 365 ExpressRoute, ma invece attraversano Internet al data center locale dell'organizzatore della riunione.
  
La destinazione degli elementi multimediali per le conferenze online sarà un centro dati interno al cloud Office 365, ma il centro dati potrebbe trovarsi in una diversa regione geografica rispetto agli utenti che partecipano alla conferenza. Ciò è possibile in uno dei due casi riportati di seguito:
  
- Se l'organizzatore della riunione proviene da un'azienda diversa rispetto ai partecipanti, e la relativa organizzazione è ospitata in una località geografica o paese/regione diversa.
    
- Se un utente partecipa da un paese o una regione diversa rispetto alla posizione dell'organizzazione dell'azienda, sia per il fatto che l'azienda è una multinazionale o che l'utente è in viaggio.
    
Fortuna sull'uso di ExpressRoute in questo scenario è che con il componente aggiuntivo premium ExpressRoute, dati che segue il percorso ExpressRoute passerà automaticamente tra dorsale Microsoft indipendentemente dall'area geografica di appartenenza dell'organizzatore della riunione Data Center dell'organizzazione.
  
 **Flusso delle chiamate di un utente online con riunione online**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### Partecipare a una conferenza ospitata da un utente locale in una distribuzione Business Server Hybrid
<a name="bk_Figure3"> </a>

Tenere presente che il server Servizi di conferenza che supportano le conferenze ospitate sono determinate nel punto in cui è assegnato l'organizzatore della riunione. In questo scenario, elementi multimediali per tutti gli utenti a partecipare a una conferenza pianificata da un utente locale in una distribuzione ibrida verranno spostato un data center locale. Verranno stabilita segnalazione per gli utenti del server Online tramite l'organizzazione nel Cloud Office 365, mentre media tenterà una connessione diretta. In questo scenario, poiché entrambi gli utenti si connettono da all'interno della rete, una connessione di supporto diretto è possibile, in modo ExpressRoute verrà usate solo per segnalazione del traffico per l'utente del server Online. Se un utente del server Online si connette da Internet, gli elementi multimediali Impossibile scorrere ExpressRoute se un server perimetrale Online viene utilizzato per la connessione.
  
 **Flusso delle chiamate per una conferenza ospitata da un utente Business Server Hybrid**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### Server perimetrale locale con conferenze ospitate su Office 365
<a name="bk_Figure5"> </a>

Quando un join utente ibrido un Online ospitato conferenza, è certi che segnalazione ed elementi multimediali verranno destinato nel cloud di Office 365 e dal momento che l'utente è il join da Internet, in genere un percorso internet diretto sarà da prendere. Tuttavia, in alcuni casi, ad esempio a causa di limitazioni firewall, un percorso Internet diretto non è disponibile. In questo caso un Edge server locali può inoltrare il traffico di elementi multimediali, che determina il traffico di elementi multimediali tornare alla rete locale prima di passare circuito ExpressRoute nel cloud di Office 365.
  
 **Utente locale che partecipa a una conferenza telefonica online utilizzando un server perimetrale locale**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Utilizzo di [Skype for Business Online Cloud connettore Edition](https://aka.ms/CloudConnectorInstaller) offre connettività PSTN utilizzando le risorse locali, ad esempio un trunk SIP o un gateway PSTN o utilizzare un dispositivo hardware minimi per l'integrazione con Skype for Business. Con Cloud connettore Edition, gli utenti sono ospitati Online e fungono da utenti Online normale quando non comportano la chiamata plan di messaggistica unificata. Segnalazione per gli scenari PSTN vengano trasferiti tra il client e nel cloud tramite una connessione ExpressRoute se disponibile, e il traffico multimediale che rientri sulla WAN. In questo caso, segnalazione diventa al cloud di Office 365 e termina con il connettore Cloud.
  
 **Chiamata PSTN tramite il sistema telefonico in Office 365 e connettore Cloud**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### Skype Meeting Broadcast con utenti che partecipano da una rete del cliente
<a name="bk_Figure6"> </a>

Skype Meeting Broadcast è una speciale utilizzare maiuscole/minuscole, costituito da una riunione di due parti con ogni parte con i profili di trasporto di rete diversa. La prima parte e quello più importante da un punto di vista della prestazioni di rete, è la riunione interna. Questa è la parte in tempo reale della riunione che include uno o più endpoint client la connessione al server per conferenze nel cloud di Office 365. Dati trasmessi utilizzando questa parte della riunione sono esattamente come nell'esempio sopra, con una partecipazione a utenti di Office 365 e conferenza in linea.
  
Ciò che rende univoco Skype Meeting Broadcast è che la riunione viene distribuita tra un numero elevato di partecipanti utilizzando la trasmissione di una servizio di streaming. La trasmissione streaming servizio non è routing su ExpressRoute, ma utilizza Internet con il supporto opzionale dei servizi di contenuti rete (CDN). Può essere utile facilmente riconoscibile che streaming broadcast è un flusso di elementi multimediali unidirezionale perché i partecipanti ascoltare ma non parlare e supporta il buffer, pertanto è meno sensibile ai problemi di prestazioni di rete, ad esempio latenza, variazione e perdita di pacchetti. Invece di ottimizzare il traffico broadcast per questi problemi, è ottimizzato per l'utilizzo della larghezza di banda dal momento che sono potenzialmente numerosi partecipanti la ricezione di flussi di dati multimediali.
  
 **Skype Meeting Broadcast con utenti della rete del cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## Modelli di flusso delle chiamate per tipo di distribuzione

Con comuni chiamare esempi flusso precedenti e la comprensione dei principi generali che controllano traffico, nella tabella seguente sono fornisca un riepilogo dei modelli di traffico per una combinazione di grandi dimensioni di scenari di distribuzione e l'uso. Le tabelle non acquisiscono tutte le possibili combinazioni di flussi di chiamata, ma essere utili per comprendere ulteriormente i principi generali di flusso di chiamate.
  
Dati di trasmissione e definiti locale per l'organizzazione. non non lasciare la rete dei clienti, Internet o ExpressRoute. I modelli elencati di seguito si basano sulle impostazioni di rete più comuni, ad esempio firewall, federazione e Internet e si suppone che tutte le organizzazioni impegnate in più parti o federati flussi ExpressRoute. In pratica, con diverse impostazioni potrebbe causare traffico diversi da quelli elencati di seguito.
  
### Flussi delle chiamate per Skype for Business online

Skype for Business Online scenari di utilizzo implicano l'invio di utenti a cui sono ospitati Online e possono chiamare dalla rete interna o Internet. Server locali non fanno parte di questi scenari, in modo che tutti i servizi di conferenza o multimediali PSTN verranno spostato nel cloud di Office 365 e gli utenti Online Edge server sarà anche nel cloud.
  
 **Riepilogo dei flussi delle chiamate per Skype for Business online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla tua rete.  <br/> |ExpressRoute  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Office 365 all'interno di rete dei clienti](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|Chiamate peer-to-peer  <br/> |Due client, uno nella rete (interna) e l'altro client su Internet (esterna).  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Internet  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Da Internet al server perimetrale Office 365.  <br/> |[Chiamata peer-to-peer per utenti di Office 365 all'interno di rete dei clienti](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Si presuppone che il firewall blocca le connessioni dirette tra i client, che richiede un server perimetrale Online. Il traffico da utenti interni alla Online Edge server segue percorso simile a quello al server di servizi di conferenza per una conferenza telefonica.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, uno sulla tua rete (interno) e uno presso l'utente online sulla rete dell'organizzazione federata (federato).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente  <br/> |Il client è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza telefonica dall'utente in Internet  <br/> |Client sia il server di Internet e servizi di conferenza nel cloud di Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza ospitata da un server locale di un'altra azienda  <br/> |Il client è sulla tua rete e il server delle conferenze è in un centro dati di terze parti.  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Poiché il server delle conferenze che ospita la conferenza si trova su una rete locale di un cliente diverso, attraverso il cloud Microsoft non passerà alcun dato.  <br/> |
|Chiamata PSTN  <br/> |Client in rete dei clienti e i server sistema telefonico in cloud di Office 365  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Chiamata PSTN  <br/> |Client nei server Internet e di sistema telefonico nel cloud di Office 365  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Gli elementi multimediali e la segnalazione verrà flusso al Data Center di Office 365. Poiché l'endpoint client su Internet, tutti i dati scorrerà al Data Center di Microsoft tramite Internet (anche se è necessario un server perimetrale Online per la connettività).  <br/> |
   
> [!NOTE]
> ExpressRoute verrà utilizzata nel percorso file multimediali da un utente che si trova nella rete aziendale in un Server perimetrale online, ma non utilizzato se viene utilizzato il Edge server per la distribuzione locale del cliente. 
  
### Flussi delle chiamate per Skype for Business Hybrid

Flussi di chiamata ibrido applicano quando si dispone di Skype per la distribuzione di Business che include almeno alcuni utenti che sono disponibili nel server locale. I flussi di chiamata in questa sezione includono entrambi conferenze locale e peer-to-peer o PSTN chiamate con almeno un utente del server locale.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla rete del cliente e ospitati localmente  <br/> |Locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Office 365 all'interno di rete dei clienti](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Poiché gli utenti sono ospitati localmente, il flusso del traffico di segnalazione avviene localmente verso il centro dati locale anziché verso il cloud Office 365.  <br/> |
|Chiamate peer-to-peer  <br/> |Due client, che si connettono entrambi dalla rete del cliente. Uno è ospitato online, mentre l'altro è ospitato localmente.  <br/> |Utente online: ExpressRoute  <br/> Utente locale: locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Office 365 all'interno di rete dei clienti](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Solo l'utente ospitato localmente invia il traffico di segnalazione al cloud Office 365.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, un utente locale sulla rete del cliente (interno) e un utente online presso la rete dell'azienda federata (federato).  <br/> |Utente interno: locale  <br/> Utente federato: ExpressRoute  <br/> |Internet o ExpressRoute (dipende se viene utilizzato un server perimetrale online o locale)  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) e parte di un[Server perimetrale locale con conferenze ospitate su Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) (per il traffico multimediale). <br/> |Si presuppone che il firewall blocca le connessioni dirette tra i client, che richiedono Online Edge server. Stato ghiaccio offrirà Online (in base alla linea) e i server perimetrali locale (in base all'utente locale) per la connettività.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente (conferenza pianificata dall'utente online)  <br/> |L'utente locale è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Risorse del server per una conferenza telefonica sono definite dall'organizzatore della riunione. In questo caso, sono state programmata da un utente in linea, in modo che le risorse sono nel cloud di Office 365.  <br/> |
|Chiamata PSTN  <br/> |Utente locale sulla tua rete e centro dati Skype for Business locale.  <br/> |Locale  <br/> |Locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |Scenario simile a quello per l'uso di Cloud Connector Edition, eccetto per il fatto che l'utente è ospitato localmente, quindi il traffico di segnalazione rimane all'interno della tua rete.  <br/> |
   
### Flussi delle chiamate per Skype for Business con Cloud Connector

Gli utenti che effettuano la connessione a Cloud Connector Edition sono tutti ospitati online. Ciò significa che la conferenza sarà online, e il traffico di segnalazione segue gli stessi modelli degli utenti online. Per gli scenari diversi da quelli delle chiamate PSTN, il flusso delle chiamate sarà esattamente quello descritto in precedenza per Skype for Business online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamata PSTN  <br/> |Utente online sulla tua rete che utilizza Cloud Connector Edition.  <br/> |locale  <br/> |locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|Chiamata PSTN  <br/> |Utente online che utilizza Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinazione di [Server perimetrale locale con conferenze ospitate su Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) e[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6).  <br/> |Gli utenti Internet effettueranno la connessione attraverso il server perimetrale incluso in Cloud Connector, mentre Cloud Connector effettuerà la connessione alla rete PSTN.  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

