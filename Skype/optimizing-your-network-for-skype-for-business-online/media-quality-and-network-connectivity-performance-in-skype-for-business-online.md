---
title: "Qualità multimediale e prestazioni della connettività di rete in Skype for Business online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 9/21/2016
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
description: "In questo argomento viene definita la serie di requisiti di prestazione di rete per i servizi di Skype for Business Online e le modalità di selezione tra Internet o ExpressRoute ai fini della connettività tra la propria rete e Skype for Business Online sulla base della valutazione della connettività di rete. Se si decide di distribuire Azure ExpressRoute ai fini della connettività dedicata a Office 365, questo documento fornisce inoltre delle linee guida su come pianificare le proprie connessioni ExpressRoute in diversi scenari di distribuzione di Skype for Business Online."
---

# Qualità multimediale e prestazioni della connettività di rete in Skype for Business online

In questo argomento viene definita la serie di requisiti di prestazione di rete per i servizi di Skype for Business Online e le modalità di selezione tra Internet o ExpressRoute ai fini della connettività tra la propria rete e Skype for Business Online sulla base della valutazione della connettività di rete. Se si decide di distribuire Azure ExpressRoute ai fini della connettività dedicata a Office 365, questo documento fornisce inoltre delle linee guida su come pianificare le proprie connessioni ExpressRoute in diversi scenari di distribuzione di Skype for Business Online.
  
La qualità della connettività di rete end-to-end influisce notevolmente sulla qualità dei supporti multimediali in tempo reale (condivisione di audio, video e applicazioni) su IP. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Azure ExpressRoute non è un requisito per i servizi di Office 365, tra cui Skype for Business Online. Tuttavia, Azure ExpressRoute è una delle opzioni di distribuzione disponibili per soddisfare i requisiti di prestazioni di rete di Skype for Business tramite la connettività con Office 365 e garantire un'esperienza multimediale di qualità ottimale su Skype for Business Online.
  
> [!TIP]
> Questo argomento fornisce solo delle linee guida generali sulle prestazioni di rete e la guida completa per la valutazione della rete non rientra nel suo ambito. Per l';elenco dei partner di Skype for Business Online in grado di offrire il loro aiuto durante la misurazione delle prestazioni di rete, come parte di una valutazione completa e approfondita della rete, visitare [Soluzioni partner Skype for Business](http://partnersolutions.skypeforbusiness.com/). 
  
## Requisiti di connettività di rete per Skype for Business Online

### Fattori che influiscono sulla qualità dei supporti multimediali di Skype for Business Online

Sono numerosi i fattori che incidono sulla qualità dei supporti multimediali in tempo reale di Skype for Business Online (condivisione di audio, video e applicazioni), tra cui i dispositivi usati, l'ambiente e la connettività della rete. 
  
#### Dispositivi

In una sessione multimediale in tempo reale, i dispositivi di rendering e acquisizione usati da tutti i partecipanti, come ad esempio cuffie auricolari e web cam, hanno un impatto notevole sulla qualità complessiva di audio e video. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Anche se non è richiesto l'uso di supporti audio e video certificati, si consiglia vivamente di usare dispositivi certificati per Skype for Business per assicurare un'esperienza multimediale ottimale. Per l'elenco di tutti i dispositivi certificati di Skype for Business, vedere la sezione [Telefoni e dispositivi per Skype for Business](https://technet.microsoft.com/en-us/office/dn947482). È possibile usare la [Dashboard Qualità delle chiamate Skype for Business](https://support.office.com/en-us/article/Turning-on-and-using-Call-Quality-Dashboard-in-Skype-for-Business-Online-553fa13c-92d2-4d5c-a3d5-41a073cb047c?ui=en-US&amp;rs=en-US&amp;ad=US), nell' **Interfaccia di amministrazione di Skype for Business**, per controllare quali dispositivi in uso funzionano correttamente e monitorare la qualità dei supporti audio e video.
  
> [!TIP]
> **Per assicurare una qualità ottimale dei supporti multimediali di Skype for Business è necessario usare un dispositivo certificato**.
  
È importante ricordare che tutti i dispositivi multimediali, client e server di Skype for Business attraverso cui funzionano i supporti multimediali in tempo reale, generano un certo livello di latenza. La latenza di elaborazione del software e del dispositivo, assieme alla latenza della rete, contribuiscono a formare una latenza generale end-to-end e hanno un forte impatto sull'esperienza dell'utente finale.
  
#### Ambiente

L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per offrire agli utenti una migliore esperienza audio e video, usare l';app di Skype for Business ** Strumenti** > **Opzioni** > **Dispositivo audio** o **Dispositivo video** per apportare modifiche al dispositivo in uso e personalizzarne le impostazioni. È possibile controllare la qualità dell';audio di una chiamata anche facendo clic su ** Controllo qualità chiamata**. Se gli utenti fanno clic su **Controllo qualità chiamata**, possono segnalare li livello di qualità e i problemi riscontrati con una chiamata di prova.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### Network

La qualità dei supporti multimediali in tempo reale su rete IP è strettamente legata alla qualità della connettività della rete, ma in particolare dal livello di:
  
- **Latenza** È il tempo necessario impiegato da un pacchetto IP a viaggiare dal punto A al punto B della rete. Questo ritardo di propagazione in rete è strettamente relazionato alla distanza fisica tra i due punti e alla velocità della luce, compreso anche un ulteriore sovraccarico sostenuto dai vari router che si trovano sul percorso. La latenza è misurata come tempo solo andata (one-way) o tempo andata/ritorno (RTT, Round-Trip Time).
    
- **Perdita dei pacchetti** Solitamente definita come percentuale di pacchetti che vengono persi in un dato lasso di tempo, la perdita dei pacchetti incide direttamente sulla qualità dell';audio; da pacchetti piccoli e singoli che praticamente non hanno alcun impatto fino a perdite burst back-to-back che causano l';interruzione totale dell';audio.
    
- **Instabilità tra arrivi di pacchetti o semplicemente instabilità** Si tratta della variazione media del ritardo tra pacchetti successivi. I software VoIP più moderni, tra cui anche Skype for Business, possono adattarsi ad alcuni livelli di instabilità tramite il buffering. È solo quando il livello di instabilità supera il buffering che i partecipanti potranno notarne gli effetti.
    
> [!NOTE]
>  Il buffering causato dall'instabilità aumenterà la latenza end-to-end.
  
Con numerose sessioni multimediali in tempo reale di Skype for Business Online, oltre al traffico di rete generato da altri servizi di Office 365 e altre applicazioni commerciali, è fondamentale assicurarsi che vi sia una sufficiente larghezza di banda sull'intero percorso di rete che collega la propria rete al servizio di Skype for Business Online per evitare la congestione e garantire una qualità eccellente dei supporti multimediali in tempo reale (condivisione di audio, video e applicazioni). 
  
#### Implementare la Qualità del Servizio (QoS) sulle reti congestionate

Inoltre, la congestione di traffico su una rete inciderà notevolmente sulla qualità multimediale. Per consentire ai pacchetti audio e video di viaggiare sulla rete più velocemente e di avere priorità su altro traffico in una rete congestionata, è possibile usufruire della Qualità del Servizio (QoS) per offrire all'utente finale un'esperienza ottimale per comunicazioni audio e video.
  
La QoS fornisce un modo per assegnare priorità più alte ai pacchetti di rete che trasportano dati audio o video. Assegnando priorità più alta a questi pacchetti, le comunicazioni audio e video possono viaggiare lungo la rete più velocemente e con meno interruzioni rispetto alle sessioni di rete che comportano trasferimenti di file, ricerche sul web o backup di database. Questo perché ai pacchetti di rete usati per il trasferimento di file o il backup di database viene assegnato di default "best effort" come priorità e la congestione della rete non avrà un grande impatto. Se ai pacchetti multimediali (condivisione di audio, video e applicazioni) non si assegna una priorità più alta e si lasciano nella categoria "best effort", verranno elaborati assieme al traffico di tutte le altre reti. In funzione del volume di congestione della rete, la qualità audio e video degli utenti potrebbe risultare più bassa.
  
Si raccomanda vivamente di implementare la QoS sulla propria rete per assicurarsi che la congestione all'interno della propria rete non abbia nessuna conseguenza. Tuttavia, perché questo abbia il massimo impatto, tutti gli endpoint di rete devono supportare la QoS, il che vuol dire che tutti gli endpoint devono rispettare i contrassegni QoS e la priorità dei pacchetti. I servizi di Skype for Business online rispettano i contrassegni QoS e la definizione di priorità nella rete Microsoft. Tuttavia, il traffico indirizzato attraverso una connessione pubblica come Internet dalla propria rete aziendale alla rete di Microsoft non manterrà i contrassegni QoS e le priorità dei pacchetti. Le connessioni private dalla propria rete a Office 365 usando [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) offrono una soluzione di distribuzione che mantiene i contrassegni QoS e la priorità dei pacchetti che, a sua volta, aumenterà la qualità complessiva audio e video per i clienti finali.
  
## Requisiti di prestazione di rete per connettersi a Skype for Business Online
<a name="bk_NetworkPerf"> </a>

I supporti multimediali in tempo reale di Skype for Business viaggiano su molti dispositivi diversi tra loro, app di client, software di server e numerose reti. La latenza end-to-end dei supporti multimediali in tempo reale è la quantità totale di latenza introdotta su tutti i componenti e segmenti di rete. La qualità della connessione di rete end-to-end è determinata dal segmento di rete con la qualità più bassa. Questo segmento rappresenta un collo di bottiglia per il traffico di questa rete.
  
Nel seguente schema è illustrato il flusso audio unidirezionale in una conferenza da un partecipante all'altro di Skype for Business.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In questo scenario, il percorso del supporto è formato dai seguenti segmenti di rete:
  
1. **Connessione dall'Utente 1 all'edge della rete di Microsoft** Di solito è inclusa una connessione di rete, come WiFi o Ethernet, la connessione WAN dall'Utente 1 al punto di uscita di Internet (dispositivo Edge rete utente), e la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Avviene tra l'Edge di Microsoft e il centro dati di Skype for Business Online, dove vengono usati i server per conferenze A/V.
    
3. **Connessione all'interno della rete Microsoft** Avviene tra il centro dati di Skype for Business Online e l'Edge della rete di Microsoft.
    
4. **Connessione dall'Edge della rete Microsoft all'Utente 2** È compresa la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft, la connessione WAN dall'Utente 2 al punto di uscita di Internet (Edge rete utente) e la connessione di rete come WiFi o Ethernet.
    
Nello schema seguente è mostrata la suddivisione dei componenti e i segmenti di rete di una chiamata PSTN su Skype for Business Online:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In uno scenario di chiamata PSTN, il percorso del supporto multimediale attraversa i seguenti segmenti di rete:
  
1. **Connessione da un chiamante client di Skype for Business all'Edge della rete Microsoft** Di solito è inclusa una connessione di rete, come WiFi o Ethernet, la connessione WAN dal chiamante client di Skype for Business al punto di uscita di Internet (dispositivo Edge rete utente), e la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Avviene tra l'Edge di Microsoft e il centro dati di Skype for Business Online, dove viene usato un Mediation Server.
    
3. **Connessione all'interno della rete Microsoft** Avviene tra il centro dati di Skype for Business Online e l'Edge della rete di Microsoft.
    
4. **Connessione tra la rete Microsoft e i partner del fornitore di servizi PSTN** Si tratta della connessione esistente per effettuare una chiamata PSTN dal client di Skype for Business che si trova al di fuori della rete Microsoft.
    
### Requisiti di prestazioni di rete da un client di Skype for Business all'Edge della rete Microsoft
<a name="bk_SfBClienttoEdge"> </a>

Per assicurare una qualità ottimale dei supporti multimediali di Skype for Business, sono richiesti i seguenti target o valori di soglia dei parametri di prestazione della rete per una connessione dalla rete aziendale all'Edge della rete di Microsoft. Questo segmento della rete comprende la rete interna dell'utente, tra cui tutte le connessioni WiFi e Ethernet, il traffico site-to-site dell'azienda su una connessione WAN, ad esempio Multiprotocol Label Switching (MPLS), oltre alle connessioni partner Internet o ExpressRoute all'Edge della rete di Microsoft.
  
> [!CAUTION]
> **La connettività tra un client di Skype for Business sulla rete aziendale dell';utente ai servizi Office 365 devono soddisfare i seguenti requisiti di prestazione di rete e valori soglia.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Target** <br/> |
|Latenza (one way)  <br/> |< 50ms  <br/> |
|Latenza (RTT o Round-trip Time)  <br/> |< 100ms  <br/> |
|Perdita di pacchetti burst  <br/> |<10% durante intervalli di 200ms  <br/> |
|Perdita di pacchetti  <br/> |<1% durante intervalli di 15s  <br/> |
|Instabilità tra arrivi di pacchetti  <br/> |<30ms durante intervalli di 15s  <br/> |
|Riordine dei pacchetti  <br/> |<0.05% di pacchetti non ordinati  <br/> |
   
 **Altri requisiti per i target prestazionali:**
  
- La rete di Microsoft è dotata di oltre 160 posizioni Edge in tutto il mondo. Lavoriamo con i principali Internet Service Provider (ISP) di tutto il mondo attraverso questi siti Edge. Il target metrico della latenza suppone che il sito o i siti aziendali dell'utente e gli Edge di Microsoft si trovino nella stesso continente.
    
- Il sito o i siti aziendali dell'utente alla connessione Edge della rete di Microsoft includono l'accesso alla rete del primo hop, che può essere WiFi o altra tecnologia senza fili. 
    
- Il target delle prestazioni di rete presuppone l'esistenza di una larghezza di banda e/o qualità corrette della pianificazione dei servizi. In altre parole, ciò si applica direttamente al traffico dei supporti multimediali in tempo reale di Skype for Business quando la connessione della rete è sottoposta a un picco di carico.
    
### Requisiti di prestazioni di rete dall'Edge della rete dell'utente all'Edge della rete Microsoft
<a name="bk_YourNetworkEdge"> </a>

Di seguito sono indicati i target o limiti di soglia delle prestazioni di rete richiesti per la connessione tra l'Edge della rete dell'utente e l'Edge della rete di Microsoft. Questo segmento della rete non comprende la rete interna del cliente o WAN, ed è intesa come linea guida durante i test sul traffico di rete dell'utente inviato su Internet, o attraverso una rete del partner ExpressRoute e può essere usato anche durante la negoziazione di un contratto di servizio (Service Level Agreement,SLA) con il provider ExpressRoute dell'utente.
  
> [!CAUTION]
> **La connettività tra l';Edge della rete aziendale dell';utente e l';Edge della rete di Microsoft deve soddisfare i seguenti requisiti e limiti di soglia delle prestazioni di rete.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Target** <br/> |
|Latenza (one way)  <br/> |< 30ms  <br/> |
|Latenza (RTT)  <br/> |< 60ms  <br/> |
|Perdita di pacchetti burst  <br/> |<1% durante intervalli di 200ms  <br/> |
|Perdita di pacchetti  <br/> |<0,1% durante intervalli di 15s  <br/> |
|Instabilità tra arrivi di pacchetti  <br/> |<15ms durante intervalli di 15s  <br/> |
|Riordine dei pacchetti  <br/> |<0,01% di pacchetti non ordinati  <br/> |
   
 **Altri requisiti per i target prestazionali:**
  
- Il target delle prestazioni richiede la connessione sullo stesso continente tra uno degli Edge della rete aziendale dell'utente e l'Edge più vicino della rete di Microsoft.
    
- Il target delle prestazioni di rete suppone l';esistenza di una larghezza di banda e/o qualità corrette della pianificazione dei servizi. Questo si applica al traffico dei supporti multimediali in tempo reale di Skype for Business quando la connessione della rete è sottoposta a un picco di carico. Per una corretta larghezza di banda e pianificazione della QoS, fare riferimento a [ExpressRoute e QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## Misurazione delle prestazioni di rete
<a name="bk_NetworkPerf"> </a>

Per misurare le prestazioni effettive della rete, in particolare per la latenza e la perdita di pacchetti, da qualsiasi sito della rete aziendale a un Edge di rete, è possibile usare diversi strumenti, tra cui il ping e il confronto di una serie di servizi di Media Relay di Skype for Business che operano dall'Edge di Microsoft e dai siti del centro dati. 
  
Per testare le connessioni Internet alla rete di Microsoft, si raccomanda di eseguire il confronto con i seguenti VIP dei Media Relay di Skype for Business. Il  *VIP Anycast*  risolverà un indirizzo IP di un Media Relay nel sito di un Edge della rete Microsoft che è più vicino alla posizione dei test.
  
||||
|:-----|:-----|:-----|
|**Indirizzo IP** <br/> |**Tipo** <br/> |**Posizione** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP Anycast  <br/> |
   
 **Ecco alcune importanti raccomandazioni da seguire durante la valutazione delle prestazioni di rete:**
  
- Valutare la rete interna dell'utente e le connessioni con Office 365.
    
- Valutare e raccogliere i dati per tutte le reti dell'utente per un lungo periodo di tempo. Si raccomanda di eseguire i test sulle prestazioni di rete per almeno una settimana in modo da poter vedere i modelli di utilizzo per tutte le ore e i giorni lavorativi. Così si potranno visualizzare i momenti di picco.
    
- È necessario prendere diversi campioni delle misurazioni delle prestazioni di rete. Si raccomanda di effettuare una misurazione ogni 10 minuti dal sito di un'azienda durante tutto il periodo di tempo dedicato alla raccolta dei dati. Per confrontare i requisiti delle prestazioni di rete di Skype for Business Online, prendere il valore di misurazione al 90° percentile da questa serie di dati campione. 
    
- Valutare in modo continuativo le prestazioni di rete. L'uso della rete varia nel tempo a causa delle variazioni dei modelli di utilizzo, delle nuove applicazioni aziendali che usano una quantità elevata di larghezza di banda e delle variazioni delle posizioni aziendali fisiche o organizzative. È importante monitorare continuamente le prestazioni della rete facendo riferimento a questi requisiti e ai target/valori di soglia e apportare adeguamenti tempestivi per assicurare una qualità ottimale dei supporti multimediali in tempo reale. 
    
## Misurazione delle prestazioni di rete con le macchine virtuali Azure
<a name="bk_NetworkPerf"> </a>

Anziché effettuare il test dei siti dell'Edge della rete Microsoft, esistono soluzioni di valutazione della rete offerte da clienti e partner di Skype for Business che ottimizzano l'impostazione del test per servizi nel cloud Microsoft Azure. In queste soluzioni, gli strumenti di valutazione della rete consentono di effettuare il test di latenza, perdita di pacchetti e instabilità, per l'impostazione degli endpoint personalizzati, come servizio nel cloud Azure. Di conseguenza, il traffico di rete del test passa attraverso un segmento di rete aggiuntivo, che rappresenta il collegamento all'interno della rete Microsoft tra i limiti di rete e i centri dati Azure che ospitano il servizio di valutazione della rete.
  
Per quelle soluzioni di valutazione della rete basate su servizi di test ospitati su Azure. Consigliamo di effettuare la valutazione della rete all'interno del paese e/o della regione. Ad esempio, per i siti dei clienti situati negli Stati Uniti orientali, la valutazione deve essere effettuata su un'istanza del servizio di test ospitata nella regione del centro dati degli Stati Uniti orientali di Azure. 
  
Di seguito vengono illustrati gli obiettivi della latenza (RTT) per l'impostazione della valutazione della rete basata sul servizio Azure. Gli obiettivi di latenza a una via saranno metà rispetto agli obiettivi RTT corrispondenti. Gli obiettivi di perdita di pacchetti e instabilità rimangono uguali a quelli definiti per il test basato su Media Relay di Skype.
  
|||||
|:-----|:-----|:-----|:-----|
|**Regione del cliente** <br/> |**Regione di Azure** <br/> |**Il proprio Edge della rete - RTT di Azure** <br/> |**Il proprio sito - RTT di Azure** <br/> |
|Stati Uniti centrali  <br/> |Stati Uniti centrali  <br/> |99  <br/> |139  <br/> |
|Stati Uniti orientali  <br/> |Stati Uniti orientali  <br/> |86  <br/> |126  <br/> |
|Stati Uniti centro settentrionali  <br/> |Stati Uniti centro settentrionali  <br/> |97  <br/> |137  <br/> |
|Stati Uniti centro meridionali  <br/> |Stati Uniti centro meridionali  <br/> |94  <br/> |134  <br/> |
|Stati Uniti occidentali  <br/> |Stati Uniti occidentali  <br/> |94  <br/> |134  <br/> |
|Hawaii USA  <br/> |Stati Uniti occidentali  <br/> |116  <br/> |156  <br/> |
|Canada centrale  <br/> |Canada centrale  <br/> |138  <br/> |178  <br/> |
|Canada orientale  <br/> |Canada orientale  <br/> |131  <br/> |171  <br/> |
|Europa settentrionale  <br/> |Europa settentrionale  <br/> |99  <br/> |139  <br/> |
|Europa occidentale  <br/> |Europa occidentale  <br/> |95  <br/> |135  <br/> |
|Asia orientale  <br/> |Asia orientale  <br/> |118  <br/> |158  <br/> |
|Asia sud-orientale  <br/> |Asia sud-orientale  <br/> |97  <br/> |137  <br/> |
|Giappone orientale  <br/> |Giappone orientale  <br/> |111  <br/> |151  <br/> |
|Giappone occidentale  <br/> |Giappone occidentale  <br/> |118  <br/> |158  <br/> |
|Brasile meridionale  <br/> |Brasile meridionale  <br/> |70  <br/> |110  <br/> |
|Australia orientale  <br/> |Australia orientale  <br/> |124  <br/> |164  <br/> |
|Australia sud-orientale  <br/> |Australia sud-orientale  <br/> |124  <br/> |164  <br/> |
|India centrale  <br/> |India centrale  <br/> |103  <br/> |143  <br/> |
|India meridionale  <br/> |India meridionale  <br/> |103  <br/> |143  <br/> |
|India occidentale  <br/> |India occidentale  <br/> |103  <br/> |143  <br/> |
|Cina orientale  <br/> |Cina orientale  <br/> |120  <br/> |160  <br/> |
|Cina settentrionale  <br/> |Cina settentrionale  <br/> |120  <br/> |160  <br/> |
   
## Qualità dei supporti multimediali e ExpressRoute
<a name="bk_NetworkPerf"> </a>

Azure ExpressRoute per Office 365 è una connessione di rete dedicata per collegarsi a Office 365. Dà la possibilità ai clienti di avere il controllo sul percorso preso dal traffico della rete di Office 365. In questo modo non si devono più preoccupare per i routing imprevedibili che si verificano su Internet dove i dati vengono trasportati da vettori sconosciuti. Il traffico di rete inviato attraverso ExpressRoute viene poi inviato direttamente tramite la rete dei partner di ExpressRoute verso la rete di Microsoft. In questo modo i clienti possono usare Office 365 come se si trovasse nel loro centro dati off-site con una connessione dedicata.
  
Azure ExpressRoute è disponibile per tutte le offerte di licenza di Office 365. Tuttavia, per attivare il routing globale da Office 365 è necessario il componente aggiuntivo Premium di Azure ExpressRoute. I clienti di Office 365 con almeno 500 postazioni che stanno implementando ExpressRoute possono ricevere il  *componente aggiuntivo Premium di ExpressRoute*  senza alcun costo.
  
### ExpressRoute è necessario per una buona qualità dei supporti multimediali?

Azure ExpressRoute non è un requisito per ottenere una qualità ottimale dei supporti multimediali di Skype for Business Online. È, tuttavia, una delle opzioni di distribuzione per far sì che la connettività cloud soddisfi i target o i valori di soglia delle prestazioni di rete di Skype for Business.
  
Office 365 è un servizio sicuro ad alte prestazioni che usa Internet. Continuiamo a investire in nuove funzionalità di sicurezza e nodi Edge regionali per migliorare costantemente la sicurezza e le prestazioni. Azure ExpressRoute non è un requisito per i servizi di Office 365, tra cui Skype for Business Online. Azure ExpressRoute è una delle opzioni di distribuzione disponibili per soddisfare i requisiti di prestazioni di rete di Skype for Business tramite la connettività con Office 365 e garantire un'esperienza multimediale di qualità ottimale su Skype for Business Online.
  
Per la qualità dei supporti multimediali di Skype for Business Online, è importante che la connessione tra i siti aziendali del cliente e gli Edge della rete di Microsoft soddisfi i target di prestazione in [Requisiti di prestazioni di rete da un client di Skype for Business all'Edge della rete Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge) e che la connessione tra gli Edge delle rete dell';utente e gli Edge della rete di Microsoft soddisfino i target di prestazione in[Requisiti di prestazioni di rete dall'Edge della rete dell'utente all'Edge della rete Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_YourNetworkEdge). 
  
È anche importante che la connettività delle rete fisica dell'azienda dell'utente, compresa la rete interna e la capacità di connettività cloud, possano ospitare il volume di traffico di picco dei supporti multimediali. Azure ExpressRoute è uno dei diversi modi per aiutare i clienti a far sì che la loro connettività cloud di Skype for Business Online soddisfi tutti questi requisiti di prestazione.
  
### ExpressRoute è necessario per l'SLA sulla qualità vocale?

No, ExpressRoute non è necessario per l'SLA sulla qualità vocale di Skype for Business Online. L'[SLA sulla qualità vocale di Skype for Business Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) si applica a qualsiasi chiamata idonea effettuata da qualsiasi utente del servizio vocale di Skype for Business Online secondo la licenza e la sottoscrizione corrette che permette all'utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. In un SLA sulla qualità vocale si deve anche includere che tutte le condizioni seguenti vengano rispettate:
  
- Chiamate da telefoni IP con certificazione Microsoft.
    
- Connessioni cablate Ethernet.
    
- Difetti di qualità vocale dovuti a problemi della rete Microsoft.
    
> [!NOTE]
> L'SLA sulla qualità vocale esclude le chiamate la cui bassa qualità è causata da problemi su reti non Microsoft, compresi partner di ExpressRoute e altre reti. 
  
### Internet o Azure ExpressRoute?

Prima di prendere una decisione tra le varie opzioni di connettività di rete per Skype for Business Online, i clienti devono valutare la loro rete e l';attuale connettività di Internet sulla base dei requisiti di prestazione di rete descritti in [Requisiti di prestazione di rete per connettersi a Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_NetworkPerf).
  
Se le prestazioni di rete sull'attuale connessione Internet offrono una capacità sufficiente durante i momenti di picco e soddisfano i requisiti della rete dai siti agli Edge della rete Microsoft e dagli Edge della rete dell'utente agli Edge della rete di Microsoft, è possibile continuare a usare la connettività Internet esistente per connettersi a Skype for Business Online.
  
Per i siti aziendali in cui non sono soddisfatti i requisiti di prestazione di rete, si raccomanda vivamente di lavorare prima con gli attuali provider del servizio di rete per migliorare le prestazioni di rete complessive. Qualora anche così non venissero rispettati, Azure ExpressRoute può aiutare a far sì che la propria connettività cloud di Skype for Business Online soddisfi i requisiti di prestazione di rete.
  
Azure ExpressRoute offre anche i seguenti vantaggi:
  
- Un contratto di servizio (SLA) sulla disponibilità della connessione tra la rete dell'utente e la rete di Microsoft. ExpressRoute ha garantito un SLA relativo alla disponibilità del 99,9%.
    
- Larghezza di banda programmata e garantita richiesta per i servizi di Office 365. È possibile raggiungere questo obiettivo inviando solo traffico di Office 365 o di Skype for Business usando ExpressRoute e poi fare in modo che tutto il traffico restante di Internet passi per altri punti di uscita/ingresso per la rete dell'utente.
    
- ExpressRoute è stato progettato per mantenere i contrassegni QoS DSCP tra la propria rete e la rete Microsoft.
    
Per maggiori informazioni sulla programmazione delle capacità e QoS di ExpressRoute, fare riferimento a [ExpressRoute e QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### È possibile configurare solo Azure ExpressRoute per Skype for Business Online?

Sì, è possibile configurare Azure ExpressRoute per assicurare una connettività di rete eccellente dalla rete aziendale dell'utente solo a Skype for Business Online. In questo modo si offre una qualità ottimale dei supporti multimediali in tempo reale per gli utenti ma poi è possibile continuare a connettersi ad altri servizi di Office 365 su Internet.
  
Il protocollo BGP (Border Gateway Protocol) è un protocollo di routing usato per instradare il traffico di rete attraverso Internet. È progettato per scambiare informazioni di routing tra i sistemi autonomi (AS) che si trovano su Internet. I valori delle Community del protocollo BGP sono tag di attributo che possono essere applicati alle route in ingresso o in uscita. Le Community del protocollo BGP vengono spesso usate per indicare all'AS ricevente quale link in uscita usare per raggiungere una data destinazione, sulla base di posizione geografica, tipo di servizio o altri criteri.
  
Grazie al supporto delle Community del protocollo BGP, Microsoft contrassegnerà prefissi e route con adeguati valori dell';attributo Community di BGP sulla base del servizio a cui appartengono. Microsoft contrassegnerà prefissi pubblicati tramite peer pubbliche e peer Microsoft con adeguati valori dell';attributo Community di BGP indicanti la regione in cui è ospitato il prefisso. È possibile contare sui valori dell';attributo Community per prendere decisioni appropriate relative al routing per configurare solo una connessione ExpressRoute per Skype for Business Online. È possibile scoprirne di più alla sezione [Requisiti di routing per ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## Scenari di connettività di ExpressRoute per Skype for Business Online
<a name="bk_NetworkPerf"> </a>

Se si è deciso che, sulla base delle raccomandazioni sopra, ExpressRoute è la soluzione ottimale, ecco alcuni consigli su dove e come è possibile ottenere numerose connessioni ExpressRoute.
  
### Solo distribuzione online - Singolo sito

Se tutti gli utenti usano il servizio Skype for Business Online e se gli uffici sono centralizzati in una singola località fisica e si decide di distribuire Azure ExpressRoute, è necessario configurare una singola connessione ExpressRoute tra il sito dell';azienda alla più vicina [località peer di ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
Nel seguente grafico è mostrato un esempio di questo tipo di distribuzione. Per questo esempio, Contoso è un'università con sede a Orlando, Florida. Conta 10.000 membri, tra personale docente e studenti.I test condotti su Internet dalla loro località ai siti Edge di Microsoft hanno mostrato una perdita di pacchetti superiore al 5% durante le ore di picco. Hanno deciso di installare una connessione dedicata a Office 365 usando ExpressRoute con larghezza di banda 'over-provisioned' per evitare così la congestione di rete per Office 365, in particolare per il traffico in tempo reale di Skype for Business Online. Si connettono a Microsoft cloud tramite ExpressRoute al sito di MeetMe ad Atlanta, Georgia.
  
![ExpressRoute Single Site.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### Solo distribuzione online - Più siti sullo stesso continente

Se l'azienda dell'utente usa i servizi Skype for Business Online da svariati uffici nella stessa regione o continente e si sceglie di implementare Azure ExpressRoute, si raccomanda di connettere il sito principale tramite ExpressRoute e poi aggiungere, a scelta, ulteriori peering ExpressRoute per altre località che non soddisfano i target prestazionali della rete raccomandati.
  
Nel seguente esempio, Contoso è un'agenzia viaggi con sede a New York ma ha altri uffici negli Stati Uniti. I loro uffici sono interconnessi tramite un WAN che usa MPLS per la connessione a Office 365. Inizialmente configurano la connessione ExpressRoute dal loro router di Internet a Hoboken, New Jersey al sito di MeetMe di New York. 
  
Con questa configurazione, il traffico di rete proveniente dalla maggior parte dei loro siti alla rete di Microsoft (sito Edge di New York) può raggiungere i target prestazionali della rete di connessione del client di Skype for Business descritti nella sezione [Requisiti di prestazioni di rete da un client di Skype for Business all'Edge della rete Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge). Tuttavia, la latenza tra gli uffici della costa occidentale di Contoso e New York va al di sopra dei 50ms one-way. Inoltre, Honolulu è il secondo ufficio più grande per Contoso e la latenza da Honolulu a New York supera gli 80ms one-way. Per assicurare una buona qualità dei supporti multimediali per gli utenti di quegli uffici, Contoso ha deciso di aggiungere una connessione ExpressRoute sulla costa occidentale tra il loro sito di San Jose e il sito MeetMe di ExpressRoute nella Silicon Valley.
  
![Express Router Multi-site on the same continent.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### Solo distribuzione online - Più siti su continenti diversi

Nel caso in cui tutti gli utenti usano il servizio di Skype for Business Online e gli uffici si trovano in diverse località fisiche sparse su vari continenti, se si decide di distribuire Azure ExpressRoute, è necessario configurare almeno una connessione ExpressRoute per ogni continente tra il sito principale di ogni continente alla più vicina [località peer di ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). A seconda dei costi/vantaggi, è possibile scegliere di distribuire ulteriori connessioni ExpressRoute dai siti in cui non vengono soddisfatti i target prestazionali della rete.
  
Nel seguente esempio, Contoso è un grande studio legale con uffici nelle principali città di Nord America ed Europa. In base alla loro connessione Internet e alla loro valutazione delle prestazioni della rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo circuito ExpressRoute per tutti gli uffici europei.
  
![ExpressRoute with multiple sites and continents.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### Distribuzione ibrida

Se si dispone di una distribuzione di Lync o Skype for Business in sede e si sceglie di implementare una integrazione ibrida di Skype for Business Online e di distribuire Azure ExpressRoute, raccomandiamo di avere almeno una connessione ExpressRoute per ogni sito Edge di Lync o Skype for Business in sede e almeno una connessione ExpressRoute per ogni continente con uffici. A seconda dei costi/vantaggi, per ogni continente è possibile scegliere di distribuire ulteriori connessioni ExpressRoute dagli uffici in cui non vengono soddisfatti i target prestazionali di rete.
  
Se non si dispone di una distribuzione di Skype for Business in sede, si deve seguire la [Guida alla distribuzione e programmazione dei server Edge](https://technet.microsoft.com/en-us/library/mt346417.aspx). Nello specifico, i server Edge devono essere raggiungibili dall';esterno della rete dell';utente. Solitamente ciò è possibile assegnando un indirizzo IP pubblico instradabile al server Edge o usando una NAT (Network Address Translation).
  
Nel seguente esempio, Contoso dispone di una distribuzione in sede di Enterprise Voice di Skype for Business. Vogliono migrare gli utenti in sede ai servizi online di Office 365. Hanno anche deciso di usare una distribuzione ibrida per poter continuare a usare la loro infrastruttura PSTN già esistente per tutti gli utenti in sede e online. Il centro dati in sede di Contoso e i server Edge di Skype for Business si trovano a Chicago. Per la distribuzione, Contoso ha deciso di configurare una connessione ExpressRoute tra il loro centro dati di Chicago e ExpressRoute di Chicago. Hanno anche aggiunto una connessione ExpressRoute sulla costa occidentale per migliorare il servizio presso l'ufficio di Honolulu.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### Distribuzione online con Cloud Connector Edition

Cloud Connector Edition di Skype for Business Online è una soluzione ibrida formata da una serie di Macchine Virtuali (VM) in pacchetto che implementano la connettività PSTN in sede. Distribuendo una topologia server minima di Skype for Business in un ambiente virtualizzato, sarà possibile inviare e ricevere chiamate con telefoni fissi e cellulari tramite l'infrastruttura vocale PSTN già esistente in sede.
  
Se si decide di distribuire Azure ExpressRoute e Cloud Connector Edition, raccomandiamo di configurare almeno una connessione Express Route per ogni continente tra il sito principale di ogni continente e la più vicina [località peer ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). In base a un'analisi costi/benefici, per ogni continente è possibile scegliere di distribuire ulteriori connessioni ExpressRoute dai siti in cui non vengono soddisfatti i target prestazionali di rete.
  
Se si dispone di una distribuzione di Skype for Business in sede, si deve seguire la [Guida alla programmazione per Skype for Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Nello specifico, ai servizi Access Edge e A/V Edge devono essere assegnati indirizzi IP pubblici e devono essere raggiungibili dai centri dati di Office 365.
  
Nel seguente esempio, Contoso è uno studio contabile europeo con una presenza nei principali paesi e città europee. Quando si sono iscritti a Skype for Business Online per tutte le loro necessità di collaborazione, hanno deciso di installare un Cloud Connector per ogni paese in cui dispongono di una località fisica per continuare a usare la loro infrastruttura PSTN e i contratti dei vettori già esistenti. Sulla base delle prove eseguite su tutti i siti e sull'Edge della rete di Microsoft, hanno concluso che una singola connessione ExpressRoute a Londra aiuterà a soddisfare i target prestazionali di rete della connessione client di Skype for Business descritti nella sezione [Requisiti di prestazioni di rete da un client di Skype for Business all'Edge della rete Microsoft](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md#bk_SfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Sotto è descritta un'altra opzione di distribuzione per Contoso. In questo caso, hanno deciso di configurare una connessione ExpressRoute su ogni sito dove è distribuito un Cloud Connector.
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## Vedere anche
<a name="bk_NetworkPerf"> </a>

#### 

[ExpressRoute e QoS in Skype for Business online](20c654da-30ee-4e4f-a764-8b7d8844431d.md)

