---
title: 'Lync Server 2013: Tabella PayloadDescription'
description: 'Lync Server 2013: Tabella PayloadDescription.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PayloadDescription table
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412971(v=OCS.15)
ms:contentKeyID: 48185353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90ba6b3b85060601487b5b6d0d8747c5fbfa2a9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557362"
---
# <a name="payloaddescription-table-in-lync-server-2013"></a>Tabella PayloadDescription in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

La tabella PayloadDescription è una tabella di supporto. Ogni record rappresenta un codec, che viene utilizzato in una sessione audio o video.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonna</strong></th>
<th><strong>Tipo di dati</strong></th>
<th><strong>Chiave/indice</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero univoco che identifica il codec.</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Univoco</p></td>
<td><p>Nome del codec.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

