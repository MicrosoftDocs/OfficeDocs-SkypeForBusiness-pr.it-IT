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
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Scopri come la qualità della trasmissione è classificata nel Dashboard Qualità della chiamata di Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: ad18b15019ed82d629a4c32c27544d052cd2bc92
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182395"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classificazione trasmissione nel Dashboard Qualità della chiamata

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definizioni di classificatore

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Classificatore audio

Una trasmissione audio è contrassegnata come scarsa se sono soddisfatte una o più delle seguenti condizioni:

|**Metrica**|**Condizione**|**Spiegazione**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|> 500|Tempo medio di round trip di propagazione di rete come specificato in RFC3550 in millisecondi.|
|Packet Loss Rate|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Jitter|> 30|Jitter medio dello stream in millisecondi.|
|Ratio Concealed Samples Avg|> 0,07|Rapporto medio del numero di fotogrammi audio con campioni nascosti generati dalla perdita di pacchetti per la guarigione del numero totale di fotogrammi audio.|

### <a name="video-classifier"></a>Classificatore video

Una trasmissione video è contrassegnata come buona o scarsa in base al valore della prima metrica disponibile nell'ordine seguente:

|**Passaggio #**|**Metrica**|**Condizione**|**Classificazione se la condizione è vera**|**Classificazione se la condizione è falsa**|**Classificazione se la metrica non è disponibile**|**Spiegazione**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Andare al passaggio 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Tasso di perdita di pacchetti dopo che FEC è stato applicato in tutti i flussi video e i codec.|

### <a name="vbss-classifier"></a>Classificatore VBSS

Una trasmissione VBSS è contrassegnata come buona o scarsa in base al valore della prima metrica disponibile nel seguente ordine:

|**Passaggio #**|**Metrica**|**Condizione**|**Classificazione se la condizione è vera**|**Classificazione se la condizione è falsa**|**Classificazione se la metrica non è disponibile**|**Spiegazione**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Andare al passaggio 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Andare al passaggio 3|Media dei fotogrammi al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Tasso di perdita di pacchetti dopo che FEC è stato applicato in tutti i flussi video e i codec.|

### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Una trasmissione di condivisione applicazioni è contrassegnata come scarsa se sono soddisfatte una o più delle seguenti condizioni:


| **Metrica**                                     | **Condizione** | **Spiegazione**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Latenza media in millisecondi dell'elaborazione tile sullo stack PDR presso il server conferenze.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Ritardo unidirezionale relativo medio tra gli endpoint in secondi per i flussi di condivisione applicazioni.                                                                                                                       |

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In CQD, una trasmissione è contrassegnata come non classificato quando la connettività ICE non riesce o quando tutte le metriche richieste per calcolare la classificazione della trasmissione non vengono segnalate.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.


## <a name="related-topics"></a>Argomenti correlati
[Attivazione e utilizzo di Call Quality Dashboard (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Dimensioni e misure disponibili in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)
