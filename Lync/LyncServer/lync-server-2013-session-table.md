---
title: 'Lync Server 2013: tabella Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 554491ebdc09789a2704835dc0dce3ddc34f8b0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Tabella di sessione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-09_

Ogni record rappresenta una sessione che coinvolge audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella Dialog in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Chiave di conferenza. A cui viene fatto riferimento dalla <a href="lync-server-2013-conference-table.md">tabella conferenze in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Chiave di correlazione. A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Categoria della finestra di dialogo; 0 è Lync Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Flag che indica se la chiamata è stata o meno ignorata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Per Lync Server, viene definito un solo valore.</p>
<p>0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Ora di inizio della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Ora di fine della chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Il pool del chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Il pool del destinatario della chiamata. A cui viene fatto riferimento dalla <a href="lync-server-2013-pool-table.md">tabella del pool in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>URI SIP nell'identità p-Asserted SIP (PAI) dell'endpoint di ricezione. A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>URI del chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-user-table.md">tabella user in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Endpoint del chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>po'</p></td>
<td><p>Stranieri</p></td>
<td><p>Agente utente del chiamante. A cui viene fatto riferimento dalla <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Priorità della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Questa colonna è obsoleta e non viene utilizzata in Microsoft Lync Server 2013. Invece, queste informazioni vengono riportate in base alle linee per i media. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>P-Asserted-Identity dell'utente che ha effettuato la chiamata. L'identità P-Asserted-Identity (PAI) viene utilizzata per trasmettere la vera identità dell'utente che ha effettuato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Endpoint che ha ricevuto la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>Agente utente impiegato dall'utente che ha ricevuto la chiamata. Gli agenti utente rappresentano il dispositivo endpoint client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Stranieri</p></td>
<td><p>URI SIP dell'utente che ha ricevuto la chiamata.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

