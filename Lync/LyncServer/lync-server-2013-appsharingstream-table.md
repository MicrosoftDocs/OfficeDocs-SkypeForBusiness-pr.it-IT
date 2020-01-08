---
title: 'Lync Server 2013: Tabella AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Tabella AppSharingStream in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-21_

La Tabella AppSharingStream contiene la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Data e ora di inizio della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Identificatore sequenziale usato per distinguere tra le sessioni avviate nella stessa data e contemporaneamente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Rappresenta il tipo di linea video usato nella chiamata. I valori consentiti sono:</p>
<ul>
<li><p>0-audio</p></li>
<li><p>1-video</p></li>
<li><p>2-video panoramico</p></li>
<li><p>3-condivisione di applicazioni/desktop</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Identificatore univoco del flusso di condivisione dell'applicazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Jitter massimo rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Importo massimo (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso massimo di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di pacchetti inviati.</p></td>
</tr>
<tr class="even">
<td><p><strong>Larghezza di banda più ampia</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Segnalati in bit al secondo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Descrizione del payload di condivisione applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo totale della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo medio della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo massimo della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze totali di burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità totale burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Totale durata burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze totali unidirezionali Gap. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità totale gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata totale del gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tempo di elaborazione totale per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tempo medio di elaborazione per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tempo di elaborazione massimo per i riquadri RDP (Remote Desktop Protocol). Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). La densità di Gap ridotta equivale a un'esperienza di visualizzazione migliore.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol). La durata del gap breve equivale a una migliore esperienza di visualizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso totale dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso medio dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso massimo dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>in t</p></td>
<td></td>
<td><p>Occorrenze di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata del gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale totale del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale media del contenuto che non ha raggiunto il visualizzatore ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale massima del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di Gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero totale di fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero medio di fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero massimo di fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze di burst nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata del gap nei fotogrammi raschiati dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero massimo di tessere in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze di burst nella frequenza delle tessere in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella tariffa del riquadro in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza delle tessere in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata del gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza fotogrammi in arrivo massima ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata del gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso di riquadri in uscita totale per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso di riquadri in uscita medio per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso di riquadri in uscita massimo per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze di burst nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella tariffa del riquadro in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza fotogrammi in uscita totale per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>frequenza fotogrammi in uscita media per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza fotogrammi in uscita massima per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze di burst nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di burst nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità di gap nella frequenza dei fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata del gap nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altezza media di risoluzione video, in pixel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza media della risoluzione video in pixel.</p></td>
</tr>
<tr class="even">
<td><p><strong>In ingresso</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in ingresso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in uscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>1 indica che la direzione del flusso è dal chiamante al chiamato.</p>
<p>0 indica che la direzione del flusso è dal chiamato al chiamante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

