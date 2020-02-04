---
title: 'Lync Server 2013: report elenco chiamate di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Report elenco chiamate di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le telefonate in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate di Response Group non vengono instradate a una singola persona, ma vengono invece indirizzate a un team di persone denominato gruppo di agenti. Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Lync Server 2013 può automaticamente indirizzare la chiamata al primo agente del supporto tecnico disponibile. In alternativa, Lync Server può porre una serie di domande ("premere 1 se si verificano problemi hardware. Premere 2 Se si verificano problemi di software. Premere 3 Se si verificano problemi di rete. ") quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.

Il report elenco delle chiamate di Response Group rappresenta una raccolta di chiamate effettuate per un determinato periodo di tempo e per un determinato tipo di chiamata. Il report sull'utilizzo dei gruppi di risposte (che deve essere aperto per primo prima di poter aprire il report di elenco delle chiamate di Response Group) riconosce i tipi di chiamata seguenti:

  - **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

  - **Chiamate di successo**. Numero totale di chiamate rilevate dall'applicazione Response Group.

  - **Chiamate offerte**. Numero totale di chiamate trasferite a un agente di Response Group.

  - **Chiamate con risposta**. Numero totale di chiamate effettivamente risolte da un agente di Response Group.

  - Percentuale di chiamate abbandonate. Percentuale di chiamate ricevute dall'applicazione Response Group, ma non è stata mai risolta da un agente. Questo valore viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute. Ad esempio, se sono state ricevute 10 chiamate e 7 sono state risolte, è necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta. Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.

  - **Chiamate trasferite**. Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Accesso al report elenco chiamate di Response Group

È possibile accedere al report elenco delle chiamate di Response Group solo facendo clic su una delle metriche seguenti disponibili nel [report sull'utilizzo dei gruppi di risposte in Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Chiamate ricevute

  - Chiamate di successo

  - Chiamate offerte

  - Chiamate con risposta

  - Chiamate trasferite

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Sfruttare al meglio il report elenco chiamate di Response Group

Il report elenco delle chiamate di Response Group consente di limitare i dati visualizzati alle chiamate che coinvolgono un determinato flusso di lavoro di Response Group. A questo scopo, devi immettere l'URI del flusso di lavoro (l'indirizzo SIP del flusso di lavoro) nella casella URI flusso di lavoro. Prima di poterlo fare, tuttavia, devi essere effettivamente in grado di vedere la casella URI flusso di lavoro. Per visualizzare le opzioni di filtro per il report elenco chiamate di Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del report.

Tieni presente che l'elenco delle chiamate di gruppo di risposta non Visualizza le informazioni sul codice di risposta o sull'ID di diagnostica se tieni premuto il mouse su una di queste metriche. Se sono necessarie altre informazioni, è possibile notare il codice di risposta e/o l'ID di diagnostica e quindi cercare tali valori nel [report errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md).

una domanda simile alla seguente: "quale singolo flusso di lavoro ha ricevuto la maggior parte delle chiamate?", è possibile eseguire le operazioni seguenti:

1.  Nel report sull'utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica chiamate ricevute. Che aprirà il report elenco delle chiamate di Response Group.

2.  Esportare i dati visualizzati nel report elenco chiamate di Response Group. Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi usare Excel per convertire i dati in un file con valori separati da virgole.

3.  Eseguire le analisi con Windows PowerShell.

Ad esempio, se i dati sono stati salvati in un file denominato C:\\elenco\\\_chiamate\_\_di\_gruppo risposta dati. csv, è possibile usare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel report:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

In questo modo le informazioni sono simili alle seguenti:

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Nella tabella seguente sono elencati i filtri che è possibile usare con il report elenco chiamate di Response Group.

### <a name="response-group-call-list-report-filters"></a>Filtri dei report elenco chiamate di Response Group

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
<td><p><strong>URI del flusso di lavoro</strong></p></td>
<td><p>Consente di limitare i dati restituiti al flusso di lavoro del gruppo di risposte specificato. Per usare questo filtro, immettere l'indirizzo SIP del flusso di lavoro. Ad esempio:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate</strong></p></td>
<td><p>Puoi selezionare uno dei tipi di chiamata seguenti:</p>
<ul>
<li><p>Chiamate ricevute</p></li>
<li><p>Chiamate di successo</p></li>
<li><p>Chiamate offerte</p></li>
<li><p>Chiamate con risposta</p></li>
<li><p>Chiamate trasferite</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di elenco delle chiamate di Response Group per ogni chiamata ricevuta dall'applicazione Response Group.

### <a name="response-group-call-list-report-metrics"></a>Metriche del report elenco chiamate di Response Group

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
<td><p><strong>Chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP del chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flusso</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP del flusso di lavoro Response Group.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di inizio</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di inizio della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di fine della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Codice di risposta SIP inviato quando la sessione non è riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

