---
title: 'Lync Server 2013: Visualizzazione FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Visualizzazione FileTransfers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

La visualizzazione filetransfer consente di archiviare informazioni sulle sessioni di trasferimento di file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La Visualizzazione FileTransfers contiene tutte le colonne della <A href="lync-server-2013-sessiondetails-view.md">Visualizzazione SessionDetails in Lync Server 2013</A> , oltre alle colonne elencate di seguito.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Nome file</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome del file trasferito.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Usato per identificare ogni messaggio di follow-up associato a questo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accettare</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, quindi Reject e Cancel saranno NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rifiutare</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, accetta e Annulla sarà NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annulla</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, accetta e rifiuta sarà NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

