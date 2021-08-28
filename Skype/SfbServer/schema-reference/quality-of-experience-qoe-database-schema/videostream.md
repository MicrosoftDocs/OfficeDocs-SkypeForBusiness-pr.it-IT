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
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Ogni record rappresenta un flusso video. Una linea multimediale video contiene in genere due flussi video.
ms.openlocfilehash: af8ae55e805019b91e9c1750d7bb036bcf79c6f7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628518"
---
# <a name="videostream-table"></a>Tabella VideoStream
 
Ogni record rappresenta un flusso video. Una linea multimediale video contiene in genere due flussi video.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |R A cui viene fatto riferimento [dalla tabella MediaLine.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco in una linea multimediale.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Foreign, Primary  <br/> |Descrizione del payload. Per altre informazioni, vedi la [tabella PayloadDescription.](payloaddescription.md) <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Massimo instabilità di rete durante la sessione video.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di round trip dalle statistiche RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo massimo di round trip per il flusso video.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Stime della larghezza di banda per il flusso video.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Velocità in bit media del flusso video.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Frequenza fotogrammi video ricevuta.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Frequenza fotogrammi video inviata.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Velocità in bit video massima durante la sessione video.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |Percentuale di fotogrammi video totali persi.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Non disponibile.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||Percentuale di fotogrammi video totali persi.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata con risoluzione CIF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata con risoluzione VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata con risoluzione HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata senza rilascio di fotogrammi.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con rilascio di fotogrammi B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con riduzione dei fotogrammi BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con riduzione dei fotogrammi BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Percentuale di durata della chiamata con rilascio di fotogrammi BPSPI.  <br/> |
|**In ingresso** <br/> |bit  <br/> | <br/> |Vengono ricevuti i dati di flusso sul lato ricevitore.  <br/> |
|**In uscita** <br/> |bit  <br/> | <br/> |I dati di flusso sul lato mittente vengono ricevuti.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.  <br/> 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica la percentuale di tempo in cui la chiamata si è verificata in uno stato di congestione della perdita.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantità media di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Percentuale della chiamata in cui l'endpoint ha determinato che la connessione di rete non è in grado di supportare video multiview.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densità burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durata burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze gap unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densità di gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durata del gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Frequenza di perdita dei pacchetti video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantità media di larghezza di banda allocata per il video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Tipo di codec video utilizzati dal mittente. Per ulteriori informazioni, vedere la tabella [CodecDescription.](codecdescription.md) <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Larghezza della risoluzione utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altezza della risoluzione utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Trasmissione media dei fotogrammi video utilizzata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il mittente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Numero massimo di flussi video utilizzati dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Codici video utilizzati dal destinatario. Per ulteriori informazioni, vedere la tabella [CodecDescription.](codecdescription.md) <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Larghezza della risoluzione utilizzata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altezza della risoluzione utilizzata dal ricevitore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Frequenza media dei fotogrammi video utilizzata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il ricevitore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Numero massimo di flussi video per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flussi video minimi per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modalità video (ad esempio, raccolta o flusso singolo) per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Frequenza di perdita dei pacchetti dopo l'applicazione della correzione degli errori di inoltro.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Percentuale di tempo in cui il flag di funzionalità dinamiche era attivo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Risoluzione minima misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Percentuale della chiamata al di sotto della soglia di frequenza dei fotogrammi bassa (7,5 fotogrammi al secondo, in ingresso).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Percentuale della chiamata che si è verificata alla risoluzione più bassa.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Durata della chiamata in secondi.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica se i dati sono stati aggregati da più chiamate.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

