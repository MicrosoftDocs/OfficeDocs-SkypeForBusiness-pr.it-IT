---
title: Classificazione dei flussi in Call Quality Dashboard (CQD)
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
description: Scopri come viene classificata la qualità dello stream nel Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: 21de07e2b590bafcb7de65495e6b7d68faa381cc
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767199"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificazione dei flussi in Call Quality Dashboard (CQD)

Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business Online consente di ottenere informazioni approfondite sulla qualità delle chiamate effettuate usando Microsoft Teams e Skype for Business servizi. Questo argomento fornisce informazioni dettagliate sulla classificazione di qualità delle trasmissione multimediali. Per altre informazioni su CQD e su come configurarlo, vedere [Configurare call quality dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definizioni di classificatore

Flussi in CQD sono classificate come _Buone,_ Scarse o _Non_ classificate in base ai valori delle metriche di qualità chiave disponibili. Le metriche e le condizioni usate per classificare lo stream vengono visualizzate nelle tabelle seguenti. Le dimensioni "Scarso a causa di" di CQD possono essere usate per comprendere quale metrica è responsabile di una _classificazione Poor._ Per altre informazioni su queste dimensioni, vedere [Dimensioni e misure disponibili in Call Quality Dashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Classificatore audio

Se vengono soddisfatte una o più delle condizioni seguenti, un flusso audio viene contrassegnato come _Poor_:

|Metrica|Scenario|Condizione|Spiegazione|
|:-----|:-----|:-----|:-----|
|Round Trip|TUTTI|> 500|Tempo medio di propagazione della rete round trip, calcolato in millisecondi. Dettagli disponibili in [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|TUTTI|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Jitter|TUTTI|> 30|Jitter medio dello stream in millisecondi.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Classifier due to Freeze

Lo stream video è contrassegnato  _come_ Buono o Scadente _in_ base al valore di un punteggio del classificatore generato per stimare che l'utente finale ha provato Frozen Video. Questo classificatore è disponibile solo per Microsoft Teams prodotto.

|Passaggio #|Metrica|Scenario|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Punteggio compreso tra 0 e 1 generato in base a una combinazione di esperienza utente, statistiche sulla durata del blocco e esperienza di chiamata generale |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Punteggio compreso tra 0 e 1 generato in base a una combinazione di esperienza utente, statistiche sulla durata del blocco e esperienza di chiamata generale |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificatore video
Un flusso video viene _contrassegnato_ come Buono _o_ Scadente in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio #|Metrica|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i frame recuperati dalle perdite di rete.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita dei pacchetti dopo l'applicazione di FEC aggregato in tutti i flussi video e i codec.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificatore VBSS

Un flusso VBSS  viene  contrassegnato come Buono o Scadente in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio # |Metrica |Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|Il codec NON è H264S</br>E</br>StreamDirection è Inbound</br></br>Se FrameLoss > 50%|_Poor_|_Good_|_Unclassified_|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i frame recuperati dalle perdite di rete. FrameLoss viene usato solo per classificare i flussi non H264S in ingresso.|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione. Si applica a tutti i flussi in uscita e a StreamDirection per H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Un flusso di condivisione applicazioni è contrassegnato _come Scadente_ se vengono soddisfatte una o più delle condizioni seguenti:

| Metrica     | Condizione | Spiegazione |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Percentuale di riquadri che vengono eliminati invece di essere inviati a un peer remoto, ad esempio dalla MCU a un visualizzatore. I riquadri eliminati (o viziati) potrebbero essere causati da restrizioni di larghezza di banda tra client e server. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latenza media in millisecondi dell'elaborazione tile sullo stack PDR presso il server conferenze. |
| AppSharing Relative OneWay Average | > 1,75 | Ritardo unidirezionare relativo medio tra gli endpoint in secondi per i flussi di condivisione delle applicazioni. |
| | | |

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In CQD, un  flusso viene contrassegnato come Non classificato quando la connettività ICE (Interactive Connectivity Establishment) non riesce o quando non vengono segnalate tutte le metriche necessarie per calcolare la classificazione dello stream.

Per verificare la presenza di errori di connettività ICE, esaminare le dimensioni "First Connectivity Ice" e "Second Connectivity Ice" per un valore "FAILED". Se uno dei due valori indica un errore, lo stream viene contrassegnato _come Unclassified_.

Se la connettività ICE ha avuto esito positivo per un flusso _non_ classificato, è probabile che lo stream sia considerato _non_ classificato perché le metriche del flusso chiave non sono state segnalate. Ci sono alcuni motivi per cui queste metriche potrebbero non essere riportate:

- **I report QoE non sono stati** ricevuti: le metriche usate per la classificazione vengono riportate in un report QoE inviato al termine di una chiamata. Se il report non viene prodotto, ad esempio perché alcuni endpoint di terze parti potrebbero non inviare QoE o non è stato possibile inviarlo, ad esempio a causa di un'interruzione di rete, CQD non è in grado di classificare lo stream.

  > [!TIP]
  > La dimensione "QoE Record Available" può essere utilizzata per determinare se un report QoE è stato ricevuto per una trasmissione. Questa dimensione avrà il valore "True" se un report QoE è stato ricevuto da entrambi gli endpoint. Un report QoE da entrambi gli endpoint è necessario per la segnalazione più accurata delle metriche.

- **Chiamate brevi:** le chiamate brevi potrebbero non avere attività multimediali sufficienti per calcolare le metriche di flusso chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.

  > [!TIP]
  > Le dimensioni "Durata (secondi)", "Durata (minuti)", "Durata 5 secondi o meno" e "Durata 60 secondi o più" possono essere utilizzate per determinare la durata di una trasmissione. La misura "Durata chiamata media" può anche essere utilizzata per calcolare la durata media di un insieme di trasmissioni.

- **Basso utilizzo dei pacchetti: come** nello scenario di "chiamata breve", è necessario un utilizzo sufficiente dei pacchetti per il calcolo delle metriche del flusso chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.
  - Uno scenario comune di utilizzo basso dei pacchetti si verifica quando un partecipante partecipa a una riunione per ascoltare il relatore, ma non parla mai (il microfono è disattivato per la maggior parte della chiamata). In questo caso, il flusso audio in ingresso al client ha un utilizzo elevato dei pacchetti, mentre il flusso audio in uscita dal client ha un utilizzo dei pacchetti poco o nessun valore. La durata dello stream può essere di un'ora o più, ma l'utilizzo dei pacchetti nel flusso  dal client al server è basso perché il microfono è stato disattivato e viene restituito uno stream non classificato.

  > [!TIP]
  > La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.

## <a name="related-topics"></a>Argomenti correlati
[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload tenant e edificio](CQD-upload-tenant-building-data.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)
