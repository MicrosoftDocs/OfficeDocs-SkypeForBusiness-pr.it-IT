---
title: Tabella AudioStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Ogni record rappresenta un flusso audio. Una linea media audio in genere contiene due flussi audio.
ms.openlocfilehash: 265125202de25da4c6e653ecd53bd465f9a5472b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810434"
---
# <a name="audiostream-table"></a>Tabella AudioStream
 
Ogni record rappresenta un flusso audio. Una linea media audio in genere contiene due flussi audio.
  
|Colonna|Tipo di dati|Chiave/indice|Dettagli|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |ID univoco all'interno di una linea media.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Variazione massima della rete durante la chiamata.  <br/> |
|**PacketLossRate** <br/> |decimale (5; 4)  <br/> | <br/> |Tasso medio di perdita di pacchetti durante la chiamata.  <br/> |
|**PacketLossRateMax** <br/> |decimale (5; 4)  <br/> | <br/> |Perdita massima del pacchetto osservata durante la chiamata.  <br/> |
|**BurstDensity** <br/> |decimale (9; 4)  <br/> | <br/> |Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.  <br/> |
|**BurstGapDensity** <br/> |decimale (9; 4)  <br/> | <br/> |Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Durata media degli intervalli tra i burst di perdita di pacchetti.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Conteggio dei pacchetti per il flusso audio.  <br/> |
|**Larghezza di banda più ampia** <br/> |Int  <br/> | <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|**DegradationAvg** <br/> |decimale (3; 2)  <br/> | <br/> |Degradazione MOS Network per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti. Per una qualità accettabile dovrebbe essere inferiore a 0,5.  <br/> |
|**DegradationMax** <br/> |decimale (3; 2)  <br/> | <br/> |Massimo degrado dei MOS di rete durante la chiamata.  <br/> |
|**DegradationJitterAvg** <br/> |decimale (3; 2)  <br/> | <br/> |Degradazione dei MOS di rete causata da jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimale (3; 2)  <br/> | <br/> |Degradazione dei MOS di rete causata da perdita di pacchetti.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Esterna  <br/> |Codec audio usato per la chiamata, a cui si fa riferimento dalla Tabella PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Frequenza di campionamento per il flusso audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo di andata e ritorno dalle statistiche di RTCP. Per una qualità accettabile, dovrebbe essere minore di 100ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo massimo di andata e ritorno per il flusso audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimale (3; 2)  <br/> | <br/> |MOS di rete a banda larga media per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati. Intervallo è [1,0 a 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimale (3; 2)  <br/> | <br/> |MOS della rete a banda larga minima per la chiamata.  <br/> |
|**SendListenMOS** <br/> |decimale (3; 2)  <br/> | <br/> |Il Punteggio di MOS in ascolto a banda larga previsto medio per l'audio inviato, incluse le caratteristiche del livello vocale, del livello di rumore e del dispositivo di acquisizione.  <br/> |
|**SendListenMOSMin** <br/> |decimale (3; 2)  <br/> | <br/> |SendListenMOS minima per la chiamata.  <br/> |
|**RecvListenMOS** <br/> |decimale (3; 2)  <br/> | <br/> |Il Punteggio di MOS a banda larga previsto medio per l'audio ricevuto dalla rete, tra cui livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.  <br/> |
|**RecvListenMOSMin** <br/> |decimale (3; 2)  <br/> | <br/> |RecvListenMOS minima per la chiamata.  <br/> |
|**AudioFECUsed** <br/> |po'  <br/> ||Contrassegno che indica se per la chiamata è stato usato l'audio FEC.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimale (5; 2)  <br/> ||Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimale (5; 2)  <br/> ||Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimale (5; 2)  <br/> ||Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.  <br/> |
|**In ingresso** <br/> |po'  <br/> | <br/> |Il flusso di dati sul lato ricevitore viene ricevuto.  <br/> |
|**Outbound** <br/> |po'  <br/> | <br/> |Il flusso di dati sul lato mittente viene ricevuto.  <br/> |
|**SenderIsCallerPAI** <br/> |po'  <br/> | <br/> |1 indica che la direzione del flusso è dal chiamante al chiamato.  <br/> 0 indica che la direzione del flusso è dal chiamato al chiamante.  <br/> |
|**JitterInterArrivalSD** <br/> |galleggiante  <br/> ||Deviazione standard per l'orario di arrivo jitter.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |galleggiante  <br/> ||Rapporto massimo dei pacchetti nascosti dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |galleggiante  <br/> ||Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |galleggiante  <br/> ||Rapporto tra i pacchetti eliminati dal guaritore rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |galleggiante  <br/> ||Rapporto tra i pacchetti di correzione degli errori in avanti usati rispetto al numero totale di pacchetti ricevuti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |galleggiante  <br/> ||Numero massimo di pacchetti audio compressi dal guaritore.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |galleggiante  <br/> ||Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |galleggiante  <br/> ||Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantità minima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantità massima di stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Deviazione standard della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Importo medio della stima della larghezza di banda misurata durante la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |galleggiante  <br/> ||Importo totale della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |galleggiante  <br/> ||Importo medio della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |galleggiante  <br/> ||Importo massimo della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze totali di burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |galleggiante  <br/> ||Densità totale burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |galleggiante  <br/> ||Totale durata burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze totali unidirezionali Gap. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |galleggiante  <br/> ||Densità totale gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |galleggiante  <br/> ||Durata totale del gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata decodificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata di cui è stato eseguito il rendering stereo tramite la soppressione dell'Echo acustica.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |galleggiante  <br/> ||Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata codificata come stereo.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |galleggiante  <br/> ||Percentuale della chiamata acquisita come stereo dalla soppressione dell'Echo acustica.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
