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
ms.openlocfilehash: b65d7b1e3677c82e562de63257f28ad1561d7190
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164635"
---
# <a name="call-flow-using-expressroute"></a>Flusso delle chiamate con ExpressRoute

[] Questo articolo illustra i principi di base del flusso delle chiamate per Skype for Business online ed ExpressRoute, e fornisce alcuni esempi dettagliati di flussi delle chiamate per una maggiore comprensione e per eseguire una corretta programmazione.

Se stai distribuendo Skype for Business online come parte di Microsoft 365 o Office 365, Skype for Business Server Hybrid o Skype for Business Cloud Connector Edition, dovrai comprendere la comunicazione tra il client e i server Di Skype for Business e il flusso delle chiamate per poter pianificare, distribuire, operare e risolvere i problemi dei servizi Skype for Business online.

## <a name="call-flow-overview"></a>Panoramica sul flusso delle chiamate

Questo documento descrive i segmenti di rete che possono portare i dati per questi flussi delle chiamate e consente di capire quale traffico rimarrà locale sulla rete rispetto al traffico che viarrà attraverso Internet o ExpressRoute. Conoscere il traffico utilizzato da ExpressRoute ti aiuterà a valutare i vantaggi che riceverà la tua azienda utilizzando ExpressRoute e a comprendere le istruzioni di distribuzione di ExpressRoute per convalidare e risolvere i problemi della distribuzione dopo aver deciso di usare ExpressRoute.

Sui flussi delle chiamate qui descritti può influire una serie di fattori che puoi controllare, come regole firewall, configurazione NAT, proxy e configurazione dei router. In questo documento si suppone che siano state applicate le impostazioni consigliate. Tali impostazioni consigliate sono descritte in:

- [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Panoramica di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

La configurazione e le configurazioni che non hanno seguito i passaggi di configurazione descritti nella documentazione possono avere flussi delle chiamate diversi rispetto a quelli documentati qui. Inoltre, potrebbero verificarsi problemi di configurazione, ad esempio percorsi di rete asimmetrici e non ottimali o protocolli di trasporto non ottimali. Il routing asimmetrico è una considerazione importante ogni volta che viene coinvolto ExpressRoute, perché ExpressRoute introduce un secondo percorso a Office 365, che crea la possibilità per un percorso che usa Internet in una direzione e un altro percorso che usa ExpressRoute nell'altra direzione. Questo può causare il blocco del traffico nella direzione di ritorno se attraversa un firewall con stato.

## <a name="network-segments-and-traffic-types"></a>Segmenti di rete e tipi di traffico

### <a name="network-segments"></a>Segmenti di rete

Prima di illustrare il flusso delle chiamate, dobbiamo definire alcuni termini che ti aiuteranno a comprendere i segmenti di rete e i tipi di elementi multimediali utilizzati in Skype for Business online.

I diagrammi del flusso delle chiamate riportati di seguito mostrano quattro diversi segmenti di rete, ciascuno dei quali è gestito da organizzazioni diverse (la tua rete interna, il tuo provider di servizi di rete e i relativi partner peer-to-peer Internet e Microsoft) con caratteristiche di prestazioni diverse. Per le linee guida sui target delle prestazioni di rete, consulta Qualità multimediale e Prestazioni della connettività di [rete in Skype for Business online.](media-quality-and-network-connectivity-performance.md)

Di seguito puoi vedere ciascun segmento di rete di cui parleremo.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **La tua rete** Si tratta del segmento di rete che fa parte della tua rete complessiva che controlli e gestisci. Ciò include tutti i collegamenti all'interno dei tuoi uffici, sia cablati che wireless, tra gli edifici degli uffici, verso centri dati locali, e le connessioni a provider Internet o partner ExpressRoute.

In genere, il perimetro della tua rete ha uno o più DMZ con firewall e/o server proxy, che applicano i criteri di sicurezza dell'organizzazione e che consentono solo il traffico di rete che hai configurato e configurato. Poiché si gestisce questa rete, si ha un controllo diretto sulle prestazioni della rete ed è consigliabile completare le valutazioni della rete per convalidare le prestazioni sia all'interno dei siti della rete che dalla propria rete a Skype for Business online. Per visualizzare i requisiti di prestazioni, consulta Qualità multimediale e prestazioni [della connettività di rete in Skype for Business online.](media-quality-and-network-connectivity-performance.md)

 **Internet** Si tratta del segmento di rete che fa parte della tua rete complessiva che verrà utilizzato dagli utenti che si connettono a Skype for Business online dall'esterno della rete e per tutte le connessioni quando Non è configurato ExpressRoute. Internet e tutte le relative connessioni non sono gestiti dall'utente o da Microsoft, quindi non è possibile determinare le prestazioni e i percorsi di routing, con un impatto massimo sul flusso delle chiamate e sulla qualità complessive.

 **ExpressRoute** Si tratta del segmento di rete che fa parte della tua rete complessiva, che ti offrirà una connessione dedicata e privata alla rete Microsoft. Questa è l'opzione consigliata per connettere la rete aziendale alla rete Microsoft (data center Microsoft 365 o Office 365) per tutti i carichi di lavoro che dipendono dalla velocità e dalle prestazioni della rete, come le comunicazioni in tempo reale di Skype for Business Online. Le connessioni ExpressRoute vengono effettuate tra la tua rete e la rete Microsoft usa i provider di connettività [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) per fornire una rete privata e gestita, con il 99,9% di tempo di attività e supporto per la qualità del servizio (QoS, Quality of Service) che può migliorare le prestazioni dei supporti multimediali in tempo reale durante i periodi di congestione della rete.

 **Rete Microsoft** Si tratta del segmento di rete che fa parte della tua rete complessiva che supporta i servizi Microsoft 365 e Office 365. Ciò include tutte le comunicazioni tra i server online per Microsoft 365 o Office 365. Può includere il traffico che attraversa la dorsale di rete Microsoft e che viene trasmesso tra le aree geografiche.

### <a name="types-of-traffic"></a>Tipi di traffico

Il traffico di rete per Skype for Business online rientra in due ampie categorie, mostrate come percorsi separati nel flusso delle chiamate:

 **Gli elementi multimediali in** tempo reale sono dati incapsulati all'interno del protocollo RTP (Real-time Transport Protocol) e supportano carichi di lavoro audio, video, di condivisione applicazioni e di trasferimento file. In generale, il traffico degli elementi multimediali è altamente sensibile alla latenza, quindi è consigliabile che questo traffico prenda il percorso più diretto possibile e che usi UDP come protocollo layer di trasporto perché l'uso di TCP introduce una latenza maggiore.

 **Il segnale** è il collegamento di comunicazione tra il client e il server o altri client usati per controllare le attività (ad esempio, quando viene avviata una chiamata) e per la distribuzione di messaggistica elettronica. La maggior parte del traffico di segnalazione utilizza il protocollo SIP, anche se alcuni client usano interfacce REST basate su HTTP. Per semplificare questo tipo di traffico, stiamo valutando una varietà di segnalazioni che possono viaggiare su connessioni HTTP e HTTPS o TLS. È importante comprendere che questo traffico è molto meno sensibile alla latenza, ma può causare interruzioni del servizio o timeout delle chiamate se la latenza tra gli endpoint supera diversi secondi.

Le destinazioni per questo traffico si trovano negli URL e negli intervalli di indirizzi IP di [Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per tutti i servizi di Microsoft 365 o Office 365. Per ogni URL, indica se quella parte di traffico può attraversare ExpressRoute per Microsoft 365 o Office 365. Per i diagrammi che indicano che Internet viene ancora usato per un certo traffico quando ExpressRoute è abilitato, vedere [Azure ExpressRoute per Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) È importante tenere presente che anche gli URL elencati come instradabili attraverso ExpressRoute possono essere instradabili anche attraverso Internet. Questo significa che, in alcuni scenari, la scelta dell'uso di Internet o ExpressRoute dipende dalla posizione del client e dalla configurazione dei server proxy e dei firewall. È anche importante tenere conto del fatto che non tutti gli URL associati a Microsoft 365 o Office 365 possono usare ExpressRoute, quindi è necessaria una connessione Internet anche se si acquista ExpressRoute da un partner ExpressRoute.

Il traffico che può essere inviato solo su Internet include dipendenze Internet comuni, come gli elenchi di revoche di certificati (CRL), le ricerche e la risoluzione dei nomi DNS, gli URL per i servizi condivisi di Microsoft 365 o Office 365, ad esempio per l'interfaccia di amministrazione di Microsoft 365, e alcune funzionalità di comunicazione non in tempo reale di Skype for Business Online, come telemetria e federazione per l'interoperabilità con Skype per utenti, nonché elementi multimediali trasmessi per Skype Meeting Broadcast. Per aiutare a prendere decisioni, vedere routing con ExpressRoute per [Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) per altre considerazioni quando si pianifica il routing di rete.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Principi dei flussi delle chiamate con Skype for Business

Prima di entrare nei dettagli di scenari di flussi delle chiamate specifici, esistono sei principi generali che ti aiutano a comprendere i flussi delle chiamate per Skype for Business.

1. Una conferenza Skype for Business viene ospitata nella stessa regione in cui è ospitato l'organizzatore della conferenza. Si trova nel cloud se l'organizzatore è un utente online oppure in un centro dati locale se l'organizzatore della riunione è un utente locale.

2. Il traffico multimediale inviato da un client a una conferenza ospitata viene sempre inviato al server in cui è ospitata la conferenza. Può trattarsi di un server locale all'interno di un data center da te gestire o di un server online all'interno del cloud. Tuttavia, un server perimetrale viene sempre utilizzato per il flusso multimediale per le conferenze online.

3. Il traffico multimediale per le chiamate peer-to-peer effettua il percorso più diretto disponibile. Il percorso preferito è diretto al peer (client) remoto, ma se tale percorso non è disponibile a causa di un blocco del traffico da parte del firewall o per altri motivi, il traffico verrà inoltrato da uno o più server perimetrali.

4. Il traffico di segnalazione viene sempre diretto verso il server che ospita l'utente, sia online o locale. Se non è possibile connettersi direttamente al server front end, verrà utilizzato un server perimetrale.

5. Gli utenti che partecipano a una conferenza ospitata online utilizzeranno sempre un server perimetrale (o due, se richiesto dalle configurazioni del firewall client).

6. Gli utenti che partecipano a una conferenza ospitata localmente in genere non useranno un server perimetrale se la connessione avviene dall'interno della stessa rete che contiene la distribuzione locale, e utilizzeranno uno o due server perimetrali quando la connessione avviene dall'esterno della rete.

Per ulteriori informazioni sui dettagli sul percorso multimediale scelto, consulta [ICE - Connettività degli elementi multimediali perimetrali.](https://aka.ms/AVEdge) Anche se questo video riguarda Lync Server 2013, i principi e i protocolli si applicano ancora a Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Flussi delle chiamate di Skype for Business con ExpressRoute

Ora che hai compreso i quattro diversi segmenti di rete e alcuni principi guida generali per i flussi delle chiamate di Skype for Business, puoi utilizzare queste informazioni per capire quale traffico Skype for Business attraverserà un segmento di rete ExpressRoute.

In generale, il traffico di rete attraverserà la connessione ExpressRoute se un endpoint è nella tua rete e l'altro endpoint si trova nel centro dati Microsoft 365 o Office 365. Ciò includerà il traffico di segnalazione tra client e server, il traffico multimediale utilizzato durante le conferenze telefoniche o le chiamate peer-to-peer che utilizzano un server perimetrale online.

Il traffico non attraversi la connessione ExpressRoute se entrambi gli endpoint sono in grado di comunicare direttamente attraverso Internet o si trovano all'interno della tua rete. Ciò includerà gli elementi multimediali per le chiamate peer-to-peer, il traffico Internet destinato a una distribuzione locale o qualsiasi traffico tra Internet e i server perimetrali Microsoft 365 o Office 365. Un esempio è un utente che partecipa a una conferenza online da un hotel.

## <a name="basic-skype-for-business-call-flow"></a>Flusso delle chiamate di base di Skype for Business

Per aiutarti ad applicare i principi generali dei flussi delle chiamate Skype for Business descritti in precedenza, la seguente sessione di questo articolo presenta diversi diagrammi di riferimento. Non si tratta di un elenco completo di tutti i flussi delle chiamate possibili, ma serve per aiutarti ad applicare i principi illustrati in precedenza. In aggiunta, gli scenari nei diagrammi sono stati scelti per trattare tipi di distribuzione comuni quali Skype for Business online, Business Server Hybrid, Business Cloud Connector Edition e, in un caso speciale, Skype Meeting Broadcast.

> [!NOTE]
> Un sottoinsieme del traffico utilizzato da Skype for Business non può essere instradato attraverso ExpressRoute e verrà sempre percorso Internet. Vedere gli URL e gli intervalli di indirizzi IP per [Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per determinare gli URL interessati.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Chiamata peer-to-peer per utenti di Microsoft 365 o Office 365 dall'interno della rete del cliente
<a name="bk_Figure2"> </a>

Per le chiamate peer-to-peer, il traffico multimediale adotta sempre il percorso più diretto verso la destinazione. Tuttavia, il traffico di segnalazione passa a un centro dati Microsoft 365 o Office 365 dove è ospitata l'utente online. Dato che entrambi gli utenti si tratta della stessa WAN e nulla impedisce ai client di comunicare direttamente, il flusso degli elementi multimediali passa direttamente tra di essi. Il traffico di segnalazione per entrambi gli utenti attraversa la connessione ExpressRoute destinata al centro dati di ogni organizzazione. Per mostrarti il flusso delle chiamate in questo scenario, vedi questo.

 **Flusso delle chiamate peer-to-peer**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Utente online sulla tua rete che partecipa a una conferenza ospitata online
<a name="bk_Figure3"> </a>

Nell'esempio peer-to-peer, il traffico multimediale adotta sempre il percorso più diretto verso la destinazione. Tuttavia, per una conferenza online, la destinazione è nel cloud. Questo significa che il traffico multimediale per tutti gli utenti che partecipano alla conferenza dall'interno della tua rete attraverserà la connessione ExpressRoute e il traffico di segnalazione viaggia verso il cloud. Il grafico seguente mostra che sia gli elementi multimediali che il traffico di segnalazione attraverseranno la connessione ExpressRoute per un utente all'interno della rete e attraverseranno direttamente Internet per gli utenti connessi a Internet dall'esterno della rete, ad esempio da un bar o un hotel.

Ricorda che la posizione di una conferenza è definita dall'organizzatore della riunione e non dai partecipanti. Questo significa che se la riunione è stata pianificata da un cliente locale, il flusso del traffico multimediale non verrà sul cloud attraverso ExpressRoute, ma attraverserebbe Internet verso il centro dati locale dell'organizzatore della riunione.

La destinazione degli elementi multimediali per le conferenze online sarà un data center all'interno del cloud Microsoft 365 o Office 365, ma il data center potrebbe essere in una regione geografica diversa rispetto agli utenti che stanno partecipando alla conferenza. Questa operazione può verificarsi in due modi:

- Se l'organizzatore della riunione proviene da un'azienda diversa rispetto ai partecipanti, e la relativa organizzazione è ospitata in una località geografica o paese/regione diversa.

- Se un utente partecipa da un paese o una regione diversa rispetto alla posizione dell'organizzazione dell'azienda, sia per il fatto che l'azienda è una multinazionale o che l'utente è in viaggio.

La buona notizia sull'uso di ExpressRoute in questo scenario è che con il componente aggiuntivo Premium di ExpressRoute i dati che seguono il percorso ExpressRoute passeranno automaticamente attraverso la dorsale di Microsoft, indipendentemente dalla regione geografica dell'organizzatore del data center dell'organizzazione della riunione.

 **Flusso delle chiamate di un utente online con riunione online**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Partecipare a una conferenza ospitata da un utente locale in una distribuzione Business Server Hybrid
<a name="bk_Figure3"> </a>

Ricorda che i server delle conferenze che supportano le conferenze ospitate sono determinati dalla posizione dell'organizzatore della riunione. In questo scenario, il flusso degli elementi multimediali per tutti gli utenti che partecipano a una conferenza pianificata da un utente locale in una distribuzione ibrida verrà fluire in un data center locale. Il segnalazione per gli utenti ospitati online verrà stabilito attraverso la loro organizzazione nel cloud, mentre gli elementi multimediali tenteranno una connessione diretta. In questo scenario, poiché entrambi gli utenti si connettono dall'interno della tua rete, è possibile una connessione media diretta, quindi ExpressRoute viene utilizzato solo per il traffico di segnalazione per l'utente ospitata online. Se un utente ospitato online si connette da Internet, l'elemento multimediale potrebbe attraversare ExpressRoute se per la connessione viene usato un server perimetrale online.

 **Flusso delle chiamate per una conferenza ospitata da un utente Business Server Hybrid**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Server perimetrale locale con conferenze ospitate su Microsoft 365 o Office 365
<a name="bk_Figure5"> </a>

Quando un utente ibrido partecipa a una conferenza ospitata online, sappiamo che il traffico di segnalazione e gli elementi multimediali saranno destinati al cloud Microsoft 365 o Office 365 e, poiché l'utente partecipa da Internet, normalmente verrebbe intrapreso un percorso Internet diretto. Tuttavia, in alcuni casi, ad esempio a causa di restrizioni del firewall, non è disponibile un percorso Internet diretto. In questo caso, un server perimetrale locale può inoltrare il traffico multimediale, il che causa il ritorno del traffico multimediale alla rete locale prima di attraversare il circuito ExpressRoute al cloud.

 **Utente locale che partecipa a una conferenza telefonica online utilizzando un server perimetrale locale**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

L'uso di [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) offre connettività PSTN utilizzando risorse locali come un trunk SIP o un gateway PSTN oppure utilizzando un dispositivo hardware minimo per l'integrazione con Skype for Business. Con Cloud Connector Edition, gli utenti sono ospitati online e fungono da normali utenti online quando non implicano piani per chiamate. Il traffico di segnalazione per scenari PSTN viaggia tra il client e il cloud attraverso una connessione ExpressRoute, se disponibile, e il traffico multimediale resta all'interno della WAN. In questo caso, il segnalazione ruota al cloud Microsoft 365 o Office 365 e termina al Cloud Connector.

 **Chiamata PSTN tramite il Sistema telefonico in Microsoft 365 o Office 365 e Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Skype Meeting Broadcast con utenti che partecipano da una rete del cliente
<a name="bk_Figure6"> </a>

Skype Meeting Broadcast è un caso d'uso speciale, che consiste in una riunione in due parti con ogni parte con profili di trasporto di rete diversi. La prima parte, quella più importante dal punto di vista delle prestazioni di rete, è la riunione interna. È la parte in tempo reale della riunione che include uno o più endpoint client che si connettono al server delle conferenze nel cloud. I dati trasmessi utilizzando questa parte della riunione sono esattamente come nell'esempio precedente, con un utente che partecipa a una conferenza online.

Ciò che rende univoco Skype Meeting Broadcast è che la riunione è distribuita a un numero elevato di partecipanti alla conferenza utilizzando un servizio di trasmissione in streaming. Questo servizio di trasmissione in streaming non può essere instradato attraverso ExpressRoute, ma usa invece Internet con il supporto facoltativo dei servizi CDN (Content Delivery Network). È utile riconoscere che la trasmissione in streaming è un flusso multimediale unidirezionale perché i partecipanti ascoltano ma non parlano e supporta il buffering, quindi è molto meno sensibile ai problemi di prestazioni di rete come latenza, perdita di pacchetti e instabilità. Invece di ottimizzare il traffico di trasmissione per questi problemi, è ottimizzato per l'utilizzo della larghezza di banda perché è potenzialmente presente un numero molto elevato di partecipanti che ricevono gli elementi multimediali in streaming.

 **Skype Meeting Broadcast con utenti della rete del cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Modelli di flusso delle chiamate per tipo di distribuzione

Con i comuni esempi di flusso delle chiamate illustrati in precedenza e la comprensione dei principi generali che controllano i modelli di traffico, le tabelle seguenti offrono un riepilogo dei modelli di traffico per una grande combinazione di scenari di distribuzione e utilizzo. Queste tabelle non catturano tutte le possibili combinazioni dei flussi delle chiamate, ma dovrebbero aiutarti a comprendere ulteriormente i principi generali del flusso delle chiamate.

I dati vengono trasmessi ed elencati come locali all'organizzazione; non lascia la rete del cliente, Internet o ExpressRoute. I criteri elencati di seguito si basano sulle impostazioni di rete più comuni, ad esempio firewall, federazione e Internet, e presuppongono che tutte le organizzazioni coinvolte in flussi tra più utenti o federati dispongono di ExpressRoute. In pratica, la presenza di impostazioni diverse può comportare modelli di traffico diversi rispetto a quelli elencati di seguito.

### <a name="call-flows-for-skype-for-business-online"></a>Flussi delle chiamate per Skype for Business online

Gli scenari di utilizzo di Skype for Business online coinvolgono utenti ospitati online e possono essere chiamate dalla tua rete interna o da Internet. I server locali non fanno parte di questi scenari, quindi il flusso di tutti gli elementi multimediali correlati a conferenze o PSTN verrà collegato al cloud e anche il server perimetrale degli utenti online sarà nel cloud.

 **Riepilogo dei flussi delle chiamate per Skype for Business online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla tua rete.  <br/> |ExpressRoute  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Microsoft 365 o Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chiamate peer-to-peer  <br/> |Due client, uno sulla tua rete (interno) e l'altro su Internet (esterno).  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: Internet  <br/> |Utente interno: ExpressRoute  <br/> Utente esterno: da Internet al server perimetrale Microsoft 365 o Office 365.  <br/> |[Chiamata peer-to-peer per utenti di Microsoft 365 o Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Presuppone che il firewall blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, uno sulla tua rete (interno) e uno presso l'utente online sulla rete dell'organizzazione federata (federato).  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. Il traffico dall'utente interno al server perimetrale online segue un percorso simile a quello del server delle conferenze per la conferenza telefonica.  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente  <br/> |Client sulla tua rete e server delle conferenze nel cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza telefonica da parte di un utente in Internet  <br/> |Il client è su Internet e il server delle conferenze è nel cloud.  <br/> |Internet  <br/> |Internet  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Partecipare a una conferenza ospitata da un server locale di un'altra azienda  <br/> |Il client è sulla tua rete e il server delle conferenze è in un centro dati di terze parti.  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Poiché il server delle conferenze che ospita la conferenza si trova su una rete locale di un cliente diverso, attraverso il cloud Microsoft non passerà alcun dato.  <br/> |
|Chiamata PSTN  <br/> |Client nella rete del cliente e server sistema telefonico nel cloud  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chiamata PSTN  <br/> |Client su Internet e server Sistema telefonico nel cloud  <br/> |Internet  <br/> |Internet  <br/> |Non applicabile  <br/> |Il flusso degli elementi multimediali e il traffico di segnalazione verrà verso il centro dati Microsoft 365 o Office 365. Poiché l'endpoint client è su Internet, il flusso di tutti i dati verrà fluire verso il data center Microsoft attraverso Internet (anche se per la connettività è necessario un server perimetrale online).  <br/> |

> [!NOTE]
> ExpressRoute verrà usato nel percorso multimediale da un utente situato sulla rete aziendale a un server perimetrale online, ma non verrà usato se viene usato il server perimetrale per la distribuzione locale di un altro cliente.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Flussi delle chiamate per Skype for Business Hybrid

I flussi delle chiamate ibridi si applicano quando si ha una distribuzione Skype for Business che include almeno alcuni utenti ospitati in locale. I flussi delle chiamate in questa sezione includono sia le conferenze locali che le chiamate peer-to-peer o PSTN con almeno un utente ospitato in sede.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamate peer-to-peer  <br/> |Due client, entrambi sulla rete del cliente e ospitati localmente  <br/> |Locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Microsoft 365 o Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Poiché gli utenti sono ospitati localmente, il flusso del traffico di segnalazione viene eseguito localmente verso il data center locale anziché verso il cloud.  <br/> |
|Chiamate peer-to-peer  <br/> |Due client, che si connettono entrambi dalla rete del cliente. Uno è ospitato online, mentre l'altro è ospitato localmente.  <br/> |Utente online: ExpressRoute  <br/> Utente locale: locale  <br/> |locale  <br/> |[Chiamata peer-to-peer per utenti di Microsoft 365 o Office 365 dall'interno della rete del cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Solo l'utente ospitato online invia il traffico di segnalazione al cloud.  <br/> |
|Chiamata peer-to-peer a un utente di un'organizzazione federata  <br/> |Due client, un utente locale sulla rete del cliente (interno) e un utente online presso la rete dell'azienda federata (federato).  <br/> |Utente interno: locale  <br/> Utente federato: ExpressRoute  <br/> |Internet o ExpressRoute (dipende se viene utilizzato un server perimetrale online o locale)  <br/> |[Utente online sulla tua rete](call-flow-using-expressroute.md#bk_Figure3) che partecipa a una conferenza ospitata online e parte del server perimetrale locale con conferenze ospitate su [Microsoft 365 o Office 365](call-flow-using-expressroute.md#bk_Figure5) (per il traffico multimediale). <br/> |Presuppone un firewall che blocchi le connessioni dirette tra client, il che richiede un server perimetrale online. La negoziazione ICE offrirà per la connettività sia server online (da parte dell'utente online) che server perimetrali locali (dall'utente locale).  <br/> |
|Partecipare a una conferenza telefonica da parte di un utente in una rete del cliente (conferenza pianificata dall'utente online)  <br/> |Utente locale sulla tua rete e server delle conferenze nel cloud.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[Utente online sulla tua rete che partecipa a una conferenza ospitata online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Le risorse del server per la conferenza telefonica sono definite dall'organizzatore della riunione. In questo caso è stata pianificata da un utente online, quindi le risorse sono nel cloud.  <br/> |
|Chiamata PSTN  <br/> |Utente locale sulla tua rete e centro dati Skype for Business locale.  <br/> |Locale  <br/> |Locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Scenario simile a quello per l'uso di Cloud Connector Edition, eccetto per il fatto che l'utente è ospitato localmente, quindi il traffico di segnalazione rimane all'interno della tua rete.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Flussi delle chiamate per Skype for Business con Cloud Connector

Gli utenti che effettuano la connessione a Cloud Connector Edition sono tutti ospitati online. Ciò significa che la conferenza sarà online, e il traffico di segnalazione segue gli stessi modelli degli utenti online. Per gli scenari diversi da quelli delle chiamate PSTN, il flusso delle chiamate sarà esattamente quello descritto in precedenza per Skype for Business online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Scenario di utilizzo** <br/> |**Endpoint** <br/> |**Percorso del traffico di segnalazione** <br/> |**Percorso degli elementi multimediali** <br/> |**Flusso di esempio** <br/> |**Note** <br/> |
|Chiamata PSTN  <br/> |Utente online sulla tua rete che utilizza Cloud Connector Edition.  <br/> |locale  <br/> |locale  <br/> |[Chiamata PSTN utilizzando Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chiamata PSTN  <br/> |Utente online che utilizza Internet con Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinazione di server perimetrale locale con conferenze ospitate su [Microsoft 365 o Office 365](call-flow-using-expressroute.md#bk_Figure5) e chiamate [PSTN con Skype for Business Cloud Connector Edition.](call-flow-using-expressroute.md#bk_Figure6)  <br/> |Gli utenti Internet effettueranno la connessione attraverso il server perimetrale incluso in Cloud Connector, mentre Cloud Connector effettuerà la connessione alla rete PSTN.  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Documentazione di ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


