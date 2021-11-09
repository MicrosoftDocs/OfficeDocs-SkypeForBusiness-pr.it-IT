---
title: Tabella AudioStream
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Ogni record rappresenta un flusso audio. Una linea multimediale audio contiene in genere due flussi audio.
ms.openlocfilehash: b9a5e184a258115934d3583e4f6cde8f659fb9fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856423"
---
# <a name="audiostream-table"></a>Tabella AudioStream
 
Ogni record rappresenta un flusso audio. Una linea multimediale audio contiene in genere due flussi audio.
  
|Colonna|Tipo di dati|Chiave/indice|Dettagli|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco in una linea multimediale.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Instabilità di rete massima durante la chiamata.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densità media di perdita di pacchetti durante burst di perdite durante la chiamata.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durata media delle pause tra burst della perdita di pacchetti.  <br/> |
|**PacketUtilization** <br/> |Soglia  <br/> | <br/> |Numero di pacchetti per il flusso audio.  <br/> |
|**BandwidthEst** <br/> |Soglia  <br/> | <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradazione MOS di rete massima durante la chiamata.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradazione MOS di rete causata dall'instabilità.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradazione MOS di rete causata dalla perdita di pacchetti.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Foreign  <br/> |Codec audio usato per la chiamata, a cui viene fatto riferimento da PayloadDescription Table.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Frequenza di campionamento per il flusso audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di round trip dalle statistiche RTCP. Per una qualità accettabile, questo valore deve essere inferiore a 100 ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo di round trip massimo per il flusso audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo è compreso tra [1,0 e 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Mos di rete a banda larga minima per la chiamata.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Punteggio MOS di ascolto a banda larga previsto medio per l'audio inviato, inclusi il livello vocale, il livello di rumore e le caratteristiche del dispositivo di acquisizione.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Valore SendListenMOS minimo per la chiamata.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |Punteggio MOS di ascolto a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello vocale, il livello di rumore, il codec, le condizioni di rete e le caratteristiche del dispositivo di acquisizione.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Valore RecvListenMOS minimo per la chiamata.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Flag che indica se per la chiamata è stato utilizzato FEC audio.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|**In ingresso** <br/> |bit  <br/> | <br/> |Vengono ricevuti i dati di flusso sul lato ricevitore.  <br/> |
|**In uscita** <br/> |bit  <br/> | <br/> |I dati di flusso sul lato mittente vengono ricevuti.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 indica che la direzione del flusso è dal chiamante al chiamato.  <br/> 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Deviazione standard per gli orari di arrivo instabilità.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Rapporto massimo di pacchetti nascosti dal healer.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Deviazione standard per il rapporto di pacchetti nascosti dal healer.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Rapporto tra i pacchetti rilasciati dal healer rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Rapporto tra i pacchetti di correzione degli errori di inoltro usati rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Numero massimo di pacchetti audio compressi dal healer.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica la percentuale di tempo in cui la chiamata si è verificata in uno stato di congestione della perdita.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantità media di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densità burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durata burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze gap unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densità di gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durata del gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Percentuale della chiamata decodificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Percentuale della chiamata sottoposta a rendering come stereo dall'eco cancellatore acustico.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Frequenza di perdita dei pacchetti dopo l'applicazione della correzione degli errori di inoltro.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Percentuale della chiamata codificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Percentuale della chiamata acquisita come stereo dall'eco cancellatore acustico.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
