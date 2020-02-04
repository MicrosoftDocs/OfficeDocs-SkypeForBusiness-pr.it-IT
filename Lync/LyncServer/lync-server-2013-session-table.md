---
title: 'Lync Server 2013: Tabella Session'
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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Tabella Session in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-09_

Ogni record rappresenta una sessione che include audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione viene definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.


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
<td><p>DateTime</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella della finestra di dialogo in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-dialog-table.md">tabella della finestra di dialogo in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Tasto Conferenza. A cui si fa riferimento dalla <a href="lync-server-2013-conference-table.md">tabella conferenze in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Chiave di correlazione. A cui si fa riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>po'</p></td>
<td><p> </p></td>
<td><p>Categoria finestra di dialogo; 0 è il server di Lync per mediazione server; 1 è Mediation Server per la gamba del gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Contrassegno che indica se la chiamata è stata ignorata o meno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Questo campo, se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono. Per Lync Server, viene definito un solo valore.</p>
<p>0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p> </p></td>
<td><p>Chiama ora di inizio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p> </p></td>
<td><p>Ora di fine chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Pool del chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-pool-table.md">tabella pool in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Pool del destinatario della chiamata. A cui si fa riferimento dalla <a href="lync-server-2013-pool-table.md">tabella pool in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI SIP nell'identità con asserzione p (PAI) SIP dell'endpoint di destinazione. A cui si fa riferimento dalla <a href="lync-server-2013-user-table.md">tabella utente in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI del chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-user-table.md">tabella utente in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Endpoint del chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>po'</p></td>
<td><p>Esterna</p></td>
<td><p>Agente utente del chiamante. A cui si fa riferimento dalla <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Priorità di questa chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Questa colonna è stata deprecata e non viene usata in Microsoft Lync Server 2013. Queste informazioni vengono invece segnalate in base a una riga per media. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>P-asserzione-identità dell'utente che ha effettuato la chiamata. Il P-Asserted-Identity (PAI) viene usato per comunicare l'identità effettiva dell'utente che ha effettuato la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Endpoint che ha ricevuto la chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Agente utente impiegato dall'utente che ha ricevuto la chiamata. Gli agenti utente rappresentano il dispositivo endpoint client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI SIP dell'utente che ha ricevuto la chiamata.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

