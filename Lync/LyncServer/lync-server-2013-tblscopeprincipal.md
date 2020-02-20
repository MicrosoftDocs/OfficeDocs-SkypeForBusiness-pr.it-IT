---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 147d71ada1d0db26e95868a7115556d30cbc2435
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>tblScopePrincipal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-12_

tblScopePrincipal contiene gli ambiti assegnati ai nodi.

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
<td><p>scopeNodeID</p></td>
<td><p>int, not null</p></td>
<td><p>ID di nodo a cui si applica l'ambito.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, non null</p></td>
<td><p>ID entità.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, not null</p></td>
<td><p>True se il tipo di ambito è Deny; False se è Allow.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID dell'ultima entità che ha aggiornato questa voce.</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblNode.nodeID.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

