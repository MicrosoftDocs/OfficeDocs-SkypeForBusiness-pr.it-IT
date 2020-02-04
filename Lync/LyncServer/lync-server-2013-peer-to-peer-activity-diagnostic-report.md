---
title: 'Lync Server 2013: report di diagnostica attività peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc98f1c81f79605da2de2b06397d8a23d8086861
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Report di diagnostica attività peer-to-peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Il report di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo e negativo delle sessioni di comunicazione peer-to-peer. Si noti che Microsoft Lync Server 2013 distingue diversi tipi di errore:

  - **Errore previsto**. Un errore previsto è in genere un errore solo in senso più tecnico. Ad esempio, supponiamo che tu chiami qualcuno, ma che sia fuori sede e che non sia in grado di rispondere al telefono. Dato che la chiamata non è stata risolta, la chiamata è tecnicamente considerata un errore. In compenso, si è verificato un errore previsto: Microsoft Lync Server 2013 non si aspetta di rispondere al telefono se non si è disponibili per rispondere al telefono. Allo stesso modo, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline oppure si accede solo a un telefono che non supporta la messaggistica istantanea.

  - **Errore imprevisto**. Un errore imprevisto è esattamente quello che il nome implica: un errore che, in base alle circostanze, non si aspetterebbe che si verifichi. Ad esempio, supponiamo che tu chiami qualcuno e che la persona sia disponibile per rispondere alla chiamata; Tuttavia, quando Lync Server 2013 prova a instradare la chiamata alla segreteria telefonica, la chiamata non riesce perché la connettività alla messaggistica unificata di Exchange è stata persa. Si tratta di un errore imprevisto: ci si aspetterebbe che le chiamate vengano sempre indirizzate alla segreteria telefonica. Come regola generale, gli errori imprevisti sono errori reali: si tratta di problemi che probabilmente non possono essere risolti tramite l'istruzione degli utenti o misure simili.

Tieni presente che l'esito positivo, l'errore previsto e le metriche degli errori imprevisti potrebbero non essere sommati alla metrica totale delle sessioni. Nella figura precedente, ad esempio, sono presenti i valori seguenti:


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


Se si aggiunge 2024 + 469 + 16 si ottengono complessivamente 2.509 sessioni, ma la colonna Total Sessions Mostra un totale di 2.521 sessioni. Le sessioni "mancanti" di 12 sono sessioni che il sistema non è in grado di categorizzare in modo riuscito o fallito. A volte succede quando un prodotto di terze parti introduce un nuovo codice diagnostico sconosciuto a Lync Server. In questo caso, le chiamate effettuate tramite tale prodotto e segnalando il codice diagnostico non possono sempre essere categorizzate come un successo, un errore previsto o un errore imprevisto.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accesso al report di diagnostica attività peer-to-peer

Il report di diagnostica peer-to-peer si accede dalla Home page dei report di monitoraggio. È possibile accedere al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:

  - Volume di errore imprevisto

  - Volume di errore previsto

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Sfruttare al meglio il rapporto di diagnostica attività peer-to-peer

Esistono diversi modi per filtrare il report di diagnostica attività peer-to-peer ma, per impostazione predefinita, le opzioni di filtro sono nascoste dalla visualizzazione. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo in alto a destra della finestra del report. Dopo aver eseguito l'operazione, le opzioni di filtro saranno disponibili per l'uso.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report di diagnostica attività peer-to-peer, ad esempio, consente di filtrare in base alla modalità di sessione, ad esempio la messaggistica istantanea, il trasferimento di file o la condivisione di applicazioni. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di diagnostica attività peer-to-peer.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>Filtri di report di diagnostica attività peer-to-peer

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
<td><p><strong>Modalità</strong></p></td>
<td><p>Indica il tipo di attività di comunicazione che ha avuto luogo. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Messaggistica istantanea</p></li>
<li><p>Trasferimento di file</p></li>
<li><p>Condivisione applicazioni</p></li>
<li><p>Audio</p></li>
<li><p>Video</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>Metriche (per modalità)

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica attività peer-to-peer per ogni modalità.

### <a name="metrics-per-modality"></a>Metriche (per modalità)

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
<td><p>Numero totale di sessioni peer-to-peer di successo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di successo</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer completate da problemi significativi. Calcolata dividendo il volume di successo per il totale delle sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume di errore previsto</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni in cui &quot;si è&quot; verificato un errore previsto.</p>
<p>Un errore previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di errore prevista</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer che hanno avuto un errore previsto. Calcolata dividendo il volume di errore previsto per le sessioni totali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume di errore imprevisto</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni in cui &quot;si è&quot; verificato un errore imprevisto.</p>
<p>Un errore imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di errore imprevisto</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer che hanno registrato un errore imprevisto. Calcolata dividendo il volume di errore imprevisto per le sessioni totali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni, incluse le sessioni di successo, le sessioni non riuscite (errori previsti e gli errori imprevisti) e le sessioni Uncategorized.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

