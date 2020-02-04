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
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>tblRoleType in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-25_

tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.

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
<td><p>ID tipo di ruolo.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Descrizione del tipo di ruolo. Esistono quattro ruoli disponibili:</p>
<ul>
<li><p>Membro: membro della chat room</p></li>
<li><p>Manager: gestione chat room</p></li>
<li><p>Voiced: relatore per una chat room dell'Auditorium</p></li>
<li><p>Creatore: può creare chat room</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint e non null</p></td>
<td><p>Set di autorizzazioni per il ruolo. I bit usati sono:</p>
<ul>
<li><p>2: true se il ruolo può gestire i nodi.</p></li>
<li><p>4: true se il ruolo può creare nodi figlio.</p></li>
<li><p>7: vero se il ruolo può partecipare a una chat room (o chat room per bambini di una categoria).</p></li>
<li><p>8: true se il ruolo può essere chattato in una chat room o in chat per bambini di una categoria.</p></li>
<li><p>10: true se il ruolo può leggere la cronologia chat anche quando non è stato aggiunto a una chat room.</p></li>
<li><p>11: vero se il ruolo può vedere la chat room. (Questa operazione viene ulteriormente affinata da fattori come l'ambito e la visibilità).</p></li>
<li><p>12: vero se il ruolo può chattare in una chat room di un auditorium.</p></li>
<li><p>13: true se il ruolo può ignorare le regole di visibilità durante la visualizzazione dei nodi.</p></li>
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

