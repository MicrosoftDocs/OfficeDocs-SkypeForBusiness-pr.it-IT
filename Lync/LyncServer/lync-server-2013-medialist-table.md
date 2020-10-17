---
title: 'Lync Server 2013: tabella multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a22ef9b9e0ef429fcac96a7f7d5c87093f79a02
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505723"
---
# <a name="medialist-table-in-lync-server-2013"></a>Tabella media in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-07-12_

La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principale</p></td>
<td><p>Valori: 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>Contenuti multimediali</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Mapping statico dei valori di MediaID e media:</p>
<ul>
<li><p>1-MESSAGGISTICA ISTANTANEA</p></li>
<li><p>2 -- Trasferimento di file</p></li>
<li><p>3 -- Assistenza remota</p></li>
<li><p>4 -- Condivisione applicazioni</p></li>
<li><p>5 – audio</p></li>
<li><p>6 – video</p></li>
<li><p>7 -- Invito applicazione</p></li>
</ul></td>
</tr>
</tbody>
</table>


Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario utilizzare il seguente frammento di join:

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

