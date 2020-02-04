---
title: 'Lync Server 2013: report trend qualità media del server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4efb7e2f29c1da75a81f4df4ec586c396d77d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Report trend qualità media server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-12_

Il report tendenze per la qualità dei contenuti multimediali consente di confrontare graficamente fino a 5 Server per la qualità delle metriche dell'esperienza, ad esempio il volume delle chiamate, la percentuale di chiamata scadente, la perdita di pacchetti e il jitter. In questo modo, è più facile eseguire operazioni come identificare i server che eseguono in modo poco corretto, identificare i server sottoutilizzati o identificare i server che vengono sovrautilizzati.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Accesso al report trend qualità media del server

È possibile accedere al report trend qualità media del server da uno dei report seguenti:

  - [Report prestazioni server in Lync server 2013](lync-server-2013-server-performance-report.md) (facendo clic sulla metrica di tendenza)

  - [Report dettagli chiamata in Lync server 2013](lync-server-2013-call-detail-report.md) (facendo clic sulla metrica a/V Edge Server. Se il chiamante o il visitatore è un server, è anche possibile raggiungere il report trend media per la qualità del server facendo clic sul nome dell'endpoint.

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Sfruttare al meglio il report trend di qualità media del server

Quando si fa clic sulla metrica di tendenza nel [report sulle prestazioni del server in Lync server 2013](lync-server-2013-server-performance-report.md) per un server specifico, verrà aperto il report trend qualità media del server. Verrà tuttavia visualizzata solo un'istanza vuota del report. il server selezionato nel report prestazioni server non verrà visualizzato sullo schermo. È invece necessario selezionare il server dall'elenco a discesa Server. Tieni presente che anche l'elenco a discesa dei server include un'opzione Seleziona tutto. Questa opzione non funziona se si hanno più di 5 Server; il report trend Quality media server può visualizzare solo i dati per un massimo di 5 server alla volta.

Nei grafici visualizzati dal report trend qualità media del server, i punti etichettati volume chiamata e percentuale di chiamata scadente sono hotlinks; Se si fa clic su un punto del grafico, verrà aperta un'istanza del [report elenco chiamate in Lync Server 2013](lync-server-2013-call-list-report.md) che mostra le chiamate totali (o chiamate non consentite) per il periodo di tempo specificato.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report trend qualità media del server.

### <a name="server-media-quality-trend-report-filters"></a>Filtri per i report sulle tendenze della qualità multimediale del server

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
<td><p><strong>Intervallo</strong></p></td>
<td><p>Intervallo di tempo. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Ogni ora (può essere visualizzato un massimo di 25 ore)</p></li>
<li><p>Giornaliera (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (può essere visualizzato un massimo di 12 settimane)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 8/7/2012 e una data di fine 9/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di server</strong></p></td>
<td><p>Tipo di server coinvolto nella chiamata. I valori consentiti sono:</p>
<ul>
<li><p>Mediation Server</p></li>
<li><p>A/V Conferencing Server</p></li>
<li><p>A/V Edge Server</p></li>
<li><p>Gateway (Mediation Server)</p></li>
<li><p>Gateway (bypass Mediation Server)</p></li>
<li><p>COME server delle conferenze</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Nome del server coinvolto nella sessione; Questo elenco a discesa viene compilato automaticamente in base al valore del filtro del tipo di server. Quando si compila un report, è possibile selezionare fino a 5 server diversi.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di accesso</strong></p></td>
<td><p>Indica se il partecipante ha effettuato l'accesso alla rete interna o alla rete esterna. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Interno</p></li>
<li><p>Esterno</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete a cui il partecipante è connesso. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un partecipante esterno usa una connessione VPN (Virtual Private Network) durante la sessione. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni disponibili nel report trend qualità media del server.

### <a name="server-media-quality-trend-report-metrics"></a>Metriche dei report sulle tendenze della qualità multimediale del server

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
<td><p>Valore medio della degradazione MOS (Media Option score) sperimentata durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0; un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
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
<td><p>Intervallo di tempo medio (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un punto finale e quindi viceversa. I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</p>
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

