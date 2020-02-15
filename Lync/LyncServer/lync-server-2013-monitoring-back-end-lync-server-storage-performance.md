---
title: 'Lync Server 2013: monitoraggio delle prestazioni di archiviazione di Lync Server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 760e66403fd1da2b5a45cf0db065dc201e1fd02a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Monitoraggio delle prestazioni di archiviazione di back-end Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-02_

I database back-end di Lync Server 2013 sono una parte molto importante della distribuzione di Lync Server 2013. È consigliabile monitorare costantemente i database e i rispettivi registri delle transazioni per garantire che il back-end di Lync Server 2013 sia in grado di eseguire in modo ottimale.

Nella tabella seguente vengono identificati i contatori delle prestazioni che devono essere monitorati per ottenere informazioni sulle prestazioni di archiviazione. I valori di base per questi contatori devono essere determinati prima (quando il sistema è normale, il carico previsto) per comprendere le modifiche apportate alle prestazioni del sistema.

### <a name="performance-counters-to-be-monitored"></a>Contatori delle prestazioni da monitorare

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contatore delle prestazioni</th>
<th>Soglie di base</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transazioni/sec (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transazioni/sec (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transazioni/sec (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vampate di log/sec (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Vampate di log/sec (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Vampate di log/sec (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Trasferimenti su disco/sec (lettura + scrittura)-RTC DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Trasferimenti disco/sec-RTC log</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Trasferimenti su disco/sec-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Trasferimenti su disco/sec-RTCDyn log</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

