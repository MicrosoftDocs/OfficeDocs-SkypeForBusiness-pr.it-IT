---
title: 'Lync Server 2013: tabella VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518563"
---
# <a name="videostream-table-in-lync-server-2013"></a>Tabella VideoStream in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-13_

Ogni record rappresenta un flusso video. Una linea video multimediale in genere contiene due flussi video.


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
<td><p>datetime</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>R a cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>ID univoco in una linea multimediale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Estero, primario</p></td>
<td><p>Descrizione payload. Per ulteriori informazioni, vedere la <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Instabilità massima della rete durante la sessione video.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo di round trip dalle statistiche RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo massimo di andata e ritorno per il flusso video.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimale (5, 4)</p></td>
<td><p> </p></td>
<td><p>Frequenza media di perdita di pacchetti durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimale (5, 4)</p></td>
<td><p> </p></td>
<td><p>Perdita di pacchetti massima rilevata durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Larghezza di banda</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Stime della larghezza di banda per il flusso video.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Velocità in bit media del flusso video.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>decimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>La frequenza fotogrammi video ricevuta.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>Frequenza fotogrammi video inviata.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Velocità in bit video massima durante la sessione video.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimale (9, 4)</p></td>
<td><p> </p></td>
<td><p>La percentuale di frame video totali persi.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Non disponibile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>decimale (9, 4)</p></td>
<td></td>
<td><p>La percentuale di frame video totali persi.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>La percentuale della chiamata che si trovava nella risoluzione CIF (Common Interchange Format).</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>La percentuale della chiamata che si trovava sulla risoluzione VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>La percentuale della chiamata che si trovava alla risoluzione di HD720.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Percentuale di durata della chiamata senza frame drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Percentuale di durata della chiamata con B frame drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Percentuale di durata della chiamata con drop frame BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Percentuale di durata della chiamata con BPSP frame drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Percentuale di durata della chiamata con BPSPI frame drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>I dati del flusso sul ricevitore vengono ricevuti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>In uscita</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>I dati del flusso sul mittente vengono ricevuti.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</p>
<p>0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale di tempo in cui la chiamata si trovava in uno stato di congestione delle perdite.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale della chiamata durante la quale la congestione è stata causata dall'arrivo ritardato dei pacchetti di rete.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Indica la percentuale di tempo in cui la chiamata è stata in competizione per le risorse di rete.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità minima di stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità massima di stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Deviazione standard della stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità media di stima della larghezza di banda misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata in cui l'endpoint ha stabilito che la connessione di rete non è in grado di supportare il video MultiView.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>decimale (9, 4)</p></td>
<td></td>
<td><p>Frequenza di perdita dei pacchetti video.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantità media di larghezza di banda allocata per il video.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Stranieri</p></td>
<td><p>Tipo di codec video utilizzati dal mittente. Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza della risoluzione utilizzata dal mittente.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altezza della risoluzione utilizzata dal mittente.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Velocità media della trasmissione dei fotogrammi video utilizzata dal mittente.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Velocità in bit massima per il mittente.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Velocità in bit media per il mittente.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero massimo di flussi video utilizzati dal mittente.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Stranieri</p></td>
<td><p>Codici video utilizzati dal destinatario. Per ulteriori informazioni, vedere la <a href="lync-server-2013-codecdescription-table.md">tabella CodecDescription in Lync Server 2013</a> .</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Larghezza della risoluzione utilizzata dal destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altezza della risoluzione utilizzata dal destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Frequenza media dei fotogrammi video utilizzata dal destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Velocità in bit massima per il destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Velocità in bit media per il destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Massimi flussi video per il destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Flussi video minimi per il destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Modalità video (ad esempio, raccolta o singolo flusso) per il destinatario.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Velocità di perdita di pacchetti dopo l'applicazione della correzione degli errori di inoltro.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale di tempo in cui il flag di funzionalità dinamica era attivo.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>Risoluzione minima misurata durante la chiamata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata al di sotto della soglia di velocità in bit bassa (70 kilobit al secondo).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata al di sotto della soglia bassa della frequenza dei fotogrammi (7,5 fotogrammi al secondo, in ingresso).</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Percentuale della chiamata che si è verificata alla risoluzione più bassa.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>galleggiante</p></td>
<td></td>
<td><p>Durata della chiamata in secondi.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Indica se i dati sono stati aggregati da più chiamate.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

