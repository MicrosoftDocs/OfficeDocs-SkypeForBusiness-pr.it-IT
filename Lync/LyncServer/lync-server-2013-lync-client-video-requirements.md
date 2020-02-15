---
title: 'Lync Server 2013: requisiti video di Lync client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d5b06123879f2f9724fbd0f49facb8336d9860
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisiti video di Lync client per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-01-29_

In questa sezione viene descritto il supporto hardware video per le chiamate video di Lync 2013 e viene descritto come determinare la qualità video prevista per le diverse configurazioni di computer, tablet e dispositivi mobili.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Requisiti e funzionalità di Windows desktop e tablet video

Lync 2013 introduce l'accelerazione hardware per la codifica e decodifica video in base allo standard di codifica video avanzato della parte 10 di H. 264/MPEG-4. Questa caratteristica consente ai computer con velocità di clock della CPU inferiori di codificare e decodificare video a risoluzioni più elevate. I requisiti hardware video variano a seconda della configurazione del computer e alla risoluzione video desiderata.

<div>

## <a name="video-hardware-requirements"></a>Requisiti hardware video


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Decodifica H.264 con accelerazione hardware mediante DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>La scheda video deve supportare DirectX 9.0 ed esporre la modalità di decodifica DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Deve essere installato il driver più recente della scheda video.</p></li>
</ul>
<div>

> [!NOTE]  
> Per informazioni dettagliate sulle modalità di decodifica, <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>vedere.


</div></td>
</tr>
<tr class="even">
<td><p>Codifica H.264 con accelerazione hardware: requisiti del chipset</p></td>
<td><p>Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware Intel:</p>
<ul>
<li><p>Chipset Intel HD Graphics 2000, 2500, 3000 e 4000 di seconda e terza generazione (o versioni successive) con codificatori video hardware integrati. È necessaria l'installazione di Intel HD Graphics driver 15.28.9.2884 o dell'ultimo driver contenente quanto segue:</p>
<ul>
<li><p>Visualizzare il driver 9.17.10.2884 o il driver più recente</p></li>
<li><p>Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o l'ultima HMFT</p></li>
</ul></li>
</ul>
<p>Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware AMD (sono necessari aggiornamenti di CU1 per Lync Server 2013):</p>
<ul>
<li><p>AMD video codec Engine, disponibile in diverse schede grafiche discrete e in unità di elaborazione con accelerazione integrata dei processori con accelerazione AMD A-Series. È necessario installare il driver del motore di codec AMD video 9.12.0.0 o versione successiva.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codifica H.264 con accelerazione hardware: requisiti fotocamera</p></td>
<td><p>Fotocamere video USB con codificatore H.264 integrato conforme alla specifica USB Video Class (UVC) versione 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 supporta le fotocamere UVC 1,5 con Windows 8 o Windows 8,1, che include il supporto per UVC 1,5. Poiché Windows 7 non include il supporto per UVC 1.5, Lync 2013 tratta le fotocamere UVC 1.5 come fotocamere normali senza supporto per la codifica hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Individuazione delle funzionalità di codifica e decodifica video H.264

In generale, esistono quattro fattori principali che determinano la capacità di codifica e decodifica massima di una particolare configurazione di computer:

  - Supporto per decodifica con accelerazione hardware mediante DXVA

  - Supporto per la codifica con accelerazione hardware

  - Numero di core fisici

  - Indice prestazioni Windows

Lo strumento Valutazione sistema Windows (WinSAT) determina l'Indice prestazioni Windows. Quando si esegue lo strumento WinSAT, viene generato un documento XML formale di valutazione nel computer nella directory% windir%\\performance\\WinSAT\\datastore. Questo file XML contiene i due punteggi indicati di seguito di particolare importanza per determinare le funzionalità di codifica e decodifica:

  - VideoEncodeScore indica le capacità di codifica video basata su software del computer.

  - Il valore GraphicsScore indica la capacità di codifica con accelerazione hardware del computer.

Nelle tre tabelle seguenti sono indicate le capacità massime di codifica e decodifica per diversi tipi di PC a seconda dell'accelerazione hardware supportata. Per risoluzioni pari a 640x360 e superiori, la massima frequenza dei fotogrammi supportata è pari a 30 fotogrammi al secondo (fps). Per risoluzioni inferiori a 640x360, la massima velocità dei fotogrammi supportata è pari a 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Computer senza DXVA e senza codificatore con accelerazione hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione codificatore</th>
<th>Risoluzione decodificatore</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 a 15 fps solo per scenari di ricezione)</p></td>
<td><p>1 core e VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 core e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 core e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 core e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 core e VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 core e VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>N/D</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Computer con DXVA ma senza codificatore con accelerazione hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione codificatore</th>
<th>Risoluzione decodificatore</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 core e VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 core e VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 core e VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 core e VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 core e VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Il Punteggio WinSAT su Windows 7 è limitato a un massimo di 7,9. Pertanto, la capacità di codifica per un computer senza un codificatore con accelerazione hardware può essere raggiunta solo su Windows 8 o Windows 8,1, dove il punteggio massimo WinSAT è 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Computer con DXVA e con codificatore con accelerazione hardware Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione codificatore</th>
<th>Risoluzione decodificatore</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Tutti i driver Intel HD Graphics di seconda e terza generazione</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Driver Intel HD Graphics di seconda e terza generazione e GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Funzionalità video per dispositivi mobili

Nella tabella seguente vengono descritte le funzionalità video massime per i dispositivi mobili supportati. Per ulteriori informazioni sul supporto dei dispositivi mobili, vedere [Planning for Mobile Clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Risoluzione massima di codifica H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e versioni successive</p></td>
<td><p>VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</p></td>
<td><p>Fino a VGA a seconda del modello di dispositivo</p></td>
</tr>
<tr class="even">
<td><p>Risoluzione massima di decodifica H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S e versioni successive</p></td>
<td><p>VGA: iPad 2 e versioni successive/iPad mini 1 e versioni successive</p>
<p>720p: iPad Air/iPad mini 2/iPad Pro e versioni successive</p></td>
<td><p>Fino a VGA a seconda del modello di dispositivo</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

