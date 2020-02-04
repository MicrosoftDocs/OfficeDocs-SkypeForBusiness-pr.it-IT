---
title: 'Lync Server 2013: Tabella AudioClientEvent'
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
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabella AudioClientEvent in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-17_

Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.


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
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento NetworkSendQuality è stato generato per lo stato "Bad".</p>
<p>La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".</p>
<p>La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione che l'evento Delay è stato generato per lo stato "Bad". La latenza della rete è grave e ha un impatto sull'esperienza impedendo comunicazioni interattive</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad". La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento CPU insufficiente è stato generato per lo stato "non valido". Sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità e le applicazioni correnti in uso. Ciò causa distorsioni con il canale audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato "Bad". Per evitare l'eco, il sistema ha immesso half duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato "Bad". Il dispositivo di rendering attualmente in uso per la sessione non funziona correttamente. Ciò può causare problemi audio unidirezionali.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato "Bad". Il dispositivo di acquisizione attualmente in uso per la sessione non funziona correttamente. Ciò può causare problemi audio unidirezionali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceGlitches è stato generato per lo stato "Bad". Il rendering dell'audio causa distorsioni è grave. Queste anomalie possono essere causate da problemi di driver, rimandi temporali (DPC), e uso elevato della CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceLowSNR è stato generato per lo stato "Bad". La qualità di acquisizione è molto povera, molto rumorosa o l'utente sta discutendo troppo lontano dal microfono. Questo causerà distorsioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato "Bad". Il livello del discorso dell'utente è troppo basso e il sistema non può aumentarlo ulteriormente. Ciò può causare distorsioni o percepire l'audio unidirezionale.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceClipping è stato generato per lo stato "Bad".</p>
<p>Quando il microfono termina con la fine del discorso, la distorsione viene pronunciata a causa del ritaglio. È importante evitare il ritaglio del microfono vicino alla fine.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceEchoEvent è stato generato per lo stato "Bad". Il dispositivo o la configurazione sta causando l'eco oltre la capacità del sistema di compensare.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Percentuale della sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato "Bad". Il discorso dell'utente è troppo basso rispetto all'eco che viene acquisito, che ha un impatto sull'esperienza degli utenti, perché limita la facilità di interruzione di un utente. Ridurre il volume dell'altoparlante, posizionare il microfono più vicino all'oratore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Numero di volte durante la sessione l'evento DeviceMultipleEndpoints è stato generato per lo stato "Bad". Più endpoint audio nella stessa sessione rilevati e il sistema ha compensato riducendo il volume di rendering.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Numero di volte durante la sessione l'evento DeviceHowlingEvent è stato generato per lo stato "Bad". Loop di feedback audio rilevato (causato da più endpoint che condividono il percorso audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Percentuale della sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato impostato su zero volume.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimale (5; 2)</p></td>
<td></td>
<td><p>Percentuale della sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato disattivato.</p>
<p>Questa colonna è stata introdotta in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

