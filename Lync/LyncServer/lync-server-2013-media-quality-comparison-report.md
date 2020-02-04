---
title: 'Lync Server 2013: report di confronto qualità multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Report di confronto qualità multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-22_

Il report di confronto qualità multimediale consente di confrontare i valori della qualità delle chiamate per i diversi tipi di chiamate audio, ad esempio le chiamate effettuate tramite una rete wireless o le chiamate effettuate tramite una connessione cablata.

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>Accesso al report di confronto qualità multimediale

È possibile accedere al report di confronto qualità multimediale dalla Home page dei report di monitoraggio.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report di confronto qualità multimediale.

### <a name="media-quality-comparison-report-filters"></a>Filtri di report di confronto qualità multimediale

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Da</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamate</strong></p></td>
<td><p>Tipo di chiamata da usare come elemento di confronto principale. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Esterno</p></li>
<li><p>Interno</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
<li><p>Esterna e cablata</p></li>
<li><p>Esterno e wireless</p></li>
<li><p>Esterna e VPN</p></li>
<li><p>Esterno e non VPN</p></li>
<li><p>Interni e cablati</p></li>
<li><p>Interni e wireless</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Confronto con le chiamate</strong></p></td>
<td><p>Tipo di chiamata da usare come elemento di confronto secondario. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Esterno</p></li>
<li><p>Interno</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
<li><p>Esterna e cablata</p></li>
<li><p>Esterno e wireless</p></li>
<li><p>Esterna e VPN</p></li>
<li><p>Esterno e non VPN</p></li>
<li><p>Interni e cablati</p></li>
<li><p>Interni e wireless</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Intervallo di tempo. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Ogni ora (può essere visualizzato un massimo di 25 ore)</p></li>
<li><p>Giornaliera (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (può essere visualizzato un massimo di 12 settimane)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di confronto qualità multimediale.

### <a name="media-quality-comparison-report-metrics"></a>Metriche del report di confronto qualità multimediale

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>No</p></td>
<td><p>Importo medio della degradazione MOS (media Opinion Score) con esperienza durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi degli opinion media sono stati calcolati avendo gli utenti valutano la qualità di una chiamata su una scala da 1 a 5. Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
<p>I valori di degradazione elevati possono essere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless oppure un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate classificate come scarse. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="even">
<td><p><strong>Andata e ritorno (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>No</p></td>
<td><p>Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol). La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto nascosto del guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto allungato guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto compresso del guaritore</strong></p></td>
<td><p>No</p></td>
<td><p>Rapporto medio tra campioni audio compressi e il numero totale di esempi. (L'audio compresso è un audio compresso che consente di mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di compressione dei campioni causati da jitter e generano un suono accelerato o distorta.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

