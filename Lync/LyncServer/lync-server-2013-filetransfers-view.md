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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Visualizzazione FileTransfers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

La visualizzazione filetransfer archivia le informazioni sulle sessioni di trasferimento file peer-to-peer. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.

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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome del file trasferito.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Valore utilizzato per identificare ogni messaggio successivo come associato a questo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificatore univoco per distinguere tra i trasferimenti di file che coinvolgono lo stesso nome di file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accettare</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Reject e Cancel saranno NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rifiuta</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Accept e Cancel saranno NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annulla</strong></p></td>
<td><p>po'</p></td>
<td><p>Può essere TRUE o NULL. Se TRUE, allora Accept e Reject saranno NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

