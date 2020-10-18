---
title: 'Lync Server 2013: tabella FileTransfers'
description: 'Lync Server 2013: tabella FileTransfers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573362"
---
# <a name="filetransfers-table-in-lync-server-2013"></a>Tabella FileTransfers in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

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
<td><p>datetime</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Data e ora della richiesta di sessione. Valore utilizzato insieme a <strong>SessionIdSeq</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaria, esterna</p></td>
<td><p>Numero ID per identificare la sessione. Valore utilizzato insieme a <strong>SessionIdTime</strong> per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la <a href="lync-server-2013-dialogs-table.md">tabella Dialogs in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Nome del file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Identificatore univoco che distingue trasferimenti diversi che interessano lo stesso nome file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Principale</p></td>
<td><p>Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accettare</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rifiuta</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annulla</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

