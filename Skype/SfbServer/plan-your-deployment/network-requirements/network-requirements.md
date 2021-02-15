---
title: Pianificare i requisiti di rete per Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Riepilogo: esaminare le considerazioni sui componenti di rete riportate di seguito prima di implementare Skype for Business Server.'
ms.openlocfilehash: 0b5d183ecc11d09569427e432121fab7de8f401b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834356"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Pianificare i requisiti di rete per Skype for Business

**Riepilogo:** Prima di implementare Skype for Business Server, leggere le considerazioni sui componenti di rete riportate di seguito.

Le informazioni contenute in questi argomenti sono descritte anche nel white paper [Pianificazione,](https://www.microsoft.com/download/details.aspx?id=39084) monitoraggio e risoluzione dei problemi di rete con Lync Server con ulteriori dettagli e informazioni dettagliate. Anche se il contenuto fa riferimento esplicitamente a Lync 2010 e Lync 2013, le considerazioni per Skype for Business Server sono invariate.

Allo stesso modo, se la rete prevede l'accesso wi-fi e cablato, il white paper Che fornisce [Lync 2013 Real-Time Communications over Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) è un buon riferimento ed è ugualmente applicabile a Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware dei server
<a name="S_hard"> </a>

La scheda di rete di ogni server nella topologia di Skype for Business Server deve supportare almeno 1 gigabit al secondo (Gbps). In generale, è consigliabile connettere tutti i ruoli del server all'interno della topologia di Skype for Business Server utilizzando una latenza bassa e una rete LAN (Local Area Network) a larghezza di banda elevata. Le dimensioni della rete LAN dipendono dalle dimensioni della topologia:

- Nelle topologie Standard Edition i server devono essere in una rete che supporta Ethernet da 1 Gbps o equivalente.

- Nelle topologie Enterprise Edition la maggior parte dei server deve essere in una rete che supporta più di 1 Gbps, soprattutto quando si supportano conferenze audio/video (A/V) e la condivisione di applicazioni.

È possibile supportare l'integrazione della rete PSTN (Public Switched Telephone Network) utilizzando linee T1/E1 o il trunking SIP.

## <a name="audiovideo-network-requirements"></a>Requisiti di rete audio/video
<a name="AV_req"> </a>

I requisiti di rete per audio/video (A/V) in una distribuzione di Skype for Business Server includono:

- Se si distribuisce un singolo server perimetrale o un pool di server perimetrali utilizzando il bilanciamento del carico DNS, è possibile configurare il  _firewall_ esterno per eseguire nat (Network Address Translation). Non è possibile configurare il firewall interno _per_ l'esecuzione di NAT. Per informazioni dettagliate, vedere [Pianificazione di porte e firewall.](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning)

    > [!IMPORTANT]
    > Se si dispone di un pool di server perimetrali e si utilizza un servizio di bilanciamento del carico hardware, è necessario utilizzare indirizzi IP pubblici nei server perimetrali e non è possibile utilizzare NAT per i server o il pool nel dispositivo compatibile con NAT, ad esempio un dispositivo firewall o un commutatore LAN. Per informazioni dettagliate, vedere [Scenari di server perimetrali in Skype for Business Server.](../edge-server-deployments/scenarios.md)

- Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente.

- Se si utilizza IPSec (Internet Protocol security), è consigliabile disabilitarlo per gli intervalli di porte usati per il traffico A/V. Per informazioni dettagliate, vedere [Eccezioni IPsec.](#ipsec-exceptions)

Per garantire una qualità multimediale ottimale, eseguire le operazioni seguenti:

- Effettuare il provisioning dei collegamenti di rete per supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 Kbps per flusso video, se abilitati, durante i periodi di utilizzo di picco. Una sessione audio o video bidiredireibile usa due flussi, quindi una semplice connessione audio/telefono richiederà 130 KBps per coprire ogni flusso. Il video utilizzerà allo stesso modo un totale di 1000 Kbps per ottenere una connessione a monte e a valle.

- Per far fronte a picchi imprevisti del traffico e a un aumento dell'utilizzo nel tempo, gli endpoint multimediali di Skype for Business Server possono adattarsi a diverse condizioni di rete e supportare una velocità effettiva tre volte superiore per audio e video mantenendo comunque una qualità accettabile. Non presupporre che questa adattabilità maschera il problema in caso di sotto-provisioning di una rete. In una rete con provisioning ridotto, la capacità degli endpoint multimediali di Skype for Business Server di gestire dinamicamente diverse condizioni di rete (ad esempio, una perdita temporanea di pacchetti elevata) è ridotta.

- Per i collegamenti di rete in cui il provisioning è molto diss costoso e difficile, potrebbe essere necessario prendere in considerazione il provisioning per un volume di traffico inferiore. In questo scenario, lasciare che l'elasticità degli endpoint multimediali di Skype for Business Server assrbisi la differenza tra il volume di traffico e il livello di traffico di picco, con il costo di una certa riduzione della qualità vocale. Inoltre, ci sarà una diminuzione della sala riunioni altrimenti disponibile per assorbire picchi improvvisi del traffico.

- Per i collegamenti di cui non è possibile eseguire correttamente il provisioning a breve termine (ad esempio, un sito che utilizza collegamenti WAN molto scadenti), è consigliabile disabilitare il video per determinati utenti.

- Effettuare il provisioning della rete per garantire un ritardo end-to-end massimo (latenza) di 150 millisecondi (ms) in condizioni di carico di picco. La latenza è l'unico problema di rete che i componenti multimediali di Skype for Business Server non possono ridurre ed è importante trovare ed eliminare i punti deboli.

- Per i server che eseguono software antivirus, includere tutti i server che eseguono Skype for Business Server nell'elenco delle eccezioni per fornire prestazioni ottimali e qualità audio.

## <a name="ipsec-exceptions"></a>Eccezioni IPsec

Per le reti aziendali in cui è stato distribuito IPsec (Internet Protocol Security) (vedere IETF RFC 4301-4309), è necessario disabilitare tale protocollo per l'intervallo delle porte utilizzate per l'invio del traffico audio, video e panorama video. Questa richiesta nasce dall'esigenza di evitare ritardi nell'allocazione delle porte multimediali a causa della negoziazione IPsec.

Nella tabella riportata di seguito vengono illustrate le impostazioni di eccezione IPsec consigliate.

**Eccezioni IPsec consigliate**

|Nome regola |IP origine |IP destinazione |Protocollo |Porta origine |Porta destinazione |Requisito di autenticazione |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V Edge Server in ingresso interno|Qualsiasi  |A/V Edge Server interno|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|A/V Edge Server in ingresso esterno|Qualsiasi  |A/V Edge Server esterno|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|A/V Edge Server interno in uscita|A/V Edge Server interno  |A/V Edge Server esterno |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|A/V Edge Server esterno in uscita|A/V Edge Server esterno |Qualsiasi |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Mediation Server in ingresso|Qualsiasi  |Mediation Server |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Mediation Server in uscita|Mediation Server  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Operatore Conferenza in ingresso|Qualsiasi  |Front End Server con Operatore Conferenza |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Operatore Conferenza in uscita|Front End Server con Operatore Conferenza  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|A/V Conferencing Server in ingresso|Qualsiasi|Front End Server|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|A/V Conferencing in uscita|Front End Server|Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Exchange in ingresso|Qualsiasi|Messaggistica unificata di Exchange|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Server di condivisione applicazioni in ingresso|Qualsiasi|Server di condivisione applicazioni|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Server di condivisione applicazioni in uscita|Server di condivisione applicazioni| Qualsiasi |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Exchange in uscita|Messaggistica unificata di Exchange|Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Client| Qualsiasi  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisiti di rete per le conferenze
<a name="Conf_req"> </a>

La larghezza di banda utilizzata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto. È possibile scegliere di monitorare l'utilizzo effettivo e modificare di conseguenza la pianificazione della larghezza di banda.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale
<a name="Conf_req"> </a>

Una parte importante della pianificazione della rete è garantire che la rete sia in grado di gestire il traffico multimediale generato da Skype for Business Server. Questa sezione fornisce supporto alla pianificazione per il traffico multimediale.

### <a name="media-traffic-network-usage"></a>Utilizzo della rete per il traffico multimediale
<a name="Net_req"> </a>

L'utilizzo della larghezza di banda per il traffico multimediale può essere difficile da calcolare per la quantità di variabili diverse, ad esempio l'utilizzo di codec, la risoluzione e i livelli di attività. L'utilizzo della larghezza di banda è una funzione del codec utilizzato e dell'attività del flusso, che può variare a seconda degli scenari. Nella tabella seguente sono elencati i codec audio utilizzati in genere negli scenari di Skype for Business Server.

**Larghezza di banda del codec audio**

|**Codec audio**|**Scenario**|**Velocità in bit del payload audio (KBPS)**|**Larghezza di banda solo per payload audio e intestazione (Kbps)**|**Larghezza di banda per payload audio, intestazione IP, UDP, RTP e SRTP (Kbps)**|**Larghezza di banda per payload audio, intestazione IP, UDP, RTP, SRTP e correzione degli errori di inoltro (FEC) (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda larga RTAudio  <br/> |Peer-to-peer  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda stretta RTAudio  <br/> |Peer-to-peer PSTN  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferenze  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|G.722 Stereo  <br/> |Conferenze peer-to-peer  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Servizi di conferenza  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferenze  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|BANDA LARGA DI TASER  <br/> |Peer-to-peer  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|BANDA LARGA DI TASER  <br/> |Peer-to-peer  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|BANDA LARGA DI TASER  <br/> |Peer-to-peer  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|BANDA LARGA/banda stretta DISAS  <br/> |Peer-to-peer  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> Le chiamate PSTN dal client Skype for Business in genere utilizzano il codec G.711, che richiede una larghezza di banda elevata. Se non è disponibile una larghezza di banda sufficiente per il codec, le chiamate possono avere esito negativo con un errore simile al seguente nei registri multimediali: almeno un codec deve essere **abilitato, hr: c0042004**. I log multimediali (file con estensione blog) sono crittografati e possono essere decodificati solo dal personale di supporto Microsoft.

I numeri della larghezza di banda nella tabella precedente si basano su pacchetti di 20 ms (50 pacchetti al secondo) e per i codec Siren e G.722 includono l'overhead SRTP (Secure Real-Time Transport Protocol) aggiuntivo dagli scenari di conferenza e presuppongono che il flusso sia attivo al 100%. La correzione degli errori in avanti (FEC, Forward Error Correction) viene utilizzata in modo dinamico in caso di perdita di pacchetti nel collegamento per mantenere la qualità del flusso audio.

La versione stereo del codec G.722 viene utilizzata dai sistemi basati su Lync Room System, che utilizza un singolo microfono stereo o una coppia di microfoni mono per consentire agli ascoltatori di distinguere meglio più altoparlanti nella sala riunioni.

**Larghezza di banda della risoluzione video**

|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit massima del payload video (Kbps)**|**Velocità in bit minima del payload video (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Il codec predefinito per il video è lo standard H.264/MPEG-4 Part 10 Advanced Video Coding, insieme alle estensioni scalabili per la codifica video per la scalabilità temporale. Per mantenere l'interoperabilità con i client legacy, il codec RTVideo viene ancora utilizzato per le chiamate peer-to-peer tra Skype for Business Server e i client legacy. Nelle sessioni di conferenza con Skype for Business Server e client legacy, l'endpoint di Skype for Business Server può codificare il video utilizzando entrambi i codec video e inviare il flusso di bit H.264 ai client Skype for Business Server e il flusso di bit RTVideo ai client legacy.

La larghezza di banda necessaria dipende dalla risoluzione, dalla qualità, dalla frequenza dei fotogrammi e dalla quantità di movimento o modifica dell'immagine. Per ogni risoluzione, sono disponibili due velocità in bit pertinenti:

- **Velocità in bit massima payload** Questa è la velocità in bit che verrà utilizzata da un endpoint per la risoluzione alla frequenza massima dei fotogrammi. Questo è il valore che consente la massima qualità video e audio.

- **Velocità in bit minima del payload** Questa è la velocità in bit al di sotto della quale un endpoint di Skype for Business Server passa alla risoluzione inferiore successiva. Per garantire una determinata risoluzione, la velocità in bit del payload video disponibile non deve essere inferiore a questa velocità in bit minima per tale risoluzione. Questo valore consente di comprendere il valore più basso possibile se la velocità in bit massima non è disponibile o pratica. Per alcuni utenti, un video con velocità in bit così bassa potrebbe offrire un'esperienza video inaccettabile, quindi usa attenzione con queste velocità in bit minime del payload video. Si noti che per le scene video statiche e immutate la velocità in bit effettiva potrebbe essere temporaneamente inferiore alla velocità in bit minima.

Skype for Business Server supporta molte risoluzioni. Ciò consente a Skype for Business Server di adattarsi alla larghezza di banda di rete e alle funzionalità client di ricezione diverse. Le proporzioni predefinite per Skype for Business Server sono 16:9. Le proporzioni 4:3 legacy sono ancora supportate per le webcam che non consentono l'acquisizione nelle proporzioni 16:9.

Il video FEC è sempre incluso nella velocità in bit del payload video quando viene usato, quindi non ci sono valori separati per feC video e senza FEC video.

Gli endpoint non inviano flussi continui di pacchetti audio o video. A seconda dello scenario, esistono livelli diversi di attività di flusso che indicano la frequenza dell'invio di pacchetti per un flusso. L'attività di un flusso dipende dal contenuto multimediale e dallo scenario e non dal codec utilizzato. In uno scenario peer-to-peer:

- Gli endpoint inviano flussi audio solo quando gli utenti parlano.

- Entrambi i partecipanti ricevono flussi audio.

- Se si usa il video, entrambi gli endpoint inviano e ricevono flussi video durante la chiamata.

- Per le scene video statiche, la velocità in bit effettiva potrebbe essere temporaneamente molto bassa perché il codec video ignora le aree di codifica del video senza alcuna modifica rispetto all'esempio precedente.

In uno scenario di conferenza:

- Gli endpoint inviano flussi audio solo quando l'utente parla.

- Tutti i partecipanti ricevono flussi audio.

- Se è utilizzato il video, tutti i partecipanti possono ricevere fino a cinque flussi video, e un flusso video panoramico (ad esempio, con proporzioni 20:3). Per impostazione predefinita, i cinque flussi video di ricezione si basano sulla cronologia dell'oratore attivo, ma gli utenti possono selezionare manualmente i partecipanti dai quali desiderano ricevere il flusso video. Se il multi-video è abilitato, il requisito di risoluzione e larghezza di banda per ognuno dei flussi video sarà inferiore.

- Ogni partecipante che attiva il flusso video di invio dell'utente invierà uno o più flussi video. Skype for Business Server è in grado di inviare fino a cinque flussi video per ottimizzare la qualità video per tutti i client di ricezione. Il numero effettivo di flussi video inviati è determinato dal mittente sulla base della capacità del CPU, della larghezza di banda disponibile, e del numero di client in ricezione che richiedono un determinato flusso video. Il caso più comune è quello in cui un flusso video H.264 e un flusso video RTVideo sono inviati se un client legacy partecipa alla conferenza. Un altro scenario comune è quello in cui diversi flussi video H.264 (ad esempio, con risoluzioni video diverse) vengono inviati al fine di soddisfare diverse richieste.

Oltre alla larghezza di banda necessaria per il traffico RTP (Real-Time Transport Protocol) per i supporti audio e video, la larghezza di banda è necessaria per RTCP (Real-Time Transport Control Protocol). RTCP viene utilizzato per segnalare le statistiche e il controllo fuori banda del flusso RTP. Per la pianificazione, utilizzare i numeri di larghezza di banda riportati nella tabella seguente per il traffico RTCP. Questi valori rappresentano la larghezza di banda massima utilizzata per RTCP e sono diversi per i flussi audio e video a causa delle differenze nei dati dei controlli

**Larghezza di banda per RTCP**

|**Contenuti multimediali**|**Larghezza di banda massima per RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (solo H.264 o RTVideo inviati/ricevuti)  <br/> |10    <br/> |
|Video (H.264 e RTVideo inviati/ricevuti)  <br/> |15   <br/> |

Per la pianificazione della capacità, sono di interesse le due statistiche seguenti:

- **Larghezza di banda massima senza FEC** Larghezza di banda massima che verrà utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario senza FEC. Si tratta della larghezza di banda utilizzata quando l'attività del flusso corrisponde al 100% e non si verificano perdite di pacchetti che attivano l'utilizzo di FEC. Ciò è utile per calcolare la quantità di larghezza di banda da allocare per consentire l'utilizzo del codec in un determinato scenario. FeC non deve essere un requisito in una rete gestita.

- **Larghezza di banda massima con FEC** Larghezza di banda massima utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario con FEC. Si tratta della larghezza di banda utilizzata quando l'attività del flusso corrisponde al 100% e si verifica una perdita di pacchetti che attiva l'utilizzo di FEC per migliorare la qualità. Ciò è utile per calcolare la quantità di larghezza di banda da allocare per consentire l'utilizzo del codec in un determinato scenario e per consentire l'utilizzo di FEC per preservare la qualità in condizioni di perdita di pacchetti.

Nelle tabelle seguenti è inoltre riportato un valore aggiuntivo per la larghezza di banda, **Larghezza di banda tipica.** Si tratta della larghezza di banda media utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario. Questa larghezza di banda può essere utilizzata per approssimare la quantità di larghezza di banda utilizzata dal traffico multimediale in un momento specifico, ma non deve essere utilizzata per la pianificazione della capacità, perché le singole chiamate supereranno questo valore quando il livello di attività è superiore alla media. La larghezza di banda tipica del flusso video nelle tabelle seguenti si basa su una combinazione di diverse risoluzioni video osservate nei dati misurati dei clienti e è probabile che le installazioni più piccole presentino numeri effettivi diversi dai dati della tabella. Ad esempio, nelle sessioni peer-to-peer la maggior parte degli utenti utilizzerebbe la finestra di rendering video predefinita, mentre una percentuale di utenti aumenterebbe o ingrandisce l'applicazione Skype for Business Server per consentire risoluzioni video migliori.

Nelle tabelle seguenti sono riportati i valori per i diversi scenari.

**Pianificazione della capacità audio/video per sessioni peer-to-peer**

|**Contenuti multimediali**|**Codec**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda larga RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda stretta RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Audio  <br/> |BANDA LARGA DI TASER  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Video principale quando si chiamano gli endpoint di Skype for Business Server  <br/> |H.264  <br/> |460  <br/> |4010 (per una risoluzione massima di 1920x1080)  <br/> |Già incluso  <br/> |
|Video principale quando si chiamano gli endpoint di Lync 2010 o Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (per una risoluzione massima di 1280x720)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano gli endpoint di Skype for Business Server  <br/> |H.264  <br/> |190  <br/> |2010 (per una risoluzione massima di 1920x288)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano gli endpoint di Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (per una risoluzione massima di 960x144)  <br/> |Già incluso  <br/> |

**Pianificazione della capacità audio/video per conferenze**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Audio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Ricezione video principale  <br/> |H.264 e RTVideo¹  <br/> |260  <br/> |8015  <br/> |Non applicabile  <br/> |
|Invio video principale  <br/> |H.264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicabile  <br/> |
|Ricezione video panoramico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2010 (per una risoluzione massima di 1920x288)  <br/> |Non applicabile  <br/> |
|Invio video panoramico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Non applicabile  <br/> |

1. Il video RT viene inviato in aggiunta a H.264 quando i client Lync 2010 sono connessi alla conferenza.

2. Se sono presenti più flussi, condividono dinamicamente la larghezza di banda allocata.

Per il video principale, la larghezza di banda tipica del flusso è la larghezza di banda aggregata su tutti i flussi video ricevuti e il flusso massimo è la larghezza di banda su tutti i flussi video di invio. Anche con più flussi video, la larghezza di banda video tipica è inferiore rispetto allo scenario peer-to-peer, perché molte conferenze video usano la condivisione di contenuti che porta a finestre video molto più piccole e quindi a risoluzioni video più piccole. La larghezza di banda massima supportata per il payload video aggregato è di 8.000 Kbps per i flussi di invio e ricezione che verrebbero utilizzati (ad esempio se sono presenti due flussi video 1920x1080p in ingresso). I valori massimi vengono visualizzati solo raramente nelle implementazioni effettive.

Quando si compila una conferenza con più partecipanti che utilizza la funzionalità di visualizzazione raccolta, l'utilizzo della larghezza di banda aumenta inizialmente quando i partecipanti aderiscono e quindi diminuisce quando le risoluzioni vengono eliminate per rientrare nel limite massimo.

||**2 partecipanti**|**3 Partecipanti**|**4 Partecipanti**|**5 partecipanti**|**6 Partecipanti**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Numero massimo di risoluzioni ricevute** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocità in bit media totale** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocità in bit massima totale** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La larghezza di banda tipica del flusso per il video panoramico si basa su dispositivi che ese streaming solo fino a 960x144 video panoramico. Quando si usano dispositivi con video panoramico 1920x288, è previsto un aumento della larghezza di banda tipica del flusso.

**Pianificazione della capacità audio per PSTN**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G.711 (inclusi i partecipanti PSTN alle conferenze)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda stretta RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

I numeri relativi alla larghezza di banda di rete riportati in queste tabelle rappresentano solo il traffico unidirezionale e includono 5 Kbps per l'overhead del traffico RTCP per ogni flusso.

## <a name="managing-quality-of-service"></a>Gestione della qualità del servizio
<a name="man_QOS"> </a>

QoS (Quality of Service) è una tecnologia di rete utilizzata in alcune organizzazioni per offrire un'esperienza utente finale ottimale per le comunicazioni audio e video. QoS viene utilizzato più di frequente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete in concorrenza per una quantità piuttosto ridotta di larghezza di banda disponibile, QoS consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video. Fornendo a questi pacchetti una priorità più alta, è probabile che le comunicazioni audio e video si completino più velocemente e con minore interruzione rispetto alle sessioni di rete che implicano trasferimenti di file, esplorazione Web o backup dei database. Questo perché ai pacchetti di rete utilizzati per i trasferimenti di file o per i backup dei database viene assegnata una priorità di "impegno ottimale".

> [!NOTE]
> Di norma, QoS si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti in un modo particolare che potrebbe non essere supportato su Internet o su altre reti. Anche se la qualità del servizio è supportata su altre reti, non esiste alcuna garanzia che QoS verrà configurata esattamente nello stesso modo in cui è stato configurato il servizio. Se si usa MPLS, è necessario collaborare con il provider MPLS.

Skype for Business Server non richiede QoS, ma è consigliabile. Se si verificano problemi di perdita di pacchetti nella rete, le soluzioni disponibili sono aggiungere più larghezza di banda o implementare QoS. Se non è possibile aggiungere più larghezza di banda, l'implementazione di QoS potrebbe essere l'unico a numero verde per risolvere il problema.

Skype for Business Server offre supporto completo per QoS: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario eseguire la procedura seguente:

- [Abilitazione di QoS in Skype for Business Server per i dispositivi non basati su Windows.](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md) Per impostazione predefinita, QoS è disabilitato per computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Sebbene sia possibile utilizzare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.

- [Configurazione degli intervalli di porte e dei criteri qualità del servizio](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)per i server per conferenze, applicazioni e Mediation Server. È necessario riservare un set univoco di porte per tipi di pacchetti diversi, ad esempio audio e video. Utilizzando Skype for Business Server non è possibile abilitare o disabilitare QoS impostando un valore di proprietà su True o Su False. È invece possibile abilitare QoS configurando intervalli di porte e quindi creando e applicando Criteri di gruppo. Se successivamente si decide di non utilizzare QoS, è possibile "disabilitare" QoS rimuovendo gli oggetti Criteri di gruppo appropriati.

- [Configurazione degli intervalli di porte e dei criteri qualità del servizio per i server perimetrali.](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Anche se non è necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server. La configurazione di un criterio QoS deve essere eseguita solo per il lato interno dei server perimetrali. Questo perché QoS è progettato per l'utilizzo nella rete interna e non in Internet.

- [Configurazione degli intervalli di porte e dei criteri qualità del servizio per i client in Skype for Business Server.](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md) Questi intervalli di porte si applicano solo ai computer client e in genere sono diversi dagli intervalli di porte configurati nei server. Skype for Business Server non supporta QoS per sistemi operativi Windows diversi da Windows 10.


> [!NOTE]
> Se utilizzi Windows Server 2012 o Windows Server 2012 R2, potresti essere interessato al nuovo set di cmdlet Windows PowerShell disponibili per la gestione di QoS su tale piattaforma. Per ulteriori informazioni, vedere [Cmdlet QoS](https://go.microsoft.com/fwlink/p/?LinkId=285379)di rete in Windows PowerShell .

QoS viene inoltre descritto nel white paper [Pianificazione della rete,](https://www.microsoft.com/download/details.aspx?id=39084) monitoraggio e risoluzione dei problemi con Lync Server con ulteriori dettagli e informazioni dettagliate. Anche se il contenuto fa riferimento esplicitamente a Lync 2010 e Lync 2013, le considerazioni per Skype for Business Server sono invariate.

## <a name="see-also"></a>Vedere anche
<a name="man_QOS"> </a>

[Pianificare IPv6 in Skype for Business](ipv6.md)

[Requisiti per il bilanciamento del carico per Skype for Business](load-balancing.md)

[Requisiti DNS per Skype for Business Server](dns.md)
