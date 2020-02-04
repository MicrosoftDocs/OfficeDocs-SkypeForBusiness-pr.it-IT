---
title: 'Lync Server 2013: report di distribuzione degli errori'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5250b03aef3fb77de2cbeefa4688a150c9b4a302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Report di distribuzione dell'errore in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Il rapporto di distribuzione errori non è in grado di classificare le sessioni non riuscite nelle categorie seguenti:

  - Principali motivi diagnostici

  - Modalità top

  - Pool principali

  - Origini principali

  - Componenti principali

  - Inizio degli utenti

  - Inizio per gli utenti

  - Inizio da agenti utente

Puoi usare queste categorie per determinare esattamente dove si verifica un problema e, in alcuni casi, perché il problema si verifica. Ad esempio, si supponga di aver registrato 242 sessioni audio/video non riuscite durante un giorno specifico. Se si esamina il report di distribuzione degli errori, potrebbe essere necessario che 237 di tali sessioni non riuscite sia avvenuto nel pool di Dublino. Questo ti offre un buon punto di partenza per il rilevamento e la diagnosi delle cause che stanno dietro a questi errori. Se si fa clic sul pool Dublin nella categoria **Top pools** , verrà visualizzato un report di distribuzione di errore solo per il pool. È quindi possibile iniziare ad analizzare il motivo per cui il pool di Dublino stava vivendo tante difficoltà.

<div>

## <a name="viewing-the-failure-distribution-report"></a>Visualizzazione del report di distribuzione degli errori

È possibile accedere al report di distribuzione dell'errore da uno dei report seguenti facendo clic sul **volume di errore previsto** o sulla metrica di **volume errore imprevisto** :

  - [Report errori principali in Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Report di diagnostica per conferenze in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Report di diagnostica attività peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

Nel report distribuzione errori è possibile fare clic su una delle metriche seguenti per visualizzare il [report elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md):

  - Principali motivi diagnostici (sessioni)

  - Modalità top (sessioni)

  - Pool principali (sessioni)

  - Origini principali (sessioni)

  - Componenti principali (sessioni)

  - Inizio da utenti (sessioni)

  - Inizio per gli utenti (sessioni)

  - Inizio da agenti utente (sessioni)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>Uso del report distribuzione errori

A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dati visualizzati nel report di distribuzione dell'errore vengano troncati durante la visualizzazione sullo schermo. Questo vale soprattutto per le metriche, ad esempio gli agenti utente, che possono avere etichette molto lunghe. Ad esempio, un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" potrebbe essere visualizzato solo parzialmente sullo schermo:

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft ly...

Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente tenendo il mouse sopra il valore troncato.

Una metrica interessante in cui è possibile applicare il filtro usando il report distribuzione errori è ID diagnostica. Se viene visualizzato lo stesso ID diagnostica in altri report, è possibile filtrare tale ID nel report distribuzione errori e ottenere un'analisi dettagliata precisamente dove e con quale frequenza è stato segnalato l'ID durante una sessione non riuscita.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report di distribuzione non riuscito consente di filtrare in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o l'ID di diagnostica che ha accompagnato ogni sessione non riuscita.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report di distribuzione dell'errore.

### <a name="failure-distribution-report-filters"></a>Filtri dei report di distribuzione errori

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
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>Tipo di attività su cui applicare il filtro. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Peer-to-peer</p></li>
<li><p>Conferenza</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria sessione</strong></p></td>
<td><p>Indica se l'attività in questione è riuscita o meno. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Successo</p></li>
<li><p>Errore previsto</p></li>
<li><p>Errore imprevisto</p></li>
</ul>
<p>Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>Metriche per i principali motivi diagnostici

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base all'ID di diagnostica segnalato più di frequente.

### <a name="metrics-for-top-diagnostic-reasons"></a>Metriche per i principali motivi diagnostici

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base agli ID di diagnostica. L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione degli errori.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principali motivi diagnostici</strong></p></td>
<td><p>No</p></td>
<td><p>ID di diagnostica generato in una sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite in cui è stato generato l'ID di diagnostica specificato.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Metriche per le modalità top

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base alle modalità di sessione che hanno registrato più errori.

### <a name="metrics-for-top-modalities"></a>Metriche per le modalità top

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa basata sulla sessione non riuscita in base al tipo di sessione, ad esempio una conferenza audio/video o una sessione di trasferimento di file peer-to-peer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalità top</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite che coinvolgono la modalità specificata.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>Metriche per i pool principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai pool che hanno sperimentato più errori.

### <a name="metrics-for-top-pools"></a>Metriche per i pool principali

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool principali</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del pool di registrazione o del server perimetrale.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per ogni pool di registrar o Edge Server.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>Metriche per le origini principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai computer con più errori.

### <a name="metrics-for-top-sources"></a>Metriche per le origini principali

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite per ogni computer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Origini principali</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del computer coinvolto nella sessione non riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per computer.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>Metriche per i componenti principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai componenti di Microsoft Lync Server 2010 che hanno sperimentato la maggior parte degli errori.

### <a name="metrics-for-top-components"></a>Metriche per i componenti principali

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base al componente Lync Server 2010 (ad esempio, ExumRouting, GroupChat o MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>Componenti principali</strong></p></td>
<td><p>No</p></td>
<td><p>Nome del componente coinvolto nella sessione non riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per componente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>Metriche per l'inizio degli utenti

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato la maggior parte degli errori quando hanno tentato di chiamare un altro utente (detto "da" utenti).

### <a name="metrics-for-top-from-users"></a>Metriche per l'inizio degli utenti

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base all'utente invitato a partecipare alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inizio degli utenti</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente invitato a partecipare alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per utente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>Metriche per i primi utenti

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato più errori quando un altro utente ha provato a chiamarli (detti "a" utenti).


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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base all'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inizio per gli utenti</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per utente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>Metriche per gli agenti Top User

La tabella seguente elenca le informazioni fornite nel report di distribuzione dell'errore in base al software dell'endpoint che ha riscontrato la maggior parte degli errori.

### <a name="metrics-for-top-user-agents"></a>Metriche per gli agenti Top User

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
<td><p><strong>Rango</strong></p></td>
<td><p>No</p></td>
<td><p>Classificazione relativa delle sessioni non riuscite in base all'agente utente (software) coinvolto nella sessione. Ad esempio: RTCC/4.0.0.0 routing in ingresso/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agenti utente principali</strong></p></td>
<td><p>No</p></td>
<td><p>Nome dell'agente utente coinvolto nella sessione non riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessioni</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di sessioni non riuscite per agente utente.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

