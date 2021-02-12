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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Scopri come la qualità dello stream viene classificata nel Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business online.
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909040"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificazione del flusso in Call Quality Dashboard (CQD)

Call Quality Dashboard (CQD) per Microsoft Teams e Skype for Business Online consente di ottenere informazioni approfondite sulla qualità delle chiamate effettuate con Microsoft Teams e i servizi di Skype for Business. Questo argomento fornisce informazioni dettagliate sulla classificazione della qualità dei flussi multimediali. Per ulteriori informazioni su CQD e su come configurarlo, consulta [Configurare Call Quality Dashboard.](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Definizioni di classificatore

I flussi in CQD sono classificati come _Buono,_ Scadente o _Non_ classificato in base ai valori delle metriche di qualità chiave disponibili. Le metriche e le condizioni usate per classificare lo stream vengono visualizzate nelle tabelle seguenti. Le dimensioni "Scarso a causa di" di CQD possono essere usate per comprendere quale metrica è responsabile di una _classificazione di_ scarsa qualità. Per ulteriori informazioni su queste dimensioni, consulta [Dimensioni e misure disponibili in Call Quality Dashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Classificatore audio

Se vengono soddisfatte una o più delle condizioni seguenti, uno stream audio viene contrassegnato come _scadente:_

|Metrica|Scenario|Condizione|Spiegazione|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|La descrizione del payload non è SATIN|> 1,0|Media del Mean Opinion Score di rete per la degradazione dello stream. Quante perdite di rete e instabilità hanno incideto sulla qualità dell'audio ricevuto.|
|Round Trip|ALL|> 500|Tempo medio di propagazione della rete round trip calcolato in millisecondi. Dettagli disponibili in [RFC3550.](https://tools.ietf.org/html/rfc3550)|
|Packet Loss Rate|ALL|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Jitter|ALL|> 30|Jitter medio dello stream in millisecondi.|
|Ratio Concealed Samples Avg|La descrizione del payload non è SATIN|> 0,07|Rapporto medio del numero di frame audio con campioni nascosti generati dalla perdita di pacchetti e dal numero totale di frame audio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Video Classifier due to Freeze

Il flusso video è  _contrassegnato_ come Buono o Scadente in base al valore del punteggio di un classificatore generato per stimare che l'utente finale ha provato il video bloccato. Questo classificatore è disponibile solo per il prodotto Microsoft Teams.

|Passaggio #|Metrica|Scenario|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Un punteggio compreso tra 0 e 1 generato sulla base di una combinazione di esperienza utente, bloccare le statistiche di durata e l'esperienza di chiamata complessiva |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Un punteggio compreso tra 0 e 1 generato sulla base di una combinazione di esperienza utente, bloccare le statistiche di durata e l'esperienza di chiamata complessiva |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificatore video
Un flusso video viene _contrassegnato_ come Buono o Scadente _in_ base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio #|Metrica|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i frame recuperati dalle perdite di rete.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita pacchetti dopo l'applicazione di FEC aggregato in tutti i codec e gli stream video.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificatore VBSS

Un flusso VBSS  è  contrassegnato come Buono o Scadente in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio # |Metrica |Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i frame recuperati dalle perdite di rete.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita pacchetti dopo l'applicazione di FEC aggregato in tutti i codec e gli stream video.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Un flusso di condivisione applicazioni viene contrassegnato come _scadente_ se vengono soddisfatte una o più delle condizioni seguenti:

| Metrica     | Condizione | Spiegazione |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Percentuale di riquadri scartati invece di essere inviati a un peer remoto, ad esempio dalla MCU a un visualizzatore. Le sezioni scartate (o spoiled) potrebbero essere causate da limitazioni di larghezza di banda tra client e server. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latenza media in millisecondi dell'elaborazione tile sullo stack PDR presso il server conferenze. |
| AppSharing Relative OneWay Average | > 1,75 | Ritardo unidirezionare relativo medio tra gli endpoint in secondi per i flussi di condivisione applicazioni. |
| | | |

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In CQD, un flusso è contrassegnato come _Nonclassificato_ quando la connettività ICE (Interactive Connectivity Connectivity connectivity) non riesce o quando non sono riportate tutte le metriche necessarie per calcolare la classificazione dello stream.

Per verificare la presenza di errori di connettività ICE, esaminare le dimensioni "First Connectivity Ice" e "Second Connectivity Ice" per un valore "FAILED". Se uno dei due valori indica un errore, lo stream viene contrassegnato _come Non classificato._

Se la connettività ICE per un flusso _non_ classificato è riuscita, è probabile che lo stream sia considerato _non_ classificato perché le metriche di flusso principali non sono state riportate. Ci sono alcuni motivi per cui queste metriche potrebbero non essere riportate:

- **I rapporti QoE non sono** stati ricevuti: le metriche usate per la classificazione sono riportate in un report QoE inviato al termine di una chiamata. Se questo report non viene prodotto (ad esempio perché alcuni endpoint di terze parti non possono inviare QoE) o non può essere inviato (ad esempio a causa di un'interruzione di rete), CQD non è in grado di classificare lo stream.

  > [!TIP]
  > La dimensione "QoE Record Available" può essere utilizzata per determinare se un report QoE è stato ricevuto per una trasmissione. Questa dimensione avrà il valore "True" se un report QoE è stato ricevuto da entrambi gli endpoint. Un report QoE da entrambi gli endpoint è necessario per la segnalazione più accurata delle metriche.

- **Chiamate brevi: le** chiamate brevi potrebbero non avere un'attività multimediale sufficiente per calcolare le metriche di flusso chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.

  > [!TIP]
  > Le dimensioni "Durata (secondi)", "Durata (minuti)", "Durata 5 secondi o meno" e "Durata 60 secondi o più" possono essere utilizzate per determinare la durata di una trasmissione. La misura "Durata chiamata media" può anche essere utilizzata per calcolare la durata media di un insieme di trasmissioni.

- **Utilizzo ridotto dei pacchetti:** come per lo scenario di "chiamata breve", è necessario utilizzare pacchetti sufficienti per il calcolo delle metriche dei flussi chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.
  - Uno scenario comune di utilizzo pacchetti basso si verifica quando un partecipante partecipa a una riunione per ascoltare il relatore, ma non parla mai (il microfono è disattivato per la maggior parte della chiamata). Qui, il flusso audio in ingresso al client ha un utilizzo elevato dei pacchetti, mentre il flusso audio in uscita dal client ha poco o nessun utilizzo di pacchetti. La durata dello stream può essere di un'ora o più, ma l'utilizzo del pacchetto sullo stream  dal client al server è basso perché l'audio del microfono era disattivato e i risultati di uno stream non classificato.

  > [!TIP]
  > La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.

## <a name="related-topics"></a>Argomenti correlati
[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Usare Call Quality Quality Call per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)
