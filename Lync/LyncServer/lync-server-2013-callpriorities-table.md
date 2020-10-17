---
title: 'Lync Server 2013: Tabella CallPriorities'
description: 'Lync Server 2013: Tabella CallPriorities.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565182"
---
# <a name="callpriorities-table-in-lync-server-2013"></a>Tabella CallPriorities in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

La tabella CallPriorities è una tabella statica in cui è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio 'emergency' (di emergenza), 'urgent' (urgente) o 'normal' (normale).


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Priorità </strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Valori consentiti:</p>
<ul>
<li><p>0 - Sconosciuto</p></li>
<li><p>1 - Non urgente</p></li>
<li><p>2 - Normale</p></li>
<li><p>3 - Urgente</p></li>
<li><p>4 - Emergenza</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

