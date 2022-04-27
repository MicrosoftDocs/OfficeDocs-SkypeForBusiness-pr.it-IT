---
title: Classificazione del flusso in Call Quality Dashboard (CQD)
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Scopri come viene classificata la qualità del flusso nel Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059257"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificazione flusso in Call Quality Dashboard (CQD)

Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business Online consente di ottenere informazioni approfondite sulla qualità delle chiamate effettuate con Microsoft Teams e servizi di Skype for Business. Questo argomento fornisce informazioni dettagliate sulla classificazione di qualità delle trasmissione multimediali. Per altre informazioni su Call Quality Dashboard e su come configurarlo, vedi [Configurare Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definizioni di classificatore

Flussi in Call Quality Dashboard vengono classificate come _Buone_, _Scadenti_ o _Non classificate_ in base ai valori delle metriche di qualità chiave disponibili. Le metriche e le condizioni usate per classificare il flusso vengono visualizzate nelle tabelle successive. Le dimensioni "Poor Due To" di Call Quality Dashboard possono essere usate per capire quale metrica è responsabile di una classificazione _scadente_ . Per ulteriori informazioni su queste dimensioni, vedere [Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificatore audio

Se vengono soddisfatte una o più delle condizioni seguenti e Utilizzo pacchetti è > 500 pacchetti, un flusso audio viene contrassegnato come _scadente_:

|Metrica|Scenario|Condizione|Spiegazione|
|:-----|:-----|:-----|:-----|
|Round Trip|TUTTI|> 500|Tempo medio di propagazione della rete round-trip, calcolato in millisecondi. Dettagli disponibili in [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|TUTTI|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Jitter|TUTTI|> 30|Jitter medio dello stream in millisecondi.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificatore video a causa del blocco

Il flusso video è contrassegnato come  _Buono_ o _Scadente_ in base al valore di un punteggio di classificatore generato per stimare che l'utente finale abbia provato Video bloccato. Questo classificatore è disponibile solo per Microsoft Teams prodotto.

|Passaggio #|Metrica|Scenario|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Un punteggio compreso tra 0 e 1 generato in base a una combinazione di esperienza utente, blocca le statistiche di durata e l'esperienza di chiamata complessiva |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Un punteggio compreso tra 0 e 1 generato in base a una combinazione di esperienza utente, blocca le statistiche di durata e l'esperienza di chiamata complessiva |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificatore video
Un flusso video è contrassegnato come _Buono_ o _Scadente_ in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio #|Metrica|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include frame recuperati da perdite di rete.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita di pacchetti dopo l'applicazione aggregata di FEC in tutti i codec e i flussi video.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificatore VBSS

Un flusso VBSS è contrassegnato come _Buono_ o _Scadente_ in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio # |Metrica |Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|Codec is NOT H264S</br>E</br>StreamDirection è in ingresso</br></br>Se FrameLoss > 50%|_Poor_|_Good_|_Unclassified_|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include frame recuperati da perdite di rete. FrameLoss viene usato solo per classificare flussi in ingresso non H264S.|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione. Si applica a tutti i flussi in uscita e a StreamDirection per H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Un flusso di condivisione applicazioni viene contrassegnato come _scadente_ se vengono soddisfatte una o più delle condizioni seguenti:

| Metrica     | Condizione | Spiegazione |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Percentuale di riquadri rimossi anziché inviati a un peer remoto (ad esempio, dalla MCU a un visualizzatore). I riquadri rimossi (o danneggiati) potrebbero essere causati da restrizioni di larghezza di banda tra client e server. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latenza media in millisecondi dell'elaborazione tile sullo stack PDR presso il server conferenze. |
| AppSharing Relative OneWay Average | > 1,75 | Ritardo unidirezionale relativo medio tra gli endpoint in secondi per i flussi di condivisione applicazioni. |
| | | |

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In Call Quality Dashboard un flusso è contrassegnato come _Non classificato_ quando la connettività ICE (Interactive Connectivity Establishment) non riesce o quando non vengono riportate tutte le metriche necessarie per calcolare la classificazione del flusso.

Per verificare la presenza di errori di connettività ICE, esaminare le dimensioni "First Connectivity Ice" e "Second Connectivity Ice" per un valore "FAILED". Se uno dei due valori indica un errore, il flusso viene contrassegnato come _Non classificato_.

Se la connettività ICE è riuscita per un flusso _non classificato_ , è probabile che il flusso sia considerato _non classificato_ perché non sono state segnalate metriche di flusso chiave. Ci sono alcuni motivi per cui queste metriche potrebbero non essere riportate:

- **I report QoE non sono stati ricevuti** - Le metriche usate per la classificazione vengono riportate in un report QoE inviato alla fine di una chiamata. Se questo report non viene prodotto (ad esempio perché alcuni endpoint di terze parti potrebbero non inviare QoE) o non è stato possibile inviarlo (ad esempio a causa di un'interruzione di rete), Call Quality Dashboard non è in grado di classificare il flusso.

  > [!TIP]
  > La dimensione "QoE Record Available" può essere utilizzata per determinare se un report QoE è stato ricevuto per una trasmissione. Questa dimensione avrà il valore "True" se un report QoE è stato ricevuto da entrambi gli endpoint. Un report QoE da entrambi gli endpoint è necessario per la segnalazione più accurata delle metriche.

- **Chiamate brevi** : le chiamate brevi potrebbero non avere un'attività multimediale sufficiente per calcolare le metriche di flusso chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.

  > [!TIP]
  > Le dimensioni "Durata (secondi)", "Durata (minuti)", "Durata 5 secondi o meno" e "Durata 60 secondi o più" possono essere utilizzate per determinare la durata di una trasmissione. La misura "Durata chiamata media" può anche essere utilizzata per calcolare la durata media di un insieme di trasmissioni.

- **Utilizzo dei pacchetti basso** : come lo scenario di "short call", è necessario un utilizzo sufficiente dei pacchetti per il calcolo delle metriche di flusso chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.
  - Uno scenario comune di utilizzo dei pacchetti basso si verifica quando un partecipante partecipa a una riunione per ascoltare il relatore, ma non parla mai (il microfono è disattivato per la maggior parte della chiamata). Qui, il flusso audio in ingresso al client ha un utilizzo elevato dei pacchetti, mentre il flusso audio in uscita dal client ha un utilizzo poco o nessun pacchetto. La durata dello stream può essere di un'ora o più, ma l'utilizzo del pacchetto nel flusso dal client al server è basso perché il microfono è stato disattivato e i risultati di un flusso _non classificato_ .

  > [!TIP]
  > La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.

## <a name="related-topics"></a>Argomenti correlati
[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)
