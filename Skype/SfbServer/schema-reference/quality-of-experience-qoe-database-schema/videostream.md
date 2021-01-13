---
title: Tabella VideoStream
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Ogni record rappresenta un flusso video. Una linea video multimediale in genere contiene due flussi video.
ms.openlocfilehash: e506f022dbfa4ef0a1a8578dc6caf7c0f3984fa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821326"
---
# <a name="videostream-table"></a>Tabella VideoStream
 
Ogni record rappresenta un flusso video. Una linea video multimediale in genere contiene due flussi video.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |R a cui viene fatto riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco in una linea multimediale.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Estero, primario  <br/> |Descrizione payload. Per ulteriori informazioni, vedere la [Tabella PayloadDescription](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Instabilità massima della rete durante la sessione video.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di round trip dalle statistiche RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo massimo di andata e ritorno per il flusso video.  <br/> |
|**PacketLossRate** <br/> |decimale (5, 4)  <br/> | <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimale (5, 4)  <br/> | <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).  <br/> |
|**Larghezza di banda** <br/> |int  <br/> | <br/> |Stime della larghezza di banda per il flusso video.  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Velocità in bit media del flusso video.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimale (9, 4)  <br/> | <br/> |La frequenza fotogrammi video ricevuta.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimale (9, 4)  <br/> | <br/> |Frequenza fotogrammi video inviata.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Velocità in bit video massima durante la sessione video.  <br/> |
|**VideoFrameLossRate** <br/> |decimale (9, 4)  <br/> | <br/> |La percentuale di frame video totali persi.  <br/> |
|**VideoFEC** <br/> |po'  <br/> | <br/> |Non disponibile.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimale (9, 4)  <br/> ||La percentuale di frame video totali persi.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||La percentuale della chiamata che si trovava sulla risoluzione VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||La percentuale della chiamata che si trovava alla risoluzione di HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata senza frame drop.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con B frame drop.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con drop frame BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con BPSP frame drop.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con BPSPI frame drop.  <br/> |
|**Inbound** <br/> |po'  <br/> | <br/> |I dati del flusso sul ricevitore vengono ricevuti.  <br/> |
|**In uscita** <br/> |po'  <br/> | <br/> |I dati del flusso sul mittente vengono ricevuti.  <br/> |
|**SenderIsCallerPAI** <br/> |po'  <br/> | <br/> |1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.  <br/> 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
|**LossCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantità media di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |galleggiante  <br/> ||Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |galleggiante  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |galleggiante  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |galleggiante  <br/> ||Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst unidirezionali totali. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densità burst unidirezionale totale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |galleggiante  <br/> ||Durata burst unidirezionale totale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze gap unidirezionali totali. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |galleggiante  <br/> ||Densità totale di gap unidirezionale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |galleggiante  <br/> ||Durata totale del gap unidirezionale. La trasmissione "bursty" è una trasmissione in cui i dati scorrono in esplosioni imprevedibili rispetto a un flusso stabile. gli spazi vuoti indicano ritardi tra queste esplosioni. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimale (9, 4)  <br/> ||Frequenza di perdita dei pacchetti video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantità media di larghezza di banda allocata per il video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Stranieri  <br/> |Tipo di codec video utilizzati dal mittente. Per ulteriori informazioni, vedere la [tabella CodecDescription](codecdescription.md) . <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Larghezza della risoluzione utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altezza della risoluzione utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |galleggiante  <br/> ||Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il mittente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Numero massimo di flussi video utilizzati dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Stranieri  <br/> |Codici video utilizzati dal destinatario. Per ulteriori informazioni, vedere la [tabella CodecDescription](codecdescription.md) . <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Larghezza della risoluzione utilizzata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altezza della risoluzione utilizzata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |galleggiante  <br/> ||Frequenza media dei fotogrammi video utilizzata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Massimi flussi video per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flussi video minimi per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |galleggiante  <br/> ||Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |galleggiante  <br/> ||Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||Risoluzione minima misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata che si è verificata alla risoluzione più bassa.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |galleggiante  <br/> ||Durata della chiamata in secondi.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |po'  <br/> ||Indica se i dati sono stati aggregati da più chiamate.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

