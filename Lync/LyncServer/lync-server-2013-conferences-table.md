---
title: 'Lync Server 2013: Tabella Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Tabella Conferences in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Ogni record in questa tabella contiene i dettagli sulle chiamate di una conferenza.


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
<td><p>Principale</p></td>
<td><p>Ora in cui la richiesta di conferenza è stata acquisita dall'agente CDR. Usato solo come chiave primaria per identificare in modo univoco un'istanza di conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Numero ID per identificare la sessione. Usato in combinazione con <strong>SessionIdTime</strong> per identificare in modo univoco un'istanza di conferenza. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>URI conferenza. Per altre informazioni, vedere la <a href="lync-server-2013-conferenceuris-table.md">tabella ConferenceUris in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>Utile per le conferenze periodiche; ogni istanza di una conferenza ricorrente ha lo stesso <strong>ConferenceUri</strong>, ma avrà un <strong>ConfInstance</strong>diverso.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p> </p></td>
<td><p>Ora di inizio conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>DateTime</p></td>
<td><p> </p></td>
<td><p>Ora di inizio conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Esterna</p></td>
<td><p>Numero ID per identificare il pool in cui è stata acquisita la conferenza. Per altre informazioni, vedere la <a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Esterna</p></td>
<td><p>Numero ID per identificare l'URI dell'organizzatore di questa conferenza. Per altre informazioni, vedere la <a href="lync-server-2013-users-table.md">tabella utenti in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Contrassegno</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Maschera di bit che contiene gli attributi della conferenza. I valori possibili sono:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Sintetico</p></li>
<li><p>Transazione</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Elaborate</strong></p></td>
<td><p>po'</p></td>
<td></td>
<td><p>Campo interno usato dal servizio di monitoraggio.</p>
<p>Questo campo è stato introdotto in Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Per la maggior parte delle sessioni, SessionIdSeq avrà il valore 1. Se due sessioni iniziano esattamente nello stesso momento, il SessionIdSeq per uno sarà 1 e per l'altro sarà 2 e così via.

</div>

<span> </span>

</div>

</div>

</div>

