---
title: 'Lync Server 2013: report di messaggistica istantanea peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Report di messaggistica istantanea peer-to-peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il report di messaggistica istantanea peer-to-peer fornisce informazioni sulla tendenza sulle sessioni di messaggistica immediata (IM) peer-to-peer, suddivise per pool e per tipo di autenticazione. Il report può visualizzare il numero totale di sessioni consentite durante il periodo di tempo specificato, ad esempio giorno per giorno o ora per ora, oppure può visualizzare il numero totale di messaggi istantanei inviati durante il periodo di tempo.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>Accesso al report di messaggistica istantanea peer-to-peer

È possibile accedere al report di messaggistica istantanea peer-to-peer solo aprendo il [report di riepilogo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e quindi facendo clic su una delle metriche seguenti:

  - Totale sessioni di messaggistica istantanea peer-to-peer

  - Totale messaggi di messaggistica istantanea peer-to-peer

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Sfruttare al meglio il report di messaggistica istantanea peer-to-peer

Per impostazione predefinita, il rapporto di messaggistica istantanea peer-to-peer Mostra il numero di messaggi per ora (o giorno), a seconda delle impostazioni. Tuttavia, puoi anche scegliere di visualizzare il giorno per sessioni per ora. A tale scopo, fare clic su **Nascondi/Mostra parametri** nell'angolo in alto a destra della finestra report e quindi fare clic su **conteggio sessioni** nell'elenco **segnala per** .

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report di messaggistica istantanea peer-to-peer.

### <a name="peer-to-peer-im-report-filters"></a>Filtri di report istantanei di messaggistica istantanea peer-to-peer

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
<td><p>Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
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
<td><p>Indica i valori da usare nel report. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Conteggio sessioni</p></li>
<li><p>Numero di messaggi</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per pool

Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per pool

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
<td><p>Nome del pool di registrazione o del server perimetrale.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui sono state svolte le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni o conteggio totale dei messaggi.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione

Nella tabella seguente sono elencate le informazioni fornite nel report di messaggistica istantanea peer-to-peer per ogni tipo di autenticazione usato dai partecipanti in una sessione peer-to-peer.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Metriche per la sessione di messaggistica istantanea peer-to-peer per tipo di autenticazione

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
<td><p><strong>Tipo di autenticazione</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di autenticazione usato dai partecipanti alla sessione. I valori sono in genere uno degli elementi seguenti:</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>Federata</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui sono state svolte le sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni o conteggio totale dei messaggi.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

