---
title: 'Lync Server 2013: report di riepilogo conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Report Riepilogo conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-09-03_

Il report Riepilogo conferenze offre una panoramica complessiva delle sessioni di conferenza online. Una conferenza include in genere più di 2 utenti e richiede l'uso di servizi di conferenza di Microsoft Lync Server 2013. In confronto, una sessione peer-to-peer in genere coinvolge solo 2 utenti e non richiede l'uso dei servizi di conferenza di Lync Server. Le attività peer-to-peer sono segnalate nel [report di riepilogo attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

Il report Riepilogo conferenza non solo indica il numero di conferenze svolte durante un determinato periodo di tempo (ogni ora, ogni giorno, ogni settimana, ogni mese), ma indica anche il totale delle persone che hanno partecipato a tali conferenze e il numero totale di conferenze esclusive organizzatori.

Un organizzatore "univoco" è chiunque abbia pianificato almeno una conferenza. Ad esempio, se Pilar Ackerman pianifica una conferenza che conta come unica organizzazione. Se Ken REQUESTO programma le conferenze di 148, conta anche come unico organizzatore. Ad esempio, la tabella seguente mostra 8 conferenze programmate, ma solo tre organizzatori unici (Ken, Pilar Ackerman e David AHS).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizzatore di conferenze</th>
<th>Data conferenza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David AHS</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Il report Riepilogo conferenza indica anche il numero di conferenze incluse audio e/o video.

<div>

## <a name="accessing-the-conference-summary-report"></a>Accesso al report di riepilogo conferenza

È possibile accedere al report di riepilogo conferenza dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel report attività conferenza facendo clic su una delle metriche seguenti:

  - Totale conferenze

  - Totale partecipanti

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Uso ottimale del report di riepilogo conferenza

I valori totali per la maggior parte delle metriche usate nel report di riepilogo conferenza possono essere trovati nella parte inferiore del report. scorrere verso il basso per visualizzare i valori, ad esempio il numero totale di conferenze detenute durante il periodo di tempo specificato, e il numero totale di persone che hanno partecipato a tali conferenze. Una metrica non totalizzata nella parte inferiore del report è totale organizzatori di conferenze univoci. Perché no? Ecco un motivo. Supponiamo che tu stia esaminando il valore di un mese di dati. Il giorno 1 hai avuto 34 organizzatori di conferenze univoci; il giorno 2 si sono organizzati 27 organizzatori di conferenze univoci. Vuol dire che hai avuto 61 organizzatori di conferenze univoci per questi due giorni? Non necessariamente. Dopo tutto, tutte le 27 persone che hanno organizzato conferenze il giorno 2 potrebbero essere tra le 34 persone che hanno organizzato conferenze il giorno 1. In questo semplice report, ad esempio, si noti che Ken Rein e Pilar Ackerman hanno programmato le conferenze sia in 7/7/2012 che in 7/2/2012:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organizzatore di conferenze</th>
<th>Data conferenza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David AHS</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Per avere un'idea migliore del numero totale di utenti univoci che hanno organizzato conferenze, modificare l'intervallo di tempo; ad esempio, esamina i dati per mese anziché per giorno.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report Riepilogo conferenza consente di scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze sono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza.

### <a name="conference-summary-report-filters"></a>Filtri di report Riepilogo conferenze

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
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, vengono visualizzati solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Tabella seguente le informazioni fornite dal report di riepilogo conferenze.

### <a name="conference-summary-report-metrics"></a>Metriche report Riepilogo conferenze

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
<td><p>Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze (indipendentemente dal tipo di conferenza) che si sono svolte. Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale partecipanti</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di persone che hanno partecipato alle conferenze. Quando si fa clic su questo elemento, nel report viene visualizzato il report attività conferenza per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Partecipanti medi per conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero medio di persone che hanno partecipato a una conferenza. Determinato dividendo le conferenze totali per il totale dei partecipanti.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale conferenze A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze che includono audio o video.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale minuti di conferenza A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di minuti dedicati alle conferenze audio/video.</p>
<p>La metrica totale minuti conferenze A/V riepiloga tutti i tipi di conferenze audio/visive, tra cui: conferenze A/V; Conferenze di messaggistica istantanea; Conferenze di condivisione delle app; Conferenze dati; e conferenze PSTN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale minuti partecipanti alla conferenza A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di minuti per i partecipanti dedicati alle conferenze audio/video. Supponiamo ad esempio che un utente spenda 5 minuti in una conferenza audio/video e un secondo utente passi 3 minuti alla stessa conferenza. Il che rende un totale di 8 minuti per i partecipanti: 5 minuti più 3 minuti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Minuti media di conferenza A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Numero medio di minuti per conferenza audio/video.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Numero totale di organizzatori univoci delle conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che hanno organizzato almeno una conferenza. Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale messaggi conferenza</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di messaggi istantanei inviati durante le conferenze.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

