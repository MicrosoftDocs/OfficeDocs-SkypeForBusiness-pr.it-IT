---
title: 'Lync Server 2013: Tabella IPAddress'
description: 'Lync Server 2013: Tabella IPAddress.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPAddress table
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205077(v=OCS.15)
ms:contentKeyID: 48184771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d987281fc310a3a179fa99f2aae51b0764349dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575012"
---
# <a name="ipaddress-table-in-lync-server-2013"></a>Tabella IPAddress in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-17_

La tabella IPAddress mappa gli indirizzi IP agli identificatori di indirizzo IP univoci usati altrove nel database QoS (Quality of Experience). Questa tabella è stata introdotta in Microsoft Lync Server 2013.


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
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Principale</p></td>
<td><p>Identificatore univoco per l'indirizzo IP specificato.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar (50)</p></td>
<td><p>Univoco</p></td>
<td><p>Indirizzo IP univoco (ad esempio, 189.168.1.1) mappato a IpAddressKey. Può trattarsi di un indirizzo IPv4 o IPv6.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

