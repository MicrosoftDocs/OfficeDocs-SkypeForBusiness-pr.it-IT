---
title: 'Lync Server 2013: report posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb42f32313acd3609b21180ddaef90c53c27564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a>Report posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Il report posizione fornisce informazioni sulle metriche di qualità delle chiamate raggruppate in base alla posizione di rete, ossia dalla subnet della rete. Se gli utenti riscontrano problemi con le chiamate, questo report consente di determinare se tali problemi sono diffusi o se sono in gran parte confinati in un determinato segmento di rete.

<div>

## <a name="accessing-the-location-report"></a>Accesso al report posizione

Il report posizione è accessibile dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel report elenco chiamate facendo clic su una delle metriche seguenti:

  - Volume chiamata

  - Percentuale di chiamata scadente

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report posizione consente di filtrare in base a elementi come la posizione in cui è stata originata una chiamata o se la chiamata ha avuto luogo in una connessione wireless o cablata. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report posizione.

### <a name="location-report-filters"></a>Filtri per i report posizione

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
<td><p><strong>Posizione del chiamante</strong></p></td>
<td><p>Subnet IP dell'utente che ha effettuato la chiamata. È possibile selezionare solo <strong>[tutti]</strong> per indicare tutte le subnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Posizione del chiamante</strong></p></td>
<td><p>Subnet IP dell'utente che ha ricevuto la chiamata. È possibile selezionare solo <strong>[tutti]</strong> per indicare tutte le subnet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di rete</strong></p></td>
<td><p>Indica il tipo di rete a cui il client è connesso quando è stata inserita la chiamata. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>Cablata</p></li>
<li><p>Wireless</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se un client esterno usa una connessione VPN (Virtual Private Network) quando la chiamata è stata inserita. Selezionare una delle opzioni seguenti:</p>
<ol>
<li><p>Tutti</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report posizione.

### <a name="location-report-metrics"></a>Metriche del report posizione

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
<td><p><strong>Subnet chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Subnet IP dell'utente che ha effettuato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Subnet IP dell'utente che ha ricevuto la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume chiamata</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di chiamate inserite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di chiamata scadente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Percentuale di chiamate classificate come chiamate scadenti. Una chiamata scadente è una chiamata che almeno una delle metriche misurate ha superato il valore consentito, ad esempio una chiamata con un eccessivo jitter.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Andata e ritorno (MS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Importo medio (in millisecondi) richiesto per un pacchetto RTP (Real-Time Transport Protocol) per spostarsi in un altro endpoint e quindi viceversa. I tempi di andata e ritorno di 100 millisecondi sono considerati di qualità accettabile.</p>
<p>I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali, da una configurazione errata del routing o da un server multimediale di overload. Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Degradazione (MOS)</strong></p></td>
<td><p>Sì</p></td>
<td><p>Valore medio della degradazione media del Punteggio di opinione (MOS) sperimentato durante una chiamata. I valori di degradazione possono variare da un minimo di 0,0 a un massimo di 5,0. Un valore di 0,5 o meno rappresenta una degradazione accettabile. Storicamente, i punteggi delle opzioni medie sono stati calcolati avendo gli utenti valutano la qualità di una chiamata in una scala da 1 a 5. In Lync Server Lync Server usa un set di algoritmi per prevedere in che modo gli utenti avrebbero valutato una chiamata.</p>
<p>I valori di degradazione elevati possono essere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale o un endpoint di overload. L'elevata degradazione genera un audio distorta o perso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perdita di pacchetti</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tasso medio di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione, dalla mancanza di larghezza di banda, dalla congestione wireless o dall'interferenza o da un server multimediale sovraccaricato. La perdita di pacchetti in genere genera un audio distorta o perso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter</strong></p></td>
<td><p>Sì</p></td>
<td><p>Jitter medio rilevato tra gli arrivi del pacchetto RTP. (Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto nascosto del guaritore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto media tra campioni audio nascosti e il totale al numero totale di esempi. (Un esempio di audio nascosto è una tecnica usata per attenuare la transizione brusca che in genere viene causata da pacchetti di rete eliminati). I valori elevati indicano livelli significativi di occultamento delle perdite applicati a causa di perdita di pacchetti o jitter e generano audio distorte o perse.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto allungato guaritore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Rapporto medio tra campioni audio allungati e il totale al numero totale di esempi. (L'audio allungato è l'audio che è stato espanso per mantenere la qualità delle chiamate quando è stato rilevato un pacchetto di rete scartato). I valori alti indicano livelli significativi di stretching dei campioni causati da jitter e generano audio o distorte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporto compresso del guaritore</strong></p></td>
<td><p>Sì</p></td>
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

