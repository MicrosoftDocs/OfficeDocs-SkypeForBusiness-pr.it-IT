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
description: Questo argomento definisce il set di requisiti di prestazioni di rete per i servizi Skype for business online e come si può scegliere di usare Internet o ExpressRoute per la connettività tra la rete e Skype for business online in base alla valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per la connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni di ExpressRoute in diversi scenari di distribuzione di Skype for business online.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164765"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualità multimediale e prestazioni della connettività di rete in Skype for Business online

Questo argomento definisce il set di requisiti di prestazioni di rete per i servizi Skype for business online e come si può scegliere di usare Internet o ExpressRoute per la connettività tra la rete e Skype for business online in base alla valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per la connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni di ExpressRoute in diversi scenari di distribuzione di Skype for business online.
  
La qualità dei contenuti multimediali in tempo reale (audio, video e condivisione applicazioni) tramite IP è fortemente influenzata dalla qualità della connettività di rete end-to-end. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Azure ExpressRoute non è un requisito per Microsoft 365 e i servizi di Office 365, tra cui Skype for business online. Azure ExpressRoute è tuttavia una delle opzioni di distribuzione disponibili per garantire che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni della rete Skype for business e assicuri l'esperienza di qualità multimediale Skype for business online più ottimale.
  
> [!TIP]
> Anche se questo argomento offre informazioni generali sulle prestazioni di rete, le linee guida complete per la valutazione della rete sono al di fuori dell'ambito del documento. Per trovare un elenco dei partner di Skype for business online che possono aiutarti con le misurazioni delle prestazioni di rete nell'ambito di una valutazione completa della rete, visita [Skype for business partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisiti di connettività di rete per Skype for business online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fattori che influiscono sulla qualità multimediale di Skype for business online

Esistono molti fattori diversi che contribuiscono alla qualità del supporto in tempo reale di Skype for business online (audio, video e condivisione applicazioni) che include i dispositivi usati, l'ambiente e la connettività di rete. 
  
#### <a name="devices"></a>Dispositivi

In una sessione multimediale in tempo reale i dispositivi di acquisizione e rendering multimediali usati da tutti i partecipanti, ad esempio auricolari e Web cam, hanno un grande impatto sulla qualità complessiva di audio e video. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Anche se i dispositivi audio e video certificati non sono necessari, i dispositivi altamente consigliati sono certificati per Skype for business per l'esperienza multimediale più ottimale. Per un elenco di tutti i dispositivi certificati Skype for business, Vedi [telefoni e dispositivi per Skype for business](https://technet.microsoft.com/office/dn947482). È possibile usare il [dashboard di qualità delle chiamate di Skype for business online](/microsoftteams/turning-on-and-using-call-quality-dashboard), disponibile nell'interfaccia di **amministrazione di Skype for business**, per verificare che i dispositivi in uso funzionino correttamente e controllino la qualità dei contenuti multimediali audio e video.
  
> [!TIP]
> **È necessario un dispositivo certificato per l'esperienza di qualità multimediale Skype for business più ottimale**.
  
È importante ricordare che tutti i dispositivi multimediali, i client Skype for business e i server Skype for business attraverso i flussi multimediali in tempo reale presentano una certa quantità di latenza. La latenza di elaborazione del dispositivo e del software, insieme alla latenza della rete, hanno un grande impatto e contribuiscono alla latenza complessiva finale e all'esperienza dell'utente finale.
  
#### <a name="environment"></a>Ambiente

L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere un quadro più chiaro dell'**esperienza audio e** > video di un utente, usare il**dispositivo audio** o il dispositivo **video** di Skype for business app **Tools** > per apportare modifiche al dispositivo in uso e personalizzare le impostazioni.

#### <a name="network"></a>Rete

La qualità dei contenuti multimediali in tempo reale sulla rete IP è fortemente influenzata dalla qualità della connettività di rete, ma soprattutto dalla quantità di:
  
- **Latenza** Questo è il tempo necessario per ottenere un pacchetto IP dal punto a al punto B della rete. Questo ritardo di propagazione della rete è essenzialmente legato alla distanza fisica tra i due punti e la velocità della luce, incluso il sovraccarico aggiuntivo adottato dai vari router in mezzo. La latenza viene misurata come RTT di sola andata o di andata e ritorno.
    
- **Perdita di pacchetti** Questa operazione viene spesso definita come percentuale di pacchetti persi in una data finestra di tempo. La perdita di pacchetti influenza direttamente la qualità audio, da piccoli pacchetti persi singoli che non hanno quasi alcun impatto, alle perdite di burst di back-to-back che causano un cut-out audio completo.
    
- **Jitter arrivo tra pacchetti o semplicemente jitter** Questa è la variazione media di ritardo tra i pacchetti successivi. La maggior parte dei moderni software VoIP, tra cui Skype for business, può adattarsi ad alcuni livelli di jitter attraverso il buffering. Solo quando il jitter supera il buffering che un partecipante noterà gli effetti di jitter.
    
> [!NOTE]
>  Il buffering per jitter aumenterà la latenza fine-fine.
  
Con molte sessioni multimediali in tempo reale di Skype for business online, oltre ad altri traffici di rete generati da altri servizi Microsoft 365 o Office 365 e altre applicazioni aziendali, verificare che la larghezza di banda sufficiente per l'intero percorso di rete che connette la rete al servizio Skype for business online sia fondamentale per evitare la congestione della rete e garantire un'eccellente media in tempo reale (audio , video e condivisione applicazioni) di qualità. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementazione della qualità del servizio (QoS) in tutte le reti congestionate

Inoltre, la congestione del traffico in una rete avrà un impatto notevole sulla qualità dei contenuti multimediali. Per consentire ai pacchetti audio e video di viaggiare rapidamente in rete e di essere prioritari rispetto ad altri traffici di rete in una rete congestionata, è possibile usare la qualità del servizio (QoS) per fornire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video.
  
QoS offre un modo per assegnare priorità più alte ai pacchetti di rete che trasportano dati audio o video. Assegnando una priorità più alta a questi pacchetti, è probabile che le comunicazioni audio e video percorrono la rete più rapidamente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come i trasferimenti di file, la navigazione web o i backup di database. Questo perché i pacchetti di rete usati per i trasferimenti di file o per i backup di database per impostazione predefinita vengono assegnati "Best Effort" come priorità e la congestione della rete non avrà un impatto elevato. Se non si assegna una priorità più alta ai pacchetti di elementi multimediali (audio, video e condivisione applicazioni) e li si lascia assegnati anche come "miglior sforzo", verranno elaborati insieme a tutto il traffico di rete. A seconda della quantità di congestione della rete, in questo modo l'utente potrebbe finire in un'esperienza di qualità audio e video complessiva inferiore per gli utenti.
  
È consigliabile implementare QoS nella rete per verificare che la congestione della rete all'interno della rete non abbia un impatto. Tuttavia, per avere il massimo impatto, tutti gli endpoint di rete devono supportare QoS, quindi tutti gli endpoint devono rispettare la marcatura QoS e la priorità dei pacchetti. Skype for Business Online Services Honor QoS e assegnazione delle priorità all'interno della rete Microsoft. Tuttavia, il traffico instradato attraverso una connessione pubblica come Internet dalla rete aziendale alla rete Microsoft non mantiene i contrassegni QoS e la priorità dei pacchetti. Le connessioni private dalla rete a Microsoft 365 o Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) offrono una soluzione di distribuzione che mantiene i contrassegni QoS e la priorità dei pacchetti che a loro volta aumentano la qualità complessiva di audio e video per gli utenti finali.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisiti di prestazioni di rete per la connessione a Skype for business online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time media viaggia in diversi dispositivi, app client, software server e in reti diverse. La latenza end-to-end di elementi multimediali in tempo reale è la quantità totale di latenza introdotta in tutti i componenti e nei segmenti di rete. La qualità della connessione di rete end-to-end viene determinata dal segmento di rete con la qualità peggiore. Questo segmento funge da collo di bottiglia per il traffico di rete.
  
Il diagramma seguente illustra il flusso audio unidirezionale in una conferenza da un partecipante di Skype for business a un altro.
  
![Flusso delle chiamate ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In questo scenario di conferenza il percorso multimediale è costituito dai segmenti di rete seguenti:
  
1. **Connessione dall'utente 1 al bordo della rete Microsoft** In genere include una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN dall'utente 1 al punto di uscita Internet (il dispositivo Edge di rete) e la connessione Internet dal bordo della rete a Microsoft Network Edge.
    
2. **Connessione all'interno di Microsoft Network** Si tratta di un centro dati Microsoft Edge per Skype for business online, in cui vengono usati i server di conferenza A/V.
    
3. **Connessione all'interno di Microsoft Network** Questo è il centro dati di Skype for business online e Microsoft Network Edge.
    
4. **Connessione da Microsoft Network Edge all'utente 2** Ciò include la connessione Internet dal bordo della rete a Microsoft Network Edge, la connessione WAN dall'utente 2 al punto di uscita Internet (il bordo della rete) e la connessione di rete, ad esempio un WiFi o un dispositivo Ethernet.
    
Il diagramma seguente mostra la ripartizione dei componenti e dei segmenti di rete di una chiamata PSTN di Skype for business online:
  
![Flusso di chiamate PSTN ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In uno scenario di chiamata PSTN il percorso multimediale attraversa i segmenti di rete seguenti:
  
1. **Connessione da un chiamante client Skype for business al bordo della rete Microsoft** In genere include una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN dal chiamante del client Skype for business al punto di uscita Internet (il dispositivo Edge di rete) e la connessione Internet dal bordo della rete a Microsoft Network Edge.
    
2. **Connessione all'interno di Microsoft Network** Si tratta di un centro dati Microsoft Edge per Skype for business online, in cui viene usato un Mediation Server.
    
3. **Connessione all'interno di Microsoft Network** Questo è il centro dati di Skype for business online e Microsoft Network Edge.
    
4. **Connessione tra Microsoft Network e i partner del provider di servizi PSTN** Questa è la connessione che esiste per effettuare una chiamata PSTN dal client Skype for business che si trova all'esterno della rete Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisiti di prestazioni di rete da un client Skype for business a Microsoft Network Edge
<a name="bkSfBClienttoEdge"></a>

Per una qualità ottimale dei contenuti multimediali di Skype for business, per una connessione dalla rete della società a Microsoft Network Edge sono necessarie le seguenti soglie o limiti di prestazioni di rete. Questo segmento della rete include la rete interna, che include tutte le connessioni WiFi e Ethernet, il traffico sito-sito aziendale tramite una connessione WAN, ad esempio il cambio di etichetta Multiprotocol (MPLS), nonché le connessioni partner Internet o ExpressRoute al Microsoft Network Edge.
  
> [!CAUTION]
> **La connettività tra un client Skype for business nella rete aziendale a Microsoft 365 o Office 365 Services deve soddisfare i requisiti e le soglie di prestazioni di rete seguenti.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (solo andata)  <br/> |< 50ms  <br/> |
|Latenza (RTT o periodo di andata e ritorno)  <br/> |< 100ms  <br/> |
|Perdita di pacchetti burst  <br/> |<10% durante l'intervallo di 200ms  <br/> |
|Perdita di pacchetti  <br/> |<1% durante qualsiasi intervallo di 15s  <br/> |
|Jitter tra i pacchetti di arrivo  <br/> |<30ms durante qualsiasi intervallo di 15s  <br/> |
|Riordino dei pacchetti  <br/> |<pacchetti fuori ordine di 0,05%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- La rete Microsoft ha oltre 160 posizioni di Edge in tutto il mondo. Collaboriamo con i principali provider di servizi Internet (ISP) in tutto il mondo attraverso questi siti Edge. La destinazione metrica di latenza presuppone che il sito o i siti della società e i bordi Microsoft si trovino nello stesso continente.
    
- Il sito della società o i siti della connessione Microsoft Network Edge includono il primo accesso alla rete hop, che può essere Wi-Fi o un'altra tecnologia wireless. 
    
- La destinazione delle prestazioni di rete presuppone la corretta larghezza di banda e/o la qualità della pianificazione del servizio. In altre parole, questo problema si applica direttamente al traffico multimediale in tempo reale di Skype for business quando la connessione di rete è sotto un carico di picco.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisiti di prestazioni di rete dal bordo della rete a Microsoft Network Edge
<a name="bkYourNetworkEdge"> </a>

Di seguito sono riportate le destinazioni o le soglie di prestazioni di rete necessarie per la connessione tra il bordo della rete e il bordo della rete Microsoft. Questo segmento della rete esclude la rete interna o WAN del cliente ed è inteso come indicazioni per testare il traffico di rete inviato tramite Internet o tramite una rete partner di ExpressRoute e può essere usato anche quando si negozia un contratto di servizio di prestazioni con il provider di ExpressRoute.
  
> [!CAUTION]
> **La connettività tra il bordo della rete aziendale e Microsoft Network Edge deve soddisfare i seguenti requisiti e soglie di prestazioni di rete.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (solo andata)  <br/> |< 30ms  <br/> |
|Latenza (RTT)  <br/> |< 60ms  <br/> |
|Perdita di pacchetti burst  <br/> |<1% durante qualsiasi intervallo di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |<0,1% durante qualsiasi intervallo di 15s  <br/> |
|Jitter tra i pacchetti di arrivo  <br/> |<15ms durante qualsiasi intervallo di 15s  <br/> |
|Riordino dei pacchetti  <br/> |<pacchetti fuori ordine di 0,01%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- La destinazione delle prestazioni richiede la connessione tra qualsiasi bordo della rete aziendale e il relativo bordo della rete Microsoft più vicino per essere nello stesso continente.
    
- La destinazione delle prestazioni di rete presuppone la corretta larghezza di banda e/o la qualità della pianificazione del servizio. Questo vale anche per il traffico multimediale in tempo reale di Skype for business quando la connessione di rete è sotto un carico di picco. Per una pianificazione corretta della larghezza di banda e QoS, vedere [ExpressRoute e QoS in Skype for business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
    
## <a name="measuring-network-performance"></a>Misurazione delle prestazioni di rete
<a name="bkNetworkPerf"> </a>

Per misurare le prestazioni effettive della rete, in particolare per la latenza e la perdita di pacchetti, da qualsiasi sito di rete aziendale a un bordo di rete, è possibile usare strumenti come ping, test su un set di servizi di inoltro multimediale Skype for business in esecuzione dai siti Microsoft Edge e Data Center. 

>[!NOTE]
> La misurazione delle prestazioni di rete tramite ping (ICMP) non è efficace. Per questo motivo, l'indirizzo IP anycast seguente smetterà di rispondere alle richieste ICMP a partire da gennaio 2020. Per misurare efficacemente la performance di rete, Microsoft consiglia lo strumento di valutazione della [rete](https://www.microsoft.com/download/details.aspx?id=53885).
  
Per testare le connessioni Internet alla rete Microsoft, è consigliabile testare i VIP seguenti per i relay multimediali di Skype for business. Il *VIP anycast* verrà risolto in un indirizzo IP di un relay multimediale in un sito Microsoft Network Edge più vicino alla posizione di test.
  
||||
|:-----|:-----|:-----|
|**Indirizzo IP** <br/> |**Tipo** <br/> |**Posizione** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP anycast World Wide  <br/> |
   
 **Ecco alcuni consigli di alto livello da seguire per valutare le prestazioni di rete:**
  
- È consigliabile valutare la rete interna e le connessioni a Microsoft 365 o Office 365.
    
- È consigliabile valutare e raccogliere dati per tutte le reti per un lungo periodo di tempo. Ti consigliamo di eseguire il test delle prestazioni di rete per un minimo di una settimana, in modo da poter vedere i modelli di utilizzo per tutti i giorni lavorativi e le ore. In questo modo verranno visualizzati gli orari di punta.
    
- È consigliabile eseguire più esempi di misurazioni delle prestazioni di rete. È consigliabile eseguire una misurazione ogni 10 minuti da un sito aziendale durante l'intero periodo di tempo in cui si raccolgono i dati. Per confrontare i requisiti di prestazioni della rete di Skype for business online, prendere il valore di misura del 90 ° percentile da questo set di dati di esempio. 
    
- Dovresti valutare continuamente le prestazioni della rete. L'utilizzo della rete varia nel tempo a causa delle modifiche del modello di utilizzo, delle nuove applicazioni basate su Enterprise che usano una grande quantità di larghezza di banda e delle modifiche apportate alle posizioni aziendali o fisiche dell'organizzazione. È importante monitorare continuamente le prestazioni della rete rispetto a questi requisiti e alle soglie di prestazioni della rete e apportare modifiche tempestive per garantire la qualità multimediale in tempo reale più ottimale. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Misurazione delle prestazioni di rete con Azure VM
<a name="bkNetworkPerf"> </a>

Invece di testare i siti Microsoft Network Edge, esistono soluzioni di valutazione della rete di clienti e partner di Skype for business che sfruttano la configurazione dei test per i servizi di Microsoft Azure cloud. In tali soluzioni gli strumenti di valutazione della rete hanno la latenza, la perdita di pacchetti e il jitter rispetto agli endpoint personalizzati configurati come servizio in Azure cloud. Di conseguenza, il traffico di rete di test viaggia attraverso un ulteriore segmento di rete, che è la connessione all'interno della rete Microsoft tra i bordi della rete e i Data Center di Azure che ospitano il servizio di valutazione della rete.
  
Per le soluzioni di valutazione della rete basate sui servizi di test ospitati di Azure. È consigliabile eseguire la valutazione della rete in un paese e/o in un'area geografica. Ad esempio, per i siti dei clienti in East USA, la valutazione deve essere eseguita in un'istanza del servizio di test ospitata nell'area centro dati di Azure East US. 
  
Di seguito sono elencate le destinazioni latenza (RTT) per la configurazione della valutazione della rete basata su Azure Service. Le destinazioni di latenza unidirezionale saranno la metà delle destinazioni corrispondenti di RTT. Gli obiettivi di perdita di pacchetti e jitter rimangono gli stessi di quelli definiti per i test basati su Skype Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Area clienti** <br/> |**Area di Azure** <br/> |**Il tuo bordo di rete-Azure round-trip time (RTT)** <br/> |**Sito di Azure-round-trip time (RTT)** <br/> |
|Stati Uniti centrali  <br/> |Stati Uniti centrali  <br/> |99  <br/> |139  <br/> |
|Stati Uniti orientali  <br/> |Stati Uniti orientali  <br/> |86  <br/> |126  <br/> |
|Stati Uniti nord-centrale  <br/> |Stati Uniti nord-centrale  <br/> |97  <br/> |137  <br/> |
|Stati Uniti del centro sud  <br/> |Stati Uniti del centro sud  <br/> |94  <br/> |134  <br/> |
|Ovest degli Stati Uniti  <br/> |Ovest degli Stati Uniti  <br/> |94  <br/> |134  <br/> |
|Hawaii US  <br/> |Ovest degli Stati Uniti  <br/> |116  <br/> |156  <br/> |
|Central Canada  <br/> |Central Canada  <br/> |138  <br/> |178  <br/> |
|Canada Est  <br/> |Canada Est  <br/> |131  <br/> |171  <br/> |
|Nord Europa  <br/> |Nord Europa  <br/> |99  <br/> |139  <br/> |
|Europa occidentale  <br/> |Europa occidentale  <br/> |95  <br/> |135  <br/> |
|Asia orientale  <br/> |Asia orientale  <br/> |118  <br/> |158  <br/> |
|Asia sud-orientale  <br/> |Asia sud-orientale  <br/> |97  <br/> |137  <br/> |
|Giappone est  <br/> |Giappone est  <br/> |111  <br/> |151  <br/> |
|Giappone ovest  <br/> |Giappone ovest  <br/> |118  <br/> |158  <br/> |
|Brasile sud  <br/> |Brasile sud  <br/> |70  <br/> |110  <br/> |
|Australia Est  <br/> |Australia Est  <br/> |124  <br/> |164  <br/> |
|Australia sud-est  <br/> |Australia sud-est  <br/> |124  <br/> |164  <br/> |
|India centrale  <br/> |India centrale  <br/> |103  <br/> |143  <br/> |
|India del sud  <br/> |India del sud  <br/> |103  <br/> |143  <br/> |
|India occidentale  <br/> |India occidentale  <br/> |103  <br/> |143  <br/> |
|Cina est  <br/> |Cina est  <br/> |120  <br/> |160  <br/> |
|Cina nord  <br/> |Cina nord  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualità multimediale e ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute per Microsoft 365 o Office 365 è una connessione di rete dedicata per la connessione a Microsoft 365 o Office 365. Offre ai clienti la possibilità di avere il controllo sul percorso che richiede il traffico di rete. Non devono più preoccuparsi del routing imprevedibile che accade su Internet, in cui i dati vengono trasportati da vettori, provider e ISP sconosciuti. Il traffico di rete inviato tramite ExpressRoute viene inviato direttamente dall'altra parte della rete del partner di ExpressRoute alla rete Microsoft. Questo consente ai clienti di trattare Microsoft 365 o Office 365 come se si trovasse nel proprio centro dati fuori sede con una connessione dedicata.
  
Azure ExpressRoute è disponibile per tutte le offerte di licenza per Microsoft 365 e Office 365. Tuttavia, è necessario il componente aggiuntivo Azure ExpressRoute Premium per Microsoft 365 e Office 365 per abilitare il routing globale. I clienti con almeno 500 seggi che implementano ExpressRoute possono ottenere il *componente aggiuntivo ExpressRoute Premium* richiesto senza ulteriori spese.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute è necessario per una qualità multimediale ottimale?

Azure ExpressRoute non è un requisito per ottenere la qualità multimediale Skype for business online più ottimale. Si tratta, tuttavia, di una delle opzioni di distribuzione che consentono di verificare che la connettività cloud soddisfi le soglie o i limiti delle prestazioni di Skype for Business Network.
  
Microsoft 365 e Office 365 sono servizi ad alte prestazioni e sicuri che usano Internet. Continuiamo a investire in nuove funzionalità di sicurezza e in nodi Edge regionali per migliorare continuamente la sicurezza e le prestazioni. Azure ExpressRoute non è un requisito per Microsoft 365 o i servizi di Office 365, incluso Skype for business online. Azure ExpressRoute è una delle opzioni di distribuzione disponibili per garantire che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni della rete Skype for business e garantisca l'esperienza di qualità multimediale Skype for business online più ottimale.
  
Per la qualità dei contenuti multimediali Skype for business online, è importante che la connessione tra i siti aziendali e i bordi della rete Microsoft soddisfi i requisiti di prestazioni per le [prestazioni di rete da un client Skype for business a Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) e che la connessione tra i bordi della rete e i bordi della rete Microsoft soddisfi i requisiti per le prestazioni di [rete dal bordo della rete a Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
È inoltre importante che la connettività di rete fisica della società, inclusa la capacità di connettività di rete interna e cloud, contenesse il volume del traffico multimediale Peak. Azure ExpressRoute è uno dei molti modi per aiutare i clienti a garantire che la connettività cloud di Skype for business online soddisfi tutti questi requisiti di prestazioni.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute è necessario per la qualità vocale SLA?

No, ExpressRoute non è necessario per il contratto di qualità vocale di Skype for business online. L' [SLA sulla qualità vocale di Skype for business online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) si applica a qualsiasi chiamata idonea effettuata da qualsiasi utente del servizio vocale di Skype for business online all'interno della licenza e dell'abbonamento corretti che consente all'utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. Un SLA sulla qualità vocale deve includere tutte le condizioni seguenti:
  
- Chiamate da telefoni IP certificati Microsoft.
    
- Connessioni Ethernet cablate.
    
- Problemi di qualità vocale a causa di problemi di rete Microsoft.
    
> [!NOTE]
> Lo SLA sulla qualità vocale esclude le chiamate in cui la qualità della chiamata bassa è causata da problemi nelle reti non Microsoft, tra cui partner di ExpressRoute e altre reti. 
  
### <a name="internet-or-azure-expressroute"></a>Internet o Azure ExpressRoute?

Prima di prendere una decisione sulle opzioni di connettività di rete a Skype for business online, i clienti devono valutare la propria rete e la connettività Internet corrente in base ai requisiti di prestazioni di rete descritti in [requisiti di prestazioni di rete per connettersi a Skype for business online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se le prestazioni di rete sulla connessione Internet corrente sono configurate per una capacità sufficiente durante il periodo di punta e che soddisfano i requisiti di prestazioni di rete da siti a bordi di rete Microsoft e dai bordi della rete ai bordi della rete Microsoft, è possibile continuare a usare la connettività Internet esistente per connettersi a Skype for business online.
  
Per i siti aziendali in cui non vengono soddisfatti i requisiti di prestazioni di rete, è consigliabile collaborare prima di tutto con i provider di servizi di rete esistenti per migliorare le prestazioni complessive della rete. Tuttavia, se non vengono ancora soddisfatte, l'uso di Azure ExpressRoute può aiutare a garantire che la connettività cloud di Skype for business online possa essere utile per soddisfare i requisiti di prestazioni della rete.
  
Azure ExpressRoute offre i seguenti vantaggi aggiuntivi:
  
- Contratto di servizio (SLA, Service Level Agreement) sulla disponibilità della connessione tra la rete e la rete Microsoft. ExpressRoute ha un SLA di disponibilità garantita di 99,9%.
    
- Larghezza di banda pianificata e garantita necessaria per Microsoft 365 e Office 365 Services. Puoi ottenere questo risultato inviando solo Microsoft 365, Office 365 o il traffico Skype for business usando il ExpressRoute e quindi tutti gli altri traffici Internet passano attraverso altri punti di uscita/ingresso di Internet per la rete.
    
- ExpressRoute è progettato per mantenere i contrassegni di DSCP QoS tra la rete e la rete Microsoft.
    
Per altre informazioni su QoS e pianificazione delle capacità di ExpressRoute, vedere [ExpressRoute e QoS in Skype for business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>È possibile configurare solo Azure ExpressRoute per Skype for business online?

Sì, è possibile configurare Azure ExpressRoute per garantire una connettività di rete eccellente dalla rete aziendale a Skype for business online. Questo fornirà la qualità multimediale in tempo reale più ottimale per gli utenti, ma è possibile continuare a connettersi ad altri servizi Microsoft 365 o Office 365 tramite Internet.
  
Il protocollo BGP (Border Gateway Protocol) è un protocollo di routing su Internet che viene usato per instradare il traffico di rete su Internet. È progettato per scambiare le informazioni di routing tra sistemi autonomi (come) trovati in Internet. I valori delle community BGP sono tag di attributo che possono essere applicati alle route in ingresso o in uscita. Le community BGP vengono spesso usate per segnalare al destinatario il collegamento in uscita da usare per raggiungere una determinata destinazione in base a geografia, tipo di servizio o altri criteri.
  
Con il supporto delle community BGP, Microsoft contrassegnerà i prefissi e le route con i valori appropriati della community BGP in base al servizio a cui appartengono. Microsoft contrassegnerà i prefissi annunciati tramite peering pubblico e Microsoft peering con i valori appropriati della community BGP che indicano l'area geografica in cui sono ospitati i prefissi. Puoi fare affidamento sui valori della community per prendere decisioni di routing appropriate per offrire un routing ottimale. Puoi usare il valore community BGP di Skype for business online per configurare una connessione ExpressRoute solo per Skype for business online. Per altre informazioni, vedere [requisiti di routing di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scenari di connettività di ExpressRoute per Skype for business online
<a name="bkNetworkPerf"> </a>

Se si è deciso che ExpressRoute in base alle raccomandazioni descritte sopra è per l'utente, ecco le raccomandazioni su dove e quante connessioni ExpressRoute dovresti ottenere.
  
### <a name="online-only-deployment---single-site"></a>Distribuzione solo online-sito singolo

Se tutti gli utenti usano il servizio Skype for business online e se gli uffici sono centrati attorno a una singola posizione fisica e si decide di distribuire Azure ExpressRoute, è necessario configurare una connessione ExpressRoute singola tra il sito della società e la posizione di [peering di ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)più vicina.
  
L'immagine seguente mostra un esempio di questo tipo di distribuzione. Per questo esempio, Contoso è un ateneo situato a Orlando, FL. Contoso include 10.000 membri della facoltà e studenti. I test Internet dalla loro posizione ai siti Microsoft Edge hanno mostrato una perdita di pacchetti maggiore del 5% durante le ore di punta della classe. Hanno deciso di ottenere una connessione dedicata a Microsoft 365 o Office 365 usando ExpressRoute con larghezza di banda troppo provisionale in modo che possano evitare la congestione della rete per Microsoft 365 o Office 365 in particolare per il traffico in tempo reale di Skype for business online. Si connettono a Microsoft Cloud tramite ExpressRoute nel sito di Atlanta, GA MeetMe.
  
![ExpressRoute sito singolo.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Distribuzione solo online: più siti nello stesso continente

Se la società usa i servizi Skype for business online da più uffici della stessa area geografica o continentale e si è scelto di implementare Azure ExpressRoute, è consigliabile connettere il sito principale tramite ExpressRoute e quindi facoltativamente aggiungere altri peer di ExpressRoute per altre posizioni che non soddisfano le destinazioni consigliate per le prestazioni di rete.
  
Nell'esempio seguente contoso è una società di servizi di viaggio degli Stati Uniti con sede a New York, ma ha altri uffici negli Stati Uniti. I loro uffici sono collegati tra loro tramite una rete WAN che usa MPLS per la connessione a Microsoft 365 o Office 365. Inizialmente hanno configurato una connessione ExpressRoute dal proprio router Internet a Hoboken, New Jersey, nel sito di New York MeetMe. 
  
Con questa configurazione, il traffico di rete dalla maggior parte dei siti al sito Microsoft Network (New York Edge) può soddisfare gli obiettivi di prestazioni della rete di connessione client Skype for business descritti in [requisiti di prestazioni di rete da un client Skype for business a Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). Tuttavia, la latenza tra gli uffici della West Coast di Contoso per New York sta superando 50ms unidirezionale. Inoltre, Honolulu è il secondo ufficio più grande per contoso, la latenza da Honolulu a New York supera 80ms unidirezionale. Per garantire una buona qualità dei contenuti multimediali per gli utenti di tali uffici, Contoso ha deciso di aggiungere una connessione ExpressRoute West Coast tra il sito di San Jose e il sito di ExpressRoute MeetMe di Silicon Valley.
  
![Router Express multi-sito nello stesso continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Distribuzione solo online: più siti in continenti diversi

Se tutti gli utenti usano il servizio Skype for business online e se gli uffici si trovano in più posizioni fisiche in più continenti, se si decide di distribuire Azure ExpressRoute, è necessario configurare almeno una connessione ExpressRoute per ogni continente tra il sito principale di ogni continente e la [posizione di peering ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)più vicina. A seconda del costo e della prestazione, è possibile scegliere di distribuire connessioni ExpressRoute aggiuntive da siti in cui le destinazioni di prestazioni di rete non sono soddisfatte.
  
Nell'esempio seguente contoso è un grande studio legale aziendale con uffici nelle principali città in Nord America e in Europa. In base alla loro connessione Internet e alla valutazione delle prestazioni di rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo circuito di ExpressRoute per tutti gli uffici europei.
  
![ExpressRoute con più siti e continenti.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Distribuzione ibrida

Se si dispone di una distribuzione locale di Lync o Skype for business e si sceglie di implementare un'integrazione ibrida di Skype for business online, è consigliabile se si decide di distribuire Azure ExpressRoute, è necessario disporre di almeno una connessione ExpressRoute per ogni sito Lync o Skype for Business Edge e almeno una connessione ExpressRoute per ogni continente con gli uffici. A seconda del costo e della prestazione, per ogni continente è possibile scegliere di distribuire connessioni ExpressRoute aggiuntive dagli uffici in cui non vengono soddisfatte le destinazioni di prestazioni di rete.
  
Se si dispone di una distribuzione Skype for business locale, è necessario seguire la [Guida alla pianificazione e distribuzione di Edge Server](https://technet.microsoft.com/library/mt346417.aspx). In particolare, gli Edge Server devono essere raggiungibili dall'esterno della rete. Questa operazione viene in genere eseguita assegnando un indirizzo IP pubblico instradabile all'Edge Server o tramite NAT (Network Address Translation).
  
Nell'esempio seguente contoso include una distribuzione vocale di Skype for Business Enterprise esistente in locale. Vogliono eseguire la migrazione degli utenti locali a Microsoft 365 o ai servizi online di Office 365. Hanno anche deciso di usare una distribuzione ibrida in modo che possano continuare a usare l'infrastruttura PSTN esistente per tutti gli utenti locali e online. Il centro dati locale di Contoso e i server Edge Skype for business si trovano a Chicago. Per la distribuzione, Contoso ha deciso di configurare una connessione ExpressRoute tra il Data Center di Chicago e il Chicago ExpressRoute. Hanno anche aggiunto una connessione ExpressRoute West Coast per servire meglio il loro ufficio di Honolulu.
  
![ExpressRoute Hybrid.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Distribuzione online con Cloud Connector Edition

Skype for business online Cloud Connector Edition è un'offerta ibrida costituita da un set di macchine virtuali in pacchetto (VM) che implementano la connettività PSTN locale. Distribuendo una topologia minima di Skype for Business Server in un ambiente virtualizzato, sarà possibile inviare e ricevere chiamate con telefoni fissi e cellulari tramite l'infrastruttura vocale PSTN esistente.
  
Se si decide di distribuire Azure ExpressRoute e Cloud Connector Edition, è consigliabile configurare almeno una connessione di route espressa per ogni continente tra il sito principale di ogni continente e la [posizione di peering ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)più vicina. A seconda del costo e della prestazione, per ogni continente è possibile scegliere di distribuire connessioni ExpressRoute aggiuntive da siti in cui non vengono soddisfatte destinazioni di prestazioni di rete.
  
Se si dispone di una distribuzione Skype for business locale, è necessario seguire la [Guida alla pianificazione per Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). In particolare, i servizi Edge e A/V Edge di Access devono essere assegnati indirizzi IP pubblici e centri dati di Microsoft 365 o Office 365 raggiungibili.
  
Nell'esempio seguente contoso è una società contabile europea con presenza in alcuni dei principali paesi europei e città. Quando si iscrivono a Skype for business online per tutte le esigenze di collaborazione, hanno deciso di inserire un Cloud Connector per ogni paese in cui hanno un percorso fisico per continuare a usare l'infrastruttura PSTN e i contratti di trasporto già esistenti. In base al test da tutti i loro siti e Microsoft Network Edge, hanno stabilito che una singola connessione ExpressRoute a Londra consentirà di soddisfare gli obiettivi di prestazioni della rete di connessione client Skype for business descritti in [requisiti di prestazioni di rete da un client Skype for business a Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Connettore Cloud ExpressRoute uno.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Di seguito è riportata un'altra opzione di distribuzione per contoso. In questo caso, hanno deciso di configurare una connessione ExpressRoute in ogni sito in cui è distribuito un connettore Cloud. 
  
![Connettore Cloud ExpressRoute due.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Argomenti correlati

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
