---
title: 'Lync Server 2013: Tabella FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Tabella FileTransfers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Ogni record rappresenta una sessione di trasferimento file.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Chiave/indice</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Ora della richiesta della sessione. Usato in combinazione con <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, straniera</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per altre informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella finestre di dialogo in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nome file</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Nome del file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Principale</p></td>
<td><p>Usato per identificare ogni messaggio di follow-up associato a questo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accettare</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, quindi Reject e Cancel saranno NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rifiutare</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, accetta e Annulla sarà NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annulla</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, accetta e rifiuta sarà NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

