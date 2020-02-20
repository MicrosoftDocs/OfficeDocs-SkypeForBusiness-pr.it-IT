---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b6e525bda0936d2059d2dcc5dce2edeebd13e32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-25_

tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.

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
<td><p>rtypeID</p></td>
<td><p>int, not null</p></td>
<td><p>ID del tipo di ruolo.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descrizione del tipo di ruolo. Sono disponibili quattro ruoli:</p>
<ul>
<li><p>Member: membro della chat.</p></li>
<li><p>Manager: responsabile della chat.</p></li>
<li><p>Voiced: relatore per una chat. auditorium</p></li>
<li><p>Creator: creazione di chat room</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, not null</p></td>
<td><p>Set di autorizzazioni per il ruolo. I bit utilizzati sono:</p>
<ul>
<li><p>2: true se il ruolo può gestire i nodi.</p></li>
<li><p>4: true se il ruolo può creare nodi figlio.</p></li>
<li><p>7: true se il ruolo può partecipare a una chat (o a chat figlio di una categoria).</p></li>
<li><p>8: true se il ruolo può eseguire chat in una chat (o in chat figlio di una categoria).</p></li>
<li><p>10: true se il ruolo può leggere la cronologia delle chat anche se non partecipa a una chat.</p></li>
<li><p>11: true se il ruolo può visualizzare la chat (ulteriormente definito da fattori come l'ambito e la visibilità).</p></li>
<li><p>12: true se il ruolo può eseguire chat in una chat auditorium.</p></li>
<li><p>13: true se il ruolo può ignorare le regole di visibilità quando visualizza i nodi.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Chiave

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
<td><p>rtypeID</p></td>
<td><p>Chiave primaria.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

