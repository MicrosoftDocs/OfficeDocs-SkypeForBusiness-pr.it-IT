---
title: 'Lync Server 2013: report errori principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Report errori principali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Il report errori principali offre un'occhiata agli errori più comunemente segnalati e alle relative tendenze nel tempo. Gli errori si basano su una combinazione delle due metriche seguenti:

  - **ID diagnostica**. Identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP. Gli ID di diagnostica contengono informazioni utili per la risoluzione dei problemi relativi alle chiamate.

  - **Codice di risposta**. I codici di risposta vengono usati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP. Ad esempio, supponiamo che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken si chiami Pilar Ackerman). Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto. Il report errori principali include solo i codici di risposta inviati in risposta a un errore di chiamata. Lync Server non tiene traccia di tutti i codici di risposta emessi durante il corso di una chiamata.

Le informazioni vengono segnalate non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti interessati dall'errore.

<div>

## <a name="accessing-the-top-failures-report"></a>Accesso al report errori principali

Il report errori principali si accede dalla Home page dei report di monitoraggio. Facendo clic sulla metrica delle sessioni segnalate si accede al [report di distribuzione dell'errore in Lync Server 2013](lync-server-2013-failure-distribution-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Sfruttare al meglio il report errori principali

Il report errori principali è inusuale in un aspetto: consente di filtrare fino a un massimo di 5 ID di diagnostica contemporaneamente. In genere è possibile filtrare solo su un elemento, ad esempio un indirizzo SIP dell'utente, alla volta. Per filtrare su più ID di diagnostica, è sufficiente immettere ogni ID nella casella ID di diagnostica, separandoli con virgole. Se si vuole, è possibile abbandonare uno spazio vuoto dopo ogni virgola. Per esempio:

1011, 2412, 1033, 52116, 1008

A tale scopo, verranno visualizzate solo le chiamate non riuscite che segnalano almeno uno di questi cinque ID diagnostici.

Se si tiene premuto il mouse su un codice di risposta, viene visualizzata una descrizione comando che indica il significato del codice di risposta in questione. Ad esempio, se si tiene premuto il puntatore del mouse sul codice di risposta 486, viene visualizzato il messaggio seguente:

Occupato qui.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report errori principali, ad esempio, consente di filtrare i dati restituiti in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o il codice di risposta SIP che ha accompagnato la sessione non riuscita. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report errori principali.

### <a name="top-failures-report-filters"></a>Filtri di report errori principali

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
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>Tipo di attività. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Peer-to-peer</p></li>
<li><p>Conferenza</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>In questo momento l'unica opzione disponibile è <strong>[tutti]</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Categoria</strong></p></td>
<td><p>Tipo di errore sperimentato. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Errore sia previsto che imprevisto</p></li>
<li><p>Errore imprevisto</p></li>
</ul>
<p>Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>Codice di risposta SIP inviato quando la conferenza non è riuscita. Immettere l'intero codice di risposta, ad esempio:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report errori principali.

### <a name="top-failures-report-metrics"></a>Principali errori di report sulle metriche

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
<td><p>Sì</p></td>
<td><p>Rango relativo in base al numero di sessioni segnalate.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessioni segnalate</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di sessioni non riuscite in base all'ID di diagnostica e al codice di risposta SIP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utenti interessati</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero totale di utenti interessati dalla sessione non riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>Informazioni sull'errore</strong></p></td>
<td><p>No</p></td>
<td><p>Informazioni dettagliate sull'errore, incluso l'ID di diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione non è riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tendenza in passato</strong></p></td>
<td><p>No</p></td>
<td><p>Grafico delle sessioni non riuscite nel tempo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

