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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Questo argomento definisce il set di requisiti di prestazioni di rete per i servizi Microsoft Teams e come è possibile scegliere di usare Internet o ExpressRoute per la connettività tra la rete e Microsoft Teams in base alla valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per la connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni ExpressRoute in diversi scenari Microsoft Teams distribuzione.
ms.openlocfilehash: 3699e225f69deda5fd69b2308dc50337a1d0b228
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618242"
---
# <a name="media-quality-and-network-connectivity-performance-in-microsoft-teams"></a>Qualità multimediale e prestazioni della connettività di rete in Microsoft Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Questo argomento definisce il set di requisiti di prestazioni di rete per i servizi Microsoft Teams e come è possibile scegliere di usare Internet o ExpressRoute per la connettività tra la rete e Microsoft Teams in base alla valutazione della connettività di rete. Se si è deciso di distribuire Azure ExpressRoute per la connettività dedicata a Microsoft 365 o Office 365, questo documento fornisce anche indicazioni su come pianificare le connessioni ExpressRoute in diversi scenari Microsoft Teams distribuzione.
  
La qualità dei Real-Time multimediali (audio, video e condivisione di applicazioni) su IP è notevolmente influenzata dalla qualità della connettività di rete end-to-end. Per garantire Microsoft Teams qualità ottimale dei supporti multimediali, è importante assicurarsi che ci sia una connessione di alta qualità tra la rete aziendale e Microsoft Teams. Il modo migliore per eseguire questa operazione è configurare la rete interna e la connettività cloud in base alla capacità della rete di gestire il volume di traffico di punta per Microsoft Teams su tutte le connessioni.
  
Azure ExpressRoute non è un requisito per Microsoft 365 e Office 365 servizi, inclusi Microsoft Teams. Tuttavia, Azure ExpressRoute è una delle opzioni di distribuzione disponibili che consentono di verificare che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni di rete di Microsoft Teams e garantisca l'esperienza di qualità multimediale Microsoft Teams ottimale.
  
> [!TIP]
> Anche se in questo argomento sono disponibili indicazioni generali sulle prestazioni di rete, le istruzioni complete per la valutazione della rete non rientra nell'ambito di questo documento. Per trovare un elenco di Microsoft Teams partner che possono aiutarti con le misurazioni delle prestazioni di rete nell'ambito di una valutazione approfondita e completa della rete, visita Skype for Business [Partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-microsoft-teams"></a>Requisiti di connettività di rete per Microsoft Teams

### <a name="factors-that-impact-microsoft-teams-media-quality"></a>Fattori che influiscono sulla qualità Microsoft Teams media

Esistono molti fattori diversi che contribuiscono alla qualità Microsoft Teams Real-Time multimediale (audio, video e condivisione di applicazioni) che include i dispositivi usati, l'ambiente e la connettività di rete. 
  
#### <a name="devices"></a>Dispositivi

In una Real-Time multimediale, i dispositivi di acquisizione e rendering multimediali usati da tutti i partecipanti, ad esempio cuffie e webcam, hanno un impatto notevole sulla qualità audio e video complessiva. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. I dispositivi certificati o i dispositivi di buona qualità consentono l'annullamento dell'eco, il filtro del rumore, la risoluzione video e la riduzione della latenza.
  
Anche se i dispositivi multimediali audio e video certificati non sono necessari, si tratta di dispositivi altamente consigliati certificati per Microsoft Teams per un'esperienza multimediale ottimale. Per un elenco di tutti i Microsoft Teams certificati, vedere Telefoni e dispositivi [per](../../SfbPartnerCertification/certification/devices-ip-phones.md)Skype for Business . È possibile usare il [dashboard](/microsoftteams/turning-on-and-using-call-quality-dashboard)Microsoft Teams qualità delle chiamate, disponibile nell'interfaccia di amministrazione di **Skype for Business**, per verificare che i dispositivi in uso funzionino correttamente e monitorare la qualità dei supporti audio e video.
  
> [!TIP]
> **È necessario un dispositivo certificato per un'esperienza Skype for Business qualità multimediale ottimale.**
  
È importante ricordare che qualsiasi dispositivo multimediale, client Microsoft Teams e server Skype for Business server attraverso cui Real-Time flussi multimediali, introducono una certa latenza. La latenza di elaborazione del dispositivo e del software, insieme alla latenza di rete, hanno un impatto notevole e contribuiscono alla latenza globale end-to-end e all'esperienza dell'utente finale.
  
#### <a name="environment"></a>Ambiente

L'ambiente e l'area circostante in cui gli utenti stanno incontrando e usano dispositivi audio e video è un altro fattore importante per la qualità audio e video. Gli utenti che chiamano da un ambiente rumoroso avranno l'eco, l'audio ovattato e poco chiaro. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere un'immagine più chiara dell'esperienza audio e video di un utente, usare l'app Skype for Business Strumenti Opzioni Dispositivo audio o Dispositivo video per apportare modifiche al dispositivo in uso e personalizzarne le  >    >   impostazioni. 

#### <a name="network"></a>Rete

La qualità dei supporti multimediali Real-Time rete IP è notevolmente influenzata dalla qualità della connettività di rete, ma in particolare dalla quantità di:
  
- **Latenza** Questo è il tempo necessario per ottenere un pacchetto IP dal punto A al punto B della rete. Questo ritardo di propagazione della rete è legato alla distanza fisica tra i due punti e alla velocità della luce, incluso il sovraccarico aggiuntivo dei vari router in mezzo. La latenza viene misurata come tempo unidirebile o di andata e ritorno (RTT).
    
- **Perdita di pacchetti** Questa opzione viene spesso definita come percentuale di pacchetti persi in un determinato intervallo di tempo. La perdita di pacchetti influisce direttamente sulla qualità audio, da piccoli pacchetti persi individuali che non hanno quasi alcun impatto, a perdite di burst back-to-back che causano il cut-out audio completo.
    
- **Instabilità di arrivo tra** pacchetti o semplicemente instabilità Questa è la variazione media del ritardo tra pacchetti successivi. La maggior parte del software VoIP moderno Microsoft Teams può adattarsi ad alcuni livelli di instabilità attraverso il buffering. È solo quando l'instabilità supera il buffering che un partecipante noterà gli effetti di instabilità.
    
> [!NOTE]
>  Il buffering per instabilità aumenterà la latenza end-to-end.
  
Con molte sessioni multimediali Microsoft Teams Real-Time simultanee e altro traffico di rete generato da altri servizi Microsoft 365 o Office 365 e altre applicazioni aziendali, assicurarsi che nell'intero percorso di rete sia disponibile larghezza di banda sufficiente per connettere la rete al servizio Microsoft Teams è fondamentale per evitare la congestione della rete e garantire una qualità eccellente dei supporti multimediali Real-Time (audio, video e condivisione applicazioni). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementazione della qualità del servizio (QoS) nelle reti congestionate

Inoltre, la congestione del traffico in una rete influisce notevolmente sulla qualità dei supporti multimediali. Per consentire ai pacchetti audio e video di viaggiare più rapidamente nella rete e di assegnare priorità rispetto ad altro traffico di rete in una rete congestionata, è possibile usare la qualità del servizio (QoS) per offrire un'esperienza utente finale ottimale per le comunicazioni audio e video.
  
QoS consente di assegnare priorità più elevate ai pacchetti di rete che trasportano dati audio o video. Assegnando una priorità più alta a questi pacchetti, è probabile che le comunicazioni audio e video viaggino sulla rete più velocemente e con meno interruzioni rispetto alle sessioni di rete che implicano operazioni come trasferimenti di file, esplorazione Web o backup di database. Questo perché ai pacchetti di rete usati per i trasferimenti di file o per i backup del database per impostazione predefinita viene assegnato il "massimo sforzo" come priorità e la congestione di rete non ha un impatto così grande. Se non si assegna una priorità più alta ai pacchetti multimediali (audio, video e condivisione di applicazioni) e non li si lascia assegnati come "sforzo migliore", anche questi verranno elaborati insieme a tutto il traffico di rete. A seconda della quantità di congestione di rete, questa operazione potrebbe terminare con un'esperienza di qualità audio e video complessiva inferiore per gli utenti.
  
È consigliabile implementare QoS nella rete per assicurarsi che la congestione di rete all'interno della rete non abbia alcun impatto. Tuttavia, per ottenere il massimo impatto, tutti gli endpoint di rete devono supportare QoS, il che significa che tutti gli endpoint devono rispettare il contrassegno QoS e la priorità dei pacchetti. Microsoft Teams servizi rispettano il contrassegno QoS e la priorità all'interno della rete Microsoft. Tuttavia, il traffico instradato attraverso una connessione pubblica come Internet dalla rete aziendale alla rete Microsoft non mantiene i contrassegni QoS e la priorità dei pacchetti. Le connessioni private dalla rete a Microsoft 365 o Office 365 usando [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) offrono una soluzione di distribuzione che mantiene i contrassegni QoS e la priorità dei pacchetti che a loro volta aumentano la qualità audio e video complessiva per gli utenti finali.
  
## <a name="network-performance-requirements-to-connect-to-microsoft-teams"></a>Requisiti di prestazioni di rete per connettersi a Microsoft Teams
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time multimediali viaggia attraverso molti dispositivi, app client, software server e reti diverse. La latenza end-to-end dei supporti multimediali Real-Time la latenza totale introdotta in tutti i componenti e segmenti di rete. La qualità della connessione di rete end-to-end è determinata dal segmento di rete con la qualità peggiore. Questo segmento funge da collo di bottiglia per questo traffico di rete.
  
Il diagramma seguente illustra il flusso audio unidirezionale in una conferenza da Microsoft Teams partecipante a un altro.
  
![Chiamata ExpressRoute Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In questo scenario di conferenza, il percorso multimediale è costituito dai segmenti di rete seguenti:
  
1. **Connessione dall'utente 1 all'edge della rete Microsoft** Questo in genere include una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN dall'utente 1 al punto di uscita Internet (il dispositivo Edge di rete) e la connessione Internet dalla rete Edge alla rete Edge Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Si tratta di un'Microsoft Edge a Microsoft Teams data center, in cui vengono usati i server A/V Conferencing.
    
3. **Connessione all'interno di Microsoft Network** Si trova tra il Microsoft Teams data center e Microsoft Network Edge.
    
4. **Connessione dall'edge di rete Microsoft all'utente 2** Questo include la connessione Internet dalla rete Edge alla rete Microsoft Edge, la connessione WAN dall'utente 2 al punto di uscita Internet (edge di rete) e la connessione di rete, ad esempio una Rete WiFi o una Ethernet.
    
Il diagramma seguente mostra la suddivisione dei componenti e dei segmenti di rete di una chiamata PSTN Microsoft Teams chiamata PSTN:
  
![Gestore chiamate PSTN ExpressRoute Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In uno scenario di chiamata PSTN, il percorso multimediale attraversa i segmenti di rete seguenti:
  
1. **Connessione da un chiamante Skype for Business client al bordo della rete Microsoft** Questo include in genere una connessione di rete, ad esempio WiFi o Ethernet, la connessione WAN dal chiamante del client Skype for Business al punto di uscita Internet (il dispositivo Edge di rete) e la connessione Internet dall'edge di rete all'edge della rete Microsoft.
    
2. **Connessione all'interno della rete Microsoft** Si tratta di un Microsoft Edge a Microsoft Teams data center, in cui viene usato un Mediation Server.
    
3. **Connessione all'interno di Microsoft Network** Si trova tra il Microsoft Teams data center e Microsoft Network Edge.
    
4. **Connessione tra Microsoft Network e i partner del provider di servizi PSTN** Questa è la connessione esistente per eseguire una chiamata PSTN dal client Skype for Business che si trova all'esterno della rete Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisiti di prestazioni di rete da un client Skype for Business a Microsoft Network Edge
<a name="bkSfBClienttoEdge"></a>

Per ottenere Skype for Business qualità ottimale dei supporti multimediali, per una connessione dalla rete aziendale all'Edge della rete Microsoft sono necessari i target o le soglie seguenti per le metriche delle prestazioni di rete. Questo segmento della rete include la rete interna, incluse tutte le connessioni WiFi ed Ethernet, qualsiasi traffico aziendale da sito a sito tramite una connessione WAN, ad esempio MPLS (Multiprotocol Label Switching), nonché le connessioni partner Internet o ExpressRoute all'Edge della rete Microsoft.
  
> [!CAUTION]
> **La connettività tra Skype for Business client nella rete aziendale a servizi Microsoft 365 o Office 365 deve soddisfare i requisiti e le soglie di prestazioni di rete seguenti.**

|**Metrica** <br/> |**Target** <br/> |
|:-----|:-----|
|Latenza (unidiret.  <br/> |< 50 ms  <br/> |
|Latenza (RTT o Tempo di andata e ritorno)  <br/> |< 100 ms  <br/> |
|Perdita di pacchetti burst  <br/> |<10% durante qualsiasi intervallo di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |<1% durante qualsiasi intervallo di 15s  <br/> |
|Instabilità tra i pacchetti  <br/> |<30 ms durante qualsiasi intervallo di 15s  <br/> |
|Riordino pacchetti  <br/> |<pacchetti non in ordine dello 0,05%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- La rete Microsoft ha più di 160 posizioni edge in tutto il mondo. Microsoft lavora con i principali provider di servizi Internet (ISP) di tutto il mondo tramite questi siti edge. L'obiettivo della metrica di latenza presuppone che il sito o i siti dell'azienda e Microsoft Edges siano nello stesso continente.
    
- Il sito o i siti aziendali alla connessione Edge di rete Microsoft includono l'accesso alla rete first hop, che può essere WiFi o un'altra tecnologia wireless. 
    
- L'obiettivo delle prestazioni di rete presuppone la corretta pianificazione della larghezza di banda e/o della qualità del servizio. In altre parole, si applica direttamente al traffico Skype for Business Real-Time multimediale quando la connessione di rete è sotto un carico di punta.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisiti di prestazioni di rete dalla rete Perimetrale a Microsoft Network Edge
<a name="bkYourNetworkEdge"> </a>

Di seguito sono riportati gli obiettivi o le soglie delle prestazioni di rete necessari per la connessione tra l'edge della rete e l'edge della rete Microsoft. Questo segmento della rete esclude la rete interna del cliente o la WAN ed è inteso come guida per testare il traffico di rete inviato tramite Internet o tramite una rete partner ExpressRoute e può essere usato anche durante la negoziazione di un contratto di servizio (SLA) sulle prestazioni con il provider ExpressRoute.
  
> [!CAUTION]
> **La connettività tra l'edge della rete aziendale e l'edge della rete Microsoft deve soddisfare i requisiti e le soglie di prestazioni di rete seguenti.**

|**Metrica** <br/> |**Target** <br/> |
|:-----|:-----|
|Latenza (unidiret.  <br/> |< 30 ms  <br/> |
|Latenza (RTT)  <br/> |< 60 ms  <br/> |
|Perdita di pacchetti burst  <br/> |<1% durante qualsiasi intervallo di 200 ms  <br/> |
|Perdita di pacchetti  <br/> |<0,1% durante qualsiasi intervallo di 15s  <br/> |
|Instabilità tra i pacchetti  <br/> |<15 ms durante qualsiasi intervallo di 15s  <br/> |
|Riordino pacchetti  <br/> |<pacchetti non in ordine dello 0,01%  <br/> |
   
 **Altri requisiti di destinazione delle prestazioni:**
  
- L'obiettivo delle prestazioni richiede la connessione tra una rete perimetrale della tua azienda e la rete Microsoft Edge più vicina, per essere nello stesso continente.
    
- L'obiettivo delle prestazioni di rete presuppone la corretta pianificazione della larghezza di banda e/o della qualità del servizio. Questo vale anche per Skype for Business Real-Time traffico multimediale quando la connessione di rete è sotto un carico di punta. Per una corretta pianificazione della larghezza di banda e della QoS, vedere ExpressRoute e [QoS in Microsoft Teams](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
    
## <a name="measuring-network-performance"></a>Misurazione delle prestazioni di rete
<a name="bkNetworkPerf"> </a>

Per misurare le effettive prestazioni di rete, in particolare per la latenza e la perdita di pacchetti, da qualsiasi sito di rete aziendale a un edge di rete, è possibile usare strumenti come ping, test su un set di servizi di inoltro multimediale di Skype for Business in esecuzione dai siti di Microsoft Edge e data center. 

>[!NOTE]
> La misurazione delle prestazioni di rete tramite ping (ICMP) non è efficace. Per questo motivo, l'ip anycast esposto di seguito smetterà di rispondere alle richieste ICMP a partire da gennaio 2020. Per misurare le prestazioni della rete in modo efficace, Microsoft consiglia lo [strumento Network Assesment Tool.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Per testare le connessioni Internet alla rete Microsoft, è consigliabile testare i VIP seguenti dei Skype for Business multimediali. *L'indirizzo VIP Anycast* si risolverà in un indirizzo IP di media relay in un sito Edge di rete Microsoft più vicino alla posizione di test.
  

|**Indirizzo IP** <br/> |**Tipo** <br/> |**Posizione** <br/>|
|:-----|:-----|:-----|
|13.107.8.2  <br/> |VIP  <br/> |Ip Anycast a livello mondiale  <br/> |
   
 **Ecco alcuni consigli di alto livello da seguire per valutare le prestazioni di rete:**
  
- È consigliabile valutare la rete interna e le connessioni a Microsoft 365 o Office 365.
    
- È consigliabile valutare e raccogliere dati per tutte le reti per un lungo periodo di tempo. È consigliabile eseguire i test delle prestazioni di rete per un minimo di una settimana, in modo da visualizzare i modelli di utilizzo per tutti i giorni e le ore lavorative. Questo ti mostrerà gli orari di punta.
    
- È consigliabile eseguire più campioni di misurazioni delle prestazioni di rete. È consigliabile eseguire una misurazione ogni 10 minuti da un sito aziendale per l'intero periodo di tempo in cui si stanno raccogliendo i dati. Per confrontare i requisiti Microsoft Teams prestazioni di rete, prendere il valore di misura del 90° percentile da questo set di dati di esempio. 
    
- È consigliabile valutare continuamente le prestazioni della rete. L'utilizzo della rete varia nel tempo a causa delle modifiche al modello di utilizzo, alle nuove applicazioni basate sull'organizzazione che usano una grande quantità di larghezza di banda e alle modifiche alle posizioni aziendali o fisiche dell'organizzazione. È importante monitorare continuamente le prestazioni della rete in base a questi requisiti e obiettivi/soglie delle prestazioni di rete e apportare modifiche in tempo reale per garantire la qualità Real-Time multimediale ottimale. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Misurazione delle prestazioni di rete con le vm di Azure
<a name="bkNetworkPerf"> </a>

Invece di testare i siti Edge della rete Microsoft, sono disponibili soluzioni di valutazione di rete di clienti e partner di Skype for Business che usano la configurazione di test per i servizi nel cloud Microsoft Azure rete. In queste soluzioni, gli strumenti di valutazione della rete testano la latenza, la perdita di pacchetti e l'instabilità rispetto agli endpoint personalizzati impostati come servizio nel cloud di Azure. Di conseguenza, il traffico di rete di prova attraversa un altro segmento di rete, ovvero la connessione all'interno della rete Microsoft tra i bordi della rete e i data center di Azure che ospita il servizio di valutazione della rete.
  
Per queste soluzioni di valutazione della rete basate sui servizi di test ospitati in Azure. È consigliabile eseguire la valutazione della rete all'interno del paese e/o dell'area geografica. Ad esempio, per i siti dei clienti negli Stati Uniti orientali, la valutazione deve essere eseguita su un'istanza del servizio di test ospitata nell'area del data center degli Stati Uniti orientali di Azure. 
  
Di seguito sono riportati gli obiettivi di latenza (RTT) per la configurazione della valutazione della rete basata su servizi di Azure. Gli obiettivi di latenza unidirettiva saranno la metà degli obiettivi RTT corrispondenti. Gli obiettivi di perdita e instabilità dei pacchetti rimangono gli stessi definiti per i test basati Skype Media Relay.
  


|**Area geografica del cliente** <br/> |**Area geografica di Azure** <br/> |**Edge della rete - Tempo di round trip di Azure (RTT)** <br/> |**Il tuo sito - Tempo di round trip di Azure (RTT)** <br/> |
|:-----|:-----|:-----|:-----|
|Stati Uniti centrali  <br/> |Stati Uniti centrali  <br/> |99  <br/> |139  <br/> |
|Stati Uniti orientali  <br/> |Stati Uniti orientali  <br/> |86  <br/> |126  <br/> |
|Stati Uniti centro-settersi  <br/> |Stati Uniti centro-settersi  <br/> |97  <br/> |137  <br/> |
|Stati Uniti centro-meridionali  <br/> |Stati Uniti centro-meridionali  <br/> |94  <br/> |134  <br/> |
|Stati Uniti occidentali  <br/> |Stati Uniti occidentali  <br/> |94  <br/> |134  <br/> |
|Hawaii Stati Uniti  <br/> |Stati Uniti occidentali  <br/> |116  <br/> |156  <br/> |
|Canada Centrale  <br/> |Canada Centrale  <br/> |138  <br/> |178  <br/> |
|Canada est  <br/> |Canada est  <br/> |131  <br/> |171  <br/> |
|Nord Europa  <br/> |Nord Europa  <br/> |99  <br/> |139  <br/> |
|Europa occidentale  <br/> |Europa occidentale  <br/> |95  <br/> |135  <br/> |
|Asia orientale  <br/> |Asia orientale  <br/> |118  <br/> |158  <br/> |
|Asia sudorientale  <br/> |Asia sudorientale  <br/> |97  <br/> |137  <br/> |
|Giappone orientale  <br/> |Giappone orientale  <br/> |111  <br/> |151  <br/> |
|Giappone occidentale  <br/> |Giappone occidentale  <br/> |118  <br/> |158  <br/> |
|Brasile sud  <br/> |Brasile sud  <br/> |70  <br/> |110  <br/> |
|Australia Orientale  <br/> |Australia Orientale  <br/> |124  <br/> |164  <br/> |
|Australia sud-orientale  <br/> |Australia sud-orientale  <br/> |124  <br/> |164  <br/> |
|India centrale  <br/> |India centrale  <br/> |103  <br/> |143  <br/> |
|India meridionale  <br/> |India meridionale  <br/> |103  <br/> |143  <br/> |
|India occidentale  <br/> |India occidentale  <br/> |103  <br/> |143  <br/> |
|Cina orientale  <br/> |Cina orientale  <br/> |120  <br/> |160  <br/> |
|Cina nord  <br/> |Cina nord  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualità multimediale ed ExpressRoute
<a name="bkNetworkPerf"> </a>

Azure ExpressRoute per Microsoft 365 o Office 365 è una connessione di rete dedicata per la connessione a Microsoft 365 o Office 365. Offre ai clienti la possibilità di avere il controllo sul percorso del traffico di rete. Non devono più preoccuparsi del routing imprevedibile che si verifica su Internet in cui i dati vengono trasportati da gestori, provider e ISP sconosciuti. Il traffico di rete inviato tramite ExpressRoute viene inviato direttamente attraverso la rete del partner ExpressRoute alla rete Microsoft. In questo modo i clienti possono Microsoft 365 o Office 365 come se si trova nel proprio data center fuori sede con una connessione dedicata.
  
Azure ExpressRoute è disponibile per tutte le Microsoft 365 e Office 365 licenze. Tuttavia, il componente aggiuntivo Azure ExpressRoute Premium è necessario Microsoft 365 e Office 365 per abilitare il routing globale. I clienti con almeno 500 postazioni che implementano ExpressRoute possono ottenere il componente aggiuntivo *ExpressRoute* Premium senza costi aggiuntivi.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute è necessario per una buona qualità multimediale?

Azure ExpressRoute non è un requisito per ottenere la qualità dei supporti Microsoft Teams ottimale. Si tratta, tuttavia, di una delle opzioni di distribuzione che consentono di assicurarsi che la connettività cloud soddisfi i Skype for Business di prestazioni di rete o le soglie.
  
Microsoft 365 e Office 365 sono servizi ad alte prestazioni e sicuri che usano Internet. Continuiamo a investire in nuove funzionalità di sicurezza e in nodi edge locali per migliorare continuamente la sicurezza e le prestazioni. Azure ExpressRoute non è un requisito per Microsoft 365 o Office 365 servizi, inclusi Microsoft Teams. Azure ExpressRoute è una delle opzioni di distribuzione disponibili che consentono di verificare che la connettività a Microsoft 365 o Office 365 soddisfi i requisiti di prestazioni di rete di Skype for Business e garantisca l'esperienza di qualità multimediale Microsoft Teams ottimale.
  
Per la qualità dei supporti multimediali di [Microsoft Teams,](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) è importante che la connessione tra i siti aziendali e i bordi della rete Microsoft soddisfi gli obiettivi di prestazioni nei requisiti di prestazioni di rete da un client Skype for Business a Microsoft Network Edge e che la connessione tra i bordi della rete e i bordi della rete Microsoft soddisfi gli obiettivi di prestazioni nei requisiti di prestazioni di rete dall'edge di rete all'edge della rete [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
È anche importante che la connettività di rete fisica dell'azienda, inclusa la rete interna e la capacità di connettività cloud, supportino il volume di traffico multimediale di punta. Azure ExpressRoute è uno dei molti modi che consentono ai clienti di garantire che la Microsoft Teams cloud soddisfi tutti questi requisiti di prestazioni.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute è necessario per il contratto di servizio sulla qualità vocale?

No, ExpressRoute non è necessario per il contratto di servizio Microsoft Teams qualità vocale. Il [contratto di](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) servizio qualità vocale di Microsoft Teams si applica a qualsiasi chiamata idonea da parte di qualsiasi utente del servizio vocale Microsoft Teams all'interno della licenza e dell'abbonamento corretti che consente all'utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. Un contratto di servizio sulla qualità vocale deve includere che siano soddisfatte tutte le condizioni seguenti:
  
- Chiamate da telefoni IP certificati Microsoft.
    
- Connessioni Ethernet cablate.
    
- Problemi di qualità vocale a causa di problemi di Rete Microsoft.
    
> [!NOTE]
> Il contratto di servizio sulla qualità vocale esclude le chiamate in cui la bassa qualità delle chiamate è causata da problemi nelle reti non Microsoft, inclusi i partner ExpressRoute e altre reti. 
  
### <a name="internet-or-azure-expressroute"></a>Internet o Azure ExpressRoute?

Prima di prendere una decisione sulle opzioni di connettività di rete per Microsoft Teams, i clienti devono valutare la propria rete e la connettività Internet corrente in base ai requisiti di prestazioni di rete descritti in Requisiti di prestazioni di rete per connettersi [a Microsoft Teams](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se le prestazioni di rete sulla connessione Internet corrente sono impostate per una capacità sufficiente durante l'orario di punta e soddisfano i requisiti di prestazioni di rete dai siti ai bordi della rete Microsoft e dai bordi della rete a Microsoft Network Edges, è possibile continuare a usare la connettività Internet esistente per connettersi a Microsoft Teams.
  
Per i siti aziendali in cui i requisiti di prestazioni di rete non vengono soddisfatti, è consigliabile collaborare con i provider di servizi di rete esistenti per migliorare le prestazioni generali della rete. Tuttavia, se non vengono ancora soddisfatte, l'uso di Azure ExpressRoute consente di verificare che la connettività cloud Microsoft Teams di rete sia utile per soddisfare i requisiti di prestazioni di rete.
  
Azure ExpressRoute offre i vantaggi aggiuntivi seguenti:
  
- Contratto di servizio sulla disponibilità della connessione tra la rete e la rete Microsoft. ExpressRoute ha un contratto di servizio disponibilità garantito del 99,9%.
    
- Larghezza di banda pianificata e garantita necessaria Microsoft 365 e Office 365 servizi. A questo scopo, è possibile inviare solo il traffico Microsoft 365, Office 365 o Skype for Business usando ExpressRoute e quindi fare in modo che tutto il traffico Internet superi altri punti di uscita/ingresso Internet per la rete.
    
- ExpressRoute è progettato per mantenere i contrassegni QoS DSCP tra la rete e la rete Microsoft.
    
Per altre informazioni sul QoS di ExpressRoute e sulla pianificazione della capacità, vedere ExpressRoute e [QoS in Microsoft Teams](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-set-up-azure-expressroute-for-microsoft-teams-only"></a>È possibile configurare Azure ExpressRoute solo per Microsoft Teams utenti?

Sì, è possibile configurare Azure ExpressRoute per garantire un'eccellente connettività di rete dalla rete aziendale solo a Microsoft Teams. In questo modo gli utenti Real-Time la qualità ottimale dei supporti multimediali, ma è possibile continuare a connettersi ad altri servizi di Microsoft 365 o Office 365 su Internet.
  
Il protocollo BGP (Border Gateway Protocol) è un protocollo di routing su Internet usato per instradare il traffico di rete attraverso Internet. È progettato per scambiare informazioni di routing tra sistemi autonomi (AS) presenti su Internet. I valori delle community BGP sono tag di attributo che possono essere applicati alle route in arrivo o in uscita. Le community BGP vengono spesso usate per segnalare all'AS ricevente quale collegamento in uscita usare per raggiungere una determinata destinazione in base alla geografia, al tipo di servizio o ad altri criteri.
  
Con il supporto delle community BGP, Microsoft contrassegnerà i prefissi e le route con i valori appropriati della community BGP in base al servizio a cui appartengono. Microsoft contrassegnerà i prefissi annunciati tramite peering pubblico e peering Microsoft con valori appropriati della community BGP che indicano l'area in cui sono ospitati i prefissi. È possibile fare affidamento sui valori della community per prendere decisioni di routing appropriate per offrire un routing ottimale. È possibile usare il valore Microsoft Teams community BGP per configurare una connessione ExpressRoute solo per Microsoft Teams. Per altre informazioni, vedere Requisiti di [routing di ExpressRoute.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-microsoft-teams"></a>Scenari di connettività ExpressRoute per Microsoft Teams
<a name="bkNetworkPerf"> </a>

Se si è deciso che ExpressRoute in base ai suggerimenti indicati in precedenza è quello che si desidera, ecco i consigli su dove e quante connessioni ExpressRoute è consigliabile ottenere.
  
### <a name="online-only-deployment---single-site"></a>Distribuzione solo online - Singolo sito

Se tutti gli utenti usano il servizio Microsoft Teams e se gli uffici sono centrati su un'unica posizione fisica e si decide di distribuire Azure ExpressRoute, è consigliabile configurare una singola connessione ExpressRoute tra il sito dell'azienda e la posizione di [peering ExpressRoute](/azure/expressroute/expressroute-locations)più vicina.
  
L'immagine seguente mostra un esempio di questo tipo di distribuzione. Per questo esempio, Contoso è un'università situata a Orlando, FL. Contoso ha 10.000 docenti e studenti. I test Internet dalla loro posizione ai siti Microsoft Edge hanno mostrato una perdita di pacchetti superiore al 5% durante le ore di punta della classe. Hanno deciso di ottenere una connessione dedicata a Microsoft 365 o Office 365 usando ExpressRoute con larghezza di banda di cui è stato eseguito il provisioning in modo da evitare la congestione di rete per Microsoft 365 o Office 365 in particolare per il traffico Microsoft Teams Real-Time. Si connettono al cloud Microsoft tramite ExpressRoute nel sito di Atlanta, GA MeetMe.
  
![Sito singolo ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Distribuzione solo online - Più siti nello stesso continente

Se l'azienda usa i servizi Microsoft Teams di più uffici nella stessa area geografica o continente ed è stato scelto di implementare Azure ExpressRoute, è consigliabile connettere il sito principale tramite ExpressRoute e quindi, facoltativamente, aggiungere ulteriore peering ExpressRoute per altre posizioni che non soddisfano gli obiettivi di prestazioni di rete consigliati.
  
Nell'esempio seguente Contoso è una società di servizi di viaggio statunitense con sede a New York ma con altri uffici negli Stati Uniti. I loro uffici sono interconnessi tramite una WAN che usa MPLS per la connessione a Microsoft 365 o Office 365. Inizialmente configurano una connessione ExpressRoute dal router Internet di Hoboken, nel New Jersey, al sito MeetMe di New York. 
  
Con questa configurazione, il traffico di rete dalla maggior parte dei siti al sito Microsoft Network (New York Edge) può soddisfare gli obiettivi di prestazioni della connessione client di Skype for Business descritti in Requisiti di prestazioni di rete da un client di Skype for Business a [Microsoft Network Edge.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Tuttavia, la latenza tra gli uffici della costa occidentale di Contoso e New York è superiore a 50 ms a senso unico. Inoltre, Honolulu è il secondo ufficio più grande per Contoso, la latenza da Honolulu a New York supera gli 80 ms a senso unico. Per garantire una buona qualità dei supporti multimediali per gli utenti di questi uffici, Contoso ha deciso di aggiungere una connessione ExpressRoute sulla costa occidentale tra il sito di San Jose e il sito MeetMe di Silicon Valley ExpressRoute.
  
![Express Router Multi-site nello stesso continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Distribuzione solo online - Più siti in continenti diversi

Se tutti gli utenti usano il servizio Microsoft Teams e se gli uffici sono in più posizioni fisiche in più continenti, se si decide di distribuire Azure ExpressRoute, è consigliabile configurare almeno una connessione ExpressRoute per ogni continente tra il sito principale di ogni continente e la posizione di [peering ExpressRoute](/azure/expressroute/expressroute-locations)più vicina. A seconda dei costi e dei vantaggi, è possibile scegliere di distribuire altre connessioni ExpressRoute da siti in cui gli obiettivi di prestazioni di rete non sono soddisfatti.
  
Nell'esempio seguente Contoso è un grande studio legale aziendale con uffici nelle principali città del Nord America e dell'Europa. In base alla connessione Internet e alla valutazione delle prestazioni della rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo circuito ExpressRoute per tutti gli uffici europei.
  
![ExpressRoute con più siti e continenti.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Distribuzione ibrida

Se si ha una distribuzione di Lync o Microsoft Teams locale e si sceglie di implementare un'integrazione ibrida di Microsoft Teams, è consigliabile che se si decide di distribuire Azure ExpressRoute, è necessario avere almeno una connessione ExpressRoute per ogni sito Lync o edge di Microsoft Teams locale e almeno una connessione ExpressRoute per ogni continente con uffici. A seconda dei costi e dei vantaggi, per ogni continente è possibile scegliere di distribuire altre connessioni ExpressRoute da uffici in cui gli obiettivi di prestazioni di rete non vengono soddisfatti.
  
Se si ha una distribuzione locale Microsoft Teams distribuzione, è necessario seguire la Guida alla pianificazione e alla distribuzione dei [server perimetrali.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) In particolare, i server perimetrali devono essere raggiungibili dall'esterno della rete. Questa operazione viene in genere ottenuta assegnando un indirizzo IP pubblico instradabile al server perimetrale o usando nat (Network Address Translation).
  
Nell'esempio seguente Contoso ha una distribuzione locale Microsoft Teams VoIP aziendale locale. Vogliono eseguire la migrazione degli utenti locali a Microsoft 365 o Office 365 online. Hanno anche deciso di usare una distribuzione ibrida in modo che possano continuare a usare l'infrastruttura PSTN esistente per tutti gli utenti locali e online. Il data center e i server perimetrali locali di Contoso Skype for Business server perimetrali sono a Chicago. Per la distribuzione, Contoso ha deciso di configurare una connessione ExpressRoute tra il data center di Chicago e Chicago ExpressRoute. Hanno anche aggiunto una connessione ExpressRoute sulla costa occidentale per servire meglio il loro ufficio di Honolulu.
  
![ExpressRoute Ibrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Distribuzione online con Cloud Connector Edition

Skype for Business Cloud Connector Edition è un'offerta ibrida costituita da un set di macchine virtuali (VM) in pacchetto che implementano la connettività PSTN locale. Distribuendo una topologia di Skype for Business Server minima in un ambiente virtualizzato, sarà possibile inviare e ricevere chiamate con telefoni fissi e telefoni cellulari tramite l'infrastruttura vocale PSTN locale esistente.
  
Se si decide di distribuire Azure ExpressRoute e Cloud Connector Edition, è consigliabile configurare almeno una connessione Express Route per ogni continente tra il sito principale di ogni continente e la posizione di [peering ExpressRoute](/azure/expressroute/expressroute-locations)più vicina. A seconda dei costi e dei vantaggi, per ogni continente è possibile scegliere di distribuire altre connessioni ExpressRoute da siti in cui gli obiettivi di prestazioni di rete non vengono soddisfatti.
  
Se si ha una distribuzione locale Microsoft Teams, è necessario seguire la Guida alla pianificazione [per](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)Skype for Business Cloud Connector Edition . In particolare, ai servizi Access Edge e A/V Edge devono essere assegnati indirizzi IP pubblici e Microsoft 365 o Office 365 data center.
  
Nell'esempio seguente Contoso è una società di contabilità europea con presenza in alcuni dei principali paesi e città europei. Quando si indosseranno a Microsoft Teams per tutte le loro esigenze di collaborazione, hanno deciso di creare un Connettore Cloud per ogni paese in cui hanno una posizione fisica in cui continuare a usare l'infrastruttura PSTN e i contratti del gestore già esistenti. In base ai test emersi da tutti i siti e dall'Edge della rete Microsoft, hanno stabilito che una singola connessione ExpressRoute a Londra aiuterà a soddisfare gli obiettivi di prestazioni della rete di connessione client di Microsoft Teams descritti in Requisiti di prestazioni di rete da un [client Skype for Business a Microsoft Network Edge.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Di seguito è riportata un'altra opzione di distribuzione per Contoso. In questo caso, hanno deciso di configurare una connessione ExpressRoute in ogni sito in cui è distribuito un connettore Cloud. 
  
![ExpressRoute Cloud Connector Due.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Argomenti correlati

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)

  
