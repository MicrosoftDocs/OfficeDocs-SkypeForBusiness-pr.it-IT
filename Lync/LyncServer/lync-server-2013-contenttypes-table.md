---
title: 'Lync Server 2013: tabella ContentTypes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ContentTypes table
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399007(v=OCS.15)
ms:contentKeyID: 48185723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5aa26746e8c970fe2685aea63ef3ff43a672846f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501993"
---
# <a name="contenttypes-table-in-lync-server-2013"></a>Tabella ContentTypes in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2010-11-07_

La tabella ContentTypes è una tabella di supporto in cui è archiviato un elenco dei tipi di contenuto utilizzati sia nelle sessioni peer-to-peer che nelle sessioni di conferenze. Ogni record della tabella rappresenta un tipo di contenuto.


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
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero univoco che identifica il tipo di contenuto.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td> </td>
<td><p>Nome del tipo di contenuto.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

