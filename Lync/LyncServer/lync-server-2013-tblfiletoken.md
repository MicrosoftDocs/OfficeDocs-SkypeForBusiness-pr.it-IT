---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547632"
---
# <a name="tblfiletoken-in-lync-server-2013"></a>tblFileToken in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.

### <a name="columns"></a>Colonne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fileToken</p></td>
<td><p>nvarchar (50), not null</p></td>
<td><p>Token univoco (un GUID).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int, not null</p></td>
<td><p>ID dell'entità che sta trasferendo il file.</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID, not null</p></td>
<td><p>GUID del nodo della chat.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime, not null</p></td>
<td><p>Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL del file trasferito (per l'uso con il servizio Conformità).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>po'</p></td>
<td><p>True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il token è bloccato. Usato per mantenere il token nella tabella finché il servizio Conformità non ha l'opportunità di recuperare i campi pertinenti dal token stesso.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Chiavi

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fileToken</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblNode.nodeGuid.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

