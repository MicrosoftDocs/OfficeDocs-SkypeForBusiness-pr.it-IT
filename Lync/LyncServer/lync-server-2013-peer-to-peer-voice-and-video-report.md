---
title: 'Lync Server 2013: report vocale e video peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Report vocale e video peer-to-peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Il report vocale e video peer-to-peer fornisce un'analisi dettagliata della distribuzione delle chiamate vocali e video in un determinato periodo di tempo, ad esempio chiamate per ora o chiamate per giorno. Il report offre anche l'opzione di visualizzare tutte le chiamate vocali e video effettuate o di visualizzare solo le chiamate di successo o non riuscito. I report mostrano le informazioni sulle chiamate suddivise nei raggruppamenti seguenti:

  - Chiamate per pool

  - Chiamate per tipo di chiamata, ad esempio Lync per una chiamata Lync e una chiamata Lync a una persona nella rete PSTN

  - Chiamate per tipo di accesso (gli utenti hanno effettuato l'accesso alla rete interna e agli utenti connessi alla rete esterna)

  - Chiamate per Mediation Server

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Per accedere al report vocale e video peer-to-peer

È possibile accedere al report vocale e video peer-to-peer solo aprendo il report di riepilogo attività peer-to-peer e quindi facendo clic su una delle metriche seguenti:

  - Totale sessioni audio peer-to-peer

  - Totale minuti audio peer-to-peer

  - Totale sessioni video peer-to-peer

  - Totale minuti di video peer-to-peer

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Per sfruttare al meglio il rapporto voce e video peer-to-peer

È possibile filtrare il report vocale e video peer-to-peer in diversi modi. Tuttavia, le opzioni di filtro sono nascoste dalla visualizzazione per impostazione predefinita. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante **Mostra/Nascondi parametri** nell'angolo in alto a destra della finestra del report.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report vocale e video peer-to-peer.

### <a name="peer-to-peer-voice-and-video-report-filters"></a>Filtri di report vocali e video peer-to-peer

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
<td><p><strong>Tipo di elemento multimediale</strong></p></td>
<td><p>Indica il tipo di elemento multimediale usato nella sessione. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Sia</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Disposizione chiamata</strong></p></td>
<td><p>Indica l'esito positivo o negativo della sessione. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Chiamate di successo</p></li>
<li><p>Chiamate non riuscite</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Report di</strong></p></td>
<td><p>Indica i valori da usare nel report. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Conteggio sessioni</p></li>
<li><p>Minuti di chiamata</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriche per l'attività vocale e video peer-to-peer per pool

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni pool.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Metriche per l'attività vocale e video peer-to-peer per pool

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
<td><p>Nome del pool di registrazione o del server perimetrale usato per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Periodo di data e ora in cui la chiamata ha avuto luogo.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di chiamata effettuata.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Metriche per l'attività vocale e video peer-to-peer tramite il tipo di chiamata

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
<td><p><strong>Tipo di chiamata</strong></p></td>
<td><p>No</p></td>
<td><p>Indica il tipo di chiamata effettuata. I valori sono uno degli elementi seguenti:</p>
<ul>
<li><p>UC-to-UC</p></li>
<li><p>UC-to-PSTN</p></li>
<li><p>PSTN-to-UC</p></li>
<li><p>PSTN-to-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Periodo di data e ora in cui la chiamata ha avuto luogo.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriche per l'attività voce e video peer-to-peer per tipo di accesso

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni tipo di accesso alla rete.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Metriche per l'attività voce e video peer-to-peer per tipo di accesso

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
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>No</p></td>
<td><p>Indica se i client hanno eseguito l'accesso alla rete interna o alla rete esterna quando è stata inserita la chiamata. I valori sono in genere uno degli elementi seguenti:</p>
<ul>
<li><p>Interno</p></li>
<li><p>Esterno</p></li>
<li><p>Misto</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Periodo di data e ora in cui la chiamata ha avuto luogo.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriche per l'attività di voce e video peer-to-peer da Mediation Server

Nella tabella seguente sono elencate le informazioni fornite nel report vocale e video peer-to-peer per ogni Mediation Server.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Metriche per l'attività di voce e video peer-to-peer da Mediation Server

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
<td><p><strong>Mediation Server</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Periodo di data e ora in cui la chiamata ha avuto luogo.</p></td>
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

