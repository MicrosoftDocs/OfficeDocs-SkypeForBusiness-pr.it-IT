---
title: 'Lync Server 2013: Tabella MediaList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fa53ff1ce4ce419a4e7a29124593c7b01006a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Tabella MediaList in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-07-12_

La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.


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
<td><p>Mapping statico di valori MediaID e media:</p>
<ul>
<li><p>1-MESSAGGISTICA ISTANTANEA</p></li>
<li><p>2-trasferimento di file</p></li>
<li><p>3-assistenza remota</p></li>
<li><p>4-condivisione delle applicazioni</p></li>
<li><p>5-audio</p></li>
<li><p>6-video</p></li>
<li><p>7-invito all'app</p></li>
</ul></td>
</tr>
</tbody>
</table>


Se si sta provando a determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario usare il frammento di join seguente:

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

