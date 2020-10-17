---
title: 'Lync Server 2013: Visualizzazione ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06e250528a56c10a573c19181fddb1d9acee494d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499163"
---
# <a name="clientversions-view-in-lync-server-2013"></a>Visualizzazione ClientVersions in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

La Visualizzazione ClientVersions archivia le informazioni sui diversi tipi di client e le versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella visualizzazione rappresenta una versione client. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Per alcune colonne possono essere presenti più record.



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Numero univoco che identifica il tipo di client e la versione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versione</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Rappresenta l'agente utente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Tipo di client.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria a cui appartiene il client. Ad esempio, il client Conferencing_Attendant_1 .0 appartiene a ClientCategory CAA.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

