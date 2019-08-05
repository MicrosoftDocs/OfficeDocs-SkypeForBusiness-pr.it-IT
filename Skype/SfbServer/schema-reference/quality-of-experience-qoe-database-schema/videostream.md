---
title: Tabella VideoStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Ogni record rappresenta un flusso video. Una linea media video in genere contiene due flussi video.
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194556"
---
# <a name="videostream-table"></a>Tabella VideoStream
 
Ogni record rappresenta un flusso video. Una linea media video in genere contiene due flussi video.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |R a cui viene fatto riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco all'interno di una linea media.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Estero, primario  <br/> |Descrizione payload. Per altre informazioni, vedere la [Tabella PayloadDescription](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Jitter della rete massimo durante la sessione video.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di andata e ritorno dalle statistiche di RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo massimo di andata e ritorno per il flusso video.  <br/> |
|**PacketLossRate** <br/> |decimale (5; 4)  <br/> | <br/> |Tasso medio di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimale (5; 4)  <br/> | <br/> |Perdita massima del pacchetto osservata durante la chiamata.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).  <br/> |
|**Larghezza di banda più ampia** <br/> |int  <br/> | <br/> |Stime della larghezza di banda per il flusso video.  <br/> |
|**VideoResolution** <br/> |codice.caratt(9  <br/> | <br/> |Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel. Segnalato come stringa.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Velocità in bit media del flusso video.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimale (9; 4)  <br/> | <br/> |Frequenza fotogrammi video ricevuta.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimale (9; 4)  <br/> | <br/> |Frequenza fotogrammi video inviata.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Velocità in bit massima video durante la sessione video.  <br/> |
|**VideoFrameLossRate** <br/> |decimale (9; 4)  <br/> | <br/> |Percentuale di fotogrammi video totali persi.  <br/> |
|**VideoFEC** <br/> |po'  <br/> | <br/> |Non disponibile.  <br/> |
|**Flussi** <br/> |decimale (9; 4)  <br/> ||Percentuale di fotogrammi video totali persi.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata alla risoluzione CIF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata con risoluzione VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Percentuale della chiamata alla risoluzione di HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Percentuale della durata della chiamata senza drop frame.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Percentuale della durata della chiamata con la riduzione del fotogramma B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Percentuale della durata della chiamata con il frame drop di BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Percentuale della durata della chiamata con il frame drop di BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Percentuale della durata della chiamata con il frame drop di BPSPI.  <br/> |
|**In ingresso** <br/> |po'  <br/> | <br/> |Il flusso di dati sul lato ricevitore viene ricevuto.  <br/> |
|**Outbound** <br/> |po'  <br/> | <br/> |Il flusso di dati sul lato mittente viene ricevuto.  <br/> |
|**SenderIsCallerPAI** <br/> |po'  <br/> | <br/> |1 indica che la direzione del flusso è dal chiamante al chiamato.  <br/> 0 indica che la direzione del flusso è dal chiamato al chiamante.  <br/> |
|**LossCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Importo medio della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |galleggiante  <br/> ||Percentuale della chiamata in cui l'endpoint ha determinato che la connessione di rete non supporta il video MultiView.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |galleggiante  <br/> ||Importo totale della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |galleggiante  <br/> ||Importo medio della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |galleggiante  <br/> ||Importo massimo della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze totali di burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densità totale burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |galleggiante  <br/> ||Totale durata burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze totali unidirezionali Gap. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |galleggiante  <br/> ||Densità totale gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |galleggiante  <br/> ||Durata totale del gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Flussi** <br/> |decimale (9; 4)  <br/> ||Frequenza con cui sono stati persi i pacchetti video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantità media di larghezza di banda allocata per il video.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Esterna  <br/> |Tipo di codec video usati dal mittente. Per altre informazioni, vedere la [tabella CodecDescription](codecdescription.md) . <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Larghezza di risoluzione usata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altezza di risoluzione usata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |galleggiante  <br/> ||Trasmissione media della frequenza dei fotogrammi video usata dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il mittente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Numero massimo di flussi video usati dal mittente.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Esterna  <br/> |Codici video usati dal destinatario. Per altre informazioni, vedere la [tabella CodecDescription](codecdescription.md) . <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Larghezza di risoluzione usata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altezza di risoluzione usata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Flussi** <br/> |galleggiante  <br/> ||Frequenza fotogrammi video media usata dal destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Velocità in bit massima per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Velocità in bit media per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Flussi video massimo per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Flussi video minimi per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Flussi** <br/> |galleggiante  <br/> ||Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Flussi** <br/> |galleggiante  <br/> ||Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |codice.caratt(9  <br/> ||Risoluzione minima misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata sotto la soglia di velocità in bit ridotta (70 kilobit al secondo).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Flussi** <br/> |galleggiante  <br/> ||Percentuale della chiamata sotto la soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**Causa** <br/> |galleggiante  <br/> ||Percentuale della chiamata che si è verificata alla risoluzione più bassa.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |galleggiante  <br/> ||Lunghezza della chiamata in secondi.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |po'  <br/> ||Indica se i dati sono stati aggregati da più chiamate.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

