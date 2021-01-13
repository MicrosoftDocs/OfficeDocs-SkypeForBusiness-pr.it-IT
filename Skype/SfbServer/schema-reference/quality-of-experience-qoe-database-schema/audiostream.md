---
title: Tabella AudioStream
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Ogni record rappresenta un flusso audio. Una linea multimediale audio in genere contiene due flussi audio.
ms.openlocfilehash: e24a5c8611c3f6bf7b56edf342aa2595f6794a90
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831366"
---
# <a name="audiostream-table"></a>Tabella AudioStream
 
Ogni record rappresenta un flusso audio. Una linea multimediale audio in genere contiene due flussi audio.
  
|Colonna|Tipo di dati|Chiave/indice|Dettagli|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco in una linea multimediale.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Instabilità di rete massima durante la chiamata.  <br/> |
|**PacketLossRate** <br/> |decimale (5, 4)  <br/> | <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimale (5, 4)  <br/> | <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|**DensitàBurst** <br/> |decimale (9, 4)  <br/> | <br/> |Densità media della perdita di pacchetti durante i burst di perdite durante la chiamata.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.  <br/> |
|**BurstGapDensity** <br/> |decimale (9, 4)  <br/> | <br/> |Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durata media delle pause tra burst della perdita di pacchetti.  <br/> |
|**PacketUtilization** <br/> |Soglia  <br/> | <br/> |Numero di pacchetti per il flusso audio.  <br/> |
|**Larghezza di banda** <br/> |Soglia  <br/> | <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|**DegradationAvg** <br/> |decimale (3, 2)  <br/> | <br/> |Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.  <br/> |
|**DegradationMax** <br/> |decimale (3, 2)  <br/> | <br/> |Degradazione MOS di rete massima durante la chiamata.  <br/> |
|**DegradationJitterAvg** <br/> |decimale (3, 2)  <br/> | <br/> |Degradazione MOS di rete causata dall'instabilità.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimale (3, 2)  <br/> | <br/> |Degradazione MOS di rete causata dalla perdita di pacchetti.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Stranieri  <br/> |Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla Tabella PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Frequenza di campionamento per il flusso audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di round trip dalle statistiche RTCP. Per una qualità accettabile questo valore deve essere inferiore a 100 ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo di round trip massimo per il flusso audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimale (3, 2)  <br/> | <br/> |MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo è compreso tra [1,0 e 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimale (3, 2)  <br/> | <br/> |Il MOS di rete a banda larga minimo per la chiamata.  <br/> |
|**Valore SendListenMOS** <br/> |decimale (3, 2)  <br/> | <br/> |La media del Punteggio MOS a banda larga stimato per l'audio inviato, inclusi il livello parlato, il livello di rumore e le caratteristiche del dispositivo di acquisizione.  <br/> |
|**SendListenMOSMin** <br/> |decimale (3, 2)  <br/> | <br/> |Valore SendListenMOS minimo per la chiamata.  <br/> |
|**RecvListenMOS** <br/> |decimale (3, 2)  <br/> | <br/> |La media del Punteggio MOS a banda larga stimato per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.  <br/> |
|**RecvListenMOSMin** <br/> |decimale (3, 2)  <br/> | <br/> |RecvListenMOS minimo per la chiamata.  <br/> |
|**AudioFECUsed** <br/> |po'  <br/> ||Contrassegno che indica se per la chiamata è stato utilizzato l'audio FEC.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |Decimal (5, 2)  <br/> ||Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |Decimal (5, 2)  <br/> ||Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |Decimal (5, 2)  <br/> ||Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**Inbound** <br/> |po'  <br/> | <br/> |I dati del flusso sul ricevitore vengono ricevuti.  <br/> |
|**In uscita** <br/> |po'  <br/> | <br/> |I dati del flusso sul mittente vengono ricevuti.  <br/> |
|**SenderIsCallerPAI** <br/> |po'  <br/> | <br/> |1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.  <br/> 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
|**JitterInterArrivalSD** <br/> |galleggiante  <br/> ||Deviazione standard per i tempi di arrivo jitter.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |galleggiante  <br/> ||Rapporto massimo dei pacchetti nascosti dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |galleggiante  <br/> ||Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |galleggiante  <br/> ||Rapporto dei pacchetti rilasciati dal guaritore rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |galleggiante  <br/> ||Rapporto dei pacchetti di correzione degli errori di inoltro utilizzati rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |galleggiante  <br/> ||Numero massimo di pacchetti audio compressi dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantità media di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |galleggiante  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |galleggiante  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |galleggiante  <br/> ||Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst unidirezionali totali. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |galleggiante  <br/> ||Densità burst unidirezionale totale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |galleggiante  <br/> ||Durata burst unidirezionale totale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze gap unidirezionali totali. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |galleggiante  <br/> ||Densità totale di gap unidirezionale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |galleggiante  <br/> ||Durata totale del gap unidirezionale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata decodificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata di cui è stato eseguito il rendering come stereo dalla soppressione dell'eco acustica.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |galleggiante  <br/> ||Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata codificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata acquisita come stereo dalla soppressione dell'eco acustica.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
