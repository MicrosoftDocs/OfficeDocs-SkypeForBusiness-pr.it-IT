---
title: 'Lync Server 2013: Tabella AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Tabella AudioStream in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Ogni record rappresenta un flusso audio. Una linea media audio in genere contiene due flussi audio.


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
<td><p>DateTime</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>ID univoco all'interno di una linea media.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Variazione massima della rete durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Tasso medio di perdita di pacchetti durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimale (5; 4)</p></td>
<td><p> </p></td>
<td><p>Perdita massima del pacchetto osservata durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>decimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>decimale (9; 4)</p></td>
<td><p> </p></td>
<td><p>Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Durata media degli intervalli tra i burst di perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Conteggio dei pacchetti per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Larghezza di banda più ampia</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Stime della larghezza di banda per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradazione MOS Network per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti. Per una qualità accettabile dovrebbe essere inferiore a 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Massimo degrado dei MOS di rete durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradazione dei MOS di rete causata da jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradazione dei MOS di rete causata da perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Codec audio usato per la chiamata, a cui si fa riferimento dalla Tabella PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Frequenza di campionamento per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo di andata e ritorno dalle statistiche di RTCP. Per una qualità accettabile, dovrebbe essere minore di 100ms.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo massimo di andata e ritorno per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>MOS di rete a banda larga media per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati. Intervallo è [1,0 a 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>MOS della rete a banda larga minima per la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Il Punteggio di MOS in ascolto a banda larga previsto medio per l'audio inviato, incluse le caratteristiche del livello vocale, del livello di rumore e del dispositivo di acquisizione.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>SendListenMOS minima per la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>Il Punteggio di MOS a banda larga previsto medio per l'audio ricevuto dalla rete, tra cui livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimale (3; 2)</p></td>
<td><p> </p></td>
<td><p>RecvListenMOS minima per la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Contrassegno che indica se per la chiamata è stato usato l'audio FEC.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.</p></td>
</tr>
<tr class="odd">
<td><p><strong>In ingresso</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Il flusso di dati sul lato ricevitore viene ricevuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Outbound</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Il flusso di dati sul lato mittente viene ricevuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che la direzione del flusso è dal chiamante al chiamato.</p>
<p>0 indica che la direzione del flusso è dal chiamato al chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Deviazione standard per l'orario di arrivo jitter.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Rapporto massimo dei pacchetti nascosti dal guaritore.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Deviazione standard per il rapporto tra i pacchetti nascosti dal guaritore.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Rapporto tra i pacchetti eliminati dal guaritore rispetto al numero totale di pacchetti ricevuti.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Rapporto tra i pacchetti di correzione degli errori in avanti usati rispetto al numero totale di pacchetti ricevuti.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Numero massimo di pacchetti audio compressi dal guaritore.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale di tempo in cui la chiamata era in stato di congestione della perdita.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale di tempo in cui la chiamata era in competizione per le risorse di rete.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità minima di stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità massima di stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Importo medio della stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo totale della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo medio della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Importo massimo della latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze totali di burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità totale burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Totale durata burst unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze totali unidirezionali Gap. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità totale gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata totale del gap unidirezionale. Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata decodificata come stereo.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata di cui è stato eseguito il rendering stereo tramite la soppressione dell'Echo acustica.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Tasso di perdita di pacchetti dopo l'applicazione della correzione degli errori in avanti.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata codificata come stereo.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata acquisita come stereo dalla soppressione dell'Echo acustica.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

