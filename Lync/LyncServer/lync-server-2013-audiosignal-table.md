---
title: 'Lync Server 2013: Tabella AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950c8457f80c69af5875064fff55c5ac7df61b24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Tabella AudioSignal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-12_

Ogni record rappresenta le metriche del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno è per il chiamante e uno per il chiamato.


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
<td><p><strong>FromCaller</strong></p></td>
<td><p>po'</p></td>
<td><p>Principale</p></td>
<td><p>0: dati del destinatario</p>
<p>1: dati del chiamante</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Rappresenta il livello di segnale audio per il controllo del guadagno post-analogico. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vedere SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Rappresenta il livello di rumore audio del controllo di guadagno post-analogico. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vedere SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Metrica di miglioramento della perdita di echo return. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Inconvenienti medi per cinque minuti per il rendering del diffusore. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Glitch media per cinque minuti per l'acquisizione del microfono. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Velocità di spostamento del dispositivo microfonico, relativo all'orologio della CPU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.</p>
<p>Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Messaggio di errore medio del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Cause della voce di interruttore vocale:</p>
<p>ENTER_VS_BADTS 0X01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0X04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La causa può essere una combinazione di queste singole cause. ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey per scopi di test.</p>
<p>Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Cause di un evento Echo:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0X02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0X10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>La causa può essere una combinazione di queste singole cause.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Percentuale di tempo in cui Echo viene rilevato in Stream inviato. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Livello di segnale ricevuto sul server Mediation dal gateway; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Livello di segnale ricevuto nel server Mediation dal gateway. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Controllo automatico del guadagno (AGC) sul lato Mediation Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>galleggiante</p></td>
<td><p> </p></td>
<td><p>Il quadrato medio radice (RMS) del segnale in arrivo fino ai primi 30 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di segnale ricevuto sul canale 1.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di segnale ricevuto sul canale 2.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di rumorosità ricevuto sul canale 1.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di rumorosità ricevuto sul canale 2.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di segnale inviato sul canale 1.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di segnale inviato sul canale 2.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di rumorosità inviato sul canale 1.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Livello di rumorosità inviato sul canale 2.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

