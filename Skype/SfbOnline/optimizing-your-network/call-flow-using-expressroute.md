---
title: Flusso delle chiamate con ExpressRoute
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.
ms.openlocfilehash: 3d03b9db85d14797a161d781f5bee16edeb581b2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279084"
---
# <a name="call-flow-using-expressroute"></a>Flusso delle chiamate con ExpressRoute

[] Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.

Se si sta distribuendo Skype for business online come parte di Office 365, Skype for Business Server Hybrid o Skype for Business Cloud Connector Edition, è necessario comprendere la comunicazione tra il client e i server Skype for business e il flusso delle chiamate in modo da è possibile pianificare, distribuire, gestire e risolvere i problemi dei servizi Skype for business online in modo efficace.

## <a name="call-flow-overview"></a>Panoramica sul flusso delle chiamate

Questo documento descrive i segmenti di rete che possono trasportare i dati per questi flussi di chiamata e consente di comprendere il traffico che resterà nella rete locale rispetto al traffico che verrà eseguito tramite Internet o tramite ExpressRoute. Conoscere il traffico che usa ExpressRoute ti aiuterà a valutare i vantaggi che la tua azienda riceverà usando ExpressRoute, oltre ad aiutarti a comprendere le linee guida per la distribuzione di ExpressRoute per convalidare e risolvere i problemi di distribuzione dopo aver deciso per usare ExpressRoute.

Sui flussi delle chiamate qui descritti può influire una serie di fattori che puoi controllare, come regole firewall, configurazione NAT, proxy e configurazione dei router. In questo documento si suppone che siano state applicate le impostazioni consigliate. Tali impostazioni consigliate sono descritte in:

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Panoramica di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Le impostazioni e le configurazioni che non hanno seguito la procedura di configurazione trovata nella documentazione precedente possono avere flussi di chiamata diversi da quelli descritti in questo articolo. Inoltre, è possibile che si verifichino problemi di configurazione, ad esempio le route di rete asimmetriche e non ottimali o i protocolli di trasporto non ottimali. Il routing asimmetrico è una considerazione importante ogni volta che ExpressRoute è coinvolto, perché ExpressRoute introduce un secondo percorso di Office 365, che crea la possibilità di una route che usa Internet in un'unica direzione e in un'altra route che usa ExpressRoute nella direzione opposta. Ciò può causare il blocco del traffico nella direzione di ritorno se attraversa un firewall con stato.

## <a name="network-segments-and-traffic-types"></a>Segmenti di rete e tipi di traffico

### <a name="network-segments"></a>Segmenti di rete

Prima di illustrare il flusso delle chiamate, dobbiamo definire alcuni termini che ti aiuteranno a comprendere i segmenti di rete e i tipi di elementi multimediali utilizzati in Skype for Business online.

I diagrammi di flusso delle chiamate seguenti mostrano quattro diversi segmenti di rete, ognuno dei quali è gestito da organizzazioni diverse (la rete interna, il provider di servizi di rete e i partner di peering Internet e Microsoft) che hanno diversi caratteristiche delle prestazioni. Per linee guida sulle destinazioni di prestazioni di rete, vedere [qualità dei contenuti multimediali e prestazioni della connettività di rete in Skype for business online](media-quality-and-network-connectivity-performance.md).

Di seguito puoi vedere ciascun segmento di rete di cui parleremo.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Rete** Questo è il segmento di rete che fa parte della rete globale che controlli e Gestisci. Ciò include tutte le connessioni all'interno degli uffici, sia cablate che wireless, tra edifici di Office, centri dati locali e le connessioni a provider Internet o partner di ExpressRoute.

In genere, il bordo della rete include una o più DMZ con firewall e/o server proxy, che applicano i criteri di sicurezza dell'organizzazione e che consentono solo un determinato traffico di rete configurato e configurato. Poiché Gestisci questa rete, hai il controllo diretto sulle prestazioni della rete e ti consigliamo di completare le valutazioni della rete per convalidare le prestazioni sia all'interno dei siti della rete che dalla rete a Skype for business Online. Per vedere i requisiti delle prestazioni, consulta [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md).

 **Internet** Questo è il segmento di rete che fa parte della rete globale che verrà usata dagli utenti che si connettono a Skype for business online dall'esterno della rete e viene usato per tutte le connessioni quando ExpressRoute non è configurato. Internet e tutte le sue connessioni non sono gestite dall'utente o da Microsoft, quindi non è possibile determinare i percorsi di prestazioni e routing e questo avrà l'impatto maggiore sul flusso di chiamata e sulla qualità generali.

 **ExpressRoute** Si tratta del segmento di rete che fa parte della tua rete complessiva e che ti garantirà una connessione dedicata e privata alla rete Microsoft. Questa è l'opzione consigliata per connettere la rete a Microsoft Network (Datacenter di Office 365) per tutti i carichi di lavoro dipendenti dalla velocità e dalle prestazioni della rete, come le comunicazioni in tempo reale di Skype for business online. Le connessioni ExpressRoute si effettuano tra la rete e la rete Microsoft usano i [provider di connettività di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) per ottenere una rete privata e gestita, con uptime del 99,9% e supporto per la qualità del servizio (QoS) in grado di migliorare le prestazioni per elementi multimediali in tempo reale durante i periodi di congestione della rete.

 **Rete Microsoft** Si tratta del segmento di rete che fa parte della tua rete complessiva che supporta i servizi Office 365. Ciò include tutte le comunicazioni tra i server online per Office 365. Questo può includere il traffico che attraversa la dorsale della rete Microsoft e viene trasmesso tra aree geografiche.

### <a name="types-of-traffic"></a>Tipi di traffico

Il traffico di rete per Skype for business online rientra in due categorie generali, visualizzate come percorsi distinti nel flusso delle chiamate:

 L'elemento **multimediale in tempo reale** è incapsulato in RTP (protocollo di trasporto in tempo reale) e supporta i carichi di lavoro di audio, video, condivisione applicazioni e trasferimento file. In generale, il traffico multimediale è molto sensibile alla latenza, quindi vorresti che il traffico percorresse il percorso più diretto possibile e utilizzasse UDP come protocollo di livello di trasporto perché l'uso di TCP introduce una maggiore latenza.

 La **segnalazione** è il collegamento di comunicazione tra il client e il server o altri client usati per controllare le attività, ad esempio quando viene avviata una chiamata, e inviare messaggi istantanei. La maggior parte del traffico di segnalazione utilizza il protocollo SIP, anche se alcuni client utilizzano interfacce REST basate su HTTP. Per semplificare, stiamo valutando una segnalazione di varietà che potrebbe spostarsi sulle connessioni HTTP e HTTPS o TLS in questo tipo di traffico. È importante comprendere che questo tipo di traffico è molto meno sensibile alla latenza, ma può causare interruzioni di servizio o timeout delle chiamate se la latenza tra gli endpoint supera diversi secondi.

Le destinazioni per questo traffico sono disponibili in [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per tutti i servizi di Office 365. Per ciascun URL, viene indicato se quella porzione di traffico può attraversare ExpressRoute per Office 365. Per i diagrammi che mostrano che Internet viene ancora usato per il traffico quando ExpressRoute è abilitato, vedere [Azure ExpressRoute per Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). È importante comprendere che anche gli URL elencati come instradabili su ExpressRoute sono instradabili anche tramite Internet. Questo significa che in alcuni scenari la determinazione di usare Internet o ExpressRoute dipende dalla posizione del client e dalla configurazione di server proxy e firewall. È anche importante capire che poiché non tutti gli URL associati a Office 365 sono in grado di usare ExpressRoute, è necessaria una connessione Internet anche se si acquista ExpressRoute da un partner di ExpressRoute.

Il traffico che può essere inviato solo su Internet include dipendenze Internet comuni, ad esempio elenchi di revoche di certificati (CRL), ricerche DNS e risoluzione dei nomi, URL per i servizi condivisi di Office 365, ad esempio per l'interfaccia di amministrazione di Office 365 e alcuni tipi di dati non in tempo reale caratteristiche di comunicazione di Skype for business online, come la telemetria e la Federazione per l'interoperabilità con Skype consumer, oltre a contenuti multimediali in streaming per Skype meeting broadcast. Per aiutarti a decidere, consulta [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) per ulteriori considerazioni quando pianifichi il routing della rete.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principi dei flussi delle chiamate con Skype for Business

Prima di entrare nei dettagli di scenari di flussi delle chiamate specifici, esistono sei principi generali che ti aiutano a comprendere i flussi delle chiamate per Skype for Business.

1. Una conferenza Skype for business è ospitata nella stessa area in cui è ospitato l'organizzatore di conferenze. Questa si trova nel cloud Office 365 se l'organizzatore è un utente online, oppure in un centro dati locale se l'organizzatore della riunione è un utente locale.

2. Il traffico multimediale inviato da un client a una conferenza ospitata passa sempre al server in cui è ospitata la conferenza. Può trattarsi di un server locale all'interno di un Data Center gestito o di un server online all'interno del cloud di Office 365. Tuttavia, un server perimetrale viene sempre usato per il flusso multimediale per le conferenze online.

3. Il traffico multimediale per le chiamate peer-to-peer effettua il percorso più diretto disponibile. Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile a causa di un blocco del traffico da parte del firewall o per altri motivi, il traffico verrà inoltrato da uno o più server perimetrali.

4. Il traffico di segnalazione viene sempre diretto verso il server che ospita l'utente, sia online o locale. Se non è possibile connettersi direttamente al server front end, verrà utilizzato un server perimetrale.

5. Gli utenti che partecipano a una conferenza ospitata online utilizzeranno sempre un server perimetrale (o due, se richiesto dalle configurazioni del firewall client).

6. Gli utenti che partecipano a una conferenza ospitata localmente in genere non useranno un server perimetrale se la connessione avviene dall'interno della stessa rete che contiene la distribuzione locale, e utilizzeranno uno o due server perimetrali quando la connessione avviene dall'esterno della rete.

Per ulteriori informazioni sui dettagli relativi al percorso multimediale scelto, consulta [ICE - Connettività degli elementi multimediali perimetrali](https://aka.ms/AVEdge). Anche se questo video riguarda Lync Server 2013, i principi e i protocolli si applicano ancora a Skype for business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flussi delle chiamate di Skype for Business con ExpressRoute

Dopo aver compreso i quattro diversi segmenti di rete e alcuni principi guida generali per i flussi di chiamate Skype for business, è possibile usare queste informazioni per comprendere il traffico di Skype for business che attraverserà un ExpressRoute segmento di rete.

In generale, il traffico di rete attraverserà la connessione ExpressRoute se un endpoint è nella tua rete e l'altro endpoint è nel centro dati Office 365. Ciò includerà il traffico di segnalazione tra client e server, il traffico multimediale utilizzato durante le conferenze telefoniche, o le chiamate peer-to-peer che utilizzano un server perimetrale online.

Il traffico non attraverserà la connessione ExpressRoute se entrambi gli endpoint sono in grado di comunicare direttamente attraverso Internet o si trovano all'interno della tua rete. Verrà incluso il supporto per le chiamate peer-to-peer, il traffico da Internet destinato a una distribuzione locale o il traffico tra Internet e i server Edge di Office 365. Un esempio di ciò potrebbe essere un utente che partecipa a una conferenza online da un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flusso delle chiamate di base di Skype for Business

Per aiutarti ad applicare i principi generali dei flussi delle chiamate Skype for Business descritti in precedenza, la seguente sessione di questo articolo presenta diversi diagrammi di riferimento. Non si tratta di un elenco completo di tutti i flussi delle chiamate possibili, ma serve per aiutarti ad applicare i principi illustrati in precedenza. In aggiunta, gli scenari nei diagrammi sono stati scelti per trattare tipi di distribuzione comuni quali Skype for Business online, Business Server Hybrid, Business Cloud Connector Edition e, in un caso speciale, Skype Meeting Broadcast.

> [!NOTE]
> Un sottoinsieme di traffico usato da Skype for business non è instradabile su ExpressRoute e prende sempre un percorso Internet. Vedere gli URL [e gli intervalli di indirizzi IP di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare gli URL che possono essere interessati.

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Chiamata peer-to-peer per gli utenti di Office 365 dall'interno della rete del cliente
<a name="bk_Figure2"> </a>

Per le chiamate peer-to-peer, il traffico multimediale effettua il percorso più diretto verso la destinazione. Tuttavia, il traffico di segnalazione è diretto a un centro dati Office 365 dove è ospitato l'utente online. Poiché entrambi gli utenti si trovano sulla stessa rete WAN e nulla impedisce ai client di comunicare direttamente, il flusso dell'elemento multimediale avviene direttamente tra essi. Il traffico di segnalazione per entrambi gli utenti attraversa la connessione ExpressRoute destinata al centro dati di ciascuna organizzazione. Per il flusso delle chiamate di questo scenario, guarda qui.

 **Flusso delle chiamate peer-to-peer**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utente online sulla tua rete che partecipa a una conferenza ospitata online
<a name="bk_Figure3"> </a>

Nell'esempio peer-to-peer, il traffico multimediale prende sempre la route più diretta verso la destinazione. Tuttavia, per una conferenza online, la destinazione è nel cloud di Office 365. Ciò significa che il traffico multimediale per tutti gli utenti che partecipano alla conferenza dall'interno della tua rete attraverserà la connessione ExpressRoute, mentre il traffico di segnalazione verrà indirizzato al cloud Office 365. L'immagine seguente mostra che sia l'elemento multimediale che la segnalazione traverseranno la connessione ExpressRoute per un utente all'interno della rete e attraverserà direttamente Internet per gli utenti connessi a Internet dall'esterno della rete, ad esempio da un caffè negozio o hotel.

Tenere presente che la posizione di una conferenza è definita dall'organizzatore della riunione e non dai partecipanti. Ciò significa che, se la riunione è stata programmata da un cliente locale, il traffico multimediale non verrà riversato nel cloud di Office 365 su ExpressRoute, ma si traverserebbe invece in Internet nel centro dati locale dell'organizzatore della riunione.

La destinazione degli elementi multimediali per le conferenze online sarà un centro dati interno al cloud Office 365, ma il centro dati potrebbe trovarsi in una diversa regione geografica rispetto agli utenti che partecipano alla conferenza. Ciò è possibile in uno dei due casi riportati di seguito:

- Se l'organizzatore della riunione proviene da un'azienda diversa rispetto ai partecipanti, e la relativa organizzazione è ospitata in una località geografica o paese/regione diversa.

- Se un utente partecipa da un paese o una regione diversa rispetto alla posizione dell'organizzazione dell'azienda, sia per il fatto che l'azienda è una multinazionale o che l'utente è in viaggio.

La buona notizia sull'uso di ExpressRoute in questo scenario è che con il componente aggiuntivo Premium ExpressRoute, i dati che seguono il percorso di ExpressRoute passeranno automaticamente tra le backbone di Microsoft indipendentemente dall'area geografica dell'organizzatore della riunione Data Center dell'organizzazione.

 **Flusso delle chiamate di un utente online con riunione online**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Partecipare a una conferenza ospitata da un utente locale in una distribuzione Business Server Hybrid
<a name="bk_Figure3"> </a>

Tenere presente che i server di conferenza che supportano le conferenze ospitate vengono determinati dalla posizione in cui è ospitato l'organizzatore della riunione. In questo scenario, il flusso di elementi multimediali per tutti gli utenti che partecipano a una conferenza pianificata da un utente locale in una distribuzione ibrida verrà riversato in un centro dati locale. La segnalazione per gli utenti di Homer online verrà stabilita tramite la propria organizzazione nel cloud di Office 365, mentre il supporto tenterà una connessione diretta. In questo scenario, dato che entrambi gli utenti si connettono dall'interno della rete, è possibile una connessione diretta multimediale, quindi ExpressRoute viene usato solo per segnalare il traffico per l'utente online homed. Se un utente homed online si connette da Internet, il supporto potrebbe attraversare ExpressRoute se si usa un server perimetrale online per la connessione.

 **Flusso delle chiamate per una conferenza ospitata da un utente Business Server Hybrid**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Server perimetrale locale con conferenze ospitate su Office 365
<a name="bk_Figure5"> </a>

Quando un utente ibrido partecipa a una conferenza ospitata online, sappiamo che i segnali e i contenuti multimediali saranno destinati al cloud di Office 365 e che l'utente si unirà da Internet, in genere sarà necessario un percorso Internet diretto. Tuttavia, in alcuni casi, ad esempio a causa di restrizioni del firewall, un percorso Internet diretto non è disponibile. In questo caso, un server perimetrale locale può inoltrare il traffico multimediale, causando il ritorno del traffico multimediale alla rete locale prima di passare al circuito di ExpressRoute al cloud di Office 365.

 **Utente locale che partecipa a una conferenza telefonica online utilizzando un server perimetrale locale**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

L'utilizzo di [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) fornisce connettività PSTN utilizzando risorse locali quali un trunk SIP o un gateway PSTN, o utilizzando un dispositivo hardware minimo da integrare con Skype for Business. Con Cloud Connector Edition gli utenti vengono ospitati online e fungono da normali utenti online quando non prevedono piani di chiamata. Il traffico di segnalazione per scenari PSTN viaggia tra il client e il cloud attraverso una connessione ExpressRoute, se disponibile, mentre il traffico multimediale rimane all'interno della rete WAN. In questo caso, il traffico di segnalazione inverte il proprio percorso al cloud Office 365 e termina al Cloud Connector.

 **Chiamata PSTN tramite il sistema telefonico in Office 365 e Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype Meeting Broadcast con utenti che partecipano da una rete del cliente
<a name="bk_Figure6"> </a>

L'utilizzo di Skype Meeting Broadcast rappresenta un caso speciale e consiste di una riunione in due parti, dove ciascuna parte dispone di profili di trasporto di rete diversi. La prima parte e quella più importante da un punto di vista delle prestazioni di rete sono le riunioni interne. Questa è la parte in tempo reale della riunione che include uno o più endpoint client che si connettono al server dei servizi di conferenza nel cloud di Office 365. I dati trasmessi tramite questa parte della riunione sono esattamente come l'esempio precedente, con una conferenza di partecipazione e online di Office 365 per l'utente.

Ciò che rende Skype meeting broadcast univoco è che la riunione viene distribuita a un numero elevato di partecipanti alla conferenza usando un servizio di streaming broadcast. Questo servizio di trasmissione broadcast non è instradabile su ExpressRoute, ma usa invece Internet con il supporto facoltativo dei servizi CDN (Content delivering Network). È utile riconoscere che lo streaming broadcast è un flusso di elementi multimediali unidirezionale perché i partecipanti ascoltano ma non parlano e supportano il buffering, quindi è molto meno sensibile ai problemi di prestazioni della rete, ad esempio la latenza, la perdita di pacchetti e il jitter. Invece di ottimizzare il traffico broadcast per questi problemi, è ottimizzato per l'utilizzo della larghezza di banda, perché potenzialmente esiste un numero molto elevato di partecipanti che ricevono il supporto in streaming.

 **Skype Meeting Broadcast con utenti della rete del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modelli di flusso delle chiamate per tipo di distribuzione

Con gli esempi di flusso delle chiamate comuni descritti sopra e la comprensione dei principi generali che controllano i modelli di traffico, le tabelle seguenti includono un riepilogo dei modelli di traffico per un'ampia combinazione di scenari di distribuzione e utilizzo. Queste tabelle non catturano tutte le combinazioni possibili dei flussi delle chiamate, ma dovrebbero aiutarti a comprenderne ulteriormente i principi generali.

I dati vengono trasmessi ed elencati come locali dell'organizzazione; non lascia la rete del cliente, Internet o ExpressRoute. I modelli elencati di seguito si basano sulle impostazioni di rete più comuni, ad esempio firewall, Federazione e Internet, e presuppongono che tutte le organizzazioni coinvolte in flussi federati o multiparte abbiano ExpressRoute. In pratica, disporre di impostazioni diverse può risultare in modelli di traffico diversi rispetto a quelli elencati di seguito.

### <a name="call-flows-for-skype-for-business-online"></a>Flussi delle chiamate per Skype for Business online

Gli scenari di utilizzo di Skype for business online coinvolgono gli utenti ospitati online e possono essere chiamati dalla rete interna o da Internet. I server locali non fanno parte di questi scenari, quindi tutte le conferenze o i contenuti multimediali PSTN verranno confluire nel cloud di Office 365 e il server Edge degli utenti online sarà anche nel cloud.

 **Riepilogo dei flussi delle chiamate per Skype for Business online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla tua rete.  <br/> |ExpressRoute  <br/> |locale  <br/> |[Chiamata peer-to-peer per gli utenti di Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chiamate peer-to-peer  <br/> |Due client, uno sulla rete (interno) e l'altro client su Internet (esterno).  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Internet  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Da Internet al server perimetrale Office 365.  <br/> |[Chiamata peer-to-peer per gli utenti di Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Presuppone che il firewall blocchi le connessioni dirette tra i client, che richiedono un server perimetrale online. Il traffico dall'utente interno all'online Edge Server segue un percorso simile a quello di conferenza server per le conferenze telefoniche.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, uno sulla tua rete (interno) e uno presso l'utente online sulla rete dell'organizzazione federata (federato).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente  <br/> |Il client è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza telefonica da parte di un utente in Internet  <br/> |Il client è su Internet e il server delle conferenze in Office 365 cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza ospitata da un server locale di un'altra azienda  <br/> |Il client è sulla tua rete e il server delle conferenze è in un centro dati di terze parti.  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Poiché il server delle conferenze che ospita la conferenza si trova su una rete locale di un cliente diverso, attraverso il cloud Microsoft non passerà alcun dato.  <br/> |
|Chiamata PSTN  <br/> |Client nella rete dei clienti e nei server del sistema telefonico in Office 365 cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chiamata PSTN  <br/> |Client su Internet e i server del sistema telefonico in Office 365 cloud  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Il flusso di lavoro multimediale e di segnalazione verrà riversato nel Data Center di Office 365. Dato che l'endpoint client si trova su Internet, tutti i dati verranno riversati nel Data Center Microsoft su Internet (anche se è necessario un server perimetrale online per la connettività).  <br/> |

> [!NOTE]
> ExpressRoute verrà usato nel percorso multimediale di un utente che si trova nella rete aziendale in un server perimetrale online, ma non verrà usato se viene usato il server perimetrale per la distribuzione locale di un altro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flussi delle chiamate per Skype for Business Hybrid

I flussi delle chiamate di Skype for Business Hybrid si applicano quando è presente una distribuzione Skype for Business che include almeno alcuni utenti ospitati localmente. I flussi delle chiamate in questa sezione includono sia le conferenze locali che le chiamate peer-to-peer o PSTN con almeno un utente locale homed.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla rete del cliente e ospitati localmente  <br/> |Locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per gli utenti di Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Poiché gli utenti sono ospitati localmente, il flusso del traffico di segnalazione avviene localmente verso il centro dati locale anziché verso il cloud Office 365.  <br/> |
|Chiamate peer-to-peer  <br/> |Due client, che si connettono entrambi dalla rete del cliente. Uno è ospitato online, mentre l'altro è ospitato localmente.  <br/> |Utente online: ExpressRoute  <br/> Utente locale: locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per gli utenti di Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo l'utente ospitato localmente invia il traffico di segnalazione al cloud Office 365.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, un utente locale sulla rete del cliente (interno) e un utente online presso la rete dell'azienda federata (federato).  <br/> |Utente interno: locale  <br/> Utente federato: ExpressRoute  <br/> |Internet o ExpressRoute (dipende se viene utilizzato un server perimetrale online o locale)  <br/> |[Utente online della rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) e parte di un [server perimetrale locale con le conferenze ospitate in Office 365](call-flow-using-expressroute.md#bk_Figure5) (per il traffico multimediale). <br/> |Presuppone che un firewall blocchi le connessioni dirette tra i client, richiedendo online Edge Server. La negoziazione ICE offrirà sia online (tramite l'utente online) che i server perimetrali locali (dall'utente locale) per la connettività.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente (conferenza pianificata dall'utente online)  <br/> |L'utente locale è sulla tua rete e il server delle conferenze è nel cloud Office 365.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Le risorse del server per la conferenza telefonica sono definite dall'organizzatore della riunione. In questo caso è stata pianificata da un utente online, pertanto le risorse si trovano nel cloud Office 365.  <br/> |
|Chiamata PSTN  <br/> |Utente locale sulla tua rete e centro dati Skype for Business locale.  <br/> |Locale  <br/> |Locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scenario simile a quello per l'uso di Cloud Connector Edition, eccetto per il fatto che l'utente è ospitato localmente, quindi il traffico di segnalazione rimane all'interno della tua rete.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flussi delle chiamate per Skype for Business con Cloud Connector

Gli utenti che effettuano la connessione a Cloud Connector Edition sono tutti ospitati online. Ciò significa che la conferenza sarà online, e il traffico di segnalazione segue gli stessi modelli degli utenti online. Per gli scenari diversi da quelli delle chiamate PSTN, il flusso delle chiamate sarà esattamente quello descritto in precedenza per Skype for Business online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamata PSTN  <br/> |Utente online sulla tua rete che utilizza Cloud Connector Edition.  <br/> |locale  <br/> |locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chiamata PSTN  <br/> |Utente online che utilizza Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinazione di [Edge Server locale con conferenze ospitate in Office 365](call-flow-using-expressroute.md#bk_Figure5) e [chiamate PSTN tramite Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Gli utenti Internet effettueranno la connessione attraverso il server perimetrale incluso in Cloud Connector, mentre Cloud Connector effettuerà la connessione alla rete PSTN.  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


