---
title: 'Lync Server 2013: Tabella AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Tabella AppSharingStream in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-21_

La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni. Questa tabella è stata introdotta in Microsoft Lync Server 2013.


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
<td><p>Primaria, esterna</p></td>
<td><p>Data e ora di avvio della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primario, esterno</p></td>
<td><p>Identificatore sequenziale utilizzato per distinguere tra loro sessioni avviate nella stessa data alla stessa ora.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</p>
<ul>
<li><p>0 – audio</p></li>
<li><p>1-video</p></li>
<li><p>2 - Panoramica</p></li>
<li><p>3 – condivisione di applicazioni/desktop</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Identificatore univoco del flusso di condivisione di applicazioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Instabilità media rilevata tra gli arrivi dei pacchetti RTP (Real-Time Transport Protocol). (Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Instabilità massima rilevata tra gli arrivi di pacchetti RTP. (Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità media di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</p>
<p>Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità massima di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</p>
<p>Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori di perdita elevati sono generalmente dovuti a congestione, larghezza di banda insufficiente, congestione/interferenze wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono generalmente dovute a congestione, larghezza di banda insufficiente, interferenze o congestione della rete wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di pacchetti inviati.</p></td>
</tr>
<tr class="even">
<td><p><strong>Larghezza di banda</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Indicata in bit al secondo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Descrizione del payload di condivisione di applicazioni.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p></td>
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
<td><p>Tempo totale di elaborazione per le sezioni RDP (Remote Desktop Protocol). Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tempo medio di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tempo massimo di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nel tempo di elaborazione per le sezioni RDP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nel tempo di elaborazione per le sezioni RDP. Una densità gap bassa corrisponde a un'esperienza di visualizzazione migliore.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nel tempo di elaborazione per le sezioni RDP. Durate gap basse corrispondono a un'esperienza di visualizzazione migliore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza totale di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>in t</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella frequenza di sezioni acquisite (sezioni al secondo).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale totale di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale media di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale massima di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero totale di fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero medio di fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero massimo di fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza totale sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella frequenza sezioni in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza totale fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza massima fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità burst nella frequenza fotogrammi in uscita per il mittente.</p></td>
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
<td><p>Densità gap nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap nella frequenza fotogrammi in uscita per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altezza media risoluzione video, in pixel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza media risoluzione video, in pixel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in entrata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>In uscita</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in uscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</p>
<p>0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

