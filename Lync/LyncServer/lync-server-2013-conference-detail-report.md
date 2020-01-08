---
title: 'Lync Server 2013: report Dettagli conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Report Dettagli conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Il report Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. Ad esempio, puoi visualizzare informazioni come la data e l'ora in cui un utente ha partecipato alla conferenza, la data e l'ora in cui l'utente ha lasciato la conferenza e l'agente utente dell'endpoint usato per connettere l'utente alla conferenza. È anche possibile visualizzare le informazioni sul ruolo dell'utente in ogni conferenza, ad esempio relatore o partecipante. Forse la cosa più importante è vedere rapidamente gli utenti che partecipano e completano la conferenza e che gli utenti non sono stati in grado di partecipare e completare la conferenza con successo.

<div>

## <a name="accessing-the-conference-detail-report"></a>Accesso al report Dettagli conferenza

È possibile accedere al report Dettagli conferenza dai report seguenti:

  - [Report di controllo ammissione chiamata in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (facendo clic sulla metrica di dettaglio per una conferenza)

  - [Report elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md) (facendo clic sulla metrica conferenza)

  - [Report attività utente in Lync Server 2013](lync-server-2013-user-activity-report.md) (facendo clic sulla metrica URI conferenza)

Dal report Dettagli conferenza è possibile accedere al [report di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (dettaglio).

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report Dettagli conferenza.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nella sezione informazioni conferenza del report Dettagli conferenza.

### <a name="conference-information-metrics"></a>Metriche delle informazioni sulla conferenza

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
<td></td>
<td><p>URI assegnato alla conferenza. Ad esempio:</p>
<p>SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: stato attiva: ID: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDN del pool</strong></p></td>
<td></td>
<td><p>Nome di dominio completo del pool di registrazione o del server perimetrale coinvolto in una sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di inizio</strong></p></td>
<td></td>
<td><p>Data e ora in cui è stata avviata la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizzatore</strong></p></td>
<td></td>
<td><p>Indirizzo SIP dell'utente che ha organizzato la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td></td>
<td><p>Data e ora di fine della conferenza.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente sono elencate le informazioni fornite nella sezione partecipazione alla conferenza del report Dettagli conferenza.

### <a name="conference-participation-metrics"></a>Metriche per la partecipazione alla conferenza

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
<td><p><strong>Utente</strong></p></td>
<td></td>
<td><p>Indirizzo SIP dell'utente che ha partecipato alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ruolo</strong></p></td>
<td></td>
<td><p>Ruolo (ad esempio, relatore) riprodotto dal partecipante alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td></td>
<td><p>Connettività di rete (in genere da interno o da esterno) per il partecipante.</p></td>
</tr>
<tr class="even">
<td><p>Tempo di partecipazione</p></td>
<td></td>
<td><p>Data e ora in cui il partecipante ha partecipato alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di uscita</strong></p></td>
<td></td>
<td><p>Data e ora in cui il partecipante ha lasciato la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente</strong></p></td>
<td></td>
<td><p>Identificatore per il software usato dall'endpoint del partecipante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Report di diagnostica</strong></p></td>
<td></td>
<td><p>Fornisce informazioni di diagnostica e risoluzione dei problemi. Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del report Dettagli conferenza.

### <a name="conference-modalities-metrics"></a>Metriche delle modalità conferenza

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
<td><p><strong>Utente</strong></p></td>
<td></td>
<td><p>Indirizzo SIP dell'utente che ha partecipato alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo di partecipazione</strong></p></td>
<td></td>
<td><p>Data e ora in cui il partecipante ha partecipato alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di uscita</strong></p></td>
<td></td>
<td><p>Data e ora in cui un partecipante ha lasciato la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI di conferenza server</strong></p></td>
<td></td>
<td><p>URI per il server delle conferenze usato nella conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Report di diagnostica</strong></p></td>
<td></td>
<td><p>Fornisce informazioni di diagnostica e risoluzione dei problemi. Inclusi i codici di risposta SIP, le intestazioni di diagnostica, le ore di conferenza e gli ID di diagnostica per le sessioni non riuscite.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

