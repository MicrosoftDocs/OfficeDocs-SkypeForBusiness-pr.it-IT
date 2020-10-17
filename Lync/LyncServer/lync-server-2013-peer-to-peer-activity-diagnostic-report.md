---
title: 'Lync Server 2013: rapporto di diagnostica attività peer-to-peer'
description: 'Lync Server 2013: rapporto di diagnostica attività peer-to-peer.'
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
ms.openlocfilehash: 80172c5e0f8b23bf05fad6ec300f0d1ffefb3327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557352"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Rapporto di diagnostica attività peer-to-peer in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Il Rapporto di diagnostica attività peer-to-peer fornisce informazioni sull'esito positivo o negativo delle sessioni di comunicazione peer-to-peer. Si noti che Microsoft Lync Server 2013 distingue diversi tipi di errore:

  - **Errore previsto**. Un errore previsto è in genere un errore solo nel senso più tecnico del termine. Si supponga ad esempio di chiamare un utente, che però non è in ufficio e dunque non può rispondere al telefono. Poiché la chiamata non ha ricevuto risposta, tecnicamente viene considerata un errore. D'altra parte, si è verificato un errore atteso: Microsoft Lync Server 2013 non prevede di rispondere al telefono se non si è a disposizione per rispondere al telefono. Analogamente, si verificherà un errore previsto se si tenta di inviare un messaggio istantaneo a un utente offline, oppure connesso a un telefono che non supporta la messaggistica istantanea.

  - **Errore imprevisto**. Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe. Si supponga, ad esempio, di chiamare qualcuno e che la persona sia disponibile per rispondere alla chiamata; Tuttavia, quando Lync Server 2013 tenta di instradare la chiamata alla segreteria telefonica, la chiamata ha esito negativo perché la connettività alla messaggistica unificata di Exchange è stata persa. Questo è un errore imprevisto: si prevede che le chiamate possano sempre essere instradate alla segreteria telefonica. Come regola generale, gli errori imprevisti sono guasti veri: sono problemi che probabilmente non possono essere risolti tramite l'educazione degli utenti o misure simili.

Tenere presente che la somma delle metriche relative a esiti positivi, errori previsti ed errori imprevisti potrebbe non corrispondere al valore della metrica Totale sessioni. Ad esempio, nell'illustrazione precedente sono presenti i valori seguenti:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operazioni riuscite</th>
<th>Errori previsti</th>
<th>Errori imprevisti</th>
<th>Totale sessioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Sommando 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, ma la colonna Totale sessioni mostra un totale di 2.521 sessioni. Le 12 sessioni "mancanti" sono quelle che il sistema non è riuscito a classificare come riuscite o non riuscite. A volte si verificherà il caso in cui un prodotto di terze parti introduce un nuovo codice diagnostico sconosciuto a Lync Server. Quando ciò accade, le chiamate effettuate usando tale prodotto e contrassegnate da tale codice diagnostico non sempre possono essere correttamente classificate come un esito positivo, un errore previsto o un errore imprevisto.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accesso al Rapporto di diagnostica attività peer-to-peer

Il rapporto di diagnostica peer-to-peer è accessibile dalla home page dei rapporti di monitoraggio. È possibile accedere al [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:

  - Quantità di errori imprevisti

  - Expected failure volume

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Uso ottimale del Rapporto di diagnostica attività peer-to-peer

È possibile filtrare il Rapporto di diagnostica attività peer-to-peer in vari modi, ma per impostazione predefinita le impostazioni di filtro sono nascoste. Per visualizzare le opzioni di filtro disponibili, fare clic sul pulsante Mostra/Nascondi parametri nell'angolo superiore destro della finestra del rapporto. Fatto questo, le opzioni di filtro saranno disponibili per l'utilizzo.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più mirato o di visualizzare i dati restituiti in diversi modi. Il rapporto di diagnostica attività peer-to-peer ad esempio consente di filtrare i dati in base ad aspetti come la modalità della sessione, ovvero messaggistica istantanea, trasferimento di file o condivisione applicazioni. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In tal caso, le chiamate vengono raggruppate in base all'ora, al giorno, alla settimana o al mese.

Nella tabella seguente sono riportati i filtri che è possibile utilizzare con il rapporto di diagnostica attività peer-to-peer.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>Filtri per il rapporto di diagnostica attività peer-to-peer

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
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Selezionare uno dei seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare un massimo di 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
<li><p>Mensile (è possibile visualizzare un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e fine superano il numero massimo di valori consentiti per l'intervallo specificato, verrà visualizzato solo il numero massimo di valori a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati per i giorni da 07/08/2012 ore 00.00 a 07/09/2012 ore 00:00 (per un totale di 31 giorni).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure fare clic su <strong>[Tutto]</strong> per visualizzare i dati di tutti i pool. Le voci disponibili in questo elenco a discesa vengono inserite automaticamente in base ai record presenti nel database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Modalità</strong></p></td>
<td><p>Indica il tipo di attività di comunicazione verificatasi. Selezionare una delle impostazioni seguenti:</p>
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

## <a name="metrics-per-modality"></a>Metrica (per modalità)

Nella tabella seguente sono riportate le informazioni fornite nel rapporto di diagnostica attività peer-to-peer per le singole modalità.

### <a name="metrics-per-modality"></a>Metrica (per modalità)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Success volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni peer-to-peer con esito positivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Success percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer completate con problemi significativi. Viene calcolata dividendo il valore Success volume per il valore Total sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected failure volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni in cui &quot; &quot; si è verificato un errore previsto.</p>
<p>Per errore previsto si intende un errore che è previsto che si verifichi. Se ad esempio un utente imposta il proprio stato su Non disturbare, è previsto che qualsiasi chiamata effettuata a tale utente non riesca.</p></td>
</tr>
<tr class="even">
<td><p><strong>Expected failure percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer in cui si è verificato un errore previsto. Viene calcolata dividendo il valore Expected failure volume per il valore Total sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Unexpected failure volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni in cui &quot; si è verificato un errore imprevisto &quot; .</p>
<p>Per errore non previsto si intende un errore che si verifica in un sistema che sembrerebbe altrimenti integro. Ad esempio, una chiamata non dovrebbe essere terminata se il chiamante la mette in attesa. Se questo errore si verifica, viene contrassegnato come imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unexpected failure percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di sessioni peer-to-peer in cui si è verificato un errore imprevisto. Viene calcolata dividendo il valore Unexpected failure volume per il valore Total sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total sessions</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni, comprendente le sessioni con esito positivo, le sessioni con esito negativo (per errori sia previsti che imprevisti) e le sessioni senza categoria.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

