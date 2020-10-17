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
ms.openlocfilehash: aad04524df22c9d299b4a871b580330052d2aa5b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531953"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Monitoraggio delle prestazioni di archiviazione di back-end Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

