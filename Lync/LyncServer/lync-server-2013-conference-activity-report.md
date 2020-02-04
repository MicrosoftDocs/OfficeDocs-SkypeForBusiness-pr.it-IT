---
title: 'Lync Server 2013: report attività conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c098bc3a1c8b937b72707c76a3943866ad7b9fbb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Report attività conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Il report attività conferenza consente di rispondere a domande di questo tipo: il numero di conferenze che si svolgono ogni giorno e quando si svolgono le conferenze? Informazioni come questa sono utili non solo per i propri diritti, ma anche come strumento di risoluzione dei problemi. Supponiamo ad esempio che gli utenti si lamentino che la rete sembra particolarmente lenta a metà giornata. Una breve panoramica dei report sulle attività di conferenza può suggerire un motivo: molte più conferenze vengono programmate tra le ore 10:00 AM e 2:00 PM in qualsiasi momento.

Se la rete lenta causa problemi, è possibile incoraggiare gli utenti a ripianificare alcune conferenze durante i periodi di traffico meno pesante del giorno.

<div>

## <a name="accessing-the-conference-activity-report"></a>Accesso al report attività conferenza

Il report attività conferenza viene eseguito dal [report di riepilogo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md) facendo clic su una delle metriche seguenti:

  - Totale conferenze

  - Totale partecipanti

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>Sfruttare al meglio il report attività conferenza

Per impostazione predefinita, il report attività conferenza Mostra il numero totale di conferenze per il periodo di tempo specificato, ad esempio il numero totale di conferenze per giorno o il numero totale di conferenze per ora del giorno. Tuttavia, è anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo o il numero totale di minuti del partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro e quindi selezionare una delle operazioni seguenti nell'elenco a discesa report per:

  - Conteggio partecipanti

  - Minuti per i partecipanti

  - Conteggio conferenze

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività conferenza.

### <a name="conference-activity-report-filters"></a>Filtri di report attività conferenza

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
<td><p><strong>Report di</strong></p></td>
<td><p>Indica i valori da usare nel report. È possibile selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Conteggio partecipanti</p></li>
<li><p>Minuti per i partecipanti</p></li>
<li><p>Conteggio conferenze</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>Metriche per le conferenze per pool

Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni pool.

### <a name="metrics-for-conferences-by-pool"></a>Metriche per le conferenze per pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del pool di registrazione o del server perimetrale usato nella conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui si è tenuta la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>Metriche per le conferenze per tipo di server

Nella tabella seguente sono elencate le informazioni nel report attività conferenza per ogni tipo di server.

### <a name="metrics-for-conferences-by-server-type"></a>Metriche per le conferenze per tipo di server

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
<td><p><strong>Tipo di server conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di server usato nella conferenza, in genere una delle opzioni seguenti:</p>
<ul>
<li><p>Web Conferencing Server</p></li>
<li><p>Server di conferenza di messaggistica istantanea</p></li>
<li><p>Server delle conferenze telefoniche</p></li>
<li><p>AV Conferencing Server</p></li>
<li><p>Condivisione applicazioni</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui si è tenuta la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale partecipanti, minuti totali partecipanti o numero totale conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

