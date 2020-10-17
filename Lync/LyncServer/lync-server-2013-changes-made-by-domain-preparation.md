---
title: 'Lync Server 2013: modifiche apportate dalla preparazione del dominio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529503"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Modifiche apportate dalla preparazione del dominio in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2010-10-18_

Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Voci di controllo di accesso aggiunte alla radice del dominio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-Services</th>
<th>Authenticated-Users</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (not inherited)</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Personal-Information</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet General-Information</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Public-Information</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet RTCPropertySet</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Write User Property Proxy-Addresses</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Write User PropertySet RTCPropertySet</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.

### <a name="aces-added-to-built-in-containers"></a>Voci di controllo di accesso aggiunte ai contenitori predefiniti

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (non ereditata)</p></td>
<td><p><strong>Sì</strong></p></td>
<td><p><strong>Sì</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

