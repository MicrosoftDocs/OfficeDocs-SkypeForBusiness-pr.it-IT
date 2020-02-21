---
title: 'Lync Server 2013: rapporto attività conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb548ad27e61284f5bc5f3fff1718faa20ef0e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Report attività conferenze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Con il Rapporto attività conferenza è semplice rispondere a domande come queste: quante conferenze si tengono ogni giorno e quando hanno luogo? Informazioni di questo tipo non sono solo utili di per sé, ma anche come strumenti di risoluzione dei problemi. Si supponga ad esempio che gli utenti si lamentino del fatto che la rete sia particolarmente lenta a metà giornata. Un rapido sguardo ai report sulle attività di conferenza potrebbe suggerire un possibile motivo: molte più conferenze vengono pianificate tra le ore 10:00 e 2:00 poi in qualsiasi altro momento.

Se la lentezza della rete crea problemi, è possibile chiedere agli utenti di riprogrammare alcune delle conferenze in orari di minor traffico.

<div>

## <a name="accessing-the-conference-activity-report"></a>Accesso al Rapporto attività conferenza

Il rapporto attività conferenza è accessibile dal [rapporto riepilogativo conferenze in Lync Server 2013](lync-server-2013-conference-summary-report.md) facendo clic su una delle metriche seguenti:

  - Totale conferenze

  - Totale partecipanti

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>Utilizzo ottimale del Rapporto attività conferenza

Per impostazione predefinita, il Rapporto attività conferenza mostra il numero totale di conferenze per il periodo di tempo specificato (ad esempio il numero totale di conferenze al giorno oppure il numero totale di conferenze all'ora). È tuttavia anche possibile scegliere di visualizzare il numero totale di partecipanti per il periodo di tempo specificato o il numero totale di minuti partecipante. A tale scopo, fare clic sul pulsante Mostra/Nascondi parametri per visualizzare le opzioni di filtro, quindi selezionare una delle seguenti opzioni dall'elenco a discesa Rapporto di:

  - Numero partecipanti

  - Minuti partecipante

  - Numero conferenze

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto attività conferenza.

### <a name="conference-activity-report-filters"></a>Filtri per il Rapporto attività conferenza

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
<td><p>Intervallo di tempo. Selezionare uno dei valori seguenti:</p>
<ul>
<li><p>Orario (è possibile visualizzare al massimo 25 ore)</p></li>
<li><p>Giornaliero (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (è possibile visualizzare un massimo di 12 settimane)</p></li>
<li><p>Mensile (è possibile visualizzare un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, verrà visualizzato solo il numero massimo di valori, a partire dalla data di inizio. Se ad esempio si seleziona l'intervallo Giornaliero con data di inizio 07/07/2012 e data di fine 28/02/2012, verranno visualizzati i dati relativi ai giorni compresi tra 07/08/2012 12.00 e 07/09/2012 12.00, ovvero i dati relativi a un totale di 31 giorni.</p></td>
</tr>
<tr class="even">
<td><p><strong>Rapporto di</strong></p></td>
<td><p>Indica i valori da utilizzare nel rapporto. È possibile selezionare uno dei valori seguenti:</p>
<ul>
<li><p>Numero partecipanti</p></li>
<li><p>Minuti partecipante</p></li>
<li><p>Numero conferenze</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>Metrica delle conferenze per pool

Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni pool.

### <a name="metrics-for-conferences-by-pool"></a>Metrica delle conferenze per pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del pool di registrazione o del server perimetrale utilizzato nella conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui è stata tenuta la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>Metrica delle conferenze per tipo di server

Nella tabella riportata di seguito vengono elencate le informazioni contenute nel Rapporto attività conferenza per ogni tipo di server.

### <a name="metrics-for-conferences-by-server-type"></a>Metrica delle conferenze per tipo di server

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
<td><p><strong>Tipo server per conferenze</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di server utilizzato nella conferenza, in genere uno dei tipi seguenti:</p>
<ul>
<li><p>Web Conferencing Server</p></li>
<li><p>IM Conferencing Server</p></li>
<li><p>Telephony Conferencing Server</p></li>
<li><p>AV Conferencing Server</p></li>
<li><p>Condivisione applicazioni</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Data/ora</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui è stata tenuta la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Totale</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di partecipanti, minuti totali dei partecipanti o numero di conferenze.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

