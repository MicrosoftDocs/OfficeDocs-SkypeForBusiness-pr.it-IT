---
title: Tabella AppSharingStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La Tabella AppSharingStream contiene la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811104"
---
# <a name="appsharingstream-table"></a>Tabella AppSharingStream
 
La Tabella AppSharingStream contiene la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primaria, straniera  <br/> |Data e ora di inizio della sessione.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Identificatore sequenziale usato per distinguere tra le sessioni avviate nella stessa data e contemporaneamente.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaria, straniera  <br/> | Vedere la [Tabella MediaLine](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Principale  <br/> |Identificatore univoco del flusso di condivisione dell'applicazione.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Jitter massimo rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della "shakiness" di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Importo massimo (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.  <br/> I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.  <br/> |
|**PacketLossRate** <br/> |galleggiante  <br/> ||Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**PacketLossRateMax** <br/> |galleggiante  <br/> ||Tasso massimo di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Numero di pacchetti inviati.  <br/> |
|**Larghezza di banda più ampia** <br/> |int  <br/> ||Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Segnalati in bit al secondo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descrizione del payload di condivisione applicazioni.  <br/> |
|**RelativeOneWayTotal** <br/> |galleggiante  <br/> ||Importo totale della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayAverage** <br/> |galleggiante  <br/> ||Importo medio della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayMax** <br/> |galleggiante  <br/> ||Importo massimo della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Occorrenze totali di burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |galleggiante  <br/> ||Densità totale burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |galleggiante  <br/> ||Totale durata burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Occorrenze totali unidirezionali Gap. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapDensity** <br/> |galleggiante  <br/> ||Densità totale gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**RelativeOneWayGapDuration** <br/> |galleggiante  <br/> ||Durata totale del gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |galleggiante  <br/> ||Tempo di elaborazione totale per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |galleggiante  <br/> ||Tempo medio di elaborazione per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |galleggiante  <br/> ||Tempo di elaborazione massimo per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). La densità di Gap ridotta equivale a un'esperienza di visualizzazione migliore.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |galleggiante  <br/> ||Durata gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). La durata del gap breve equivale a una migliore esperienza di visualizzazione.  <br/> |
|**CaptureTileRateTotal** <br/> |galleggiante  <br/> ||Tasso totale dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateAverage** <br/> |galleggiante  <br/> ||Tasso medio dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateMax** <br/> |galleggiante  <br/> ||Tasso massimo dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |in t  <br/> ||Occorrenze di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |galleggiante  <br/> ||Durata del gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |galleggiante  <br/> ||Percentuale totale del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentAverage** <br/> |galleggiante  <br/> ||Percentuale media del contenuto che non ha raggiunto il visualizzatore ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentMax** <br/> |galleggiante  <br/> ||Percentuale massima del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |galleggiante  <br/> ||Durata burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |galleggiante  <br/> ||Densità di Gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |galleggiante  <br/> ||Durata gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.  <br/> |
|**ScrapingFrameRateTotal** <br/> |galleggiante  <br/> ||Numero totale di fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateAverage** <br/> |galleggiante  <br/> ||Numero medio di fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateMax** <br/> |galleggiante  <br/> ||Numero massimo di fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze di burst nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |galleggiante  <br/> ||Durata del gap nei fotogrammi raschiati dall'origine grafica.  <br/> |
|**IncomingTileRateTotal** <br/> |galleggiante  <br/> ||Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.  <br/> |
|**IncomingTileRateAverage** <br/> |galleggiante  <br/> ||Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.  <br/> |
|**IncomingTileRateMax** <br/> |galleggiante  <br/> ||Numero massimo di tessere in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze di burst nella frequenza delle tessere in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nella tariffa del riquadro in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza delle tessere in arrivo ricevute dal visualizzatore.  <br/> |
|**IncomingTileRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingTileRateGapDuration** <br/> |galleggiante  <br/> ||Durata del gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateTotal** <br/> |galleggiante  <br/> ||Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateAverage** <br/> |galleggiante  <br/> ||Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateMax** <br/> |galleggiante  <br/> ||Frequenza fotogrammi in arrivo massima ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**IncomingFrameRateDuration** <br/> |galleggiante  <br/> ||Durata del gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.  <br/> |
|**OutgoingTileRateTotal** <br/> |galleggiante  <br/> ||Tasso di riquadri in uscita totale per il mittente.  <br/> |
|**OutgoingTileRateAverage** <br/> |galleggiante  <br/> ||Tasso di riquadri in uscita medio per il mittente.  <br/> |
|**OutgoingTileRateMax** <br/> |galleggiante  <br/> ||Tasso di riquadri in uscita massimo per il mittente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze di burst nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |galleggiante  <br/> ||Durata gap nella tariffa del riquadro in uscita per il mittente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |galleggiante  <br/> ||Frequenza fotogrammi in uscita totale per il mittente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |galleggiante  <br/> ||frequenza fotogrammi in uscita media per il mittente.  <br/> |
|**OutgoingFrameRateMax** <br/> |galleggiante  <br/> ||Frequenza fotogrammi in uscita massima per il mittente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Occorrenze di burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |galleggiante  <br/> ||Densità di burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |galleggiante  <br/> ||Durata burst nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |galleggiante  <br/> ||Densità di gap nella frequenza dei fotogrammi in uscita per il mittente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |galleggiante  <br/> ||Durata del gap nella frequenza fotogrammi in uscita per il mittente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Altezza media di risoluzione video, in pixel.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Larghezza media della risoluzione video in pixel.  <br/> |
|**In ingresso** <br/> |po'  <br/> ||Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in ingresso.  <br/> |
|**Outbound** <br/> |po'  <br/> ||Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in uscita.  <br/> |
|**SenderIsCallerPAI** <br/> |po'  <br/> ||1 indica che la direzione del flusso è dal chiamante al chiamato.  <br/> 0 indica che la direzione del flusso è dal chiamato al chiamante.  <br/> |
   

