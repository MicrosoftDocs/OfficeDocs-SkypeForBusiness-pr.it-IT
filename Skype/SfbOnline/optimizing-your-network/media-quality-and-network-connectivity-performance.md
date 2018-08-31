---
title: Qualità multimediale e prestazioni della connettività di rete
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: In questo argomento definisce il set di requisiti di prestazioni di rete per Skype per i servizi in linea di Business e la valutazione della rete in base a come è possibile scegliere di utilizzare Internet o ExpressRoute per la connettività tra la rete e Skype Business online connettività. Se si è deciso di distribuire ExpressRoute Azure per la connettività dedicata a Office 365, questo documento vengono inoltre fornite indicazioni su come pianificare le connessioni ExpressRoute in Skype diversi per gli scenari aziendali in linea.
ms.openlocfilehash: 3a57ba58e2881f2e279949877d17e115cb1c23df
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779357"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online

In questo argomento definisce il set di requisiti di prestazioni di rete per Skype per i servizi in linea di Business e la valutazione della rete in base a come è possibile scegliere di utilizzare Internet o ExpressRoute per la connettività tra la rete e Skype Business online connettività. Se si è deciso di distribuire ExpressRoute Azure per la connettività dedicata a Office 365, questo documento vengono inoltre fornite indicazioni su come pianificare le connessioni ExpressRoute in Skype diversi per gli scenari aziendali in linea.
  
La qualità dei supporti in tempo reale (audio, video e condivisione di applicazioni) over IP notevolmente è interessata dalla qualità della connettività di rete end-to-end. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
ExpressRoute Azure non è un requisito per servizi di Office 365 inclusi Skype Business online. Tuttavia, ExpressRoute Azure è una distribuzione di opzioni disponibili che verranno consentono di assicurarsi che la connettività a Office 365 soddisfi Skype per requisiti di prestazioni di rete aziendali e garantisce Skype ottimale per i supporti del Business Online QoE.
  
> [!TIP]
> Anche se questo argomento vengono fornite Guida generale delle prestazioni delle reti, guida completa per la valutazione della rete non rientra nell'ambito di questo documento. Per trovare un elenco di Skype per partner aziendali Online che possono rivelarsi utili per le misurazioni delle prestazioni di rete come parte di una valutazione completa e completa la rete, visitare [Skype per le soluzioni Partner aziendali](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisiti di connettività di rete per Skype Business online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fattori che influiscono su Skype per Business Online della qualità multimediale

Esistono molti diversi fattori che contribuiscono a Skype per la qualità dei supporti (audio, video e applicazioni condivisione) Business Online in tempo reale che includono i dispositivi che vengono utilizzati, l'ambiente e la connettività di rete. 
  
#### <a name="devices"></a>Dispositivi

In una sessione multimediale in tempo reale, supporti l'acquisizione e il rendering dei dispositivi utilizzati da tutti i partecipanti, ad esempio auricolari e Web camme avere un impatto significativo sul complessiva qualità audio e video. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Sebbene certified dispositivi multimediali audio e video non siano obbligatori, è consigliabile dispositivi certificati per Skype for Business per l'esperienza multimediale ottimale. Per un elenco di tutti i Skype per le aziende dispositivi certificati, vedere [telefoni e dispositivi per Skype per le aziende](https://technet.microsoft.com/en-us/office/dn947482). È possibile utilizzare [Skype per Business Online i Dashboard qualità delle chiamate](/microsoftteams/turning-on-and-using-call-quality-dashboard), disponibili in **Skype per Business admin center**, per verificare i dispositivi in uso funzionino correttamente e monitorare la qualità multimediale audio e video.
  
> [!TIP]
> **Un dispositivo certificato è necessario per Skype ottimale per la qualità multimediale Business**.
  
È importante ricordare che eventuali dispositivi multimediali, Skype per i client aziendali e Skype per server aziendali tramite i flussi multimediali in tempo reale, introdurre alcune quantità di latenza. Il dispositivo e il software elaborazione latenza e la latenza di rete, avere un impatto significativo e di collaborazione per la latenza complessiva end-to-end e dell'utente finale.
  
#### <a name="environment"></a>Ambiente

L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere una visione dell'utilizzo di audio e video esperienza dell'utente di Skype per app Business **Strumenti** > **Opzioni** > **Dispositivo Audio** o **Video** per apportare modifiche al dispositivo in uso e personalizzare le impostazioni. È inoltre possibile controllare la qualità dell'audio di una chiamata facendo clic su **Controlla qualità chiamata**. Se gli utenti fanno clic su **Controllo qualità chiamata**, possono segnalare li livello di qualità e i problemi riscontrati con una chiamata di prova.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Rete

La qualità dei dati multimediali in tempo reale tramite rete IP notevolmente è interessata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:
  
- **Latenza** Questo è il tempo che necessario per ottenere un pacchetto IP da un punto a punto B sulla rete. Questo ritardo di propagazione della rete è essenzialmente associato alla distanza fisica tra i due punti e la velocità della luce, incluso l'overhead aggiuntivo effettuate dal router diversi intermedi. Latenza viene misurata unidirezionali o round trip Time (RTT).
    
- **Perdita di pacchetti** Questo spesso è definito come una percentuale di pacchetti persi in un determinato intervallo di tempo. Perdita di pacchetti influisce direttamente sulla qualità dell'audio, ovvero da piccoli, singole perdita pacchetti non con quasi alcun impatto, a perdite burst back to back causare completo ritaglio audio.
    
- **Pacchetti tra arrivo instabilità o semplicemente instabilità** Si tratta della modifica Media in ritardo tra i pacchetti successivi. Più moderni VoIP software, inclusi Skype per le aziende possono essere adattate a alcuni livelli di instabilità attraverso la memorizzazione nel buffer. È solo quando l'instabilità supera la memorizzazione nel buffer che un partecipante potrà notare gli effetti di instabilità.
    
> [!NOTE]
>  La memorizzazione nel buffer di instabilità aumenterà latenza end-to-end.
  
Con molti Skype simultanee per sessioni multimediali in tempo reale in linea di Business, nonché altro traffico di rete generati da altre applicazioni aziendali e altri servizi di Office 365, assicurandosi che vi sia larghezza di banda sufficiente tramite l'intero percorso di rete che si connette alla rete per il Skype per servizio Business Online è fondamentale per evitare di congestione della rete e garantire una qualità multimediale in tempo reale (audio, video e applicazioni condivisione) eccellente supporto. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>L'implementazione di qualità del servizio (QoS) su reti traffico ridotto

Inoltre, congestione di traffico attraverso una rete notevolmente influirà sulla qualità multimediale. Per consentire i pacchetti audio e video per viaggio della rete più rapida e avere una priorità su altro traffico di rete in una rete traffico ridotto, qualità del servizio (QoS) consente di assicurare un'esperienza utente ottimale per le comunicazioni audio e video.
  
QoS consente di assegnare priorità maggiore ai pacchetti di rete che sono che contiene i dati audio o video. Per assegnare una priorità superiore a questi pacchetti, le comunicazioni audio e video sono probabilmente di viaggiare sulla rete più rapidamente e con meno interruzioni di sessioni di rete che coinvolgono elementi quali trasferimenti di file, esplorazione del web o backup dei database. Ciò avviene perché i pacchetti di rete utilizzato per i trasferimenti di file o backup dei database per impostazione predefinita vengono assegnati "massimo sforzo" come una priorità e non sarà necessario congestione della rete come grande impatto. Se non assegnare una priorità superiore ai pacchetti media (condivisione audio, video e applicazioni) e lasciare loro assegnato anche come "massimo sforzo", sono troppo verranno elaborate insieme a tutto il traffico di rete. A seconda della quantità di congestione della rete, potenzialmente fine in un'esperienza complessiva audio e video di qualità inferiore per gli utenti.
  
È consigliabile implementare QoS sulla rete per verificare che un impatto non disporrà di congestione della rete all'interno della rete. Per questa opzione per essere il massimo impatto, tuttavia, tutti gli endpoint di reti devono supportare QoS, indica che tutti gli endpoint è necessario che il contrassegno QoS e definizione delle priorità dei pacchetti. Skype per i servizi Online Business positivamente il contrassegno QoS e ordine di priorità all'interno della rete di Microsoft. Tuttavia, il traffico viene instradato attraverso una connessione pubblica come Internet dalla rete aziendale per la rete di Microsoft non mantiene QoS classificazione e definizione delle priorità dei pacchetti. Le connessioni dalla rete private a Office 365 utilizzando [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) offrono una soluzione di distribuzione che consente di mantenere QoS contrassegni e ordine di priorità dei pacchetti a sua volta aumenterà generale audio e la qualità video per gli utenti finali.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisiti relativi alle prestazioni di rete a cui connettersi Skype Business online
<a name="bkNetworkPerf"> </a>

Skype per i segnali multimediali in tempo reale Business passa attraverso numerosi dispositivi diversi, applicazioni client, software server e tra reti diverse. La latenza end-to-end di dati multimediali in tempo reale è la quantità totale di latenza che è stato introdotto in tutti i componenti e i segmenti di rete. La qualità della connessione di rete end-to-end dipende dal segmento di rete con la qualità peggiore. Questo segmento funge da un collo di bottiglia per il traffico di rete.
  
Nel diagramma seguente illustra flusso audio unidirezionale in una conferenza da una Skype per partecipante Business a un altro.
  
![Flusso di chiamate ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In questo scenario di conferenza, è necessario eseguire percorso multimediale tra i segmenti di rete seguenti:
  
1. **Connessione da 1 utente e il lato della rete di Microsoft** Generalmente, si tratta di una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN dall'utente 1 per il punto di uscita Internet (dispositivo Edge network) e la connessione Internet tra la rete perimetrale Microsoft network Edge.
    
2. **Connessione all'interno della rete di Microsoft** Si tratta tra Edge Microsoft a Skype per centro dati Business in linea, dove l'A / V Conferencing Server vengono utilizzati.
    
3. **Connessione all'interno della rete di Microsoft** Si tratta tra Skype per data center Business Online e Microsoft network Edge.
    
4. **Connessione dal bordo rete Microsoft all'utente 2** Sono incluse la connessione Internet tra la rete perimetrale Microsoft network Edge, la connessione WAN dall'utente 2 per il punto di uscita Internet, rete perimetrale e la connessione di rete, ad esempio un WiFi o un Ethernet.
    
Nel diagramma seguente mostra suddivisione dei componenti e dei segmenti di rete di Skype per chiamata PSTN in linea aziendale:
  
![Flusso di chiamate di operatore di telefonia PSTN ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In uno scenario di chiamata PSTN, il percorso multimediale croci i segmenti di rete seguenti:
  
1. **Connessione da Skype per chiamante client aziendali e il lato della rete di Microsoft** Generalmente, si tratta di una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN tra Skype per chiamante client Business il punto di uscita Internet (dispositivo Edge network) e la connessione Internet tra la rete perimetrale Microsoft network Edge.
    
2. **Connessione all'interno della rete di Microsoft** Si tratta tra Edge Microsoft a Skype per data center Business Online, in cui viene utilizzato un server Mediation Server.
    
3. **Connessione all'interno della rete di Microsoft** Si tratta tra Skype per data center Business Online e Microsoft network Edge.
    
4. **Connessione tra Microsoft Network e i partner di provider di servizi PSTN** Si tratta della connessione esistente per mettere una chiamata PSTN da Skype per client di Business che è all'esterno della rete di Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisiti relativi alle prestazioni di rete da Skype per client Business a Microsoft di rete perimetrale
<a name="bkSfBClienttoEdge"></a>

Skype ottimale per la qualità dei supporti aziendali, i seguenti obiettivi metriche delle prestazioni di rete o soglie sono necessarie per una connessione di rete della società a Microsoft network Edge. In questo segmento di rete include la rete interna, sono incluse tutte le connessioni WiFi e una scheda Ethernet, qualsiasi tipo di traffico da sito aziendale tramite una connessione WAN, ad esempio commutazione etichetta Multiprotocol (MPLS), nonché il partner Internet o ExpressRoute connessioni a Microsoft di rete perimetrale.
  
> [!CAUTION]
> **Connettività tra Skype per Business client sulla rete aziendale per servizi di Office 365 deve soddisfare i seguenti requisiti di prestazioni di rete e soglie.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (unidirezionale)  <br/> |< 50ms  <br/> |
|Latenza (RTT o tempo di round trip)  <br/> |< 100 ms  <br/> |
|Burst di perdita di pacchetti  <br/> |< pari al 10% durante un intervallo di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |< % 1 durante qualsiasi 15s intervallo  <br/> |
|Instabilità in arrivo tra pacchetti  <br/> |< 30 ms durante qualsiasi 15s intervallo  <br/> |
|Riordino dei pacchetti  <br/> |< pacchetti in ordine 0,05%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- Microsoft network ha le posizioni dei bordi oltre 160 tutto il mondo. Si lavora principali provider di servizi Internet (ISP) in tutto il mondo a quei siti Edge. L'obiettivo di metriche di latenza presuppone sito della società o siti e Edges Microsoft si trovino sulla stessa continente.
    
- La società o più siti di Microsoft network connessione Edge includono primo accesso alla rete hop, che può essere WiFi o qualsiasi altra tecnologia wireless. 
    
- I target di prestazioni di rete si presuppone che la larghezza di banda appropriato e/o di qualità del servizio di pianificazione. In altre parole, applicabile direttamente a Skype per il traffico multimediale in tempo reale Business quando la connessione di rete è sottoposto a un carico di picco.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisiti relativi alle prestazioni di rete dalla rete perimetrale a Microsoft di rete perimetrale
<a name="bkYourNetworkEdge"> </a>

Di seguito è gli obiettivi di prestazioni di rete o soglie necessari per la connessione tra la rete perimetrale e Microsoft network Edge. In questo segmento di rete esclude rete interna del cliente o WAN ed è progettato come guida per il test del traffico di rete che viene inviato tramite Internet o tramite una rete di partner ExpressRoute e può essere utilizzato anche durante la negoziazione sulle prestazioni Service Level Agreement (SLA) con il provider ExpressRoute.
  
> [!CAUTION]
> **Connettività tra la rete aziendale Edge e il margine di rete Microsoft deve soddisfare i seguenti requisiti di prestazioni di rete e soglie.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (unidirezionale)  <br/> |< 30 ms  <br/> |
|Latenza (RTT)  <br/> |< 60 MS  <br/> |
|Burst di perdita di pacchetti  <br/> |< % 1 durante un intervallo di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |< 0,1% durante qualsiasi 15s intervallo  <br/> |
|Instabilità in arrivo tra pacchetti  <br/> |< 15 ms durante qualsiasi 15s intervallo  <br/> |
|Riordino dei pacchetti  <br/> |< pacchetti in ordine allo 0,01%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- Destinazione prestazioni richiede la connessione tra una rete aziendale Edge e il più vicino Microsoft network Edge a trovarsi nella stessa continente.
    
- I target di prestazioni di rete si presuppone che la larghezza di banda appropriato e/o di qualità del servizio di pianificazione. Questo vale anche per Skype per il traffico multimediale in tempo reale Business quando la connessione di rete è sottoposto a un carico di picco. Per la pianificazione QoS e la larghezza di banda appropriato, fare riferimento a [ExpressRoute e QoS in Skype Business online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Misurare le prestazioni della rete
<a name="bkNetworkPerf"> </a>

Per misurare le prestazioni di rete effettive, in particolare per latenza e la perdita di pacchetti, da un sito di rete della società a una rete perimetrale, è possibile utilizzare gli strumenti, ad esempio ping, con una serie di Skype per media relay servizi in esecuzione Microsoft Edge e dati di test siti centro. 
  
Per testare le connessioni Internet alla rete Microsoft, è consigliabile confrontare VIP seguenti di Skype di inoltro media Business. *VIP Anycast* verrà risolto in un indirizzo IP dei Media Relay Server in Microsoft rete perimetrale in un sito vicino alla località test.
  
||||
|:-----|:-----|:-----|
|**Indirizzo IP** <br/> |**Tipo** <br/> |**Posizione** <br/> |
|13.107.8.2  <br/> |INDIRIZZO IP VIRTUALE  <br/> |World Wide Anycast IP  <br/> |
   
 **Di seguito sono riportati alcuni consigli di alto livelli da seguire per la valutazione delle prestazioni di rete:**
  
- È necessario valutare la rete interna, nonché le connessioni a Office 365.
    
- È necessario valutare e raccogliere dati per tutte le reti per un lungo periodo di tempo. È consigliabile per poter eseguire il test delle prestazioni della rete per un periodo minimo di una settimana, in modo che è possibile visualizzare i modelli di utilizzo per tutti i giorni lavorativi e le ore. Verranno visualizzate le ore di punta.
    
- È consigliabile eseguire più esempi di misurazioni delle prestazioni di rete. Si consiglia di prendere una misura 10 minuti da un sito di società durante l'intero periodo di tempo che si raccolgono dati. Per confrontare Skype per Business Online requisiti di prestazioni di rete, accettare il valore di misura percentile 90 di questo set di dati di esempio. 
    
- È necessario valutare continuamente le prestazioni della rete. Utilizzo della rete varia nel tempo dovuta a modifiche del modello di dati di utilizzo, nuove applicazioni aziendali che utilizzano una grande quantità di larghezza di banda e le modifiche apportate ai percorsi fisico o dell'organizzazione della società. È importante monitorare le prestazioni di rete rispetto a questi requisiti relativi alle prestazioni di rete e gli obiettivi/soglie continuamente e apportare modifiche tempestivi per garantire la qualità multimediale in tempo reale ottimale. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Misurare le prestazioni della rete utilizzando macchine virtuali di Azure
<a name="bkNetworkPerf"> </a>

Invece di test con i siti di Microsoft rete perimetrale, sono disponibili soluzioni di valutazione di rete di Skype per i clienti aziendali e partner che utilizza la verifica dell'installazione per i servizi cloud Microsoft Azure. In tali soluzioni, gli strumenti di valutazione di rete verificare latenza, la perdita di pacchetti e instabilità rispetto degli endpoint personalizzati impostare come servizio nel cloud Azure. Di conseguenza, il traffico di rete di testing passa attraverso un segmento di rete aggiuntive, ovvero la connessione all'interno della rete Microsoft tra i bordi di rete e Azure data Center che ospita il servizio di valutazione di rete.
  
Per tali rete soluzioni assessment basate su Azure ospitata verificare i servizi. È consigliabile eseguire la valutazione della rete all'interno di paese e/o area. Ad esempio, per i siti dei clienti negli Stati Uniti orientale, la valutazione deve essere eseguita su un'istanza del servizio test ospitata in orientale dell'Azure area del centro dati negli Stati Uniti. 
  
Di seguito è la latenza delle destinazioni (RTT) per l'installazione di valutazione Azure servizio basato su rete. Gli obiettivi di latenza unidirezionale sarà metà delle destinazioni RTT corrispondente. Gli obiettivi di instabilità e perdita di pacchetti rimane uguale come quelle definite per Skype Media Relay basato su test.
  
|||||
|:-----|:-----|:-----|:-----|
|**Area del cliente** <br/> |**Area di Azure** <br/> |**Rete perimetrale - tempo di round trip Azure (RTT)** <br/> |**Il sito - tempo di round trip Azure (RTT)** <br/> |
|Usa centrale  <br/> |Usa centrale  <br/> |99  <br/> |139  <br/> |
|Usa orientale  <br/> |Usa orientale  <br/> |86  <br/> |126  <br/> |
|Nord centrale USA  <br/> |Nord centrale USA  <br/> |97  <br/> |137  <br/> |
|Sud centrale USA  <br/> |Sud centrale USA  <br/> |94  <br/> |134  <br/> |
|Usa occidentale  <br/> |Usa occidentale  <br/> |94  <br/> |134  <br/> |
|Hawaii negli Stati Uniti  <br/> |Usa occidentale  <br/> |116  <br/> |156  <br/> |
|Canada centrale  <br/> |Canada centrale  <br/> |138  <br/> |178  <br/> |
|Canada orientale  <br/> |Canada orientale  <br/> |131  <br/> |171  <br/> |
|Nord Europa  <br/> |Nord Europa  <br/> |99  <br/> |139  <br/> |
|Europa occidentale  <br/> |Europa occidentale  <br/> |95  <br/> |135  <br/> |
|Asia orientale  <br/> |Asia orientale  <br/> |118  <br/> |158  <br/> |
|Sud-est asiatico  <br/> |Sud-est asiatico  <br/> |97  <br/> |137  <br/> |
|Giappone Oriente  <br/> |Giappone Oriente  <br/> |111  <br/> |151  <br/> |
|Giappone ovest  <br/> |Giappone ovest  <br/> |118  <br/> |158  <br/> |
|Sud Brasile  <br/> |Sud Brasile  <br/> |70  <br/> |110  <br/> |
|Australia orientale  <br/> |Australia orientale  <br/> |124  <br/> |164  <br/> |
|Australia sud-est  <br/> |Australia sud-est  <br/> |124  <br/> |164  <br/> |
|India centrale  <br/> |India centrale  <br/> |103  <br/> |143  <br/> |
|India meridionale  <br/> |India meridionale  <br/> |103  <br/> |143  <br/> |
|India occidentale  <br/> |India occidentale  <br/> |103  <br/> |143  <br/> |
|Cinese Oriente  <br/> |Cinese Oriente  <br/> |120  <br/> |160  <br/> |
|Nord cinese  <br/> |Nord cinese  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualità multimediale ed ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure per Office 365 è una connessione di rete dedicato per la connessione a Office 365. Offre ai clienti la possibilità di controllare il percorso loro il traffico di rete di Office 365. Non è più hanno problemi imprevisti ciclo che si verifica in Internet in cui viene eseguiti dati dai gestori telefonici sconosciuti, provider e provider di servizi Internet. Il traffico di rete che viene inviato tramite ExpressRoute verrà inviato direttamente tramite rete dell'organizzazione partner ExpressRoute alla rete Microsoft. In questo modo i clienti di gestire Office 365 come se si trova centri di dati esterni con una connessione dedicata.
  
ExpressRoute Azure è disponibile per tutte le offerte di licenze di Office 365. Tuttavia, il componente aggiuntivo Premium ExpressRoute Azure è necessario per Office 365 abilitare il routing globale. I clienti di Office 365 con almeno 500 postazioni che implementano ExpressRoute possono ottenere necessari *ExpressRoute Premium aggiuntivo* non spese aggiuntive.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute necessari per la qualità multimediale ottimale?

ExpressRoute Azure non è un requisito per la visualizzazione Skype ottimale per la qualità multimediale Business Online. È tuttavia, uno della distribuzione di opzioni che consentono di assicurano che la connettività del cloud soddisfi Skype per gli obiettivi di prestazioni rete aziendale o soglie.
  
Office 365 è una prestazioni elevate e il servizio sicura che utilizza Internet. È continuano a investire in nuove funzionalità di sicurezza e regionali nodi Edge per continuare a migliorare le prestazioni e protezione. ExpressRoute Azure non è un requisito per servizi di Office 365 inclusi Skype Business online. ExpressRoute Azure è una distribuzione di opzioni disponibili che verranno consentono di assicurarsi che la connettività a Office 365 soddisfi Skype per requisiti di prestazioni di rete aziendali e garantisce Skype ottimale per la qualità multimediale Business Online esperienza.
  
Per Skype per la qualità multimediale in linea aziendale, è importante che la connessione tra i siti della società e i bordi di rete Microsoft soddisfi gli obiettivi di prestazioni in requisiti [le prestazioni della rete da Skype per client Business alla rete di Microsoft Bordo](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) e che la connessione tra i bordi di rete e i bordi di rete Microsoft soddisfi gli obiettivi di prestazioni in [requisiti relativi alle prestazioni di rete dalla rete perimetrale per Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
È inoltre importante che la connettività di rete fisica dell'azienda, tra cui la capacità di connettività di rete e cloud interna supportare il volume del traffico multimediale picco. ExpressRoute Azure è uno dei molti modi che consente di verificare che le Skype per la connettività cloud in linea aziendale soddisfi tutti questi requisiti di prestazioni.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute necessari per SLA qualità vocale?

No, ExpressRoute non è obbligatorio per Skype per Business Online vocale qualità contratto di servizio. [Skype per SLA di qualità vocale Online Business](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) si applica a qualsiasi chiamata idoneo effettuata da qualsiasi Skype per utente del servizio vocale aziendale Online all'interno della licenza corretta e sottoscrizione che consente all'utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. Deve includere un contratto di servizio di qualità vocale che si basano tutte le condizioni seguenti:
  
- Le chiamate provenienti da Microsoft certified telefoni IP.
    
- Connessioni Ethernet cablate.
    
- Problemi di qualità audio a causa di problemi di Microsoft Network.
    
> [!NOTE]
> Il contratto di servizio di qualità vocale esclude tali chiamate dove la qualità delle chiamate ridotto è dovuta a problemi di reti non Microsoft inclusi ExpressRoute partner e altre reti. 
  
### <a name="internet-or-azure-expressroute"></a>Internet o ExpressRoute Azure?

Prima di prendere una decisione sulla rete opzioni di integrazione applicativa per Skype Business online, è necessario valutare i clienti corrente in base ai requisiti di prestazioni di rete descritti in requisiti relativi alle prestazioni di rete [per la connettività Internet e della rete connettersi a Skype Business online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se le prestazioni della rete con la connessione Internet corrente viene impostata per una capacità sufficiente durante periodi di picco e che soddisfi i requisiti di prestazioni di rete da siti ai bordi di rete di Microsoft e verso i bordi di rete ai bordi di rete di Microsoft, è possibile continuare a utilizzare la connettività Internet esistente a cui connettersi Skype Business online.
  
Società nei siti di cui non sono stati soddisfatti i requisiti di prestazioni rete, è consigliabile innanzitutto collaborare con i provider di servizi di rete esistente per migliorare le prestazioni complessive della rete. Tuttavia, se che non sono ancora vengono soddisfatti, utilizzando Azure ExpressRoute possibile evitare che il Skype per la connettività cloud Business Online consentono di soddisfare i requisiti di prestazioni di rete.
  
ExpressRoute Azure sono disponibili ulteriori vantaggi seguenti:
  
- Un contratto di servizio (SLA) sulla disponibilità della connessione tra la rete e Microsoft network. ExpressRoute dispone di un contratto di servizio garantito disponibilità del 99,9%.
    
- Pianificati e garantito larghezza di banda necessaria per servizi di Office 365. È possibile ottenere questo risultato inviando solo il traffico di Office 365 o Skype per il traffico Business utilizzando il ExpressRoute e quindi dispone tutte le altre Internet passare il traffico tra i punti di ingresso/uscita altri Internet per la rete.
    
- ExpressRoute è progettato per mantenere il contrassegno DSCP QoS contrassegni tra la rete e Microsoft Network.
    
Per ulteriori informazioni sulla pianificazione della capacità ed ExpressRoute QoS, fare riferimento a [ExpressRoute e QoS in Skype Business online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>È possibile configurare Azure ExpressRoute per Skype per Business solo in linea?

Sì, è possibile impostare ExpressRoute Azure per garantire la connettività di rete eccellente dalla rete aziendale per solo Skype Business online. Ciò fornirà la qualità multimediale in tempo reale ottimale per gli utenti, ma è possibile continuare la connessione ad altri servizi di Office 365 tramite Internet.
  
Border Gateway Protocol (BGP) è un protocollo di routing su Internet che viene utilizzata per instradare il traffico di rete in Internet. Progettato per lo scambio di informazioni di routing tra sistemi autonomi (AS) trovate in Internet. I valori delle community BGP sono tag di attributi che possono essere applicati alle route in ingresso o in uscita. Le community BGP vengono spesso utilizzate per segnalare la ricezione come i collegamenti in uscita da utilizzare per raggiungere una destinazione specificata in base geography, tipo di servizio o altri criteri.
  
Con il supporto per le community BGP, Microsoft verrà contrassegnare con i valori di community BGP appropriati basati sul servizio che a cui appartengono i prefissi e route. Microsoft verrà contrassegnare i prefissi annunciati tramite peering pubblici e Microsoft peering con i valori di community BGP appropriati che indica l'area a cui sono ospitati nei prefissi. È possibile utilizzare i valori di community per prendere le decisioni di routing appropriate per offrire il routing ottimale. È possibile utilizzare il Skype per valore community BGP Online Business per l'installazione di una connessione ExpressRoute solo per Skype Business online. È possibile trovare ulteriori informazioni su [requisiti di routing ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scenari di integrazione applicativa ExpressRoute per Skype Business online
<a name="bkNetworkPerf"> </a>

Se si è deciso di ExpressRoute in base alle raccomandazioni precedenti è rivolta, ecco quante connessioni ExpressRoute e i suggerimenti in cui dovrebbe ottenere.
  
### <a name="online-only-deployment---single-site"></a>Distribuzione sola online - singolo sito

Se tutti gli utenti di utilizzare il Skype per servizio Business Online e delle sedi sono incentrate su un'unica posizione fisica e si decide di distribuire ExpressRoute Azure, è necessario impostare singola ExpressRoute connessione tra il sito aziendale per i collaboratori più stretti [Percorso peering ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
Nella figura seguente viene illustrato un esempio di questo tipo di distribuzione. In questo esempio, Contoso è un university nella Orlando, FL. 10.000 docenti e studenti contoso. I test Internet dal relativo percorso ai siti edge Microsoft hanno dimostrato maggiori di 5% la perdita di pacchetti durante le ore di punta classe. Di avere deciso ottenere una connessione dedicata a Office 365 utilizzando ExpressRoute con larghezza di banda si verifichi il provisioning per poter evitare di congestione della rete per Office 365 in particolare per Skype per il traffico in tempo reale in linea aziendale. Si connettono al cloud Microsoft tramite ExpressRoute nel sito di Atlanta, GA MeetMe.
  
![Sito singolo ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Distribuzione sola online - più siti su continente stesso

Se l'azienda utilizza Skype per i servizi Online Business da più uffici nella stessa area o continente e si sceglie di implementare ExpressRoute Azure, è consigliabile per connettere il sito principale tramite ExpressRoute e facoltativamente aggiungere ulteriori ExpressRoute peering per altri percorsi in grado di soddisfare gli obiettivi di prestazioni di rete consigliato.
  
Nell'esempio seguente, Contoso è una società di servizi di viaggi negli Stati Uniti che sede a New York, ma anche altri uffici in tutti gli Stati Uniti. Loro uffici sono tra connessi tramite una rete WAN che utilizza MPLS per la connessione a Office 365. Vengono inizialmente impostare una connessione ExpressRoute da loro router Internet Hoboken, New Jersey al sito MeetMe New York. 
  
Con questo programma di installazione per il traffico di rete dalla maggior parte dei propri siti Microsoft Network (sito Edge New York) può soddisfare Skype per Business client Connessione rete gli obiettivi di prestazioni descritti in requisiti di prestazioni della rete [da Skype per client di Business a Microsoft di rete perimetrale](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Tuttavia, verranno latenza tra uffici occidentale Contoso a New York tramite 50ms unidirezionale. Inoltre, Honolulu è la seconda più grande per Contoso, la latenza di Honolulu a New York supera 80ms unidirezionale. Per garantire una qualità multimediale ottimale per gli utenti di tali uffici, Contoso ha deciso di aggiungere un occidentale ExpressRoute connessione tra i siti Douglas San e il sito valle silicio ExpressRoute MeetMe.
  
![Esprimere Router più siti su continente stesso.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Distribuzione sola online - più siti in continenti diversi

Se tutti gli utenti utilizzano Skype per servizio Business Online e delle sedi sono in più posizioni fisiche tra più continenti, se si decide di distribuire ExpressRoute Azure, è consigliabile impostare almeno una connessione ExpressRoute per ogni continente tra siti principale di ogni continente il più vicino [ExpressRoute peering posizione](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). A seconda dei costi e benefici, è possibile distribuire le connessioni ExpressRoute dai siti di cui non sono soddisfatta gli obiettivi di prestazioni di rete.
  
Nell'esempio seguente, Contoso è un'azienda di grandi dimensioni legale aziendale con uffici a città principali in Nord America ed Europa. In base alle loro connessione Internet e la valutazione delle prestazioni di rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo ExpressRoute a commutazione di circuito per tutti i suoi uffici European.
  
![ExpressRoute con più siti e continenti.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Distribuzione ibrida

Se si dispone di un Lync in locale o Skype per la distribuzione di Business e sceglie di implementare un ambiente ibrido Skype per l'integrazione di Business in linea, è consigliabile che se si decide di distribuire ExpressRoute Azure, è necessario disporre di almeno una connessione ExpressRoute per ogni locale con Lync o Skype per sito Business Edge e almeno una connessione ExpressRoute per ogni continente con uffici. A seconda dei costi e benefici, per ogni continente è possibile distribuire le connessioni ExpressRoute da uffici dove gli obiettivi di prestazioni di rete non sono soddisfatte.
  
Se si dispone di un Skype locale per la distribuzione di Business, è necessario eseguire la [pianificazione dei Server perimetrali e Guida alla distribuzione](https://technet.microsoft.com/en-us/library/mt346417.aspx). In particolare, i server perimetrali devono essere raggiungibili all'esterno della rete. In genere realizzata mediante l'assegnazione di un indirizzo IP instradabile al server perimetrale o utilizzando il protocollo NAT (NAT).
  
Nell'esempio seguente, Contoso è un Skype locali esistenti per la distribuzione di Enterprise Voice Business. Si desidera eseguire la migrazione degli utenti locali ai servizi in linea di Office 365. Vengono inoltre deciso di utilizzare una distribuzione ibrida, in modo che possono continuare a utilizzare l'infrastruttura di rete PSTN esistente per tutte le organizzazioni locali e utenti in linea. Centro dati locali e Skype per i server perimetrali aziendali di Contoso sono Chicago. Per la distribuzione, Contoso ha deciso di impostare una connessione ExpressRoute tra i data center di Chicago ed ExpressRoute Chicago. Vengono inoltre aggiunti un occidentale connessione ExpressRoute per realizzare al meglio le office Honolulu.
  
![ExpressRoute ibrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Distribuzione in linea con Cloud connettore Edition

Skype per Business Online Cloud connettore Edition è che offrono un ambiente ibrido costituita da un insieme di largo macchine () che implementano la connettività PSTN in locale. Distribuendo un Skype minimo per la topologia Server aziendale in un ambiente virtualizzato, sarà in grado di inviare e ricevere chiamate con landlines e telefoni cellulari tramite l'infrastruttura vocale PSTN locale esistente.
  
Se si decide di distribuire ExpressRoute Azure e Cloud connettore Edition, è consigliabile consente di configurare almeno una connessione Express Route per ogni continente tra sito principale di ogni continente collaboratori più stretti [ExpressRoute peering posizione](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). A seconda dei costi e benefici, per ogni continente è possibile distribuire le connessioni ExpressRoute dai siti di cui non sono soddisfatte gli obiettivi di prestazioni di rete.
  
Se si dispone di un Skype locale per la distribuzione di Business, è necessario eseguire la [Guida alla pianificazione di Skype per Business Cloud connettore Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). In particolare, l'Access Edge Server e A / V Edge Server devono essere assegnati indirizzi IP pubblici e raggiungibile da Office 365 data center.
  
Nell'esempio seguente, Contoso è una società contabile European con la presenza in pochi principali paesi Europa e città. Quando si iscrivere Skype Business Online per tutte le proprie esigenze di collaborazione, essi deciso di inserire un connettore Cloud per ogni paese che hanno una posizione fisica per continuare a utilizzare l'infrastruttura di rete PSTN e i contratti di gestore già esistenti. In base alle loro di test da tutti i relativi siti e Microsoft network Edge, si è deciso che una singola connessione ExpressRoute Londra aiuterà soddisfare Skype per Business client Connessione rete gli obiettivi di prestazioni descritti in [le prestazioni della rete requisiti di Skype per client Business a Microsoft di rete perimetrale](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Connettore Cloud ExpressRoute uno.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Di seguito è un'altra opzione di distribuzione per Contoso. In questo caso, si ha deciso di configurare una connessione ExpressRoute in ogni sito in cui viene distribuito un connettore Cloud. 
  
![Connettore Cloud ExpressRoute due.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>See also

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)

  
 