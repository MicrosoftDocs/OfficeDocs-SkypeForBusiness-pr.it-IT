---
title: 'Lync Server 2013: report di riepilogo conferenza PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8cd36f651a84b25f7e8163a8cfc40aff5162f90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Report di riepilogo conferenza PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

In Microsoft Lync Server 2013 una conferenza PSTN è una conferenza in cui almeno un partecipante compone la parte audio tramite un telefono PSTN (Public Switched Telephone Network). (Un telefono PSTN è un "telefono fisso", un cellulare o un altro telefono che non fa uso di Voice over IP.) Anche se si fa riferimento a conferenze PSTN nei report di monitoraggio, queste conferenze sono forse più comunemente note come conferenze telefoniche con accesso esterno.

Il report Riepilogo conferenza PSTN contiene informazioni su tutte le conferenze PSTN svolte nell'organizzazione, ovvero tutte le conferenze con almeno un utente con accesso esterno. Il report include informazioni sul numero totale di conferenze PSTN, il numero totale di persone che hanno partecipato a tali conferenze e, forse, più importante, il numero totale di utenti con accesso esterno (la metrica totale dei partecipanti PSTN).

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>Accesso al report di riepilogo conferenza PSTN

Il report Riepilogo conferenza PSTN può essere accessibile solo dalla Home page dei report di monitoraggio. Questo report non è collegato ad altri report. Tieni presente che non puoi recuperare informazioni dettagliate sulle chiamate per una conferenza PSTN, in parte perché i singoli endpoint sono responsabili dell'invio di queste informazioni. I telefoni PSTN non sono in grado di tenere traccia o inviare informazioni dettagliate sulle chiamate.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Uso ottimale del report di riepilogo conferenza PSTN

Per determinare la percentuale di tutte le conferenze che includono utenti con accesso esterno, confrontare il valore della metrica totale conferenze PSTN con la metrica totale conferenze disponibile [nel report di riepilogo conferenza in Lync Server 2013](lync-server-2013-conference-summary-report.md).

Se non si vedono tutte le conferenze PSTN che si potrebbero prevedere, tenere presente che la possibilità di organizzare una conferenza che consente agli utenti di accesso esterno dipende dal criterio di conferenza assegnato a un utente: se pochissimi utenti sono autorizzati a tenere premuto PS Conferenze TN si vedranno ovviamente pochissime conferenze PSTN. È possibile verificare rapidamente quale dei criteri di conferenza (se presenti) consente agli utenti di pianificare conferenze PSTN eseguendo il comando seguente da Lync Server Management Shell:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Che restituirà dati simili a questi:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Che restituirà dati simili a questi:

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report Riepilogo conferenza PSTN consente di scegliere la modalità di raggruppamento dei dati. In questo caso, le conferenze vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di riepilogo conferenza PSTN.

### <a name="pstn-conference-summary-report-filters"></a>Filtri report Riepilogo conferenza PSTN

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni nel report di riepilogo conferenza PSTN.

### <a name="pstn-conference-summary-report-metrics"></a>Metriche report Riepilogo conferenza PSTN

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
<td><p>Indica l'intervallo di tempo selezionato. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale conferenze PSTN</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale partecipanti</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di persone che hanno partecipato a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale minuti di conferenza A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Quantità totale di tempo per le conferenze audio/visive.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale minuti partecipanti alla conferenza A/V</strong></p></td>
<td><p>No</p></td>
<td><p>Quantità totale di tempo dei partecipanti audio/visivi. Ad esempio, se un partecipante ha trascorso cinque minuti in una conferenza A/V e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale per i partecipanti alla conferenza A/V sarebbe di otto minuti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Totale partecipanti PSTN</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che hanno eseguito la chiamata a conferenze che hanno consentito l'accesso tramite chiamata in ingresso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minuti totali dei partecipanti PSTN</strong></p></td>
<td><p>No</p></td>
<td><p>Importo totale del tempo di conferenza trascorso dagli utenti con accesso esterno. Ad esempio, se un partecipante con accesso esterno ha trascorso cinque minuti in una conferenza e un altro partecipante ha trascorso tre minuti nella stessa conferenza, il tempo totale dei partecipanti PSTN sarebbe di otto minuti.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizzatori di conferenze univoci</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di utenti che hanno organizzato almeno una conferenza che consentiva l'accesso esterno. Gli utenti che hanno organizzato più di una conferenza vengono conteggiati come un unico organizzatore, proprio come gli utenti che hanno organizzato una singola conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

