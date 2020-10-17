---
title: 'Lync Server 2013: rapporto elenco chiamate Response Group'
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
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511763"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a>Rapporto elenco chiamate Response Group in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le chiamate telefoniche in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate a Response Group non vengono instradate a una singola persona ma piuttosto a un team di persone definito gruppo di agenti. Ad esempio, se un utente chiama il numero di telefono per il supporto tecnico, Lync Server 2013 può instradare automaticamente la chiamata al primo agente del supporto tecnico disponibile. In alternativa, è possibile che Lync Server chieda una serie di domande ("premere 1 se si riscontrano problemi hardware. Premere 2 in caso di problemi software. Premere 3 Se si verificano problemi di rete. " e quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.

Il Rapporto Elenco chiamate Response Group è una raccolta di chiamate di un determinato tipo effettuate per un determinato periodo di tempo. Il Rapporto di utilizzo di Response Group, che deve essere aperto prima di poter aprire il Rapporto Elemento chiamate Response Group, riconosce i tipi di chiamate seguenti:

  - **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

  - **Chiamate riuscite**. Numero totale di chiamate ritirate dall'applicazione Response Group.

  - **Chiamate offerte**. Numero totale di chiamate trasferite a un agente Response Group.

  - **Chiamate con risposta**. Numero totale di chiamate che hanno effettivamente ricevuto una risposta da un agente Response Group.

  - Percentuale di chiamate interrotte. Percentuale di chiamate ricevute dall'applicazione Response Group alle quali però non è stata mai fornita risposta da un agente. Questo valore viene calcolato sottraendo il valore di Chiamate con risposta dal valore di Chiamate ricevute e quindi dividendo tale valore per il numero di Chiamate ricevute. Se ad esempio si ricevono 10 chiamate, di cui 7 con risposta, sarà necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta. Tale valore verrà poi diviso per 10 e si otterrà una percentuale di chiamate interrotte pari al 30%.

  - **Chiamate trasferite**. Numero totale di chiamate di Response Group trasferite a causa del timeout o dell'overflow di una coda.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>Accesso al Rapporto Elenco chiamate Response Group

È possibile accedere al rapporto elenco chiamate Response Group solo facendo clic su una delle metriche riportate di seguito riportate nel [report sull'utilizzo di Response Group in Lync Server 2013](lync-server-2013-response-group-usage-report.md):

  - Chiamate ricevute

  - Chiamate riuscite

  - Chiamate offerte

  - Chiamate con risposta

  - Chiamate trasferite

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Utilizzo ottimale del Rapporto Elenco chiamate Response Group

Il Rapporto Elenco chiamate Response Group consente di limitare i dati visualizzati alle chiamate che interessano un particolare flusso di lavoro di Response Group. A tale scopo, è necessario immettere l'URI del flusso di lavoro, ovvero l'indirizzo SIP del flusso di lavoro, nella casella URI flusso di lavoro. Prima di poter immettere tali informazioni, è tuttavia necessario che la casella URI flusso di lavoro sia visibile. Per visualizzare le opzioni di filtro per il Rapporto Elenco chiamate Response Group, fare clic sul pulsante Mostra/Nascondi parametri nella parte superiore sinistra della finestra del rapporto.

Si noti che nell'elenco chiamate Response Group non vengono visualizzate informazioni relative al codice di risposta o all'ID diagnostica posizionando il puntatore del mouse su una di queste metriche. Se sono necessarie ulteriori informazioni, è possibile prendere nota del codice di risposta e/o dell'ID di diagnostica e quindi cercare tali valori nel [rapporto errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md).

Per sapere ad esempio quale singolo flusso di lavoro ha ricevuto il maggior numero di chiamate, è possibile eseguire le operazioni seguenti:

1.  Nel Rapporto di utilizzo di Response Group impostare il periodo di tempo desiderato e quindi fare clic sulla metrica Chiamate ricevute. Verrà aperto il Rapporto Elenco chiamate Response Group.

2.  Esportare i dati visualizzati nel Rapporto Elenco chiamate Response Group. Ad esempio, è possibile esportare i dati nel formato di Microsoft Excel e quindi utilizzare Excel per convertire tali dati in un file con valori delimitati da virgole.

3.  Eseguire le analisi utilizzando Windows PowerShell.

Ad esempio, se i dati sono stati salvati in un file denominato C: \\ data \\ Response \_ Group \_ Call \_ List \_Report.csv, è possibile utilizzare il comando seguente per restituire il numero totale di chiamate ricevute per ogni flusso di lavoro elencato nel rapporto:

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

Verranno restituite informazioni simili alle seguenti:

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

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Nella tabella seguente sono elencati i filtri applicabili al rapporto Elenco chiamate Response Group.

### <a name="response-group-call-list-report-filters"></a>Filtri rapporto Elenco chiamate Response Group

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
<td><p><strong>URI flusso di lavoro</strong></p></td>
<td><p>Consente di limitare i dati restituiti al flusso di lavoro di Response Group specificato. Per utilizzare questo filtro, immettere l'indirizzo SIP del flusso di lavoro, ad esempio:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate</strong></p></td>
<td><p>È possibile selezionare uno dei tipi di chiamata seguenti:</p>
<ul>
<li><p>Chiamate ricevute</p></li>
<li><p>Chiamate completate</p></li>
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

Nella tabella seguente sono elencate le informazioni fornite nel rapporto Elenco chiamate Response Group Call per ogni chiamata ricevuta dall'applicazione Response Group.

### <a name="response-group-call-list-report-metrics"></a>Metriche del rapporto Elenco chiamate Response Group

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
<td><p><strong>Chiamante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP del chiamante.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flusso di lavoro</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP del flusso di lavoro Response Group.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora inizio</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di inizio della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora fine</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di fine della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Codice di risposta SIP inviato per la sessione non riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

