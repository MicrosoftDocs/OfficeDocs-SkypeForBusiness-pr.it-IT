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
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.
ms.openlocfilehash: 098949c41430bc939197a21373489b1aaa10c1678943d0ee695cd7ade02be142
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304638"
---
# <a name="call-flow-using-expressroute"></a>Flusso delle chiamate con ExpressRoute

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.

Se si distribuisce Skype for Business Online come parte di Microsoft 365 o Office 365, Skype for Business Server ibrido o Skype for Business Cloud Connector Edition, è necessario comprendere la comunicazione tra il client e i server di Skype for Business e il flusso delle chiamate in modo da poter pianificare, distribuire, gestire e risolvere i problemi dei servizi di Skype for Business Online.

## <a name="call-flow-overview"></a>Panoramica sul flusso delle chiamate

Questo documento descrive i segmenti di rete che possono contenere i dati per questi flussi di chiamata e consente di capire quale traffico rimarrà locale alla rete rispetto al traffico che viascierà su Internet o tramite ExpressRoute. Conoscere il traffico utilizzato da ExpressRoute ti aiuta a valutare i benefici che riceverà la tua azienda dal suo utilizzo, oltre a capirne le istruzioni di distribuzione in modo da convalidare e risolvere i problemi della distribuzione una volta che avrai deciso di utilizzarlo.

Sui flussi delle chiamate qui descritti può influire una serie di fattori che puoi controllare, come regole firewall, configurazione NAT, proxy e configurazione dei router. In questo documento si suppone che siano state applicate le impostazioni consigliate. Tali impostazioni consigliate sono descritte in:

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Panoramica di ExpressRoute](/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

La configurazione e le configurazioni che non hanno seguito i passaggi di configurazione descritti nella documentazione precedente possono avere flussi di chiamata diversi da quelli documentati in questa pagina. Inoltre, potrebbero verificarsi problemi di configurazione, ad esempio route di rete asimmetriche e non ottimali o protocolli di trasporto non ottimali. Il routing asimmetrico è una considerazione importante ogni volta che expressRoute è coinvolto, perché ExpressRoute introduce un secondo percorso a Office 365, che crea la possibilità per una route che usa Internet in una direzione e un'altra che usa ExpressRoute nell'altra direzione. Ciò può causare il blocco del traffico nella direzione di ritorno se attraversa un firewall con stato.

## <a name="network-segments-and-traffic-types"></a>Segmenti di rete e tipi di traffico

### <a name="network-segments"></a>Segmenti di rete

Prima di illustrare il flusso delle chiamate, dobbiamo definire alcuni termini che ti aiuteranno a comprendere i segmenti di rete e i tipi di elementi multimediali utilizzati in Skype for Business online.

I diagrammi del flusso delle chiamate seguenti mostrano quattro diversi segmenti di rete, ognuno dei quali è gestito da organizzazioni diverse (la rete interna, il provider di servizi di rete e i partner di peering Internet e Microsoft) con caratteristiche di prestazioni diverse. Per le linee guida sui target delle prestazioni di rete, consulta [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md).

Di seguito puoi vedere ciascun segmento di rete di cui parleremo.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **La tua rete** Si tratta del segmento di rete che fa parte della rete complessiva da te controllata e gestita. Sono incluse tutte le connessioni all'interno degli uffici, sia cablate che wireless, tra gli edifici degli uffici, i data center locali e le connessioni a provider Internet o partner ExpressRoute.

In genere, il perimetro della rete include uno o più dmz con firewall e/o server proxy, che applicano i criteri di sicurezza dell'organizzazione e consentono solo il traffico di rete configurato e configurato. Poiché si gestisce questa rete, si ha il controllo diretto sulle prestazioni della rete ed è consigliabile completare le valutazioni della rete per convalidare le prestazioni sia all'interno dei siti della rete che dalla rete a Skype for Business Online. Per vedere i requisiti delle prestazioni, consulta [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md).

 **Internet** Si tratta del segmento di rete che fa parte della tua rete complessiva, utilizzato da utenti che si connettono a Skype for Business online dall'esterno della rete, e per tutte le connessioni quando non è stato configurato ExpressRoute. Internet e tutte le connessioni non sono gestite dall'utente o da Microsoft, quindi non è possibile determinare le prestazioni e i percorsi di routing e questo avrà l'impatto maggiore sul flusso complessivo delle chiamate e sulla qualità.

 **ExpressRoute** Si tratta del segmento di rete che fa parte della tua rete complessiva e che ti garantirà una connessione dedicata e privata alla rete Microsoft. Questa è l'opzione consigliata per connettere la rete alla rete Microsoft (data center Microsoft 365 o Office 365) per tutti i carichi di lavoro che dipendono dalla velocità e dalle prestazioni della rete, ad esempio le comunicazioni in tempo reale di Skype for Business Online. Le connessioni ExpressRoute vengono effettuate tra la rete e la rete Microsoft usano i provider di connettività [ExpressRoute](/azure/expressroute/expressroute-locations) per fornire una rete privata e gestita, con il 99,9% di tempo di attività e supporto per la qualità del servizio (QoS) che può migliorare le prestazioni per i supporti multimediali in tempo reale durante i periodi di congestione della rete.

 **Rete Microsoft** Questo è il segmento di rete che fa parte della rete generale che supporta i servizi Microsoft 365 e Office 365 rete. Sono incluse tutte le comunicazioni tra i server online per Microsoft 365 o Office 365. Questo può includere il traffico che attraversa la dorsale di rete Microsoft e viene trasmesso tra aree geografiche.

### <a name="types-of-traffic"></a>Tipi di traffico

Il traffico di rete per Skype for Business Online è suddiviso in due ampie categorie, visualizzate come percorsi separati nel flusso delle chiamate:

 **I supporti multimediali in** tempo reale sono dati incapsulati all'interno di RTP (Real-time Transport Protocol) e supportano carichi di lavoro audio, video, condivisione di applicazioni e trasferimento di file. In generale, il traffico degli elementi multimediali è altamente sensibile alla latenza, e pertanto dovresti fare in modo che questo traffico effettui il percorso più diretto possibile, utilizzando UDP come protocollo layer di trasporto anziché TCP poiché quest'ultimo introduce una latenza maggiore.

 **La segnalazione** è il collegamento di comunicazione tra il client e il server o altri client usati per controllare le attività (ad esempio, quando viene avviata una chiamata) e recapitare messaggistica elettronica. La maggior parte del traffico di segnalazione utilizza il protocollo SIP, anche se alcuni client utilizzano interfacce REST basate su HTTP. Per semplificare, stiamo valutando un'ampia gamma di segnalazioni che possono viaggiare su connessioni HTTP e HTTPS o TLS in questo tipo di traffico. È importante comprendere che questo tipo di traffico è molto meno sensibile alla latenza, ma può causare interruzioni di servizio o timeout delle chiamate se la latenza tra gli endpoint supera diversi secondi.

Le destinazioni per questo traffico si trovano negli URL Office 365 indirizzi [IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per tutti i servizi Microsoft 365 o Office 365 ip. Per ogni URL, indica se tale parte di traffico può attraversare ExpressRoute per Microsoft 365 o Office 365. Per i diagrammi che indicano che Internet è ancora usato per un certo traffico quando ExpressRoute è abilitato, vedere [Azure ExpressRoute per](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)Office 365 . È importante tenere presente che anche gli URL elencati come instradabili su ExpressRoute sono instradabili su Internet. Questo significa che in alcuni scenari, la determinazione dell'uso di Internet o ExpressRoute dipende dalla posizione del client e dalla configurazione dei server proxy e dei firewall. È anche importante comprendere che, poiché non tutti gli URL associati a Microsoft 365 o Office 365 sono in grado di usare ExpressRoute, è necessaria una connessione Internet anche se si acquista ExpressRoute da un partner ExpressRoute.

Il traffico che può essere inviato solo tramite Internet include dipendenze Internet comuni, ad esempio elenchi di revoche di certificati (CRL), ricerche DNS e risoluzione dei nomi, URL per servizi Microsoft 365 o Office 365 condivisi, ad esempio per il interfaccia di amministrazione di Microsoft 365, e alcune funzionalità di comunicazione non in tempo reale di Skype for Business Online, ad esempio telemetria e federazione per l'interoperabilità con gli utenti Skype consumer, nonché i supporti multimediali trasmessi per Riunione Skype Broadcast. Per aiutarti a decidere, consulta [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) per ulteriori considerazioni quando pianifichi il routing della rete.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principi dei flussi delle chiamate con Skype for Business

Prima di entrare nei dettagli di scenari di flussi delle chiamate specifici, esistono sei principi generali che ti aiutano a comprendere i flussi delle chiamate per Skype for Business.

1. Una Skype for Business conferenza è ospitata nella stessa area geografica in cui si trova l'organizzatore della conferenza. Si trova nel cloud se l'organizzatore è un utente online o in un data center locale se l'organizzatore della riunione è un utente locale.

2. Il traffico multimediale inviato da un client a una conferenza ospitata viene sempre diretto al server che ospita la conferenza. Può trattarsi di un server locale all'interno di un data center che si gestisce o di un server online all'interno del cloud. Tuttavia, viene sempre utilizzato un server perimetrale per il flusso multimediale per le conferenze online.

3. Il traffico multimediale per le chiamate peer-to-peer effettua il percorso più diretto disponibile. Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile a causa di un blocco del traffico da parte del firewall o per altri motivi, il traffico verrà inoltrato da uno o più server perimetrali.

4. Il traffico di segnalazione viene sempre diretto verso il server che ospita l'utente, sia online o locale. Se non è possibile connettersi direttamente al server front end, verrà utilizzato un server perimetrale.

5. Gli utenti che partecipano a una conferenza ospitata online utilizzeranno sempre un server perimetrale (o due, se richiesto dalle configurazioni del firewall client).

6. Gli utenti che partecipano a una conferenza ospitata localmente in genere non useranno un server perimetrale se la connessione avviene dall'interno della stessa rete che contiene la distribuzione locale, e utilizzeranno uno o due server perimetrali quando la connessione avviene dall'esterno della rete.

Per ulteriori informazioni sui dettagli relativi al percorso multimediale scelto, consulta [ICE - Connettività degli elementi multimediali perimetrali](https://aka.ms/AVEdge). Anche se questo video riguarda Lync Server 2013, i principi e i protocolli sono ancora applicabili Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flussi delle chiamate di Skype for Business con ExpressRoute

Dopo aver compreso i quattro diversi segmenti di rete e alcuni principi guida generali per i flussi delle chiamate di Skype for Business, è possibile usare queste informazioni per comprendere quale traffico di Skype for Business attraverserà un segmento di rete ExpressRoute.

In generale, il traffico di rete attraverserà la connessione ExpressRoute se un endpoint si trova nella rete e l'altro endpoint si trova nel data center Microsoft 365 o Office 365 dati. Ciò includerà il traffico di segnalazione tra client e server, il traffico multimediale utilizzato durante le conferenze telefoniche, o le chiamate peer-to-peer che utilizzano un server perimetrale online.

Il traffico non attraverserà la connessione ExpressRoute se entrambi gli endpoint sono in grado di comunicare direttamente attraverso Internet o si trovano all'interno della tua rete. Questo includerà i supporti per le chiamate peer-to-peer, il traffico da Internet destinato a una distribuzione locale o il traffico tra Internet e i server perimetrali Microsoft 365 o Office 365 server perimetrali. Un esempio di ciò potrebbe essere un utente che partecipa a una conferenza online da un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flusso delle chiamate di base di Skype for Business

Per aiutarti ad applicare i principi generali dei flussi delle chiamate Skype for Business descritti in precedenza, la seguente sessione di questo articolo presenta diversi diagrammi di riferimento. Non si tratta di un elenco completo di tutti i flussi delle chiamate possibili, ma serve per aiutarti ad applicare i principi illustrati in precedenza. In aggiunta, gli scenari nei diagrammi sono stati scelti per trattare tipi di distribuzione comuni quali Skype for Business online, Business Server Hybrid, Business Cloud Connector Edition e, in un caso speciale, Skype Meeting Broadcast.

> [!NOTE]
> Un sottoinsieme di traffico usato Skype for Business non è instradabile su ExpressRoute e accetta sempre un percorso Internet. Consulta [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare gli URL interessati.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Chiamata peer-to-peer per Microsoft 365 o Office 365 utente dall'interno della rete del cliente
<a name="bk_Figure2"> </a>

Per le chiamate peer-to-peer, il traffico multimediale effettua il percorso più diretto verso la destinazione. Tuttavia, il traffico di segnalazione viene Microsoft 365 o Office 365 data center in cui si trova l'utente online. Poiché entrambi gli utenti si trovano sulla stessa rete WAN e nulla impedisce ai client di comunicare direttamente, il flusso dell'elemento multimediale avviene direttamente tra essi. Il traffico di segnalazione per entrambi gli utenti attraversa la connessione ExpressRoute destinata al centro dati di ciascuna organizzazione. Per il flusso delle chiamate di questo scenario, guarda qui.

 **Flusso delle chiamate peer-to-peer**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utente online sulla tua rete che partecipa a una conferenza ospitata online
<a name="bk_Figure3"> </a>

Nell'esempio peer-to-peer, il traffico multimediale prende sempre il percorso più diretto verso la destinazione. Tuttavia, per una conferenza online, la destinazione è nel cloud. Questo significa che il traffico multimediale per tutti gli utenti che partecipano alla conferenza dall'interno della rete attraverserà la connessione ExpressRoute e il traffico di segnalazione verrà recato nel cloud. L'immagine seguente mostra che sia gli elementi multimediali che la segnalazione attraverseranno la connessione ExpressRoute per un utente all'interno della rete e attraverseranno direttamente Internet per gli utenti connessi a Internet dall'esterno della rete, ad esempio da un bar o un hotel.

Ricorda che la posizione della conferenza viene definita dall'organizzatore della riunione e non dai partecipanti. Questo significa che se la riunione è stata pianificata da un cliente locale, il traffico multimediale non fluirà nel cloud tramite ExpressRoute, ma attraverserebbe Invece Internet verso il data center locale dell'organizzatore della riunione.

La destinazione per i contenuti multimediali per le conferenze online sarà un data center all'interno del cloud Microsoft 365 o Office 365, ma il data center potrebbe essere in un'area geografica diversa rispetto agli utenti che stanno partecipando alla conferenza. Ciò è possibile in uno dei due casi riportati di seguito:

- Se l'organizzatore della riunione proviene da un'azienda diversa rispetto ai partecipanti, e la relativa organizzazione è ospitata in una località geografica o paese/regione diversa.

- Se un utente partecipa da un paese o una regione diversa rispetto alla posizione dell'organizzazione dell'azienda, sia per il fatto che l'azienda è una multinazionale o che l'utente è in viaggio.

La buona notizia sull'uso di ExpressRoute in questo scenario è che con il componente aggiuntivo ExpressRoute Premium, i dati che seguono il percorso ExpressRoute passeranno automaticamente attraverso la spina dorsale di Microsoft, indipendentemente dall'area geografica dell'organizzatore del data center dell'organizzazione della riunione.

 **Flusso delle chiamate di un utente online con riunione online**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Partecipare a una conferenza ospitata da un utente locale in una distribuzione Business Server Hybrid
<a name="bk_Figure3"> </a>

Ricorda che i server delle conferenze che supportano le conferenze ospitate sono determinati dalla posizione dell'organizzatore della riunione. In questo scenario, il flusso degli elementi multimediali per tutti gli utenti che partecipano a una conferenza pianificata da un utente locale in una distribuzione Business Server Hybrid avverrà verso un centro dati locale. La segnalazione per gli utenti ospitati online verrà stabilita tramite l'organizzazione nel cloud, mentre gli elementi multimediali tenteranno una connessione diretta. In questo scenario, poiché entrambi gli utenti si connettono dall'interno della rete, è possibile una connessione multimediale diretta, quindi ExpressRoute viene usato solo per segnalare il traffico per l'utente ospitato online. Se un utente ospitato online si connette da Internet, il supporto multimediale potrebbe attraversare ExpressRoute se per la connessione viene usato un server perimetrale online.

 **Flusso delle chiamate per una conferenza ospitata da un utente Business Server Hybrid**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Server perimetrale locale con conferenze Microsoft 365 o Office 365 ospitate
<a name="bk_Figure5"> </a>

Quando un utente ibrido partecipa a una conferenza ospitata online, sappiamo che la segnalazione e i supporti multimediali saranno destinati al cloud Microsoft 365 o Office 365 e, poiché l'utente partecipa da Internet, in genere viene intrapreso un percorso Internet diretto. Tuttavia, in alcuni casi, ad esempio a causa di restrizioni del firewall, non è disponibile un percorso Internet diretto. In questo caso, un server perimetrale locale può inoltrare il traffico multimediale, causando il ritorno del traffico multimediale alla rete locale prima di attraversare il circuito ExpressRoute nel cloud.

 **Utente locale che partecipa a una conferenza telefonica online utilizzando un server perimetrale locale**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

L'utilizzo di [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) fornisce connettività PSTN utilizzando risorse locali quali un trunk SIP o un gateway PSTN, o utilizzando un dispositivo hardware minimo da integrare con Skype for Business. Con Cloud Connector Edition, gli utenti sono ospitati online e fungono da normali utenti online quando non implicano piani per chiamate. Il traffico di segnalazione per scenari PSTN viaggia tra il client e il cloud attraverso una connessione ExpressRoute, se disponibile, mentre il traffico multimediale rimane all'interno della rete WAN. In questo caso, la segnalazione viene Microsoft 365 o Office 365 cloud e termina in Cloud Connector.

 **Chiamata PSTN tramite Sistema telefonico in Microsoft 365 o Office 365 e Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype Meeting Broadcast con utenti che partecipano da una rete del cliente
<a name="bk_Figure6"> </a>

L'utilizzo di Skype Meeting Broadcast rappresenta un caso speciale e consiste di una riunione in due parti, dove ciascuna parte dispone di profili di trasporto di rete diversi. La prima parte, e quella più importante dal punto di vista delle prestazioni di rete, è la riunione interna. Questa è la parte in tempo reale della riunione che include uno o più endpoint client che si connettono al server delle conferenze nel cloud. I dati trasmessi usando questa parte della riunione sono esattamente come nell'esempio precedente, con un utente che partecipa a una conferenza online.

Ciò che Riunione Skype broadcast è che la riunione viene distribuita a un numero elevato di partecipanti alla conferenza usando un servizio di trasmissione in streaming. Questo servizio di trasmissione in streaming non è instradabile su ExpressRoute, ma usa Internet con il supporto facoltativo dei servizi rete per la distribuzione di contenuti (rete CDN). È utile riconoscere che lo streaming broadcast è un flusso multimediale unidirezionale perché i partecipanti ascoltano, ma non parlano e supportano il buffering, quindi è molto meno sensibile ai problemi di prestazioni di rete come la latenza, perdita di pacchetti e instabilità. Invece di ottimizzare il traffico broadcast per questi problemi, è ottimizzato per l'utilizzo della larghezza di banda perché è potenzialmente presente un numero molto elevato di partecipanti che ricevono il contenuto multimediale in streaming.

 **Skype Meeting Broadcast con utenti della rete del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modelli di flusso delle chiamate per tipo di distribuzione

Con gli esempi comuni relativi al flusso di chiamate riportati sopra e la comprensione dei principi generali che controllano i modelli di traffico, le tabelle seguenti forniscono un riepilogo dei modelli di traffico per una combinazione di scenari di distribuzione e utilizzo di grandi dimensioni. Queste tabelle non catturano tutte le combinazioni possibili dei flussi delle chiamate, ma dovrebbero aiutarti a comprenderne ulteriormente i principi generali.

I dati vengono trasmessi ed elencati come locali per l'organizzazione. non lascia la rete del cliente, Internet o ExpressRoute. I modelli elencati di seguito si basano sulle impostazioni di rete più comuni, ad esempio firewall, federazione e Internet, e presuppongono che tutte le organizzazioni coinvolte in flussi multi-party o federati siano expressRoute. In pratica, disporre di impostazioni diverse può risultare in modelli di traffico diversi rispetto a quelli elencati di seguito.

### <a name="call-flows-for-skype-for-business-online"></a>Flussi delle chiamate per Skype for Business online

Skype for Business Gli scenari di utilizzo online coinvolgono utenti ospitati online e che potrebbero chiamare dalla rete interna o da Internet. I server locali non fanno parte di questi scenari, quindi tutti i servizi di conferenza o i supporti multimediali correlati a PSTN fluiranno nel cloud e anche il server perimetrale degli utenti online sarà nel cloud.

 **Riepilogo dei flussi delle chiamate per Skype for Business online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla tua rete.  <br/> |ExpressRoute  <br/> |locale  <br/> |[Chiamata peer-to-peer per Microsoft 365 o Office 365 utente dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chiamate peer-to-peer  <br/> |Due client, uno sulla rete (interno) e l'altro su Internet (esterno).  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Internet  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: da Internet a Microsoft 365 o Office 365 edge server.  <br/> |[Chiamata peer-to-peer per Microsoft 365 o Office 365 utenti dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Presuppone che il firewall blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per conferenza telefonica.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, uno sulla tua rete (interno) e uno presso l'utente online sulla rete dell'organizzazione federata (federato).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente  <br/> |Client nella rete e nel server delle conferenze nel cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza telefonica per utente in Internet  <br/> |Il client si trova su Internet e sul server delle conferenze nel cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza ospitata da un server locale di un'altra azienda  <br/> |Il client è sulla tua rete e il server delle conferenze è in un centro dati di terze parti.  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Poiché il server delle conferenze che ospita la conferenza si trova su una rete locale di un cliente diverso, attraverso il cloud Microsoft non passerà alcun dato.  <br/> |
|Chiamata PSTN  <br/> |Client nella rete dei clienti e Sistema telefonico server nel cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chiamata PSTN  <br/> |Client su Internet e Sistema telefonico server nel cloud  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Il supporto e la segnalazione fluiranno nel Microsoft 365 o Office 365 data center. Poiché l'endpoint client è su Internet, tutti i dati verranno fluire nel data center Microsoft attraverso Internet (anche se è necessario un server perimetrale online per la connettività).  <br/> |

> [!NOTE]
> ExpressRoute verrà usato nel percorso multimediale da un utente che si trova nella rete aziendale a un server perimetrale online, ma non verrà usato se viene usato il server perimetrale per la distribuzione locale di un altro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flussi delle chiamate per Skype for Business Hybrid

I flussi delle chiamate di Skype for Business Hybrid si applicano quando è presente una distribuzione Skype for Business che include almeno alcuni utenti ospitati localmente. I flussi di chiamata in questa sezione includono sia le conferenze locali che le chiamate peer-to-peer o PSTN con almeno un utente ospitato locale.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla rete del cliente e ospitati localmente  <br/> |Locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per Microsoft 365 o Office 365 utente dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Poiché gli utenti sono ospitati in locale, la segnalazione passa localmente al data center locale invece che al cloud.  <br/> |
|Chiamate peer-to-peer  <br/> |Due client, che si connettono entrambi dalla rete del cliente. Uno è ospitato online, mentre l'altro è ospitato localmente.  <br/> |Utente online: ExpressRoute  <br/> Utente locale: locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per Microsoft 365 o Office 365 utenti dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo l'utente homed online invia il traffico di segnalazione al cloud.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, un utente locale sulla rete del cliente (interno) e un utente online presso la rete dell'azienda federata (federato).  <br/> |Utente interno: locale  <br/> Utente federato: ExpressRoute  <br/> |Internet o ExpressRoute (dipende se viene utilizzato un server perimetrale online o locale)  <br/> |[Utente online della](call-flow-using-expressroute.md#bk_Figure3) rete che partecipa a una conferenza ospitata online e che fa parte del server perimetrale locale con conferenze ospitate Microsoft 365 [o Office 365](call-flow-using-expressroute.md#bk_Figure5) (per il traffico multimediale). <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. La negoziazione ICE fornirà per la connettività sia server online (da parte dell'utente online), sia server perimetrali locali (da parte dell'utente locale).  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente (conferenza pianificata dall'utente online)  <br/> |Utente locale nella rete e nel server delle conferenze nel cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Le risorse del server per la conferenza telefonica sono definite dall'organizzatore della riunione. In questo caso, è stato pianificato da un utente online, quindi le risorse sono nel cloud.  <br/> |
|Chiamata PSTN  <br/> |Utente locale sulla tua rete e centro dati Skype for Business locale.  <br/> |Locale  <br/> |Locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scenario simile a quello per l'uso di Cloud Connector Edition, eccetto per il fatto che l'utente è ospitato localmente, quindi il traffico di segnalazione rimane all'interno della tua rete.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flussi delle chiamate per Skype for Business con Cloud Connector

Gli utenti che effettuano la connessione a Cloud Connector Edition sono tutti ospitati online. Ciò significa che la conferenza sarà online, e il traffico di segnalazione segue gli stessi modelli degli utenti online. Per gli scenari diversi da quelli delle chiamate PSTN, il flusso delle chiamate sarà esattamente quello descritto in precedenza per Skype for Business online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamata PSTN  <br/> |Utente online sulla tua rete che utilizza Cloud Connector Edition.  <br/> |locale  <br/> |locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chiamata PSTN  <br/> |Utente online che utilizza Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinazione [di server](call-flow-using-expressroute.md#bk_Figure5) perimetrale locale con Microsoft 365 o Office 365 conferenze ospitate e chiamate [PSTN con Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Gli utenti Internet effettueranno la connessione attraverso il server perimetrale incluso in Cloud Connector, mentre Cloud Connector effettuerà la connessione alla rete PSTN.  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](/azure/expressroute/)
