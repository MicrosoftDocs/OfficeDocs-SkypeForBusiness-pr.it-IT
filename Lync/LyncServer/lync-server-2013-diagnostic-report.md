---
title: 'Lync Server 2013: report di diagnostica'
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
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Report di diagnostica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

Il report di diagnostica fornisce informazioni di diagnostica e risoluzione dei problemi per una sessione non riuscita. Queste informazioni includono sia l'ID di diagnostica che l'intestazione di diagnostica segnalate quando la sessione non è riuscita. L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) che viene associato a un messaggio SIP, mentre l'intestazione di diagnostica fornisce una descrizione associata per l'ID di diagnostica. Il report può anche contenere dettagli utili per la risoluzione dei problemi noti dal componente di creazione di report. Ad esempio:

  - Il codice di causa fornito dal gateway PSTN che ha generato l'errore. Quando una chiamata in uscita ha esito negativo nella rete PSTN, viene generato automaticamente un codice di causa ISDN User Part (ISUP). Ad esempio, un gateway PSTN può inviare il codice di causa 34 per indicare che non è disponibile alcun circuito o canale per completare la chiamata.

  - Errori di FQDN, porta e Winsock peer per i problemi di connettività.

  - Nomi cercati per gli errori di risoluzione DNS. La risoluzione DNS viene applicata ogni volta che un client contatta un server dei nomi e richiede l'indirizzo IP corrispondente al nome del dispositivo specificato.

<div>

## <a name="accessing-the-diagnostic-report"></a>Accesso al report di diagnostica

È possibile accedere al report di diagnostica facendo clic sulla metrica rapporto di diagnostica (dettaglio) nel [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) o nel report Dettagli conferenza.

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report di diagnostica.

</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di diagnostica per ogni sessione.

### <a name="diagnostic-report-metrics"></a>Metriche del report di diagnostica

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
<td><p><strong>Tempo di report</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui il report è stato registrato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Codice di risposta SIP inviato quando la sessione non è riuscita.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di richiesta</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di richiesta SIP non riuscito. Ad esempio, invita, BYE o SERVICE.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fonte</strong></p></td>
<td><p>No</p></td>
<td><p>Origine dell'errore.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Da URI utente</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dall'agente utente</strong></p></td>
<td><p>No</p></td>
<td><p>Software usato dall'endpoint dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo di contenuto</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di contenuto multimediale non riuscito. Ad esempio, un tipo di contenuto comune è Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Applicazione</strong></p></td>
<td><p>No</p></td>
<td><p>Applicazione coinvolta nell'errore.</p></td>
</tr>
<tr class="even">
<td><p><strong>All'URI utente</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente invitato alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p>Orari di partecipazione alla conferenza (MS)</p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo (in millisecondi) che l'utente ha impiegato per partecipare alla conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Intestazione di diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Descrizione dell'ID di diagnostica.</p></td>
</tr>
</tbody>
</table>


Un elenco di errori di diagnostica può essere trovato nella [pagina di intestazione MS-Diagnostics](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

