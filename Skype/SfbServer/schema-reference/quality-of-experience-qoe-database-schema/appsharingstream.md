---
title: Tabella AppSharingStream
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 5577777c96618e6cf601e8b80763f74acdad5a5a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592420"
---
# <a name="appsharingstream-table"></a>Tabella AppSharingStream
 
La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primaria/o, esterna/o  <br/> |Data e ora di avvio della sessione.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaria/o, esterna/o  <br/> |Identificatore sequenziale utilizzato per distinguere tra loro sessioni avviate nella stessa data alla stessa ora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaria, esterna  <br/> | Vedi [MediaLine Table.](./medialine-0.md) <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco del flusso di condivisione di applicazioni.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Instabilità media rilevata tra gli arrivi dei pacchetti RTP (Real-Time Transport Protocol). L'instabilità è un indice della qualità di una chiamata. Valori di instabilità elevati sono generalmente dovuti a congestione o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Instabilità massima rilevata tra gli arrivi dei pacchetti RTP (l'instabilità è un indice della qualità di una chiamata). Valori di instabilità elevati sono generalmente dovuti a congestione o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Quantità media di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.  <br/> Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantità massima di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.  <br/> Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori di perdita elevati sono generalmente dovuti a congestione, larghezza di banda insufficiente, congestione/interferenze wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Frequenza massima di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono generalmente dovute a congestione, larghezza di banda insufficiente, interferenze o congestione della rete wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Numero di pacchetti inviati.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Indicata in bit al secondo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descrizione del payload di condivisione di applicazioni.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densità burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Durata burst unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze gap unidirezionali totali. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densità di gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Durata del gap unidirezionale totale. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante. le lacune indicano ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tempo totale di elaborazione per le sezioni RDP (Remote Desktop Protocol). Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Tempo medio di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tempo massimo di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nel tempo di elaborazione per le sezioni RDP. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densità burst nel tempo di elaborazione per le sezioni RDP. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Durata burst nel tempo di elaborazione per le sezioni RDP. Una trasmissione "bursty" è una trasmissione in cui i dati sfociano in burst imprevedibili anziché in un flusso costante.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nel tempo di elaborazione per le sezioni RDP.  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densità gap nel tempo di elaborazione per le sezioni RDP. Una densità gap bassa corrisponde a un'esperienza di visualizzazione migliore.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Durata gap nel tempo di elaborazione per le sezioni RDP. Durate gap basse corrispondono a un'esperienza di visualizzazione migliore.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Frequenza totale di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Frequenza media di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Frequenza massima di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |in t  <br/> ||Occorrenze burst nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densità burst nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Durata burst nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densità gap nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Durata gap nella frequenza di sezioni acquisite (sezioni al secondo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Percentuale totale di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Percentuale media di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Percentuale massima di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densità burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Durata burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densità gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Durata gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Numero totale di fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Numero medio di fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Numero massimo di fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densità burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Durata burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densità gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Durata gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Frequenza massima sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densità burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Durata burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densità gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Durata gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Frequenza massima fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densità burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Durata burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densità gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Durata gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Frequenza totale sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Frequenza media sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Frequenza massima sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densità burst nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Durata burst nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densità gap nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Durata gap nella frequenza sezioni in uscita per il mittente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Frequenza totale fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||Frequenza media fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Frequenza massima fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densità burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Durata burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densità gap nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Durata gap nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Altezza media risoluzione video, in pixel.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Larghezza media risoluzione video, in pixel.  <br/> |
|**In ingresso** <br/> |bit  <br/> ||Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in entrata.  <br/> |
|**In uscita** <br/> |bit  <br/> ||Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in uscita.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.  <br/> 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
