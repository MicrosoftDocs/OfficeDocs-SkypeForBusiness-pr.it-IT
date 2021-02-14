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
description: In questo argomento viene definita la serie di requisiti di prestazione di rete per i servizi di Skype for Business Online e le modalità di scelta tra Internet o ExpressRoute per la connettività tra la propria rete e Skype for Business Online sulla base della valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per una connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni ExpressRoute in diversi scenari di distribuzione di Skype for Business Online.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164765"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualità multimediale e prestazioni della connettività di rete in Skype for Business online

In questo argomento viene definita la serie di requisiti di prestazione di rete per i servizi di Skype for Business Online e le modalità di scelta tra Internet o ExpressRoute per la connettività tra la propria rete e Skype for Business Online sulla base della valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per una connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni ExpressRoute in diversi scenari di distribuzione di Skype for Business Online.
  
La qualità della connettività di rete end-to-end influisce notevolmente sulla qualità dei supporti multimediali Real-Time (condivisione di audio, video e applicazioni) su IP. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Azure ExpressRoute non è un requisito per i servizi di Microsoft 365 e Office 365, incluso Skype for Business online. Tuttavia, Azure ExpressRoute è una delle opzioni di distribuzione disponibili per garantire che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni di rete di Skype for Business e garantisca un'esperienza multimediale di qualità ottimale su Skype for Business Online.
  
> [!TIP]
> Anche se questo argomento fornisce indicazioni generali sulle prestazioni di rete, la guida completa per la valutazione della rete non rientra nell'ambito di questo documento. Per trovare un elenco di partner di Skype for Business online che possono aiutarti con le misurazioni delle prestazioni di rete nell'ambito di una valutazione completa e approfondita della rete, visita le soluzioni partner di [Skype for Business.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisiti di connettività di rete per Skype for Business online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fattori che influiscono sulla qualità dei supporti multimediali di Skype for Business Online

La qualità dei supporti multimediali Real-Time di Skype for Business Online (condivisione di audio, video e applicazioni) è influenzata da diversi fattori, tra cui i dispositivi usati, l'ambiente e la connettività di rete. 
  
#### <a name="devices"></a>Dispositivi

In una sessione Real-Time multimediale, i dispositivi di rendering e acquisizione usati da tutti i partecipanti, ad esempio cuffie auricolari e web cam, hanno un impatto notevole sulla qualità complessiva di audio e video. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Anche se non sono necessari dispositivi multimediali audio e video certificati, si consiglia vivamente di utilizzare dispositivi certificati per Skype for Business per un'esperienza multimediale ottimale. Per un elenco di tutti i dispositivi certificati Skype for Business, consulta [Telefoni e dispositivi per Skype for Business.](https://technet.microsoft.com/office/dn947482) È possibile utilizzare Call Quality Dashboard di [Skype for Business Online,](/microsoftteams/turning-on-and-using-call-quality-dashboard)disponibile nell'interfaccia di amministrazione di **Skype for Business,** per verificare il corretto funzionamento dei dispositivi in uso e monitorare la qualità dei supporti audio e video.
  
> [!TIP]
> **Per un'esperienza multimediale ottimale sui** supporti multimediali di Skype for Business è necessario un dispositivo certificato.
  
È importante ricordare che tutti i dispositivi multimediali, client di Skype for Business e server di Skype for Business attraverso cui Real-Time flussi multimediali, introducono una certa latenza. La latenza di elaborazione del software e del dispositivo, insieme alla latenza della rete, hanno un forte impatto sulla latenza generale end-to-end e sull'esperienza dell'utente finale.
  
#### <a name="environment"></a>Ambiente

L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere un'immagine più chiara dell'esperienza audio e video di un utente, usa il dispositivo audio o video Strumenti dell'app Skype for Business per apportare modifiche al dispositivo in uso e personalizzarne le  >    >   impostazioni. 

#### <a name="network"></a>Rete

La qualità dei supporti Real-Time via IP è notevolmente influenzata dalla qualità della connettività di rete, ma in particolare dalla quantità di:
  
- **Latenza** È il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione in rete è strettamente collegato alla distanza fisica tra i due punti e alla velocità della luce, compreso un ulteriore sovraccarico dei vari router che si trova tra di loro. La latenza viene misurata come tempo unidiredirebile o tempo di round trip (RTT).
    
- **Perdita pacchetti** Spesso viene definita come percentuale di pacchetti che vengono persi in un intervallo di tempo specificato. La perdita di pacchetti influisce direttamente sulla qualità audio, da pacchetti piccoli e singoli che non hanno quasi alcun impatto, a perdite di durata "back-to-back" che causano il cut-out completo dell'audio.
    
- **Instabilità tra arrivi di pacchetti o semplicemente instabilità** Si tratta della variazione media del ritardo tra pacchetti successivi. La maggior parte del software VoIP moderno, incluso Skype for Business, può adattarsi ad alcuni livelli di instabilità attraverso il buffering. È solo quando l'instabilità supera il buffering che un partecipante noterà gli effetti di instabilità.
    
> [!NOTE]
>  Il buffering per instabilità aumenterà la latenza end-to-end.
  
Con molte sessioni multimediali Real-Time di Skype for Business Online simultanee, oltre al traffico di rete generato da altri servizi Di Microsoft 365 o Office 365 e altre applicazioni aziendali, è fondamentale assicurarsi che vi sia una larghezza di banda sufficiente sull'intero percorso di rete che collega la rete al servizio Skype for Business Online per evitare la congestione della rete e garantire una qualità eccellente dei supporti multimediali Real-Time (condivisione di audio, video e applicazioni). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementazione della qualità del servizio (QoS, Quality of Service) sulle reti congestionate

Inoltre, la congestione di traffico su una rete inciderà notevolmente sulla qualità multimediale. Per consentire ai pacchetti audio e video di viaggiare sulla rete più velocemente e di avere priorità su altro traffico di rete in una rete congestionata, è possibile usare la qualità del servizio (QoS, Quality of Service) per offrire all'utente finale un'esperienza ottimale per le comunicazioni audio e video.
  
La QoS consente di assegnare priorità più elevate ai pacchetti di rete che trasportano dati audio o video. Assegnando priorità più alta a questi pacchetti, è probabile che le comunicazioni audio e video viaggiano sulla rete più velocemente e con meno interruzioni rispetto alle sessioni di rete che implicano trasferimenti di file, esplorazione del Web o backup di database. Questo è dovuto al fatto che ai pacchetti di rete usati per il trasferimento di file o il backup di database viene assegnato per impostazione predefinita il "best effort" come priorità e la congestione di rete non ha un grande impatto. Se non si assegna una priorità più alta ai pacchetti multimediali (condivisione di audio, video e applicazioni) e li si lascia assegnati come "best effort", verranno elaborati insieme a tutto il traffico di rete. A seconda del livello di congestione della rete, la qualità audio e video degli utenti potrebbe essere inferiore.
  
È altamente consigliabile implementare la QoS sulla propria rete per assicurarsi che la congestione all'interno della rete non abbia alcun impatto. Tuttavia, per ottenere il massimo impatto, tutti gli endpoint di rete devono supportare la QoS, il che significa che tutti gli endpoint devono rispettare i contrassegni QoS e la priorità dei pacchetti. I servizi di Skype for Business Online rispettano i contrassegni QoS e le priorità all'interno della rete Microsoft. Tuttavia, il traffico instradato attraverso una connessione pubblica come Internet dalla rete aziendale alla rete di Microsoft non mantiene i contrassegni QoS e la priorità dei pacchetti. Le connessioni private dalla propria rete a Microsoft 365 o Office 365 con [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) offrono una soluzione di distribuzione che mantiene i contrassegni QoS e la priorità dei pacchetti che a loro volta aumenterà la qualità audio e video complessiva per gli utenti finali.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisiti di prestazioni di rete per connettersi a Skype for Business online
<a name="bkNetworkPerf"> </a>

I supporti multimediali Real-Time Skype for Business viaggiano su molti dispositivi diversi, app client, software server e reti diverse. La latenza end-to-end dei supporti Real-Time è la quantità totale di latenza introdotta su tutti i componenti e segmenti di rete. La qualità della connessione di rete end-to-end è determinata dal segmento di rete con la qualità più bassa. Questo segmento rappresenta un collo di bottiglia per il traffico di questa rete.
  
Il diagramma seguente illustra il flusso audio unidirezionale in una conferenza da un partecipante a un altro di Skype for Business.
  
![Flusso delle chiamate ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In questo scenario di conferenza, il percorso del supporto è costituito dai seguenti segmenti di rete:
  
1. **Connessione dall'Utente 1 all'edge della rete di Microsoft** Di solito è inclusa una connessione di rete come WiFi o Ethernet, la connessione WAN dall'Utente 1 al punto di uscita di Internet (dispositivo Edge rete utente) e la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Si trova tra l'Edge di Microsoft e il centro dati di Skype for Business Online, dove vengono utilizzati i server per conferenze A/V.
    
3. **Connessione all'interno della rete Microsoft** Si trova tra il centro dati di Skype for Business Online e l'Edge della rete di Microsoft.
    
4. **Connessione dall'Edge della rete Microsoft all'Utente 2** Ciò include la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft, la connessione WAN dall'Utente 2 al punto di uscita di Internet (Edge rete utente) e la connessione di rete come WiFi o Ethernet.
    
Il diagramma seguente mostra la suddivisione dei componenti e dei segmenti di rete di una chiamata PSTN di Skype for Business Online:
  
![Flusso delle chiamate PSTN ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In uno scenario di chiamata PSTN, il percorso del supporto multimediale attraversa i seguenti segmenti di rete:
  
1. **Connessione da un chiamante client di Skype for Business all'edge della rete Microsoft** Di solito è inclusa una connessione di rete come WiFi o Ethernet, la connessione WAN dal chiamante client di Skype for Business al punto di uscita di Internet (dispositivo Edge rete utente), e la connessione Internet dall'Edge della propria rete all'Edge della rete di Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Si trova tra l'Edge di Microsoft e il centro dati di Skype for Business Online, dove viene usato un Mediation Server.
    
3. **Connessione all'interno della rete Microsoft** Si trova tra il centro dati di Skype for Business Online e l'Edge della rete di Microsoft.
    
4. **Connessione tra la rete Microsoft e i partner del provider di servizi PSTN** Questa è la connessione esistente per eseguire una chiamata PSTN dal client Skype for Business che si trova al di fuori della rete Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisiti di prestazione di rete da un client di Skype for Business all'Edge della rete di Microsoft
<a name="bkSfBClienttoEdge"></a>

Per una qualità ottimale dei supporti multimediali di Skype for Business, sono necessari i seguenti target o valori di soglia per le metriche sulle prestazioni di rete per una connessione dalla rete aziendale all'Edge della rete di Microsoft. Questo segmento della rete include la tua rete interna, che include tutte le connessioni WiFi ed Ethernet, il traffico da sito a sito dell'azienda su una connessione WAN, ad esempio Multiprotocol Label Switching (MPLS), nonché le connessioni partner Internet o ExpressRoute all'Edge della rete di Microsoft.
  
> [!CAUTION]
> **La connettività tra un client Skype for Business nella rete aziendale dell'utente e i servizi di Microsoft 365 o Office 365 devono soddisfare i seguenti requisiti e soglie delle prestazioni di rete.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (one way)  <br/> |< 50 ms  <br/> |
|Latenza (RTT o Round-trip Time)  <br/> |< 100 ms  <br/> |
|Perdita di pacchetti a scatto pieno  <br/> |<10% durante intervalli di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |<1% durante intervalli di 15s  <br/> |
|Instabilità tra arrivi di pacchetti  <br/> |<30 ms durante intervalli di 15s  <br/> |
|Riordino pacchetti  <br/> |<lo 0,05% di pacchetti non in ordine  <br/> |
   
 **Altri requisiti per gli obiettivi di prestazioni:**
  
- La rete di Microsoft ha più di 160 posizioni Edge in tutto il mondo. Lavoriamo con i principali Internet Service Provider (ISP) di tutto il mondo attraverso questi siti Edge. Il target metrico della latenza presuppone che il sito o i siti aziendali dell'utente e gli Edges di Microsoft si spongono sullo stesso continente.
    
- Il sito o i siti aziendali alla connessione Edge della rete di Microsoft includono l'accesso alla rete del primo hop, che può essere WiFi o un'altra tecnologia wireless. 
    
- Il target delle prestazioni di rete presuppone la larghezza di banda e/o la qualità corrette della pianificazione dei servizi. In altre parole, ciò si applica direttamente al traffico dei supporti multimediali Real-Time Skype for Business quando la connessione di rete è sotto un picco di carico.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisiti di prestazioni di rete dall'Edge della tua rete all'Edge della rete di Microsoft
<a name="bkYourNetworkEdge"> </a>

Di seguito sono riportati i target o limiti di soglia delle prestazioni di rete necessari per la connessione tra l'Edge della rete dell'utente e l'Edge della rete di Microsoft. Questo segmento della rete non include la rete interna del cliente o WAN ed è inteso come guida durante i test sul traffico di rete inviato su Internet o attraverso una rete partner ExpressRoute e può essere usato anche durante la negoziazione di un contratto di servizio (Service Level Agreement, SLA) con il provider ExpressRoute dell'utente.
  
> [!CAUTION]
> **La connettività tra l'Edge della rete aziendale dell'utente e l'Edge della rete di Microsoft deve soddisfare i seguenti requisiti e soglie per le prestazioni di rete.**
  
|||
|:-----|:-----|
|**Metrica** <br/> |**Destinazione** <br/> |
|Latenza (one way)  <br/> |< 30 ms  <br/> |
|Latenza (RTT)  <br/> |< 60 ms  <br/> |
|Perdita di pacchetti a scatto pieno  <br/> |<1% durante intervalli di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |<0,1% durante intervalli di 15s  <br/> |
|Instabilità tra arrivi di pacchetti  <br/> |<15 ms durante intervalli di 15s  <br/> |
|Riordino pacchetti  <br/> |<lo 0,01% dei pacchetti non in ordine  <br/> |
   
 **Altri requisiti per gli obiettivi di prestazioni:**
  
- Il target delle prestazioni richiede la connessione sullo stesso continente tra uno degli Edge della rete aziendale dell'utente e l'Edge più vicino della rete di Microsoft.
    
- Il target delle prestazioni di rete presuppone la larghezza di banda e/o la qualità corrette della pianificazione dei servizi. Ciò vale anche per il traffico multimediale Real-Time Skype for Business quando la connessione di rete è sotto un picco di carico. Per una larghezza di banda corretta e una pianificazione QoS, consulta [ExpressRoute e QoS in Skype for Business online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Misurazione delle prestazioni di rete
<a name="bkNetworkPerf"> </a>

Per misurare le prestazioni effettive della rete, in particolare per la latenza e la perdita di pacchetti, da qualsiasi sito di rete aziendale a un Edge della rete, è possibile utilizzare strumenti come il ping e il test su un set di servizi di Media Relay di Skype for Business in esecuzione dall'Edge di Microsoft e dai siti del data center. 

>[!NOTE]
> Misurare le prestazioni di rete tramite ping (ICMP) non è efficace. Per questo motivo, l'IP anycast esposto di seguito smetterà di rispondere alle richieste ICMP a partire da gennaio 2020. Per misurare le prestazioni di rete in modo efficace, Microsoft consiglia lo [strumento Network Assesment Tool.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Per testare le connessioni Internet alla rete di Microsoft, è consigliabile eseguire il test sui seguenti VIP dei Media Relay di Skype for Business. Il *VIP Anycast risolverà*  un indirizzo IP di un Media Relay in un sito Edge della rete Microsoft più vicino alla posizione di test.
  
||||
|:-----|:-----|:-----|
|**Indirizzo IP** <br/> |**Tipo** <br/> |**Posizione** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Ecco alcuni consigli di alto livello da seguire per valutare le prestazioni di rete:**
  
- Valutare la rete interna e le connessioni a Microsoft 365 o Office 365.
    
- Valutare e raccogliere dati per tutte le reti dell'utente per un lungo periodo di tempo. È consigliabile eseguire i test sulle prestazioni di rete per almeno una settimana, in modo da poter vedere i modelli di utilizzo per tutti i giorni e gli orari lavorativi. Questo ti mostrerà i momenti di picco.
    
- È consigliabile prendere diversi campioni delle misurazioni delle prestazioni di rete. È consigliabile effettuare una misurazione ogni 10 minuti dal sito di un'azienda per l'intero periodo di tempo in cui si stanno raccogliendo i dati. Per confrontare i requisiti di prestazione di rete di Skype for Business Online, prendere il valore di misurazione al 90° percentile da questo set di dati campione. 
    
- Valutare continuamente le prestazioni della rete. L'utilizzo della rete varia nel tempo a causa delle variazioni dei modelli di utilizzo, delle nuove applicazioni aziendali che usano una grande quantità di larghezza di banda e delle variazioni alle posizioni aziendali fisiche o organizzative. È importante monitorare continuamente le prestazioni della rete rispetto a questi requisiti e target/valori di soglia e apportare modifiche tempormente per assicurare una qualità ottimale dei supporti multimediali Real-Time rete. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Misurazione delle prestazioni di rete con le macchine virtuali Azure
<a name="bkNetworkPerf"> </a>

Invece di eseguire test sui siti Edge della rete Di Microsoft, esistono soluzioni di valutazione della rete di clienti e partner di Skype for Business che sfruttano la configurazione dei test per i servizi nel cloud Microsoft Azure. In queste soluzioni, gli strumenti di valutazione della rete testano latenza, perdita di pacchetti e instabilità rispetto agli endpoint personalizzati impostati come servizio nel cloud Azure. Di conseguenza, il traffico di rete del test viaggia attraverso un segmento di rete aggiuntivo, ovvero la connessione all'interno della rete Microsoft tra i bordi della rete e i data center Azure che ospitano il servizio di valutazione della rete.
  
Per le soluzioni di valutazione della rete basate sui servizi di test ospitati su Azure. È consigliabile eseguire la valutazione della rete all'interno del paese e/o dell'area geografica. Ad esempio, per i siti dei clienti negli Stati Uniti orientali, la valutazione deve essere eseguita su un'istanza del servizio di test ospitata nella regione del data center degli Stati Uniti orientali di Azure. 
  
Di seguito sono indicati gli obiettivi della latenza (RTT) per l'impostazione della valutazione della rete basata sul servizio Azure. Gli obiettivi di latenza a una via saranno metà degli obiettivi RTT corrispondenti. Gli obiettivi di perdita di pacchetti e instabilità rimangono uguali a quelli definiti per i test basati su Media Relay di Skype.
  
|||||
|:-----|:-----|:-----|:-----|
|**Area geografica del cliente** <br/> |**Area geografica Azure** <br/> |**Edge della rete - RTT di Azure** <br/> |**Sito personale - RTT di Azure** <br/> |
|Stati Uniti centrali  <br/> |Stati Uniti centrali  <br/> |99  <br/> |139  <br/> |
|Stati Uniti orientali  <br/> |Stati Uniti orientali  <br/> |86  <br/> |126  <br/> |
|Stati Uniti centro settersi  <br/> |Stati Uniti centro settersi  <br/> |97  <br/> |137  <br/> |
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
   
## <a name="media-quality-and-expressroute"></a>Qualità dei supporti multimediali ed ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute per Microsoft 365 o Office 365 è una connessione di rete dedicata per la connessione a Microsoft 365 o Office 365. Offre ai clienti la possibilità di avere il controllo sul percorso che assume il traffico di rete. Non devono più preoccuparsi del routing imprevedibile che si verifica su Internet, in cui i dati vengono trasportati da gestori sconosciuti, provider e ISP. Il traffico di rete inviato attraverso ExpressRoute viene inviato direttamente attraverso la rete del partner ExpressRoute alla rete Microsoft. In questo modo i clienti possono trattare Microsoft 365 o Office 365 come se si trovavano nel loro centro dati fuori sede con una connessione dedicata.
  
Azure ExpressRoute è disponibile per tutte le offerte di licenza di Microsoft 365 e Office 365. Tuttavia, per abilitare il routing globale è necessario il componente aggiuntivo Premium di Azure ExpressRoute per Microsoft 365 e Office 365. I clienti con almeno 500 postazioni che stanno implementando ExpressRoute possono ottenere il componente aggiuntivo *Premium expressRoute* richiesto senza costi aggiuntivi.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute è necessario per una buona qualità multimediale?

Azure ExpressRoute non è un requisito per ottenere una qualità ottimale dei supporti multimediali di Skype for Business Online. Si tratta, tuttavia, di una delle opzioni di distribuzione che consentono di assicurarsi che la connettività cloud soddisfi i target o le soglie delle prestazioni di rete di Skype for Business.
  
Microsoft 365 e Office 365 sono servizi ad alte prestazioni e sicuri che usano Internet. Continuiamo a investire in nuove funzionalità di sicurezza e nodi Edge regionali per migliorare continuamente la sicurezza e le prestazioni. Azure ExpressRoute non è un requisito per i servizi di Microsoft 365 o Office 365, incluso Skype for Business online. Azure ExpressRoute è una delle opzioni di distribuzione disponibili per garantire che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni di rete di Skype for Business e garantisca un'esperienza multimediale di qualità ottimale su Skype for Business Online.
  
Per la qualità dei supporti multimediali di Skype for Business Online, è importante che la connessione tra i siti aziendali e gli Edge della rete di Microsoft soddisfi i target delle prestazioni di rete da un [client di Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) all'Edge della rete di Microsoft e che la connessione tra gli Edge della rete dell'utente e gli edge della rete di Microsoft soddisfi i target di prestazioni di rete dall'Edge della propria rete all'Edge della rete di [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
È anche importante che la connettività della rete fisica dell'azienda dell'utente, compresa la rete interna e la capacità di connettività cloud, supportino il volume di traffico di picco dei supporti multimediali. Azure ExpressRoute è uno dei diversi modi per aiutare i clienti a far sì che la loro connettività cloud di Skype for Business Online soddisfi tutti questi requisiti di prestazioni.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute è necessario per l'SLA sulla qualità vocale?

No, ExpressRoute non è necessario per l'SLA sulla qualità vocale di Skype for Business Online. L'SLA sulla qualità vocale di [Skype for Business online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) si applica a tutte le chiamate idonee effettuate da qualsiasi utente del servizio vocale di Skype for Business Online entro la licenza e l'abbonamento corretti, che consente a tale utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. Un SLA sulla qualità vocale deve includere che tutte le condizioni seguenti siano soddisfatte:
  
- Chiamate da telefoni IP certificati Microsoft.
    
- Connessioni Ethernet cablate.
    
- Problemi di qualità vocale dovuti a problemi della rete Microsoft.
    
> [!NOTE]
> L'SLA sulla qualità vocale esclude le chiamate in cui la bassa qualità delle chiamate è causata da problemi nelle reti non Microsoft, inclusi i partner ExpressRoute e altre reti. 
  
### <a name="internet-or-azure-expressroute"></a>Internet o Azure ExpressRoute?

Prima di prendere una decisione sulle opzioni di connettività di rete per Skype for Business online, i clienti devono valutare la propria rete e l'attuale connettività Internet in base ai requisiti di prestazione di rete descritti nei requisiti di prestazione di rete per connettersi a [Skype for Business online.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Se le prestazioni di rete sull'attuale connessione Internet sono impostate per avere una capacità sufficiente durante i momenti di picco e soddisfano i requisiti di prestazione di rete dai siti agli Edges della rete Microsoft e dagli Edges della rete dell'utente agli Edges della rete di Microsoft, è possibile continuare a usare la connettività Internet esistente per connettersi a Skype for Business online.
  
Per i siti aziendali in cui non sono soddisfatti i requisiti di prestazione di rete, è consigliabile collaborare prima con gli attuali provider dei servizi di rete per migliorare le prestazioni di rete complessive. Tuttavia, se non sono ancora soddisfatti, l'uso di Azure ExpressRoute consente di verificare che la connettività cloud di Skype for Business Online possa aiutarti a soddisfare i requisiti di prestazione di rete.
  
Azure ExpressRoute offre i seguenti vantaggi aggiuntivi:
  
- Un contratto di servizio (SLA) sulla disponibilità della connessione tra la rete dell'utente e la rete di Microsoft. ExpressRoute ha garantito un SLA sulla disponibilità del 99,9%.
    
- Larghezza di banda pianificata e garantita richiesta per i servizi di Microsoft 365 e Office 365. Per ottenere questo risultato, è possibile inviare solo il traffico di Microsoft 365, Office 365 o Skype for Business usando ExpressRoute e quindi fare in modo che tutto il traffico internet passa attraverso altri punti di uscita/ingresso per la rete aziendale.
    
- ExpressRoute è progettato per mantenere i contrassegni QoS DSCP tra la propria rete e la rete Microsoft.
    
Per ulteriori informazioni sulla QoS di ExpressRoute e sulla pianificazione della capacità, consulta ExpressRoute e [QoS in Skype for Business online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>È possibile configurare solo Azure ExpressRoute per Skype for Business online?

Sì, è possibile configurare Azure ExpressRoute per garantire una connettività di rete eccellente dalla rete aziendale dell'utente solo a Skype for Business online. In questo modo si offre una qualità Real-Time multimediale ottimale per gli utenti, ma è possibile continuare a connettersi ad altri servizi di Microsoft 365 o Office 365 tramite Internet.
  
Il protocollo BGP (Border Gateway Protocol) è un protocollo di routing usato su Internet per instradare il traffico di rete attraverso Internet. È progettato per scambiare informazioni di routing tra i sistemi autonomi (AS) disponibili su Internet. I valori delle community BGP sono tag di attributo che possono essere applicati alle route in ingresso o in uscita. Le community BGP vengono spesso usate per segnalare all'AS ricevente quale collegamento in uscita usare per raggiungere una determinata destinazione in base a geografia, tipo di servizio o altri criteri.
  
Con il supporto delle community BGP, Microsoft contrassegnerà prefissi e route con i valori appropriati della community BGP in base al servizio a cui appartengono. Microsoft tagerà i prefissi annunciati tramite il peering pubblico e il peering Microsoft con i valori appropriati della community BGP che indicano l'area in cui sono ospitati i prefissi. È possibile fare affidamento sui valori della community per prendere decisioni appropriate per il routing, in modo da offrire un routing ottimale. È possibile utilizzare il valore dell'attributo Community BGP di Skype for Business online per configurare una connessione ExpressRoute solo per Skype for Business online. Per altre informazioni, vedere i [requisiti di routing di ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Scenari di connettività di ExpressRoute per Skype for Business online
<a name="bkNetworkPerf"> </a>

Se si è deciso che ExpressRoute in base ai suggerimenti precedenti è la cosa più importante, ecco i consigli su dove e quante connessioni ExpressRoute si dovrebbero ottenere.
  
### <a name="online-only-deployment---single-site"></a>Solo distribuzione online - Singolo sito

Se tutti gli utenti usano il servizio Skype for Business online e se gli uffici sono centrati su un'unica località fisica e si decide di distribuire Azure ExpressRoute, è necessario configurare una singola connessione ExpressRoute tra il sito dell'azienda alla posizione [peering expressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)più vicina.
  
L'immagine seguente mostra un esempio di questo tipo di distribuzione. In questo esempio Contoso è un'università situata a Orlando, FL. Contoso ha 10.000 docenti e studenti. I test di Internet dalla loro posizione ai siti edge di Microsoft hanno mostrato una perdita di pacchetti superiore al 5% durante le ore di picco della classe. Hanno deciso di ottenere una connessione dedicata a Microsoft 365 o Office 365 utilizzando ExpressRoute con larghezza di banda di cui è stato eseguito il provisioning in modo da evitare la congestione di rete per Microsoft 365 o Office 365, in particolare per il traffico Real-Time di Skype for Business Online. Si connettono al cloud Microsoft attraverso ExpressRoute al sito di Atlanta, Ga MeetMe.
  
![Singolo sito ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Solo distribuzione online - Più siti nello stesso continente

Se la tua azienda usa i servizi Skype for Business Online da più uffici nella stessa regione o continente e hai scelto di implementare Azure ExpressRoute, è consigliabile connettere il sito principale tramite ExpressRoute e quindi, facoltativamente, aggiungere ulteriori peering ExpressRoute per altre località che non soddisfano i target di prestazioni di rete consigliati.
  
Nell'esempio seguente, Contoso è un'agenzia viaggi con sede a New York ma ha altri uffici negli Stati Uniti. I loro uffici sono interconnessi tramite un WAN che usa MPLS per la connessione a Microsoft 365 o Office 365. Inizialmente configurano una connessione ExpressRoute dal loro router di Internet a Hoboken, New Jersey al sito di MeetMe di New York. 
  
Con questa configurazione, il traffico di rete dalla maggior parte dei loro siti alla rete di Microsoft (sito Edge di New York) può soddisfare i target delle prestazioni di rete della connessione client di Skype for Business descritti nei requisiti di prestazione di rete da un client di Skype for Business all'Edge della rete [di Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Tuttavia, la latenza tra gli uffici della costa occidentale di Contoso e New York va oltre i 50ms one-way. Inoltre, Honolulu è il secondo ufficio più grande per Contoso, la latenza da Honolulu a New York supera gli 80ms one-way. Per garantire una buona qualità dei supporti multimediali per gli utenti di questi uffici, Contoso ha deciso di aggiungere una connessione ExpressRoute sulla costa occidentale tra il loro sito di San Jose e il sito MeetMe di ExpressRoute nella Silicon Valley.
  
![Express Router con più siti sullo stesso continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Solo distribuzione online - Più siti su continenti diversi

Se tutti gli utenti usano il servizio Skype for Business online e se gli uffici si trovare in più sedi fisiche su più continenti, se si decide di distribuire Azure ExpressRoute, è necessario configurare almeno una connessione ExpressRoute per ogni continente tra il sito principale di ogni continente e la località [di peering ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)più vicina. A seconda dei costi/vantaggi, è possibile scegliere di distribuire altre connessioni ExpressRoute dai siti in cui non vengono soddisfatti i target delle prestazioni di rete.
  
Nell'esempio seguente Contoso è un grande studio legale con uffici nelle principali città di Nord America ed Europa. In base alla connessione Internet e alla valutazione delle prestazioni della rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo circuito ExpressRoute per tutti gli uffici europei.
  
![ExpressRoute con più siti e continenti.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Distribuzione ibrida

Se si dispone di una distribuzione locale di Lync o Skype for Business e si sceglie di implementare una integrazione ibrida di Skype for Business Online, si consiglia di avere almeno una connessione ExpressRoute per ogni sito Edge di Lync o Skype for Business in sede e almeno una connessione ExpressRoute per ogni continente con uffici. A seconda dei costi/vantaggi, per ogni continente è possibile scegliere di distribuire ulteriori connessioni ExpressRoute dagli uffici in cui non vengono soddisfatti i target delle prestazioni di rete.
  
Se si dispone di una distribuzione di Skype for Business in sede, è necessario seguire la Guida alla pianificazione e alla distribuzione [dei server perimetrali.](https://technet.microsoft.com/library/mt346417.aspx) In particolare, i server perimetrali devono essere raggiungibili dall'esterno della rete. Questa operazione viene in genere ottenuta assegnando un indirizzo IP pubblico instradabile al server perimetrale o usando NAT (Network Address Translation).
  
Nel seguente esempio, Contoso ha una distribuzione locale di skype for Business VoIP aziendale distribuzione. Vogliono eseguire la migrazione degli utenti locali ai servizi online di Microsoft 365 o Office 365. Hanno anche deciso di usare una distribuzione ibrida in modo che possano continuare a usare l'infrastruttura PSTN esistente per tutti gli utenti locali e online. Il centro dati locale di Contoso e i server perimetrali Skype for Business sono a Chicago. Per la distribuzione, Contoso ha deciso di configurare una connessione ExpressRoute tra il centro dati di Chicago e ExpressRoute di Chicago. Ha anche aggiunto una connessione ExpressRoute sulla costa occidentale per migliorare il servizio dell'ufficio di Honolulu.
  
![ExpressRoute ibrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Distribuzione online con Cloud Connector Edition

Cloud Connector Edition di Skype for Business Online è un'offerta ibrida costituita da un set di Macchine virtuali (VM) in pacchetto che implementano la connettività PSTN locale. Distribuendo una topologia server minima di Skype for Business in un ambiente virtualizzato, sarà possibile inviare e ricevere chiamate con telefoni fissi e cellulari attraverso l'infrastruttura vocale PSTN esistente in sede.
  
Se si decide di distribuire Azure ExpressRoute e Cloud Connector Edition, è consigliabile configurare almeno una connessione Express Route per ogni continente tra il sito principale di ogni continente e la più vicina posizione [di peering di ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) A seconda dei costi/vantaggi, per ogni continente è possibile scegliere di distribuire ulteriori connessioni ExpressRoute dai siti in cui non vengono soddisfatti i target delle prestazioni di rete.
  
Se si dispone di una distribuzione di Skype for Business in sede, è necessario seguire la Guida alla pianificazione per [Skype for Business Cloud Connector Edition.](https://technet.microsoft.com/library/mt605227.aspx) In particolare, ai servizi Access Edge e A/V Edge devono essere assegnati indirizzi IP pubblici e datacenter Microsoft 365 o Office 365 raggiungibili.
  
Nell'esempio seguente Contoso è uno studio contabile europeo con una presenza in alcuni dei principali paesi e città europee. Quando effettuano l'iscrizione a Skype for Business online per tutte le loro esigenze di collaborazione, hanno deciso di inserire un Cloud Connector per ogni paese in cui hanno una posizione fisica per continuare a usare la propria infrastruttura PSTN e i contratti dei gestori già esistenti. Sulla base dei test e dei test e dell'Edge della rete di Microsoft, hanno stabilito che una singola connessione ExpressRoute a Londra aiuterà a soddisfare i target delle prestazioni di rete della connessione client di Skype for Business descritti nei requisiti di prestazione di rete da un client di Skype for Business all'Edge della rete [di Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![ExpressRoute Cloud Connector 1.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Di seguito è riportata un'altra opzione di distribuzione per Contoso. In questo caso, hanno deciso di configurare una connessione ExpressRoute in ogni sito in cui è distribuito un Cloud Connector. 
  
![ExpressRoute Cloud Connector 2.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Argomenti correlati

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
