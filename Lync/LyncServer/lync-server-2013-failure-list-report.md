---
title: 'Lync Server 2013: report elenco errori'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Report elenco errori in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-07-02_

Il report elenco errori contiene informazioni sui singoli partecipanti che hanno partecipato a una sessione peer-to-peer o conferenza non riuscita. Queste informazioni includono l'URI dell'utente che ha riscontrato il problema, nonché il codice di risposta SIP e l'ID di diagnostica associati all'errore.

<div>

## <a name="accessing-the-failure-list-report"></a>Accesso al report elenco errori

Per accedere al report elenco errori, fare clic su una delle metriche seguenti nel [report distribuzione errori in Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Principali motivi diagnostici (sessioni)

  - Modalità top (sessioni)

  - Pool principali (sessioni)

  - Origini principali (sessioni)

  - Componenti principali (sessioni)

  - Inizio da utenti (sessioni)

  - Inizio per gli utenti (sessioni)

  - Inizio da agenti utente (sessioni)

Nel report elenco errori è possibile accedere al [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) facendo clic sulla metrica di dettaglio della sessione per una sessione peer-to-peer. È anche possibile accedere al report Dettagli conferenza facendo clic sulla metrica conferenza per una conferenza.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Sfruttare al meglio il report elenco errori

Nel report elenco errori è possibile visualizzare una descrizione per ogni codice di risposta o ogni ID di diagnostica semplicemente tenendo premuto il mouse su tale valore. Ad esempio, se si tiene premuto il mouse sull'ID di diagnostica 7025, in una descrizione comandi verranno visualizzati i seguenti elementi:

Errore del server interno che crea elementi multimediali per l'utente.

È importante notare che il report elenco errori non offre un modo semplice per recuperare direttamente un elenco di tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita, né offre un modo per determinare gli utenti più spesso coinvolti in un errore sessione. Per prima cosa, il report elenco errori non ha funzionalità di filtro. Tuttavia, se si esportano i dati e quindi lo si converte in un file con valori delimitati da virgole, è possibile usare Windows PowerShell per trovare le risposte a domande come quelle. Supponiamo ad esempio di salvare i dati in un. File CSV denominato C:\\errore\\\_di dati List. csv. In base ai dati salvati nel file, questo comando elenca tutti gli utenti che hanno partecipato ad almeno una sessione non riuscita:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Questo comando restituirà un elenco simile al seguente:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Questi due comandi segnalano il numero totale di sessioni non riuscite in cui ogni utente è coinvolto:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Che restituirà dati simili a questi:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report elenco errori.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report elenco errori per ogni chiamata non riuscita.

### <a name="failure-list-report-metrics"></a>Metriche rapporto Elenco errori

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
<td><p><strong>Tempo segnalato</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui il report è stato registrato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Richiesta</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di richiesta SIP non riuscito. Ad esempio, invita o BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Codice di risposta SIP inviato quando la conferenza non è riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tempo di costo di partecipazione (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo (in millisecondi) necessario affinché l'utente partecipi alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dall'utente</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dall'agente utente</strong></p></td>
<td><p>No</p></td>
<td><p>Software usato dall'endpoint dell'utente che ha avviato la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>All'utente</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che veniva chiamato.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

