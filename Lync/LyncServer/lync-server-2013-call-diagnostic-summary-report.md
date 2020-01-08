---
title: 'Lync Server 2013: report di riepilogo diagnostica chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e747d257e7c88973790e8fd0c9ba828949248598
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Report riepilogo diagnostica chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Il report riepilogo diagnostica chiamata offre una panoramica complessiva delle sessioni peer-to-peer e di conferenza non riuscite. Il report Mostra la frequenza di errore complessiva per entrambi i tipi di sessioni e interrompe ulteriormente le informazioni di errore in base al tipo di modalità di sessione:

  - Messaggistica istantanea

  - Condivisione applicazioni

  - Trasferimento di file

  - Audio

  - Video

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Accesso al report di riepilogo diagnostica chiamata

Il report riepilogo diagnostica chiamata è accessibile dalla Home page dei report di monitoraggio. Nel report di riepilogo diagnostica chiamata è possibile accedere al [report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) facendo clic sulla metrica tasso di errore nella sezione Riepilogo sessione peer-to-peer del report. È anche possibile accedere al [report di diagnostica conferenza in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) facendo clic su una delle metriche di conferenza seguenti:

  - Tasso di errore complessivo della sessione

  - Tasso di errore dello stato di avanzamento

  - Tasso di errore MCU

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Uso ottimale del report di riepilogo diagnostica chiamata

Il report riepilogo diagnostica chiamata include grafici che confrontano i tassi di errore per le varie modalità usate in Microsoft Lync Server 2013. Le colonne in questi grafici sono in realtà hotlinks; ad esempio, se si fa clic sulla colonna messaggistica istantanea per le sessioni peer-to-peer, sarà possibile eseguire il drill-down in un'istanza del [report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un report che fornisce informazioni aggiuntive su tutte le sessioni di messaggistica istantanea incluse nel report di riepilogo di diagnostica delle chiamate.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report riepilogo diagnostica chiamata consente di filtrare in base a un pool di registrazione o a un server perimetrale usato nella sessione. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo di diagnostica chiamata.

### <a name="call-diagnostic-summary-report-filters"></a>Filtri dei report di riepilogo delle chiamate di diagnostica

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
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo di diagnostica delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

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
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni peer-to-peer condotte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tasso di errore</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer non riuscite. Quando si fa clic su questo elemento, il report Mostra il rapporto di diagnostica attività peer-to-peer, in cui vengono visualizzate informazioni più dettagliate sulle sessioni peer-to-peer non riuscite.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica delle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.

### <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

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
<td><p><strong>Totale conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze condotte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale delle sessioni di conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di conferenza condotte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore complessivo della sessione</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale delle sessioni di conferenza totale non riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni di stato attiva</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di conferenza basate su stato non riuscito.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore dello stato di avanzamento</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale delle sessioni di conferenza basate su stato non riuscito.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze basate su server di conferenza (precedentemente noto come unità di controllo multipunto o MCU) che non sono state riuscite.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tasso di errore MCU</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale delle conferenze basate su server di conferenza (precedentemente note come unità di controllo multipunto o MCU) che non sono state riuscite.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

