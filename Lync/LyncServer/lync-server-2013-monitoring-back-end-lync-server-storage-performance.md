---
title: 'Lync Server 2013: monitoraggio delle prestazioni di archiviazione di Lync Server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Monitoraggio delle prestazioni di archiviazione di back end Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-02_

I database back-end di Lync Server 2013 sono una parte molto importante della distribuzione di Lync Server 2013. È consigliabile monitorare costantemente i database e i rispettivi registri delle transazioni per verificare che il back-end di Lync Server 2013 sia in grado di eseguire in modo ottimale.

La tabella seguente identifica i contatori delle prestazioni che devono essere monitorati per ottenere informazioni sulle prestazioni dello spazio di archiviazione. I valori della linea di base per questi contatori devono essere determinati prima (quando il sistema è al suo normale carico previsto) per comprendere le modifiche alle prestazioni quando il sistema viene sottolineato.

### <a name="performance-counters-to-be-monitored"></a>Contatori delle prestazioni da monitorare

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contatore delle prestazioni</th>
<th>Soglie della previsione</th>
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
<td><p>Svuota log/sec (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Svuotamenti del log/sec (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Svuotamenti del log/sec (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Trasferimenti disco/sec (lettura + scrittura)-RTC DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Trasferimenti disco/sec-log RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Trasferimenti disco/sec-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Trasferimenti disco/sec-log di RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

