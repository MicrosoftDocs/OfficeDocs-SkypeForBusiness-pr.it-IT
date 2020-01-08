---
title: "Lync Server 2013: report sull'ora di partecipazione alla conferenza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Report sull'ora di partecipazione alla conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-23_

Il riepilogo dell'ora di partecipazione alla conferenza consente di determinare il tempo impiegato dagli utenti per partecipare a una conferenza. Il report Mostra il tempo medio di partecipazione (in millisecondi) e fornisce anche una ripartizione che consente di conoscere il numero di utenti che hanno potuto partecipare a una conferenza in 2 secondi o meno, il numero di utenti necessari tra 2 e 5 secondi per partecipare alla conferenza e così via.

<div>

## <a name="accessing-the-conference-join-time-report"></a>Accesso al report tempo di partecipazione alla conferenza

È possibile accedere al report Time join della conferenza dalla Home page dei report di monitoraggio.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report tempo di partecipazione alla conferenza.

### <a name="conference-join-time-report-filters"></a>Filtri per i report sull'ora di conferenza

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
<li><p>Mensile (può essere visualizzato un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni di conferenza</strong></p></td>
<td><p>Tipo di sessione. I valori consentiti sono:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Sessioni di stato attiva (lo stato principale è lo stato di policy e il gestore di stato per le riunioni online e coordina tutti gli aspetti di una conferenza</p></li>
<li><p>Condivisione applicazioni</p></li>
<li><p>Servizi di conferenza A/V</p></li>
</ul>
<p>Se si seleziona [tutti], nella parte superiore del report verrà visualizzato il tempo totale di partecipazione alla conferenza. Tieni presente che questi totali sono solo per le conferenze pianificate con Microsoft Exchange o Microsoft Outlook.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report tempo di partecipazione alla conferenza.

### <a name="conference-join-time-report-metrics"></a>Metriche del report Time join conferenza

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
<td><p><strong>Data</strong></p>
<p>Il titolo effettivo per questa metrica sarà diverso a seconda dell'intervallo selezionato.</p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui la conferenza ha avuto luogo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Media (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo medio (in millisecondi) che ha richiesto ai partecipanti di partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni &lt; 2 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno potuto partecipare alla conferenza in meno di 2 secondi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni &lt; 2 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni 2-5 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni 2-5 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 2 secondi e 5 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni 5-10 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni 5-10 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale dei partecipanti totali alle chiamate che hanno impiegato tra 5 secondi e 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni &gt; di 10 secondi, volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di partecipanti che hanno richiesto più di 10 secondi per partecipare alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni &gt; di 10 secondi, percentuale</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale dei partecipanti totali alle chiamate che hanno richiesto più di 10 secondi per partecipare alla conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

