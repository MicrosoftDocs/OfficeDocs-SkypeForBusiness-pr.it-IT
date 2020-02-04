---
title: 'Lync Server 2013: report di controllo ammissione chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a>Report controllo ammissione chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-29_

Il report controllo ammissione chiamata fornisce informazioni sulle sessioni peer-to-peer e di conferenza che sono state svolte in restrizioni impostate in posizione tramite il controllo di ammissione delle chiamate. Il controllo di ammissione delle chiamate, introdotto in Microsoft Lync Server 2010, consente agli amministratori di consentire alle sessioni di comunicazione (o non consentire) in base ai vincoli di larghezza di banda. Ad esempio, gli amministratori possono creare criteri che impongono un limite alla quantità di larghezza di banda disponibile per le chiamate vocali e video. Se è stato raggiunto il limite di larghezza di banda, non è possibile inserire nuove chiamate vocali o videochiamate finché una delle chiamate correnti non è terminata e ha liberato le risorse di rete necessarie.

<div>

## <a name="accessing-the-call-admission-control-report"></a>Accesso al report di controllo ammissione chiamata

Il report controllo ammissione chiamata si accede dalla Home page dei report di monitoraggio. Nel report controllo ammissione chiamata è possibile eseguire il drill-down per uno dei report seguenti:

  - Report Dettagli conferenza: per accedere a questo report, fare clic sulla metrica dettagli di una sessione di conferenza.

  - Report Dettagli sessione peer-to-peer: per accedere a questo report, fare clic sulla metrica Dettagli per una sessione peer-to-peer.

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Uso ottimale del report di controllo dell'ammissione alle chiamate

Per ottenere un elenco delle chiamate non riuscite a causa della larghezza di banda insufficiente, selezionare chiamate rifiutate a causa del controllo di ammissione di chiamata nell'elenco a discesa categoria chiamata. La maggior parte delle chiamate restituite avrà probabilmente un ID di diagnostica pari a 5:

Larghezza di banda insufficiente per stabilire una sessione. Provare a eseguire la reinstradazione PSTN.

Ciò indica che le limitazioni del controllo di ammissione alle chiamate impedivano che la chiamata venisse eseguita nella rete VoIP.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report controllo ammissione chiamata consente di filtrare le chiamate dall'utente che ha avviato la chiamata o dall'utente che è stato chiamato. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le chiamate vengono raggruppate per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report controllo ammissione chiamata.

### <a name="call-admission-control-report-filters"></a>Filtri dei report di controllo ammissione chiamata

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
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su <strong>[tutti]</strong> per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>Tipo di attività. Selezionare una delle attività seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Peer-to-peer</p></li>
<li><p>Conferenza</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria chiamata</strong></p></td>
<td><p>Indica il motivo per cui è stato usato CAC per la chiamata. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Chiamata rifiutata a causa del controllo di ammissione di chiamata</p></li>
<li><p>Chiamate reinstradate tramite PSTN a causa del controllo di ammissione di chiamata</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

La tabella seguente elenca le informazioni fornite nel report di controllo dell'ammissione delle chiamate per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

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
<td><p><strong>Dettaglio</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, il report Mostra un report Dettagli sessione peer-to-peer per la sessione specificata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dall'utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All'utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente invitato a partecipare alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>Sì</p></td>
<td><p>Modalità di comunicazione (ad esempio audio e video) usate durante la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitare il tempo</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora in cui l'invito alla sessione iniziale è stato inviato all'utente da.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo di risposta</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora in cui è stata ricevuta l'accettazione dell'invito.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di fine della sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione alle chiamate per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.

### <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

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
<td><p><strong>URI conferenza</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore univoco per la conferenza. Quando si fa clic su questo elemento, il report Mostra i singoli partecipanti alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizzatore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha organizzato la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Sì</p></td>
<td><p>Server perimetrale usato nella conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di inizio</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora in cui è stata avviata la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di fine della conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>Metriche per singoli partecipanti alla conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report di controllo dell'ammissione delle chiamate per singoli partecipanti alla conferenza.

### <a name="metrics-for-individual-conference-participants"></a>Metriche per singoli partecipanti alla conferenza

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
<td><p><strong>Ruolo</strong></p></td>
<td><p>No</p></td>
<td><p>Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Partecipante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP del partecipante alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td><p>No</p></td>
<td><p>Connettività di rete (in genere da interno o da esterno) per il partecipante.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di conferenza (ad esempio, A/V Conferencing).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tempo di partecipazione</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui il partecipante ha partecipato alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di uscita</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui il partecipante ha lasciato la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

