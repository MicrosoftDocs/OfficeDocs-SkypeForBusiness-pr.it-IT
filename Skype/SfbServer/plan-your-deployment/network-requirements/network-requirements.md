---
title: Pianificare i requisiti di rete per Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: esaminare le considerazioni del componente di rete seguenti prima di implementare Skype for Business Server.'
ms.openlocfilehash: b7b9c7e239aab5d395fcdadf0cb254df4e13cecd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802026"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Pianificare i requisiti di rete per Skype for business

**Riepilogo:** Esaminare le considerazioni del componente di rete seguenti prima di implementare Skype for Business Server.

Le informazioni contenute in questi argomenti sono discusse anche nel whitepaper [pianificazione, monitoraggio e risoluzione dei problemi con Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con dettagli e profondità aggiuntivi. Mentre il contenuto si riferisce esplicitamente a Lync 2010 e Lync 2013, le considerazioni per Skype for Business Server sono invariate.

Allo stesso modo, se la rete include Wi-Fi e accesso via cavo, il whitepaper che [trasporta le comunicazioni in tempo reale di Lync 2013 tramite Wi-Fi](https://www.microsoft.com/en-us/download/details.aspx?id=36494) è un buon riferimento ed è ugualmente applicabile a Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware del server
<a name="S_hard"> </a>

La scheda di rete di ogni server nella topologia di Skype for Business Server deve supportare almeno 1 Gigabit al secondo (Gbps). In generale, è consigliabile connettere tutti i ruoli del server all'interno della topologia di Skype for Business Server con una rete LAN (Local Area Network) a bassa latenza e ad alta larghezza di banda. La dimensione della LAN dipende dalle dimensioni della topologia:

- Nelle topologie standard Edition i server devono essere in una rete che supporta 1 Gbps Ethernet o equivalente.

- Nelle topologie Enterprise Edition la maggior parte dei server dovrebbe essere in una rete che supporta più di 1 Gbps, in particolare per il supporto della condivisione di applicazioni e conferenze audio/video (A/V).

Per l'integrazione PSTN (Public Switched Telephone Network), è possibile integrare tramite linee T1/E1 o trunking SIP.

## <a name="audiovideo-network-requirements"></a>Requisiti di rete audio/video
<a name="AV_req"> </a>

I requisiti di rete per audio/video (A/V) in una distribuzione di Skype for Business Server includono i seguenti:

- Se si distribuisce un singolo Edge Server o un pool di Edge tramite il bilanciamento del carico DNS, è possibile configurare il firewall _esterno_ per l'esecuzione di NAT (Network Address Translation). Non è possibile configurare il firewall _interno_ per eseguire NAT. Per informazioni dettagliate, vedere [pianificazione della porta e del firewall](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Se si ha un pool di bordi e si usa un dispositivo di bilanciamento del carico hardware, è necessario usare gli indirizzi IP pubblici negli Edge Server e non è possibile usare il NAT per i server o il pool in cui è abilitato il supporto NAT, ad esempio un apparecchio firewall o un interruttore LAN. Per informazioni dettagliate, vedere [scenari di Edge Server in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Se l'organizzazione usa un'infrastruttura QoS (Quality of Service), il sottosistema multimediale è progettato per funzionare all'interno di questa infrastruttura esistente.

- Se si usa Internet Protocol Security (IPsec), è consigliabile disabilitare IPsec sugli intervalli di porte usati per il traffico A/V. Per informazioni dettagliate, vedere [Eccezioni IPsec](#ipsec-exceptions).

Per ottenere qualità multimediali ottimali, eseguire le operazioni seguenti:

- Eseguire il provisioning dei collegamenti di rete per supportare la velocità effettiva di 65 kilobit al secondo (Kbps) per flusso audio e 500 kbps per ogni flusso video, se abilitati, durante i periodi di utilizzo di picco. Una sessione audio o video a due vie usa due flussi, quindi una semplice connessione audio/telefono richiederà a 130Kbps di coprire ogni flusso. Il video utilizzerà anche il totale di 1000 kbps per trasportare una connessione a Monte e a valle.

- Per far fronte a picchi imprevisti nel traffico e a un maggiore utilizzo nel tempo, gli endpoint multimediali di Skype for Business Server possono adattarsi alle diverse condizioni di rete e supportare tre volte la velocità effettiva per l'audio e il video mantenendo comunque la qualità accettabile. Non supporre che questa adattabilità maschererà il problema quando una rete viene sottoposta a provisioning. In una rete sottoposta a provisioning, la capacità degli endpoint multimediali di Skype for Business Server di gestire in modo dinamico le diverse condizioni di rete, ad esempio la perdita di pacchetti ad alto contenuto temporaneo, è ridotta.

- Per i collegamenti di rete in cui il provisioning è molto costoso e difficile, potrebbe essere necessario prendere in considerazione il provisioning per un volume di traffico più basso. In questo scenario, l'elasticità degli endpoint multimediali di Skype for Business Server assorbe la differenza tra il volume del traffico e il livello di traffico massimo, a scapito di una certa riduzione della qualità vocale. Inoltre, in caso contrario sarà disponibile una diminuzione dello spazio di espansione per assorbire picchi improvvisi nel traffico.

- Per i collegamenti che non è possibile eseguire il provisioning corretto a breve termine, ad esempio un sito che usa collegamenti WAN molto poveri, è consigliabile disabilitare il video per alcuni utenti.

- Eseguire il provisioning della rete per garantire un massimo ritardo end-to-end (latenza) di 150 millisecondi (MS) in caricamento massimo. La latenza è l'unica compromissione della rete che i componenti multimediali di Skype for Business Server non possono ridurre ed è importante trovare ed eliminare i punti deboli.

- Per i server che usano software antivirus, includere tutti i server che usano Skype for Business Server nell'elenco eccezioni per ottenere prestazioni e qualità audio ottimali.

## <a name="ipsec-exceptions"></a>Eccezioni IPsec

Per le reti aziendali in cui è stato distribuito Internet Protocol Security (IPsec) (Vedi IETF RFC 4301-4309), IPsec deve essere disabilitato tramite l'intervallo di porte usate per il recapito di audio, video e video panoramico. La raccomandazione è motivata dalla necessità di evitare qualsiasi ritardo nell'allocazione delle porte multimediali a causa della negoziazione IPsec.

La tabella seguente illustra le impostazioni di eccezione IPsec consigliate.

**Eccezioni IPsec consigliate**

|Nome regola |IP di origine |IP di destinazione |Protocollo |Porta di origine |Porta di destinazione |Requisito di autenticazione |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|A/V Edge Server Internal in ingresso|Qualsiasi  |A/V Edge Server interno|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|A/V Edge Server esterno in ingresso|Qualsiasi  |A/V Edge Server esterno|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|A/V Edge Server in uscita interna|A/V Edge Server interno  |A/V Edge Server esterno |UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|A/V Edge Server in uscita esterna|A/V Edge Server esterno |Qualsiasi |UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Mediation Server in ingresso|Qualsiasi  |Mediation Server (s) |UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Mediation Server in uscita|Mediation Server (s)  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Operatore di conferenza in ingresso|Qualsiasi  |Server front-end con l'operatore di conferenza |UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Operatore di conferenza in uscita|Server front-end con l'operatore di conferenza  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|A/V Conferencing in ingresso|Qualsiasi|Server front-end|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|A/V Conferencing in uscita|Server front-end|Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Exchange in ingresso|Qualsiasi|Messaggistica unificata di Exchange|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Server di condivisione applicazioni in ingresso|Qualsiasi|Server di condivisione applicazioni|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Server di condivisione applicazioni in uscita|Server di condivisione applicazioni| Qualsiasi |UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Exchange in uscita|Messaggistica unificata di Exchange|Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|Client| Qualsiasi  |Qualsiasi|UDP e TCP|Qualsiasi |Qualsiasi |Non eseguire l'autenticazione|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisiti di rete per i servizi di conferenza
<a name="Conf_req"> </a>

La larghezza di banda usata per scaricare il contenuto delle conferenze dal server Internet Information Services (IIS) dipende dalle dimensioni del contenuto. Si può scegliere di monitorare l'uso effettivo e regolare di conseguenza la pianificazione della larghezza di banda.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale
<a name="Conf_req"> </a>

Una parte importante della pianificazione della rete garantisce che la rete sia in grado di gestire il traffico multimediale generato da Skype for Business Server. Questa sezione consente di pianificare il traffico multimediale.

### <a name="media-traffic-network-usage"></a>Utilizzo della rete per il traffico multimediale
<a name="Net_req"> </a>

L'utilizzo della larghezza di banda del traffico multimediale può essere difficile da calcolare a causa del numero di variabili diverse, ad esempio l'uso dei codec, la risoluzione e i livelli di attività. L'utilizzo della larghezza di banda è una funzione del codec usato e dell'attività del flusso, che può variare tra gli scenari. La tabella seguente elenca i codec audio usati in genere negli scenari di Skype for Business Server.

**Larghezza di banda del codec audio**

|**Codec audio**|**Scenario**|**Velocità in bit del payload audio (KBPS)**|**Payload di larghezza di banda audio e solo intestazione IP (Kbps)**|**Payload audio con larghezza di banda, intestazione IP, UDP, RTP e SRTP (Kbps)**|**Payload audio a larghezza di banda, intestazione IP, UDP, RTP, SRTP e correzione degli errori in avanti (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|RTAudio a banda larga  <br/> |Peer-to-peer  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|RTAudio stretta  <br/> |PSTN peer-to-peer  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Servizi di conferenza  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|Stereo G. 722  <br/> |Conferenza peer-to-peer  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |Servizi di conferenza PSTN  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Sirena  <br/> |Servizi di conferenza  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Banda larga in seta  <br/> |Peer-to-peer  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Banda larga in seta  <br/> |Peer-to-peer  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda larga in seta  <br/> |Peer-to-peer  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|Banda larga in seta/stretta  <br/> |Peer-to-peer  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> Le chiamate PSTN dal client Skype for business usano in genere il codec G. 711, che richiede una larghezza di banda elevata. Se non è disponibile una larghezza di banda sufficiente per il codec, le chiamate possono non riuscire con un errore simile al seguente nei registri multimediali: **atleast un codec deve essere abilitato, HR: c0042004**. I registri multimediali (file. Blog) sono crittografati e possono essere decodificati solo dal personale del supporto Microsoft.

I numeri di larghezza di banda nella tabella precedente si basano sulla packetation 20ms (pacchetti di 50 al secondo) e per i codec Siren e G. 722 includono l'overhead di protocollo di trasporto in tempo reale (SRTP) aggiuntivo protetto dagli scenari di conferenza e si presuppone che il flusso sia 100% attivo. La correzione degli errori in avanti (FEC) viene usata in modo dinamico quando c'è perdita di pacchetti sul collegamento per mantenere la qualità del flusso audio.

La versione stereo del codec G. 722 viene usata dai sistemi basati sul sistema room Lync, che usa un singolo microfono stereo o una coppia di microfoni mono per consentire agli ascoltatori di distinguere più oratori in una sala riunioni.

**Larghezza di banda di risoluzione video**

|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit (Kbps) massimo del payload video**|**Velocità in bit del payload video minimo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H. 264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Il codec predefinito per video è lo standard di codifica video avanzato H. 264/MPEG-4 Part 10, insieme alle estensioni di codifica video scalabili per la scalabilità temporale. Per mantenere l'interoperabilità con i client legacy, il codec RTVideo viene ancora usato per le chiamate peer-to-peer tra Skype for Business Server e i client legacy. Nelle sessioni di conferenza con Skype for Business Server e i client legacy l'endpoint di Skype for Business Server può codificare il video con codec video e inviare il Bitstream H. 264 ai client di Skype for Business Server e al Bitstream RTVideo a Legacy client.

La larghezza di banda necessaria dipende dalla risoluzione, la qualità, la frequenza dei fotogrammi e la quantità di movimento o di modifica nell'immagine. Per ogni risoluzione, sono disponibili due velocità in bit pertinenti:

- **Velocità in bit del payload massimo** Si tratta della velocità in bit che verrà usata da un endpoint per la risoluzione alla frequenza massima dei fotogrammi. Questo è il valore che consente la massima qualità audio e video.

- **Velocità in bit minima del payload** Questa è la velocità in bit sotto la quale un endpoint di Skype for Business Server passerà alla risoluzione inferiore successiva. Per garantire una determinata risoluzione, la velocità in bit del payload video disponibile non deve scendere al di sotto di questa velocità minima per la risoluzione. Questo valore consente di comprendere il valore più basso possibile se la velocità in bit massima non è disponibile o pratica. Per alcuni utenti, un video a basso tasso può offrire un'esperienza video inaccettabile in modo da usare la massima cautela con questi bitrate del payload video minimo. Tieni presente che per le scene video statiche e non modificate, la velocità in bit effettiva può scendere temporaneamente al di sotto della velocità in bit minima.

Skype for Business Server supporta molte risoluzioni. Ciò consente a Skype for Business Server di adattarsi a diverse larghezze di banda e a ricevere funzionalità client. Le proporzioni predefinite per Skype for Business Server sono 16:9. Le proporzioni legacy di 4:3 sono ancora supportate per le webcam che non consentono l'acquisizione nelle proporzioni 16:9.

Il video FEC è sempre incluso nella velocità di bit del payload video quando viene usato in modo che non ci siano valori distinti per con video FEC e senza video FEC.

Gli endpoint non eseguono il flusso continuo di pacchetti audio o video. A seconda dello scenario, sono presenti diversi livelli di attività di flusso che indicano la frequenza di invio dei pacchetti per un flusso. L'attività di un flusso dipende dall'elemento multimediale e dallo scenario e non dipende dal codec usato. In uno scenario peer-to-peer:

- Gli endpoint inviano solo flussi audio quando gli utenti parlano.

- Entrambi i partecipanti ricevono flussi audio.

- Se viene usato il video, entrambi gli endpoint inviano e ricevono flussi video durante la chiamata.

- Per le scene video statiche la velocità in bit effettiva può essere temporaneamente molto bassa perché il codec video salterà la codifica delle aree del video senza modificare l'esempio precedente.

In uno scenario di conferenza:

- Gli endpoint inviano flussi audio solo quando gli utenti parlano.

- Tutti i partecipanti ricevono flussi audio.

- Se viene usato il video, tutti i partecipanti possono ricevere fino a cinque flussi video di ricezione e uno stream video panoramico (ad esempio, aspect ratio 20:3). Per impostazione predefinita, i cinque flussi video di ricezione si basano sulla cronologia degli oratori attivi, ma gli utenti possono anche selezionare manualmente i partecipanti da cui vogliono ricevere un flusso video. Se è abilitata la funzionalità multivideo, la risoluzione e il requisito della larghezza di banda per ogni flusso video saranno più bassi.

- Ogni partecipante che attiva il flusso video di invio dell'utente invierà uno o più flussi video. Skype for Business Server offre la possibilità di inviare fino a cinque flussi video per ottimizzare la qualità del video per tutti i client di ricezione. Il numero effettivo di flussi video inviati viene determinato dal mittente in base alle funzionalità della CPU, alla larghezza di banda di uplink disponibile e al numero di client di ricezione che richiedono un determinato flusso video. Il caso più comune è che si sta inviando un flusso video H. 264 e uno RTVideo nel caso in cui un client legacy partecipi alla conferenza. Un altro scenario comune è che diversi flussi video H. 264, ad esempio con risoluzioni video diverse, vengono inviati per ospitare diverse richieste di ricevitore.

Oltre alla larghezza di banda necessaria per il traffico RTP (Real-Time Transport Protocol) per i supporti audio e video, è necessaria la larghezza di banda per il protocollo di controllo del trasporto in tempo reale (RTCP). RTCP viene usato per segnalare le statistiche e il controllo fuori banda del flusso RTP. Per la pianificazione, usare i numeri di larghezza di banda nella tabella seguente per il traffico RTCP. Questi valori rappresentano la larghezza di banda massima usata per RTCP e sono diversi per i flussi audio e video a causa delle differenze tra i dati del controllo

**Larghezza di banda RTCP**

|**Contenuti multimediali**|**Larghezza di banda massima RTCP (Kbps)**|
|:-----|:-----|
|Audio  <br/> |5  <br/> |
|Video (solo H. 264 o RTVideo inviati/ricevuti)  <br/> |10  <br/> |
|Video (H. 264 e RTVideo inviati/ricevuti)  <br/> |15  <br/> |

Per la pianificazione della capacità, sono interessanti le due statistiche seguenti:

- **Larghezza di banda massima senza FEC** La larghezza di banda massima che verrà utilizzata da un flusso. Questo include l'attività tipica dello Stream e il codec tipico usato nello scenario senza FEC. Questa è la larghezza di banda quando il flusso si trova all'attività di 100% e non è disponibile alcuna perdita di pacchetti che attiva l'uso di FEC. Questo è utile per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'uso del codec in uno scenario specifico. FEC non dovrebbe essere un requisito per una rete gestita.

- **Larghezza di banda massima con FEC** La larghezza di banda massima utilizzata da un flusso. Questo include l'attività tipica dello Stream e il codec tipico usato nello scenario con FEC. Questa è la larghezza di banda quando il flusso è a 100% di attività e la perdita di pacchetti attiva l'uso di FEC per migliorare la qualità. Questo è utile per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'utilizzo del codec in uno scenario specifico e consentire l'uso di FEC per mantenere la qualità in condizioni di perdita di pacchetti.

Le tabelle seguenti elencano anche un valore di larghezza di banda aggiuntivo, la **larghezza di banda tipica**. Si tratta della larghezza di banda media utilizzata da un flusso. Questo include l'attività tipica dello Stream e il codec tipico usato nello scenario. Questa larghezza di banda può essere usata per approssimare la quantità di larghezza di banda utilizzata dal traffico multimediale in un determinato momento, ma non deve essere usata per la pianificazione della capacità, perché le singole chiamate supereranno questo valore quando il livello di attività è maggiore della media. La larghezza di banda tipica del flusso video nelle tabelle seguenti si basa su una combinazione di risoluzioni video diverse, come osservato nei dati dei clienti misurati, e le installazioni più piccole possono avere numeri reali che differiscono dai dati della tabella. Ad esempio, nelle sessioni peer-to-peer la maggior parte degli utenti utilizzerebbe la finestra di rendering video predefinita, mentre una certa percentuale di utenti aumenterebbe o massimizza l'applicazione di Skype for Business Server per consentire migliori risoluzioni video.

Le tabelle seguenti includono valori per i vari scenari.

**Pianificazione della capacità audio/video per le sessioni peer-to-peer**

|**Contenuti multimediali**|**Codec**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |RTAudio a banda larga  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Audio  <br/> |RTAudio stretta  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Audio  <br/> |Banda larga in seta  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Video principale quando si chiamano endpoint di Skype for Business Server  <br/> |H. 264  <br/> |460  <br/> |4010 (per la risoluzione massima di 1920x1080)  <br/> |Già incluso  <br/> |
|Video principale quando si chiamano gli endpoint di Lync 2010 o Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (per la risoluzione massima di 1280x720)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano endpoint di Skype for Business Server  <br/> |H. 264  <br/> |190  <br/> |2010 (per la risoluzione massima di 1920x288)  <br/> |Già incluso  <br/> |
|Video panoramico quando si chiamano endpoint di Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (per la risoluzione massima di 960x144)  <br/> |Già incluso  <br/> |

**Pianificazione della capacità audio/video per le conferenze**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Audio  <br/> |Sirena  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Ricezione video principale  <br/> |H. 264 e RTVideo ¹  <br/> |260  <br/> |8015  <br/> |Non applicabile  <br/> |
|Invio video principale  <br/> |H. 264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Non applicabile  <br/> |
|Ricezione video panoramico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2010 (per la risoluzione massima di 1920x288)  <br/> |Non applicabile  <br/> |
|Invio video panoramico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Non applicabile  <br/> |

1. Il video RT viene inviato oltre a H. 264 quando i client di Lync 2010 sono connessi alla conferenza.

2. Se sono presenti più flussi, condividono dinamicamente la larghezza di banda allocata.

Per il video principale, la larghezza di banda tipica del flusso è la larghezza di banda aggregata rispetto a tutti i flussi video ricevuti e il flusso massimo è la larghezza di banda di tutti i flussi video di invio. Anche con più flussi video, la larghezza di banda video tipica è più piccola rispetto allo scenario peer-to-peer, poiché molte videoconferenze usano la condivisione di contenuto che porta a finestre video molto più piccole e quindi a risoluzioni video più piccole. La larghezza di banda complessiva del payload video aggregato supportata è di 8000 kbps per i flussi di invio e ricezione che verrebbero usati (ad esempio, se sono presenti due flussi video di 1920x1080p in arrivo). I valori massimi vengono visualizzati solo raramente nelle implementazioni effettive.

Quando si crea una conferenza multiparte che usa la caratteristica visualizzazione raccolta, l'utilizzo della larghezza di banda aumenta inizialmente quando i partecipanti partecipano, quindi diminuisce man mano che le risoluzioni vengono rimosse in modo da adattarsi al massimo.

||**2 partecipanti**|**3 partecipanti**|**4 partecipanti**|**5 partecipanti**|**6 partecipanti**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Risoluzioni max ricevute** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Velocità in bit media totale** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Tasso di bit massimo totale** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

La tipica larghezza di banda del flusso per il video panoramico si basa su dispositivi che solo Stream fino a 960x144 video panoramico. Aspettarsi che la larghezza di banda tipica del flusso aumenti quando si usano i dispositivi con video panoramico 1920x288.

**Pianificazione della capacità audio per PSTN**

|**Contenuti multimediali**|**Codec tipico**|**Larghezza di banda tipica del flusso (Kbps)**|**Larghezza di banda massima del flusso senza FEC**|**Larghezza di banda massima del flusso con FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Audio  <br/> |G. 711 (inclusi i partecipanti PSTN nelle conferenze)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Audio  <br/> |RTAudio stretta  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

I numeri di larghezza di banda di rete in queste tabelle rappresentano solo il traffico unidirezionale e includono 5 kbps per il sovraccarico del traffico di RTCP per ogni flusso.

## <a name="managing-quality-of-service"></a>Gestione della qualità del servizio
<a name="man_QOS"> </a>

La qualità del servizio (QoS) è una tecnologia di rete usata in alcune organizzazioni per offrire un'esperienza ottimale per l'utente finale per le comunicazioni audio e video. Il QoS viene usato più di frequente nelle reti in cui la larghezza di banda è limitata: con un numero elevato di pacchetti di rete che competono per una quantità abbastanza piccola di larghezza di banda disponibile, QoS consente agli amministratori di assegnare priorità più alte ai pacchetti che trasportano dati audio o video. Assegnando a questi pacchetti una priorità più alta, le comunicazioni audio e video possono essere completate più rapidamente e con meno interruzioni rispetto alle sessioni di rete che coinvolgono operazioni come i trasferimenti di file, la navigazione web o i backup di database. Il motivo è che i pacchetti di rete usati per i trasferimenti di file o i backup di database hanno la priorità "migliore sforzo".

> [!NOTE]
> Come regola generale, QoS si applica solo alle sessioni di comunicazione nella rete interna. Quando si implementa QoS, si configurano i server e i router per supportare il contrassegno dei pacchetti in modo particolare che potrebbe non essere supportato in Internet o in altre reti. Anche se la qualità del servizio è supportata in altre reti, non c'è alcuna garanzia che la QoS venga configurata esattamente nello stesso modo in cui è stato configurato il servizio. Se si usa MPLS, è necessario collaborare con il provider MPLS.

Skype for Business Server non richiede QoS, ma è vivamente consigliato. Se si verificano problemi di perdita di pacchetti nella rete, le soluzioni disponibili sono per aggiungere più larghezza di banda o per implementare QoS. Se non è possibile aggiungere più larghezza di banda, l'implementazione di QoS potrebbe essere l'unico tributo per risolvere il problema.

Skype for Business Server offre il supporto completo per QoS: ciò significa che le organizzazioni che già usano QoS possono integrare facilmente Skype for Business Server nell'infrastruttura di rete esistente. Per eseguire questa operazione è necessario seguire questa procedura:

- [Abilitazione di QoS in Skype for Business Server per dispositivi che non sono basati su Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Per impostazione predefinita, QoS è disabilitato per i computer e altri dispositivi (ad esempio iPhone) che eseguono altri sistemi operativi. Anche se puoi usare Skype for Business Server per abilitare e disabilitare la qualità del servizio per i dispositivi, in genere non puoi usare il prodotto per modificare i codici DSCP usati da questi dispositivi.

- [Configurazione di intervalli di porte e criteri di qualità dei servizi per i server di conferenza, applicazione e mediazione](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). È necessario prenotare un set di porte univoco per tipi di pacchetto diversi, ad esempio audio e video. Usando Skype for Business Server non è possibile abilitare o disabilitare QoS impostando un valore di proprietà su true o su false. Puoi invece abilitare QoS configurando gli intervalli di porte e quindi creando e applicando criteri di gruppo. Se in seguito si decide di non usare QoS, è possibile disabilitare il QoS rimuovendo gli oggetti Criteri di gruppo appropriati.

- [Configurazione di intervalli di porte e di criteri di qualità dei servizi per i server perimetrali](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Anche se non è necessario, è possibile configurare gli Edge Server in modo da usare gli stessi intervalli di porte degli altri server. La configurazione di un criterio QoS verrà eseguita solo per il lato interno degli Edge Server. Questo perché QoS è progettato per l'uso nella rete interna e non in Internet.

- [Configurare gli intervalli di porte e i criteri di qualità dei servizi per i clienti in Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Questi intervalli di porte si applicano solo ai computer client e sono in genere diversi dagli intervalli di porte configurati nei server. Tieni presente che Skype for Business Server non supporta QoS per sistemi operativi Windows diversi da Windows 10.


> [!NOTE]
> Se si usa Windows Server 2012 o Windows Server 2012 R2, potrebbe essere interessante il nuovo set di cmdlet di Windows PowerShell disponibile per la gestione del QoS su tale piattaforma. Per altre informazioni, vedere [cmdlet QoS di rete in Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

La QoS viene discussa anche nel whitepaper [pianificazione, monitoraggio e risoluzione dei problemi con Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) con dettagli e profondità aggiuntivi. Mentre il contenuto si riferisce esplicitamente a Lync 2010 e Lync 2013, le considerazioni per Skype for Business Server sono invariate.

## <a name="see-also"></a>Vedere anche
<a name="man_QOS"> </a>

[Pianificare IPv6 in Skype for Business](ipv6.md)

[Requisiti per il bilanciamento del carico per Skype for Business](load-balancing.md)

[Requisiti DNS per Skype for Business Server](dns.md)
