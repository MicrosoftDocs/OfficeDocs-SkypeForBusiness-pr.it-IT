---
title: 'Lync Server 2013: rapporto di diagnostica conferenze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e735193d75e0e8b5f23376844a712ce0e87d106
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Rapporto di diagnostica conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Il Rapporto di diagnostica conferenze fornisce informazioni sull'esito positivo o negativo di tutte le sessioni di conferenza. Si noti che Microsoft Lync Server distingue tra diversi tipi di errore:

  - **Errore previsto**. Un errore previsto è tipicamente un errore solo in senso strettamente tecnico. Si immagini ad esempio che qualcuno avvii una conferenza, ma poi riagganci prima che qualcuno possa parteciparvi. Tecnicamente parlando, si tratta di un errore: la conferenza è stata avviata, ma non completata. Si tratta tuttavia di un errore previsto: se l'organizzatore annulla la conferenza prima che qualcuno possa parteciparvi, non ci si può aspettare che la conferenza venga completata.

  - **Errore imprevisto**. Un errore imprevisto è esattamente tale, ovvero un errore che, in determinate circostanze, non ci si aspetterebbe. Si immagini ad esempio una conferenza che non possa essere tenuta perché non è possibile recuperare il criterio riunione dell'organizzatore. Questo è un errore imprevisto: dopotutto, dovrebbe essere sempre possibile recuperare il criterio riunione di un utente.

Si noti che le metriche di successo, errore previsto ed errore imprevisto potrebbero non sommarsi alla metrica totale delle sessioni. È ad esempio possibile che il report contenga i valori seguenti:


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


Se si somma 2024 + 469 + 16 si ottiene un totale di 2.509 sessioni, tuttavia, nella colonna Totale sessioni viene indicato un totale di 2.521 sessioni. Le 12 sessioni "mancanti" sono quelle il cui esito non è stato definito come positivo o negativo. A volte si verificherà il caso in cui un prodotto di terze parti introduce un nuovo codice diagnostico non pratico per il Monitoring Server. In questi casi le chiamate fatte utilizzando tale prodotto, che presentano quel codice diagnostico, non possono essere categorizzate con Esito positivo, Errore previsto o Errore imprevisto.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>Accesso al Rapporto di diagnostica conferenze

È possibile accedere al Rapporto di diagnostica conferenze dalla home page di Relazioni monitoraggio. È possibile accedere al [rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) facendo clic su una delle metriche seguenti:

  - Quantità di errori imprevisti

  - Quantità di errori previsti

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Utilizzare al meglio il Rapporto di diagnostica conferenze

Il Rapporto di diagnostica conferenze include una serie di grafici. Ogni colonna del grafico è un collegamento ipertestuale. Se si fa clic su una colonna, sarà possibile eseguire il drill-down [nel rapporto distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md) per quel periodo di tempo e quel tipo di conferenza.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, il Rapporto di diagnostica conferenze consente di filtrare in base al tipo di conferenza condotto (ad esempio, una conferenza basata su Focus) o al server perimetrale utilizzato nella conferenza. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso le conferenze sono raggruppabili per ora, giorno, settimana o mese.

Nella tabella che segue sono elencati i filtri applicabili al Rapporto di diagnostica conferenze.

### <a name="conference-diagnostic-report-filters"></a>Filtri del Rapporto di diagnostica conferenze

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
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
<td><p><strong>Sessioni conferenza</strong></p></td>
<td><p>Indica il tipo di sessione di conferenza. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Sessioni Focus</p></li>
<li><p>Tutte le sessioni MCU</p></li>
<li><p>IM Conferencing</p></li>
<li><p>Condivisione applicazioni</p></li>
<li><p>Conferenze audio/video</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica conferenza per tipo di sessione.

### <a name="conference-diagnostic-report-metrics"></a>Metriche del Rapporto di diagnostica conferenze

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Success volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze riuscite.</p></td>
</tr>
<tr class="even">
<td><p><strong>Success percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze completate con problemi significativi. Questo valore viene calcolato dividendo la quantità di conferenze con esito positivo per il numero totale delle sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected failure volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze in cui &quot;si è&quot; verificato un errore previsto.</p>
<p>Per errore previsto si intende un errore che è previsto che si verifichi. Se ad esempio un utente imposta il proprio stato su Non disturbare, è previsto che qualsiasi chiamata effettuata a tale utente non riesca.</p></td>
</tr>
<tr class="even">
<td><p><strong>Expected failure percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze in cui si è verificato un errore previsto. Questo valore viene calcolato dividendo la quantità totale di errori previsti per il numero totale di sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Unexpected failure volume</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze in cui &quot;si è&quot; verificato un errore imprevisto.</p>
<p>Per errore non previsto si intende un errore che si verifica in un sistema che sembrerebbe altrimenti integro. Ad esempio, una chiamata non dovrebbe essere terminata se il chiamante la mette in attesa. Se questo errore si verifica, viene contrassegnato come imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unexpected failure percentage</strong></p></td>
<td><p>No</p></td>
<td><p>Percentuale di conferenze in cui si è verificato un errore imprevisto. Questo valore viene calcolato dividendo la quantità totale di errori imprevisti per il numero totale di sessioni.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di conferenze, incluse quelle riuscite, non riuscite (per errori previsti e imprevisti) e non categorizzate.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

