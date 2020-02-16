---
title: 'Lync Server 2013: rapporto di diagnostica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a906e131329df1b59c4ac6067a4696871f0bebfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Rapporto di diagnostica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

Nel Rapporto di diagnostica vengono fornite informazioni per la diagnostica e la risoluzione dei problemi di una sessione non riuscita. Queste informazioni includono l'ID diagnostica e l'intestazione di diagnostica segnalati quando la sessione ha avuto esito negativo. L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione di tale ID. Nel rapporto possono inoltre essere inclusi per la risoluzione dei problemi dettagli importanti, noti al componente di segnalazione errori. Ad esempio:

  - Codice di causa fornito dal gateway PSTN che ha generato il problema. Se una chiamata in uscita ha esito negativo sulla rete PSTN, viene generato automaticamente un codice di causa ISUP (ISDN User Part). Un gateway PSTN ad esempio può inviare un codice di causa 34 per indicare l'indisponibilità di circuiti o canali per effettuare la chiamata.

  - FQDN del peer, porta ed errori Winsock per i problemi di connettività.

  - Nomi ricercati per i problemi di risoluzione DNS. Tale risoluzione ha luogo ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome di dispositivo specificato.

<div>

## <a name="accessing-the-diagnostic-report"></a>Accesso al Rapporto di diagnostica

È possibile accedere al rapporto di diagnostica facendo clic sulla metrica del rapporto di diagnostica (dettaglio) nel [rapporto Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o nel rapporto Dettagli conferenza.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il Rapporto di diagnostica.

</div>

<div>

## <a name="metrics"></a>Metriche

La tabella seguente elenca le informazioni disponibili nel Rapporto di diagnostica per ogni sessione.

### <a name="diagnostic-report-metrics"></a>Metriche del Rapporto di diagnostica

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
<td><p><strong>Ora rapporto</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora di registrazione del rapporto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Codice di risposta SIP inviato per la sessione non riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di richiesta</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di richiesta SIP non riuscita. Ad esempio, INVITE, BYE o SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>No</p></td>
<td><p>Origine dell'errore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI utente di origine</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Da agente utente</strong></p></td>
<td><p>No</p></td>
<td><p>Software utilizzato dall'endpoint dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione ms-diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione dei problemi e degli errori.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di contenuto</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di contenuto multimediale con errori. Un tipo di contenuto comune è ad esempio Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard utilizzato per gli annunci di sessione, gli inviti per le sessioni e altre forme di avvio di sessioni multimediali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applicazione</strong></p></td>
<td><p>No</p></td>
<td><p>Applicazione coinvolta nell'errore.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI utente di destinazione</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che è stato invitato nella sessione.</p></td>
</tr>
<tr class="odd">
<td><p>Tempi partecipazione conferenza (ms)</p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo, in millisecondi, che è stato necessario all'utente per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intestazione di diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Descrizione dell'ID diagnostica.</p></td>
</tr>
</tbody>
</table>


È possibile trovare un elenco di errori diagnostici nella [pagina di intestazione MS-Diagnostics](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

