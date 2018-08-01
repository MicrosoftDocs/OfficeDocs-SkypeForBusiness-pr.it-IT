---
title: Classificazione trasmissione nel Dashboard Qualità della chiamata
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Scopri come la qualità della trasmissione è classificata nel Dashboard Qualità della chiamata di Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: a77ca0605589c99b88ba3287bf8febcc7514cbd1
ms.sourcegitcommit: e5a54e2ead0edd9e450bbed4b6e50b3cfd2e91c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2018
ms.locfileid: "21645309"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classificazione trasmissione nel Dashboard Qualità della chiamata

Il Dashboard Qualità della chiamata (DQC) per Microsoft Teams e Skype for Business online ti consente di analizzare la qualità delle chiamate effettuate con i servizi Microsoft Teams e Skype for Business. Questo argomento fornisce informazioni dettagliate sulla classificazione di qualità delle trasmissione multimediali. Per sapere di più sul DQC e sul modo di attivarlo, consulta [Attivazione e utilizzo di Dashboard Qualità della chiamata](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definizioni di classificatore

Le trasmissioni in DQC sono classificate come buone, scarse o non classificate in base ai valori delle metriche di qualità chiave disponibili. Le metriche e le condizioni utilizzate per classificare le trasmissioni sono mostrate nelle tabelle seguenti. Le dimensioni "Scarsa a causa di" di DQC possono essere utilizzate per capire quale metrica è responsabile di una classificazione scarsa. Per maggiori informazioni su queste dimensioni, consultare [Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificatore audio

Una trasmissione audio è contrassegnata come scarsa se sono soddisfatte una o più delle seguenti condizioni:

|**Metrica**|**Condizione**|**Spiegazione**|
|:-----|:-----|:-----|
|Media della degradazione audio|> 1,0|Media del Mean Opinion Score di rete per la degradazione dello stream. Rappresenta l'entità dell'impatto esercitato dalla perdita di rete e dall'instabilità sulla qualità dell'audio ricevuto.|
|Round Trip|> 500|Tempo medio di round trip di propagazione di rete come specificato in RFC3550, in millisecondi.|
|Tasso di perdita di pacchetti|> 0,1|Percentuale media di perdita pacchetti dello stream.|
|Instabilità|> 30|Instabilità media dello stream in millisecondi.|
|Rapporto medio campioni nascosti|> 0,07|Rapporto medio del numero di frame audio con campioni nascosti generati dalla compensazione di perdita di pacchetti rispetto al numero totale di frame audio.|

### <a name="video-classifier"></a>Classificatore video

Una trasmissione video è contrassegnata come buona o scarsa in base al valore della prima metrica disponibile nell'ordine seguente:

|**Passaggio #**|**Metrica**|**Condizione**|**Classificazione se la condizione è vera**|**Classificazione se la condizione è falsa**|**Classificazione se la metrica non è disponibile**|**Spiegazione**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Percentuale media di perdita di frame video locale|> 50% |Scarsa|Buona|Andare al passaggio 2|Percentuale media di frame video persi come visualizzato all'utente. Sono inclusi i frame ripristinati dalle perdite di rete.|
|2|Percentuale media frame video|< 7|Scarsa|Buona|Andare al passaggio 3|Media dei frame al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|Scarsa|Buona|Non classificata|Il tasso di perdita di pacchetti dopo l'applicazione di FEC in aggregato in tutti i codec e gli stream video.|

### <a name="vbss-classifier"></a>Classificatore VBSS

Una trasmissione VBSS è contrassegnata come buona o scarsa in base al valore della prima metrica disponibile nel seguente ordine:

|**Passaggio #**|**Metrica**|**Condizione**|**Classificazione se la condizione è vera**|**Classificazione se la condizione è falsa**|**Classificazione se la metrica non è disponibile**|**Spiegazione**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Percentuale media di perdita di frame video locale|> 50% |Scarsa|Buona|Andare al passaggio 2|Percentuale media di frame video persi come visualizzato all'utente. Sono inclusi i frame ripristinati dalle perdite di rete.|
|2|Percentuale media frame video|< 2|Scarsa|Buona|Andare al passaggio 3|Media dei frame al secondo ricevuti per uno stream video, calcolata per tutta la durata della sessione.|
|3|Video Post FECPLR|> 0,15|Scarsa|Buona|Non classificata|Il tasso di perdita di pacchetti dopo l'applicazione di FEC in aggregato in tutti i codec e gli stream video.|

### <a name="application-sharing-classifier"></a>Classificatore di condivisione applicazioni

Una trasmissione di condivisione applicazioni è contrassegnata come scarsa se sono soddisfatte una o più delle seguenti condizioni:

**Metrica**|**Condizione**|**Spiegazione**|
|:-----|:-----|:-----|
|Totale percentuale sezioni danneggiate|> 36|Percentuale di sezioni che vengono scartate invece di essere inviate ad un peer remoto (ad esempio, dalla MCU a un visualizzatore). Le sezioni possono essere scartate (o danneggiate) a causa di limitazioni di larghezza di banda tra il client e il server.|
|Latenza media elaborazione sezioni RDP condivisione applicazioni|> 400|Latenza media in millisecondi dell'elaborazione di sezioni sullo stack PDR presso il server conferenze.|
|Media unidirezionale relativa condivisione applicazioni|> 1,75|Ritardo relativo unidirezionale medio tra gli endpoint in millisecondi per le trasmissioni di condivisione delle applicazioni.|

## <a name="unclassified-streams"></a>Trasmissioni non classificate

In CQD, una trasmissione è contrassegnata come non classificato quando la connettività ICE non riesce o quando tutte le metriche richieste per calcolare la classificazione della trasmissione non vengono segnalate.

Per verificare la presenza di errori di connettività ICE, esaminare le dimensioni "First Connectivity Ice" e "Second Connectivity Ice" per un valore "FAILED". Se uno dei due valori indica un errore, la trasmissione verrà contrassegnata come non classificata.

Se la connettività ICE è riuscita per una trasmissione non classificata, la trasmissione è probabilmente considerata non classificata poiché le metriche della trasmissione chiave non sono state segnalate. Ci sono alcuni motivi per cui queste metriche potrebbero non essere riportate:

- **I report QoE non sono stati ricevuti** - Le metriche utilizzate per la classificazione sono riportate in un report QoE inviato alla fine di una chiamata. Se questo report non viene prodotto (ad esempio, perché alcuni endpoint di terze parti potrebbero non inviare QoE) o non è stato possibile inviarlo (ad esempio, a causa di un'interruzione della rete), CQD non è in grado di classificare la trasmissione.

> [!TIP]
> La dimensione "QoE Record Available" può essere utilizzata per determinare se un report QoE è stato ricevuto per una trasmissione. Questa dimensione avrà il valore "True" se un report QoE è stato ricevuto da entrambi gli endpoint. Un report QoE da entrambi gli endpoint è necessario per la segnalazione più accurata delle metriche.

- **Chiamate brevi** - Le chiamate brevi potrebbero non avere abbastanza attività multimediali per calcolare le metriche della trasmissione chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.

> [!TIP]
> Le dimensioni "Durata (secondi)", "Durata (minuti)", "Durata 5 secondi o meno" e "Durata 60 secondi o più" possono essere utilizzate per determinare la durata di una trasmissione. La misura "Durata chiamata media" può anche essere utilizzata per calcolare la durata media di un insieme di trasmissioni.

- **Basso utilizzo dei pacchetti** - Come lo scenario "chiamata breve", un utilizzo di pacchetti sufficiente è necessario per il calcolo delle metriche della trasmissione chiave. Senza queste metriche, CQD non è in grado di classificare la trasmissione.
    - Uno scenario comune di basso utilizzo dei pacchetti si verifica quando un utente partecipa a una riunione per ascoltare il relatore ma non parla mai (probabilmente disattivando il microfono per la maggior parte della chiamata). In tale scenario, una trasmissione audio avrà un elevato utilizzo dei pacchetti (in entrata per il client) mentre l'altro avrà un utilizzo del pacchetto minimo o nullo (in uscita dal client). In questo scenario, la durata della trasmissione può essere di un'ora o più, ma l'utilizzo del pacchetto nella trasmissione dal client al server sarà estremamente basso a causa del silenziamento del microfono, che determinerà una trasmissione non classificata.

> [!TIP]
> La dimensione "Utilizzo pacchetto" e la misura "Utilizzo medio del pacchetto" possono essere utilizzate per determinare l'attività del pacchetto di una trasmissione.


## <a name="related-topics"></a>Argomenti correlati
[Attivazione e utilizzo di Dashboard Qualità della chiamata (DQC)](turning-on-and-using-call-quality-dashboard.md)

[Dimensioni e misure disponibili in Dashboard Qualità della chiamata](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Uso di Call Analytics per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)
