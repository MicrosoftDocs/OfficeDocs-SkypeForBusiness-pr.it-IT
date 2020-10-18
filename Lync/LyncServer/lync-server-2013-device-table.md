---
title: 'Lync Server 2013: tabella Device'
description: 'Lync Server 2013: tabella Device.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575642"
---
# <a name="device-table-in-lync-server-2013"></a>Tabella Device in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

La tabella Device è una tabella di supporto in cui vengono archiviate le informazioni sui vari dispositivi di acquisizione o rendering. Ogni record nella tabella rappresenta un dispositivo.


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
<td><p><strong>DeviceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero univoco che identifica il dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>DeviceName + DeviceType è univoco</p></td>
<td><p>Nome del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>po'</p></td>
<td><p>DeviceName + DeviceType è univoco</p></td>
<td><p>Tipo di dispositivo. 1 è un dispositivo di acquisizione, 0 è un dispositivo di rendering.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

