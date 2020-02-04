---
title: 'Lync Server 2013: Tabella Locations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a>Tabella Locations in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-05-25_

Ogni record rappresenta un riferimento di posizione in una chiamata di emergenza, ad esempio una chiamata E9-1-1.


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
<td><p><strong>Posizione</strong></p></td>
<td><p>nvarchar (max)</p></td>
<td></td>
<td><p>Posizione della chiamata di emergenza.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

