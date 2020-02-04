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
ms.openlocfilehash: 7c4d3741564cd0228213400d7ee1fbb7271c4ddd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="ade4c-102">Monitoraggio delle prestazioni di archiviazione di back end Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ade4c-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ade4c-103">_**Argomento Ultima modifica:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="ade4c-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="ade4c-104">I database back-end di Lync Server 2013 sono una parte molto importante della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ade4c-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ade4c-105">È consigliabile monitorare costantemente i database e i rispettivi registri delle transazioni per verificare che il back-end di Lync Server 2013 sia in grado di eseguire in modo ottimale.</span><span class="sxs-lookup"><span data-stu-id="ade4c-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="ade4c-106">La tabella seguente identifica i contatori delle prestazioni che devono essere monitorati per ottenere informazioni sulle prestazioni dello spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ade4c-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="ade4c-107">I valori della linea di base per questi contatori devono essere determinati prima (quando il sistema è al suo normale carico previsto) per comprendere le modifiche alle prestazioni quando il sistema viene sottolineato.</span><span class="sxs-lookup"><span data-stu-id="ade4c-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="ade4c-108">Contatori delle prestazioni da monitorare</span><span class="sxs-lookup"><span data-stu-id="ade4c-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ade4c-109">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="ade4c-109">Performance Counter</span></span></th>
<th><span data-ttu-id="ade4c-110">Soglie della previsione</span><span class="sxs-lookup"><span data-stu-id="ade4c-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ade4c-111">Transazioni/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="ade4c-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade4c-112">Transazioni/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="ade4c-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade4c-113">Transazioni/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="ade4c-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade4c-114">Svuota log/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="ade4c-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade4c-115">Svuotamenti del log/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="ade4c-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade4c-116">Svuotamenti del log/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="ade4c-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade4c-117">Trasferimenti disco/sec (lettura + scrittura)-RTC DB</span><span class="sxs-lookup"><span data-stu-id="ade4c-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade4c-118">Trasferimenti disco/sec-log RTC</span><span class="sxs-lookup"><span data-stu-id="ade4c-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ade4c-119">Trasferimenti disco/sec-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="ade4c-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ade4c-120">Trasferimenti disco/sec-log di RTCDyn</span><span class="sxs-lookup"><span data-stu-id="ade4c-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

