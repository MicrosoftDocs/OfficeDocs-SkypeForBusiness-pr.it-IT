---
title: 'Lync Server 2013: report di riepilogo attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Report di riepilogo attività peer-to-peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Il report di riepilogo attività peer-to-peer offre una visualizzazione complessiva delle sessioni di comunicazione peer-to-peer. Una sessione peer-to-peer in genere coinvolge solo due utenti e non richiede l'uso dei servizi di conferenza di Lync Server. In confronto, una conferenza coinvolge in genere più di due utenti e richiede l'uso di servizi di conferenza di Microsoft Lync Server 2013. L'attività conferenza viene segnalata nel report di riepilogo conferenza.

Il report di riepilogo attività peer-to-peer consente di rispondere a domande come le seguenti:

  - Quanti messaggi istantanei peer-to-peer i miei utenti inviano in un giorno tipico?

  - I miei utenti sfruttano effettivamente le funzionalità di condivisione delle applicazioni e di trasferimento di file di Lync Server?

  - Gli utenti si lamentano che la rete sembra lenta in determinate ore del giorno. Quanti minuti sono dedicati alle sessioni audio e video peer-to-peer in questi periodi di tempo?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accesso al report di riepilogo attività peer-to-peer

È possibile accedere al report di riepilogo attività peer-to-peer dalla Home page dei report di monitoraggio. Per aprire il [report di messaggistica istantanea peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , fare clic su una delle metriche seguenti:

  - Totale sessioni di messaggistica istantanea peer-to-peer

  - Totale messaggi di messaggistica istantanea peer-to-peer

Analogamente, è possibile aprire il report vocale e video peer-to-peer facendo clic su una delle metriche seguenti:

  - Totale sessioni audio peer-to-peer

  - Totale minuti sessioni audio peer-to-peer

  - Totale sessioni audio peer-to-peer

  - Totale minuti sessioni audio peer-to-peer

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Sfruttare al meglio il rapporto di riepilogo attività peer-to-peer

Nella parte inferiore del report di riepilogo attività peer-to-peer si trovano i totali per le metriche, ad esempio le sessioni di messaggistica istantanea Total peer-to-peer e i messaggi di messaggistica istantanea totali peer-to-peer. In questo modo è disponibile un breve riepilogo delle informazioni dettagliate presenti nel corpo del report.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report di riepilogo attività peer-to-peer, ad esempio, consente di scegliere la modalità di raggruppamento dei dati. In questo caso, attività raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo attività peer-to-peer.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filtri dei report di riepilogo attività peer-to-peer

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
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
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
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/17/12012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/12012 12:00 da AM a 9/7/12012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di riepilogo attività peer-to-peer.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Metriche rapporto di riepilogo attività peer-to-peer

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
<td><p><strong>Oraria</strong></p>
<p><strong>Quotidiana</strong></p>
<p><strong>Settimanale</strong></p>
<p><strong>Mensile</strong></p></td>
<td><p>No</p></td>
<td><p>Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/17/12012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni peer-to-peer condotte, indipendentemente dal tipo di sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni di messaggistica istantanea peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni di messaggistica istantanea peer-to-peer. Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale messaggi di messaggistica istantanea peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di messaggi istantanei inviati nelle sessioni peer-to-peer. Quando si fa clic su questo elemento, nel report viene visualizzato il report di messaggistica istantanea peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni audio peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate audio peer-to-peer. Quando si fa clic su questo campo, nel report viene visualizzato il report vocale e video peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale minuti sessioni audio peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Quantità totale di tempo trascorso nelle sessioni audio peer-to-peer. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minuti medi della sessione audio peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo medio trascorso nelle sessioni audio peer-to-peer. Calcolata dividendo il tempo totale della sessione audio in base al numero totale di sessioni audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni video peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate video peer-to-peer. Tieni presente che le sessioni video vengono conteggiate anche come sessioni audio: ogni sessione video viene conteggiata come una sessione video e una sessione audio. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale minuti sessioni video peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Quantità totale di tempo trascorso nelle sessioni video peer-to-peer. Quando si fa clic su questo elemento, il report Mostra il report vocale e video peer-to-peer per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Minuti media sessione video peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo medio trascorso nelle sessioni video peer-to-peer. Calcolata dividendo il tempo totale della sessione video in base al numero totale di sessioni video.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni di trasferimento di file peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni peer-to-peer che includevano i trasferimenti di file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale sessioni di condivisione applicazioni peer-to-peer</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni peer-to-peer che includevano la condivisione di applicazioni.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

