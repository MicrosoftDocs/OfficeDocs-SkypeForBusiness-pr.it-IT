---
title: 'Lync Server 2013: report di diagnostica conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Report di diagnostica per conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Il report di diagnostica conferenza fornisce informazioni sull'esito positivo e negativo di tutte le sessioni di conferenza. Si noti che il server Microsoft Lync distingue tra diversi tipi di errore:

  - **Errore previsto**. Un errore previsto è in genere un errore solo in senso più tecnico. Ad esempio, supponiamo che qualcuno inizi una conferenza, ma si riaggancia prima che tutti possano partecipare. Tecnicamente si tratta di un errore: la conferenza è stata avviata, ma non è stata completata. Tuttavia, questo è un errore che ci si aspetterebbe di avere: se l'organizzatore Annulla la conferenza prima che tutti possano partecipare, non si prevede che la conferenza venga completata.

  - **Errore imprevisto**. Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi. Supponiamo ad esempio che non sia possibile tenere una conferenza perché non è stato possibile recuperare i criteri della riunione dell'organizzatore. Si tratta di un errore imprevisto: dopo tutto, dovresti sempre essere in grado di recuperare i criteri di riunione di un utente.

Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni. Ad esempio, è possibile che nel report vengano visualizzati i valori seguenti:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Successi</th>
<th>Errori previsti</th>
<th>Errori imprevisti</th>
<th>Totale sessioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni. Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito. A volte succede quando un prodotto di terze parti introduce un nuovo codice diagnostico che non conosce il server di monitoraggio. In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>Accesso al report di diagnostica conferenza

È possibile accedere al report di diagnostica della conferenza dalla Home page dei report di monitoraggio. È possibile accedere al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:

  - Volume di errore imprevisto

  - Volume di errore previsto

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Uso ottimale del report di diagnostica conferenza

Il report di diagnostica conferenza include una serie di grafici. Ognuna delle colonne visualizzate nel grafico è in realtà un collegamento ipertestuale. Se si fa clic su una colonna, è possibile eseguire il drill-down [nel report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) per il periodo di tempo e il tipo di conferenza.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report di diagnostica per le conferenze consente di filtrare in base al tipo di conferenza che viene eseguita, ad esempio una conferenza basata su stato attivo, o dall'Edge Server usato nella conferenza. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica conferenza.

### <a name="conference-diagnostic-report-filters"></a>Filtri di report di diagnostica conferenza

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
<td><p>Indica il tipo di sessione di conferenza. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Sessioni di stato attiva</p></li>
<li><p>Tutte le sessioni MCU</p></li>
<li><p>Conferenza di messaggistica istantanea</p></li>
<li><p>Condivisione applicazioni</p></li>
<li><p>Servizi di conferenza A/V</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica conferenza per ogni tipo di sessione di conferenza.

### <a name="conference-diagnostic-report-metrics"></a>Metriche del report di diagnostica conferenza

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
<td><p><strong>Volume di successo</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze di successo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di successo</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze completate con problemi significativi. Calcolata dividendo il volume di successo per il totale delle sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume di errore previsto</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze in cui &quot;si è&quot; verificato un errore previsto.</p>
<p>Un errore previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di errore prevista</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze con un errore previsto. Calcolata dividendo il volume di errore previsto per le sessioni totali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume di errore imprevisto</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze in cui &quot;si è&quot; verificato un errore imprevisto.</p>
<p>Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di errore imprevisto</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze in cui si è verificato un errore imprevisto. Calcolata dividendo il volume di errore imprevisto per le sessioni totali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze, tra cui conferenze di successo, conferenze non riuscite (errori previsti e errori imprevisti) e conferenze Uncategorized.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

