---
title: 'Lync Server 2013: rapporto Dettagli conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51dc2a6834241e355f4a681e4b4d55ef95438fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Rapporto Dettagli conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Il Rapporto Dettagli conferenza offre informazioni dettagliate su tutti gli utenti che hanno partecipato a una conferenza. È ad esempio possibile conoscere la data e l'ora in cui un utente si è unito alla conferenza o in cui l'ha abbandonata e l'agente utente dell'endpoint utilizzato per connettere tale utente alla conferenza. È anche possibile visualizzare informazioni sul ruolo dell'utente in ciascuna conferenza (relatore o partecipante). E ancora più importante, è possibile sapere rapidamente quali utenti si sono uniti alla conferenza e l'hanno completata e quali non ci sono riusciti.

<div>

## <a name="accessing-the-conference-detail-report"></a>Accesso al Rapporto Dettagli conferenza

Il Rapporto Dettagli conferenza è accessibile dai rapporti seguenti:

  - Il [rapporto di controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (facendo clic sulla metrica Dettagli per una conferenza)

  - Il [rapporto Elenco errori in Lync Server 2013](lync-server-2013-failure-list-report.md) (facendo clic sulla metrica conferenza)

  - Il [rapporto attività utente in Lync Server 2013](lync-server-2013-user-activity-report.md) (facendo clic sulla metrica URI conferenza)

Dal rapporto Dettagli conferenza è possibile accedere al [rapporto di diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica del rapporto di diagnostica (dettaglio).

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile applicare filtri al Rapporto Dettagli conferenza.

</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni contenute nella sezione Informazioni conferenza del Rapporto Dettagli conferenza.

### <a name="conference-information-metrics"></a>Metriche Informazioni conferenza

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
<td><p><strong>URI conferenza</strong></p></td>
<td></td>
<td><p>URI assegnato alla conferenza, ad esempio:</p>
<p>SIP: kmyer@litwareinc. com; GRUU; opaque = app: conf: Focus: ID: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDN pool</strong></p></td>
<td></td>
<td><p>Nome di dominio completo del pool di registrazione o del server perimetrale operativo in una sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di inizio</strong></p></td>
<td></td>
<td><p>Data e ora di inizio della conferenza.</p></td>
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


La tabella seguente elenca le informazioni fornite nella sezione Partecipazione conferenza del Rapporto Dettagli conferenza.

### <a name="conference-participation-metrics"></a>Metriche di Partecipazione conferenza

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
<td><p><strong>Utente</strong></p></td>
<td></td>
<td><p>Indirizzo SIP dell'utente che ha partecipato alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ruolo</strong></p></td>
<td></td>
<td><p>Ruolo, ad esempio Relatore, ricoperto dal partecipante alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td></td>
<td><p>Connettività di rete, solitamente Dall'interno o Dall'esterno, per il partecipante.</p></td>
</tr>
<tr class="even">
<td><p>Ora partecipazione</p></td>
<td></td>
<td><p>Data e ora in cui il partecipante si è unito alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora uscita</strong></p></td>
<td></td>
<td><p>Data e ora in cui il partecipante è uscito dalla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agente utente</strong></p></td>
<td></td>
<td><p>Identificatore del software utilizzato dall'endpoint del partecipante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporti di diagnostica</strong></p></td>
<td></td>
<td><p>Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente sono elencate le informazioni fornite nella sezione modalità conferenza del rapporto Dettagli conferenza.

### <a name="conference-modalities-metrics"></a>Metriche di Modalità conferenza

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
<td><p><strong>Utente</strong></p></td>
<td></td>
<td><p>Indirizzo SIP dell'utente che ha partecipato alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora partecipazione</strong></p></td>
<td></td>
<td><p>Data e ora in cui il partecipante si è unito alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora uscita</strong></p></td>
<td></td>
<td><p>Data e ora in cui un partecipante è uscito dalla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI server per conferenze</strong></p></td>
<td></td>
<td><p>URI per il server per conferenze utilizzato nella conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rapporti di diagnostica</strong></p></td>
<td></td>
<td><p>Contiene informazioni relative alla diagnostica e alla risoluzione dei problemi, tra cui codici di risposta SIP, intestazioni di diagnostica, ore di partecipazione alla conferenza e ID diagnostica per le sessioni non riuscite.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

