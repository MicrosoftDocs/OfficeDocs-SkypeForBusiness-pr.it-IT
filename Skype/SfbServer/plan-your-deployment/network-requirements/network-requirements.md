---
title: Pianificare i requisiti di rete per Skype for business
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
description: "Riepilogo: esaminare le considerazioni relative ai componenti di rete seguenti prima dell'implementazione di Skype for Business Server."
ms.openlocfilehash: 0b5d183ecc11d09569427e432121fab7de8f401b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834356"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Pianificare i requisiti di rete per Skype for business

**Riepilogo:** Esaminare le considerazioni relative ai componenti di rete seguenti prima di implementare Skype for Business Server.

Le informazioni contenute in questi argomenti sono descritte anche nel whitepaper [pianificazione della rete, monitoraggio e risoluzione dei problemi con Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con dettagli e profondità aggiuntivi. Anche se il contenuto si riferisce in modo esplicito a Lync 2010 e Lync 2013, le considerazioni relative a Skype for Business Server sono invariate.

Analogamente, se la rete include Wi-Fi e accesso cablato, il white paper che [distribuisce Lync 2013 Real-Time comunicazioni tramite Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) è un buon riferimento ed è ugualmente applicabile a Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware dei server
<a name="S_hard"> </a>

La scheda di rete di ogni server nella topologia di Skype for Business Server deve supportare almeno 1 Gigabit al secondo (Gbps). In generale, è consigliabile connettere tutti i ruoli del server nella topologia di Skype for Business Server con una bassa latenza e una rete LAN (Local Area Network) di larghezza di banda elevata. Le dimensioni della rete LAN dipendono dalle dimensioni della topologia:

- Nelle topologie standard Edition i server devono trovarsi in una rete che supporta 1 Gbps Ethernet o equivalente.

- Nelle topologie Enterprise Edition, la maggior parte dei server deve trovarsi in una rete che supporta più di 1 Gbps, soprattutto quando si supportano le conferenze audio/video (A/V) e la condivisione di applicazioni.

È possibile supportare l'integrazione della rete PSTN (Public Switched Telephone Network) utilizzando linee T1/E1 o il trunking SIP.

## <a name="audiovideo-network-requirements"></a>Requisiti di rete audio/video
<a name="AV_req"> </a>

I requisiti di rete per audio/video (A/V) in una distribuzione di Skype for Business Server includono quanto segue:

- Se si sta distribuendo un singolo server perimetrale o un pool di Edge utilizzando il bilanciamento del carico DNS, è possibile configurare il firewall  _esterno_ per l'esecuzione di NAT (Network Address Translation). Non è possibile configurare il firewall _interno_ per l'esecuzione di NAT. Per informazioni dettagliate, vedere [pianificazione di porte e firewall](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Se si dispone di un pool di server perimetrali e si utilizza un dispositivo di bilanciamento del carico hardware, è necessario utilizzare gli indirizzi IP pubblici nei server perimetrali e non è possibile utilizzare il NAT per il pool o il computer in cui è abilitato NAT (ad esempio, un firewall appliance o un interruttore LAN. Per ulteriori informazioni, vedere [scenari server perimetrali in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Se nell'organizzazione è prevista un'infrastruttura di qualità del servizio (QoS), il sottosistema multimediale è progettato per essere utilizzato nell'infrastruttura esistente.

- Se si utilizza IPSec (Internet Protocol security), è consigliabile disabilitarlo per gli intervalli di porte usati per il traffico A/V. Per informazioni dettagliate, vedere [IPSec Exceptions](#ipsec-exceptions).

Per garantire una qualità multimediale ottimale, eseguire le operazioni seguenti:

- Eseguire il provisioning dei collegamenti di rete per il supporto di velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 kbps per flusso video, se abilitati, durante i periodi di utilizzo di punta. Una sessione audio o video bidirezionale utilizza due flussi, quindi una semplice connessione audio/telefono richiederà a 130Kbps di coprire ogni flusso. Video utilizzerà similarmente 1000 kbps Total per portare una connessione a Monte e a valle.

- Per far fronte ai picchi inattesi del traffico e all'aumento dell'utilizzo nel tempo, gli endpoint multimediali di Skype for Business Server possono adattarsi a diverse condizioni di rete e supportare tre volte la velocità effettiva per l'audio e il video mantenendo la qualità accettabile. Non si supponga che questa adattabilità maschera il problema quando una rete è sottoposta a provisioning. In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Skype for Business Server di gestire in modo dinamico le diverse condizioni di rete, ad esempio la perdita temporanea di pacchetti elevati, è ridotta.

- Per i collegamenti di rete in cui il provisioning è molto costoso e difficile, potrebbe essere necessario prendere in considerazione il provisioning per un volume di traffico più basso. In questo scenario, lasciare che l'elasticità degli endpoint multimediali di Skype for Business Server assorba la differenza tra il volume del traffico e il livello di traffico massimo, a scapito di una certa riduzione della qualità vocale. Inoltre, ci sarà una diminuzione dell'altezza libera altrimenti disponibile per assorbire picchi improvvisi nel traffico.

- Per i collegamenti che non è possibile eseguire il provisioning in modo corretto a breve termine (ad esempio, un sito che utilizza collegamenti WAN molto poveri), è consigliabile disabilitare video per alcuni utenti.

- Eseguire il provisioning della rete per garantire un massimo ritardo end-to-end (latenza) di 150 millisecondi (MS) sotto carico di picco. Latenza è l'unica compromissione della rete che i componenti multimediali di Skype for Business Server non possono ridurre e che è importante individuare ed eliminare i punti deboli.

- Per i server che eseguono il software antivirus, includere tutti i server che eseguono Skype for Business Server nell'elenco delle eccezioni per garantire prestazioni ottimali e qualità audio.

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
|Mediation Server in ingresso|Qualsiasi  |Mediation Server (s) |UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
|Mediation Server in uscita|Mediation Server (s)  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non autenticare|
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

La larghezza di banda utilizzata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto. È possibile scegliere di monitorare l'utilizzo effettivo e regolare di conseguenza la pianificazione della larghezza di banda.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale
<a name="Conf_req"> </a>

Una parte importante della pianificazione della rete è garantire che la rete sia in grado di gestire il traffico multimediale generato da Skype for Business Server. Questa sezione fornisce supporto alla pianificazione per il traffico multimediale.

### <a name="media-traffic-network-usage"></a>Utilizzo della rete per il traffico multimediale
<a name="Net_req"> </a>

L'utilizzo della larghezza di banda per il traffico multimediale può essere difficile da calcolare per la quantità di variabili diverse, ad esempio l'utilizzo di codec, la risoluzione e i livelli di attività. L'utilizzo della larghezza di banda è una funzione del codec utilizzato e dell'attività del flusso, che può variare tra gli scenari. Nella tabella seguente sono elencati i codec audio utilizzati in genere negli scenari di Skype for Business Server.

**Larghezza di banda del codec audio**

|**Codec audio**|**Scenario**|**Velocità in bit del payload audio (KBPS)**|**Larghezza di banda solo per payload audio e intestazione (Kbps)**|**Larghezza di banda per payload audio, intestazione IP, UDP, RTP e SRTP (Kbps)**|**Larghezza di banda per payload audio, intestazione IP, UDP, RTP, SRTP e correzione degli errori di inoltro (FEC) (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda larga RTAudio  <br/> |Peer-to-peer  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Banda stretta RTAudio  <br/> |PSTN peer-to-peer  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Conferenze  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|G.722 Stereo  <br/> |Servizi di conferenza peer-to-peer  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |PSTN, servizi di conferenza  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Sirena  <br/> |Conferenze  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Banda larga di seta  <br/> |Peer-to-peer  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Banda larga di seta  <br/> |Peer-to-peer  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda larga di seta  <br/> |Peer-to-peer  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Banda larga di seta/a banda stretta  <br/> |Peer-to-peer  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Le chiamate PSTN provenienti dal client Skype for business utilizzano solitamente il codec G. 711, che richiede un'elevata larghezza di banda. Se non è disponibile una larghezza di banda sufficiente per tale codec, le chiamate possono avere esito negativo con un errore simile al seguente nei registri multimediali: **atleast un codec deve essere abilitato, HR: c0042004**. I registri multimediali (file con estensione Blog) sono crittografati e possono essere decodificati solo dal personale del supporto tecnico Microsoft.

I numeri della larghezza di banda nella tabella precedente sono basati su pacchettizzazione di 20ms (50 pacchetti al secondo) e per i codec Siren e G. 722 sono inclusi l'overhead di protocollo di trasporto (SRTP) (Secure Real-Time Transport Protocol) da scenari di conferenza e si presuppone che il flusso sia 100% attivo. La correzione degli errori inoltrati (FEC) viene utilizzata in modo dinamico quando si verifica una perdita di pacchetti sul collegamento per garantire la qualità del flusso audio.

La versione stereo del codec G. 722 viene utilizzata da sistemi basati su Lync room System, che utilizza un singolo microfono stereo o una coppia di microfoni mono per consentire agli ascoltatori di distinguere meglio gli altoparlanti multipli nella sala riunioni.

**Larghezza di banda della risoluzione video**

|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit massima del payload video (Kbps)**|**Velocità in bit di payload video minimo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H. 264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Il codec predefinito per il video è lo standard di codifica video avanzato H. 264/MPEG-4 parte 10, insieme alle estensioni di codifica video scalabili per la scalabilità temporale. Per mantenere l'interoperabilità con i client legacy, il codec RTVideo è ancora utilizzato per le chiamate peer-to-peer tra Skype for Business Server e i client legacy. Nelle sessioni di conferenza sia con Skype for Business Server che con i client legacy l'endpoint di Skype for Business Server può codificare il video utilizzando entrambi i codec video e inviare il Bitstream H. 264 ai client Skype for Business Server e a RTVideo Bitstream ai client legacy.

La larghezza di banda necessaria dipende dalla risoluzione, dalla qualità, dalla frequenza dei fotogrammi e dall'entità del movimento o della modifica dell'immagine. Per ogni risoluzione sono disponibili due bit rate pertinenti:

- **Velocità in bit massima del payload** Questo è il bit rate che un endpoint utilizzerà per la risoluzione alla frequenza massima dei fotogrammi. Questo è il valore che consente la qualità audio e video più alta.

- **Velocità in bit minima del payload** Questo è il bit rate al di sotto del quale un endpoint di Skype for Business Server passerà alla risoluzione inferiore successiva. Per garantire una determinata risoluzione, la frequenza di bit del payload del video disponibile non deve essere inferiore a quella minima velocità in bit per tale soluzione. Questo valore consente di comprendere il valore più basso possibile se la velocità in bit massima non è disponibile o pratico. Per alcuni utenti, un video a bassa velocità in bit potrebbe fornire un'esperienza video inaccettabile, in modo da utilizzare la prudenza con questi bitrate minimo dei carichi di lavoro video. Si noti che per le scene video statiche e inalterabili la velocità in bit effettiva può cadere temporaneamente al di sotto del bit rate minimo.

Skype for Business Server supporta numerose risoluzioni. In questo modo Skype for Business Server viene adattato alla larghezza di banda di rete diversa e alle funzionalità client di ricezione. Le proporzioni predefinite per Skype for Business Server sono 16:9. Le proporzioni legacy 4:3 sono ancora supportate per le webcam che non consentono l'acquisizione nelle proporzioni 16:9.

Video FEC è sempre incluso nella velocità di bit del payload del video quando viene utilizzato in modo che non vi siano valori separati per con video FEC e senza video FEC.

Gli endpoint non inviano flussi continui di pacchetti audio o video. A seconda dello scenario, esistono livelli diversi di attività di flusso che indicano la frequenza dell'invio di pacchetti per un flusso. L'attività di un flusso dipende dal contenuto multimediale e dallo scenario e non dal codec utilizzato. In uno scenario peer-to-peer:

- Gli endpoint inviano solo flussi audio quando gli utenti parlano.

- Entrambi i partecipanti ricevono flussi audio.

- Se viene utilizzato il video, entrambi gli endpoint inviano e ricevono flussi video durante la chiamata.

- Per le scene video statiche, la velocità in bit effettiva può essere estremamente bassa poiché il codec video ignorerà le aree di codifica del video senza modifiche dopo l'esempio precedente.

In uno scenario di conferenza:

- Gli endpoint inviano flussi audio solo quando l'utente parla.

- Tutti i partecipanti ricevono flussi audio.

- Se è utilizzato il video, tutti i partecipanti possono ricevere fino a cinque flussi video, e un flusso video panoramico (ad esempio, con proporzioni 20:3). Per impostazione predefinita, i cinque flussi video di ricezione si basano sulla cronologia dell'oratore attivo, ma gli utenti possono selezionare manualmente i partecipanti dai quali desiderano ricevere il flusso video. Se è abilitato il multi-video, la risoluzione e il requisito di larghezza di banda per ognuno dei flussi video saranno inferiori.

- Ogni partecipante che attiva il flusso video di invio dell'utente invierà uno o più flussi video. Skype for Business Server è in grado di inviare fino a cinque flussi video per ottimizzare la qualità video per tutti i client di ricezione. Il numero effettivo di flussi video inviati è determinato dal mittente sulla base della capacità del CPU, della larghezza di banda disponibile, e del numero di client in ricezione che richiedono un determinato flusso video. Il caso più comune è quello in cui un flusso video H.264 e un flusso video RTVideo sono inviati se un client legacy partecipa alla conferenza. Un altro scenario comune è quello in cui diversi flussi video H.264 (ad esempio, con risoluzioni video diverse) vengono inviati al fine di soddisfare diverse richieste.

Oltre alla larghezza di banda necessaria per il traffico RTP (Real-Time Transport Protocol) per i file multimediali audio e video, è necessaria la larghezza di banda per il protocollo RTCP (Real-Time Transport Control Protocol). RTCP viene utilizzato per la creazione di report di statistiche e il controllo fuori banda del flusso RTP. Per la pianificazione, utilizzare i numeri di larghezza di banda nella tabella seguente per il traffico RTCP. Questi valori rappresentano la larghezza di banda massima utilizzata per RTCP e sono diversi per i flussi audio e video a causa delle differenze nei dati di controllo

**Larghezza di banda per RTCP**

|**Contenuti multimediali**|**Larghezza di banda massima per RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5   <br/> |
|Video (solo H.264 o RTVideo inviati/ricevuti)  <br/> |10   <br/> |
|Video (H.264 e RTVideo inviati/ricevuti)  <br/> |15   <br/> |

Per la pianificazione della capacità, sono interessanti le due statistiche seguenti:

- **Larghezza di banda massima senza FEC** La larghezza di banda massima utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario senza FEC. Si tratta della larghezza di banda utilizzata quando l'attività del flusso corrisponde al 100% e non si verificano perdite di pacchetti che attivano l'utilizzo di FEC. Questo è utile per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'utilizzo del codec in un determinato scenario. Non è previsto che FEC sia un requisito per una rete gestita.

- **Larghezza di banda massima con FEC** La larghezza di banda massima utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario con FEC. Si tratta della larghezza di banda utilizzata quando l'attività del flusso corrisponde al 100% e si verifica una perdita di pacchetti che attiva l'utilizzo di FEC per migliorare la qualità. Questo è utile per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'utilizzo del codec in un determinato scenario e consentire l'uso di FEC per mantenere la qualità in condizioni di perdita di pacchetti.

Nelle tabelle seguenti sono inoltre elencati un valore di larghezza di banda aggiuntivo, la **larghezza di banda tipica**. Si tratta della larghezza di banda media utilizzata da un flusso. Ciò include l'attività tipica del flusso e il codec tipico utilizzato nello scenario. Questa larghezza di banda può essere utilizzata per approssimare la quantità di larghezza di banda utilizzata dal traffico multimediale in un determinato momento, ma non deve essere utilizzata per la pianificazione della capacità, in quanto le singole chiamate superano questo valore quando il livello di attività è superiore alla media. La larghezza di banda di flusso video tipica nelle tabelle seguenti si basa su una combinazione di risoluzioni video diverse, come osservato nei dati dei clienti misurati, e le installazioni più piccole possono avere numeri effettivi che differiscono dai dati della tabella. Ad esempio, nelle sessioni peer-to-peer la maggior parte degli utenti utilizzerà la finestra di rendering video predefinita mentre una percentuale di utenti aumenterà o ingrandirà l'applicazione Skype for Business Server per consentire migliori risoluzioni video.

Nelle tabelle seguenti vengono forniti i valori per i diversi scenari.

**Pianificazione della capacità audio/video per sessioni peer-to-peer**

|**Contenuti multimediali**|**Codec**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |Banda larga RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |Banda stretta RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Banda larga di seta  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Video principale quando si chiamano gli endpoint di Skype for Business Server  <br/> |H. 264  <br/> |460  <br/> |4010 (per una risoluzione massima di 1920x1080)  <br/> |Già incluso  <br/> |
|Video principale quando si chiamano gli endpoint di Lync 2010 o Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (per una risoluzione massima di 1280x720)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano gli endpoint di Skype for Business Server  <br/> |H. 264  <br/> |190  <br/> |2010 (per una risoluzione massima di 1920x288)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano gli endpoint di Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (per una risoluzione massima di 960x144)  <br/> |Già incluso  <br/> |

**Pianificazione della capacità audio/video per conferenze**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Sirena  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Ricezione video principale  <br/> |H. 264 e RTVideo ¹  <br/> |260  <br/> |8015  <br/> |Non applicabile  <br/> |
|Invio video principale  <br/> |H. 264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicabile  <br/> |
|Ricezione video panoramico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2010 (per una risoluzione massima di 1920x288)  <br/> |Non applicabile  <br/> |
|Invio video panoramico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Non applicabile  <br/> |

1. Il video RT viene inviato oltre a H. 264 quando i client Lync 2010 sono connessi alla conferenza.

2. Se sono presenti più flussi, condividono dinamicamente la larghezza di banda allocata.

Per il video principale la larghezza di banda tipica del flusso è la larghezza di banda complessiva su tutti i flussi video ricevuti e il flusso massimo è la larghezza di banda su tutti i flussi video di invio. Anche con più flussi video, la larghezza di banda video tipica è più piccola rispetto allo scenario peer-to-peer perché molte conferenze video utilizzano la condivisione di contenuto che porta a finestre video molto più piccole e quindi risoluzioni video più piccole. La larghezza di banda complessiva massima supportata per il payload video è di 8000 kbps sia per i flussi di invio che di ricezione che verrebbero utilizzati (ad esempio, se sono presenti due flussi video di 1920x1080p in ingresso). I valori massimi sono raramente visibili solo nelle implementazioni effettive.

Durante la creazione di una conferenza con più partecipanti che utilizza la funzionalità visualizzazione raccolta, l'utilizzo della larghezza di banda aumenta inizialmente come partecipazione dei membri, quindi diminuisce quando le risoluzioni vengono rimosse per adattarsi all'interno del limite massimo.

||**2 partecipanti**|**3 partecipanti**|**4 partecipanti**|**5 partecipanti**|**6 partecipanti**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Risoluzioni massime ricevute** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocità in bit media totale** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Velocità in bit massima totale** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La larghezza di banda tipica del flusso per i video panoramici si basa su dispositivi che vengono trasmessi solo al video panoramico di 960x144. Si prevede che la larghezza di banda tipica del flusso aumenti quando si utilizzano dispositivi con video panoramico di 1920x288.

**Pianificazione della capacità audio per PSTN**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (inclusi i partecipanti PSTN nelle conferenze)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |Banda stretta RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

I numeri relativi alla larghezza di banda di rete riportati in queste tabelle rappresentano solo il traffico unidirezionale e includono 5 Kbps per l'overhead del traffico RTCP per ogni flusso.

## <a name="managing-quality-of-service"></a>Gestione della qualità del servizio
<a name="man_QOS"> </a>

La qualità del servizio (QoS) è una tecnologia di rete utilizzata in alcune organizzazioni per fornire una migliore esperienza utente finale per le comunicazioni audio e video. La funzionalità QoS viene utilizzata più di frequente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete che competono per una quantità di larghezza di banda disponibile relativamente ridotta, QoS consente agli amministratori di assegnare priorità più elevate ai pacchetti che trasportano dati audio o video. Assegnando a questi pacchetti una priorità più elevata, è probabile che le comunicazioni audio e video vengano completate più velocemente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni quali il trasferimento di file, la navigazione web o i backup dei database. Ciò è dovuto al fatto che i pacchetti di rete utilizzati per i trasferimenti di file o i backup dei database sono assegnati come priorità "Best Effort".

> [!NOTE]
> Come regola generale, QoS si applica solo alle sessioni di comunicazione sulla rete interna. Quando si implementa QoS, i server e i router vengono configurati per supportare il contrassegno dei pacchetti in modo particolare che potrebbe non essere supportato su Internet o su altre reti. Anche se la qualità del servizio è supportata su altre reti, non vi è alcuna garanzia che QoS venga configurata esattamente allo stesso modo in cui il servizio è stato configurato. Se si utilizza MPLS, è necessario collaborare con il provider MPLS.

Skype for Business Server non richiede QoS, ma è fortemente consigliato. Se si verificano problemi di perdita di pacchetti sulla rete, le soluzioni disponibili sono l'aggiunta di una larghezza di banda maggiore o l'implementazione del QoS. Se l'aggiunta di più larghezza di banda non è possibile, l'implementazione del QoS potrebbe essere l'unico pedaggio per risolvere il problema.

Skype for Business Server offre supporto completo per QoS: ciò significa che le organizzazioni che utilizzano già QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. A tale scopo, è necessario attenersi alla seguente procedura:

- [Abilitazione del QoS in Skype for Business Server per dispositivi che non sono basati su Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitata per i computer e altri dispositivi (ad esempio iPhones) che eseguono altri sistemi operativi. Anche se è possibile utilizzare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non è possibile utilizzare il prodotto per modificare i codici DSCP utilizzati da questi dispositivi.

- [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i servizi di conferenza, applicazione e Mediation Server](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario riservare un insieme univoco di porte per diversi tipi di pacchetti, ad esempio audio e video. Utilizzando Skype for Business Server non è possibile abilitare o disabilitare QoS impostando un valore della proprietà su true o su false. Al contrario, è possibile abilitare QoS configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non utilizzare QoS, è possibile disabilitare il QoS rimuovendo gli oggetti Criteri di gruppo corretti.

- [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i server perimetrali](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Sebbene non sia necessario, è possibile configurare i server perimetrali in modo che utilizzino gli stessi intervalli di porte degli altri server. La configurazione di un criterio QoS deve essere completata solo per il lato interno dei server perimetrali. Questo perché QoS è stato creato per essere utilizzato sulla rete interna e non su Internet.

- [Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Questi intervalli di porte si applicano solo ai computer client e in genere sono diversi dagli intervalli di porte configurati nei server. Si noti che Skype for Business Server non supporta QoS per i sistemi operativi Windows diversi da Windows 10.


> [!NOTE]
> Se si utilizza Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessato al nuovo set di cmdlet di Windows PowerShell disponibili per la gestione del QoS su tale piattaforma. Per ulteriori informazioni, vedere [Network QoS cmdlets in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La QoS è descritta anche nella [pianificazione, monitoraggio e risoluzione dei problemi di rete del Whitepaper con Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) con dettagli e profondità aggiuntivi. Anche se il contenuto si riferisce in modo esplicito a Lync 2010 e Lync 2013, le considerazioni relative a Skype for Business Server sono invariate.

## <a name="see-also"></a>Vedere anche
<a name="man_QOS"> </a>

[Pianificare IPv6 in Skype for business](ipv6.md)

[Requisiti per il bilanciamento del carico per Skype for business](load-balancing.md)

[Requisiti DNS per Skype for Business Server](dns.md)
