---
title: 'Lync Server 2013: Tabella AudioClientEvent'
description: 'Lync Server 2013: Tabella AudioClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568782"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabella AudioClientEvent in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-17_

Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.


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
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>po'</p></td>
<td><p>Principale</p></td>
<td><p>0: dati del destinatario della chiamata</p>
<p>1: dati del chiamante</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento NetworkSendQuality è stato generato per lo stato ' Bad '.</p>
<p>La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</p>
<p>La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento Delay è stato generato per lo stato ' Bad '. La latenza della rete è grave e influisce sull'esperienza impedendo le comunicazioni interattive</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '. La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento CPU insufficiente è stato generato per lo stato ' Bad '. Non sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità correnti e le applicazioni in uso. In questo modo le distorsioni vengono causate dal canale audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato ' Bad '. Al fine di prevenire l'eco, il sistema ha immesso half duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato ' Bad '. Il dispositivo di rendering attualmente utilizzato per la sessione non funziona correttamente. Ciò può causare problemi di tipo audio unidirezionale.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato ' Bad '. Il dispositivo di acquisizione attualmente utilizzato per la sessione non funziona correttamente. Ciò può causare problemi di tipo audio unidirezionale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceGlitches è stato generato per lo stato ' Bad '. Vi sono gravi problemi di rendering dell'audio che causano distorsioni. Questi difetti possono essere causati da problemi relativi ai driver, dalla tempesta di chiamate di routine posticipate (DPC) e dall'elevato utilizzo della CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceLowSNR è stato generato per lo stato ' Bad '. La qualità di acquisizione è molto scarsa, sia molto rumoroso o l'utente sta parlando troppo lontano dal microfono. Ciò provocherà distorsioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato ' Bad '. Il livello di sintesi vocale dell'utente è troppo basso e il sistema non può aumentare ulteriormente. Questo può causare distorsioni o percepito come un audio unidirezionale.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceClipping è stato generato per lo stato ' Bad '.</p>
<p>Quando il microfono viene ritagliato da un punto di vista intermedio, la distorsione di fine-estremità si sente a causa del clipping. È importante evitare il clipping del microfono near-end.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento cui è stato generato per lo stato ' Bad '. Il dispositivo o il programma di installazione stanno causando l'eco oltre la capacità del sistema di compensare.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale di sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato ' Bad '. La voce dell'utente è troppo bassa rispetto all'acquisizione dell'eco che influisce sull'esperienza degli utenti, in quanto limita la facilità di interruzione di un utente. Ridurre il volume degli altoparlanti, spostare il microfono più vicino all'oratore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di volte durante la sessione in cui è stato generato l'evento DeviceMultipleEndpoints per lo stato ' Bad '. Sono stati rilevati più endpoint audio nella stessa sessione e il sistema ha compensato la riduzione del volume di rendering.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Numero di volte durante la sessione in cui è stato generato l'evento DeviceHowlingEvent per lo stato ' Bad '. Ciclo di commenti e suggerimenti audio rilevato (causato da più endpoint che condividono il percorso audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Percentuale di sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato impostato su zero volume.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td></td>
<td><p>Percentuale di sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad". La periferica di rendering è stata disattivata.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

