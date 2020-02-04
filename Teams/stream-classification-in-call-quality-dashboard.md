---
title: Classificazione trasmissione nel Dashboard Qualità della chiamata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
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
- NOCSH
ms.custom:
- Optimization
description: Scopri come la qualità della trasmissione è classificata nel Dashboard Qualità della chiamata di Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: 49063ab0e957a0afee256fb0e5500d0f2b2a8ae6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680533"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classificazione trasmissione nel Dashboard Qualità della chiamata

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definizioni di classificatore

I flussi in Call Quality dashboard sono classificati come _buoni_, _poveri_o non _classificati_ in base ai valori delle metriche di qualità chiave disponibili. Le metriche e le condizioni usate per classificare il flusso vengono visualizzate nelle tabelle seguenti. Le dimensioni "povero a causa di" di Call Quality dashboard possono essere usate per capire quale metrica è responsabile di una classificazione _scadente_ . Per altre informazioni su queste dimensioni, vedere [dimensioni e misure disponibili nel dashboard qualità chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificatore audio

Se vengono soddisfatte una o più delle condizioni seguenti, un flusso audio viene contrassegnato come _scadente_:

|Metrica|Condizione|Spiegazione|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Media Network valutazione della degradazione del Punteggio di opinione per Stream. La quantità di perdite di rete e jitter ha influenzato la qualità dell'audio ricevuto.|
|Round Trip|> 500|Media del tempo di propagazione della rete di andata e ritorno, calcolata in millisecondi. Dettagli disponibili in [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Jitter|> 30|Jitter medio dello stream in millisecondi.|
|Ratio Concealed Samples Avg|> 0,07|Rapporto medio del numero di fotogrammi audio con campioni nascosti generati dalla perdita di pacchetti per la guarigione del numero totale di fotogrammi audio.|
||||

### <a name="video-classifier"></a>Classificatore video

Un flusso video è contrassegnato come _buono_ o _scarso_ in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio #|Metrica|Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i fotogrammi recuperati da perdite di rete.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita di pacchetti dopo che FEC è stato applicato in tutti i flussi video e i codec.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificatore VBSS

Un flusso VBSS è contrassegnato come _buono_ o _scarso_ in base al valore della prima metrica disponibile nell'ordine seguente:

|Passaggio # |Metrica |Condizione |Classificazione se la condizione è vera |Classificazione se la condizione è falsa |Classificazione se la metrica non è disponibile |Spiegazione |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Andare al passaggio 2|Percentuale media di fotogrammi video persi come visualizzato all'utente. La media include i fotogrammi recuperati da perdite di rete.|
|2|Video Frame Rate Avg|< 2|_Poor_|_Good_|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|_Poor_|_Good_|_Unclassified_|Tasso di perdita di pacchetti dopo che FEC è stato applicato in tutti i flussi video e i codec.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Un flusso di condivisione delle applicazioni viene contrassegnato come _scadente_ se vengono soddisfatte una o più delle condizioni seguenti:

| Metrica     | Condizione | Spiegazione |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Percentuale di riquadri scartati anziché inviati a un peer remoto, ad esempio dalla MCU a un visualizzatore. I riquadri scartati (o viziati) potrebbero essere causati da restrizioni della larghezza di banda tra client e server. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latenza media in millisecondi dell'elaborazione tile sullo stack PDR presso il server conferenze. |
| AppSharing Relative OneWay Average | > 1,75 | Ritardo unidirezionale relativo medio tra gli endpoint in secondi per i flussi di condivisione applicazioni. |
| | | |

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In Call Quality dashboard un flusso è contrassegnato come non _Classificato_ quando la connettività Interactive Connectivity Establishment (Ice) non riesce o quando tutte le metriche necessarie per calcolare la classificazione del flusso non vengono segnalate.

Per verificare la presenza di errori di connettività ICE, esaminare le dimensioni "First Connectivity Ice" e "Second Connectivity Ice" per un valore "FAILED". Se uno dei due valori indica un errore, il flusso viene contrassegnato come non _Classificato_.

Se la connettività ICE è riuscita per un flusso non _Classificato_ , il flusso è probabilmente considerato non _Classificato_ perché le metriche del flusso di tasti non sono state segnalate. Ci sono alcuni motivi per cui queste metriche potrebbero non essere riportate:

- I **report QoE non sono stati ricevuti** : le metriche usate per la classificazione vengono segnalate in un report QoE inviato alla fine di una chiamata. Se il report non viene prodotto, ad esempio perché alcuni endpoint di terze parti potrebbero non inviare QoE o non possono essere inviati, ad esempio a causa di un'interruzione di rete, Call Quality Dashboard non è in grado di classificare il flusso.

> [!TIP]
> La dimensione "QoE Record Available" può essere utilizzata per determinare se un report QoE è stato ricevuto per una trasmissione. Questa dimensione avrà il valore "True" se un report QoE è stato ricevuto da entrambi gli endpoint. Un report QoE da entrambi gli endpoint è necessario per la segnalazione più accurata delle metriche.

- **Chiamate brevi** : le chiamate brevi potrebbero non avere abbastanza attività multimediali per calcolare le metriche del flusso di tasti. Senza queste metriche, CQD non è in grado di classificare la trasmissione.

> [!TIP]
> Le dimensioni "Durata (secondi)", "Durata (minuti)", "Durata 5 secondi o meno" e "Durata 60 secondi o più" possono essere utilizzate per determinare la durata di una trasmissione. La misura "Durata chiamata media" può anche essere utilizzata per calcolare la durata media di un insieme di trasmissioni.

- **Basso utilizzo di pacchetti** , ad esempio lo scenario "chiamata breve", è necessario un sufficiente utilizzo dei pacchetti per il calcolo delle metriche del flusso di chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.
  - Uno scenario di utilizzo dei pacchetti basso comune si verifica quando un partecipante partecipa a una riunione per ascoltare il relatore, ma non parla mai (il microfono è disattivato per la maggior parte della chiamata). In questo caso, il flusso audio in ingresso al client ha un elevato utilizzo dei pacchetti mentre il flusso audio in uscita dal client non ha un utilizzo di pacchetti limitato. La durata del flusso può essere di un'ora o più, ma l'utilizzo del pacchetto nel flusso dal client al server è basso, poiché il microfono è stato disattivato e i risultati di un flusso non _Classificato_ .

> [!TIP]
> La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.

## <a name="related-topics"></a>Argomenti correlati

[Attivazione e utilizzo di Call Quality Dashboard (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Uso dell'analisi delle chiamate per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)
