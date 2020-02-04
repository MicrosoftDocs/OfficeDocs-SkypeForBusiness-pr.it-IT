---
title: 'Lync Server 2013: requisiti per i video client di Lync'
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
ms.openlocfilehash: d174b73bd4369220ae83bc8365267a626849e235
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Requisiti per i video client di Lync per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-01-29_

Questa sezione descrive il supporto hardware video per le chiamate video di Lync 2013 e descrive come determinare la qualità video prevista per varie configurazioni di computer, tablet e dispositivi mobili.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Requisiti e funzionalità di Windows desktop e tablet video

Lync 2013 introduce l'accelerazione hardware per la codifica e la decodifica video in base allo standard di codifica video avanzato H. 264/MPEG-4 Part 10. Questa funzionalità consente ai computer con velocità di clock della CPU inferiore di codificare e decodificare video con risoluzione superiore. I requisiti hardware video variano in base alla configurazione del computer e alla risoluzione video desiderata.

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
<td><p>Decodifica H. 264 con accelerazione hardware con DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>La scheda grafica deve supportare DirectX 9,0 e deve esporre la modalità di decodifica DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Il driver della scheda grafica più recente deve essere installato.</p></li>
</ul>
<div>

> [!NOTE]  
> Per informazioni dettagliate sulle modalità di decodifica, <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>vedere.


</div></td>
</tr>
<tr class="even">
<td><p>Codifica H. 264 con accelerazione hardware: requisiti del chipset</p></td>
<td><p>Sono supportate le soluzioni di codifica video con accelerazione hardware Intel seguenti:</p>
<ul>
<li><p>La seconda e la terza generazione di chipset Intel HD Graphics 2000, 2500, 3000 e 4000 (o versioni successive) con codificatori video hardware integrati. È necessario installare il driver di grafica Intel HD 15.28.9.2884 o il driver più recente che contiene le opzioni seguenti:</p>
<ul>
<li><p>Visualizzare il driver 9.17.10.2884 o il driver più recente</p></li>
<li><p>Hardware Media Foundation Transform (HMFT) versione 3.12.10.31 o l'ultima HMFT</p></li>
</ul></li>
</ul>
<p>Sono supportate le seguenti soluzioni di codifica video con accelerazione hardware AMD (richiede gli aggiornamenti di CU1 per Lync Server 2013):</p>
<ul>
<li><p>AMD video codec Engine, disponibile in diverse schede grafiche discrete e in unità di elaborazione accelerata integrata di processori AMD A-Series accelerati. Il driver del motore di codec AMD video 9.12.0.0 o versione successiva deve essere installato.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Codifica H. 264 con accelerazione hardware: requisiti della fotocamera</p></td>
<td><p>Videocamere USB con codificatore hardware H. 264 integrato conforme alla specifica UVC (USB video Class) versione 1,5.</p>
<div>

> [!NOTE]  
> Lync 2013 supporta le telecamere UVC 1,5 con Windows 8 o Windows 8,1, che include il supporto per UVC 1,5. Dato che Windows 7 non include il supporto per UVC 1,5, Lync 2013 tratta le fotocamere UVC 1,5 come normali fotocamere senza supporto per la codifica hardware.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinazione delle funzionalità di codifica e decodifica video H. 264

In genere, esistono quattro fattori principali che determinano la funzionalità di codifica e decodifica massima di una particolare configurazione del computer:

  - Supporto della decodifica con accelerazione hardware tramite DXVA

  - Supporto per la codifica accelerata hardware

  - Numero di core fisici

  - Indice di Windows Experience (WEI)

Lo strumento di valutazione di sistema Windows (WinSAT) determina il WEI. Quando si esegue lo strumento WinSAT, viene generato un documento XML formale di valutazione nel computer nella directory% windir%\\performance\\WinSAT\\datastore. Questo file XML contiene i due punteggi seguenti che rivestono particolare importanza per la determinazione delle funzionalità di codifica e decodifica:

  - VideoEncodeScore indica la funzionalità di codifica video basata sul software del computer.

  - Il valore GraphicsScore indica la funzionalità di codifica accelerata hardware del computer.

Le tre tabelle seguenti spiegano la funzionalità di codifica e decodifica massima per diversi tipi di PC, a seconda dell'accelerazione hardware supportata. Per le risoluzioni di 640x360 e successive, la frequenza dei fotogrammi supportata massima è di 30 fotogrammi al secondo (fps). Per le risoluzioni inferiori a 640x360, la frequenza dei fotogrammi massima supportata è di 15 fps.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Computer senza DXVA e senza codificatore accelerato hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione encoder in grado</th>
<th>Risoluzione del decoder in grado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 a 15fps per gli scenari di ricezione solo)</p></td>
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


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Computer con DXVA ma senza codificatore accelerato hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione encoder in grado</th>
<th>Risoluzione del decoder in grado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 core e VideoEncodeScore ≥ 3,0</p></td>
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
> Il Punteggio WinSAT in Windows 7 è limitato a un massimo di 7,9. Di conseguenza, la funzionalità di codifica per un computer senza un codificatore accelerato hardware può essere raggiunta solo in Windows 8 o Windows 8,1, dove il punteggio massimo di WinSAT è 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Computer con DXVA e con encoder accelerato hardware per grafica Intel HD

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione encoder in grado</th>
<th>Risoluzione del decoder in grado</th>
<th>Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Tutte le seconde e terze generazioni di Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ° e 3 ° generazione di grafica Intel HD e GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Funzionalità video per dispositivi mobili

La tabella seguente descrive le funzionalità video massime per i dispositivi mobili supportati. Per altre informazioni sul supporto di dispositivi mobili, vedere [pianificazione per i client mobili in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<td><p>Risoluzione massima della codifica H. 264</p></td>
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

