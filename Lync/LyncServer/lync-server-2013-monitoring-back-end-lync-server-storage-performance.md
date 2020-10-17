---
title: 'Lync Server 2013: monitoraggio delle prestazioni di archiviazione di Lync Server back-end'
description: 'Lync Server 2013: monitoraggio delle prestazioni di archiviazione di Lync Server back-end.'
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
ms.openlocfilehash: e7501418d3589b941b7e92d2b414492c1d27a3ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562072"
---
# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="2218e-103">Monitoraggio delle prestazioni di archiviazione di back-end Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2218e-103">Monitoring back end Lync Server 2013 storage performance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2218e-104">_**Ultimo argomento modificato:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="2218e-104">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="2218e-105">I database back-end di Lync Server 2013 sono una parte molto importante della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2218e-105">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="2218e-106">È consigliabile monitorare costantemente i database e i rispettivi registri delle transazioni per garantire che il back-end di Lync Server 2013 sia in grado di eseguire in modo ottimale.</span><span class="sxs-lookup"><span data-stu-id="2218e-106">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="2218e-107">Nella tabella seguente vengono identificati i contatori delle prestazioni che devono essere monitorati per ottenere informazioni sulle prestazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2218e-107">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="2218e-108">I valori di base per questi contatori devono essere determinati prima (quando il sistema è normale, il carico previsto) per comprendere le modifiche apportate alle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="2218e-108">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="2218e-109">Contatori delle prestazioni da monitorare</span><span class="sxs-lookup"><span data-stu-id="2218e-109">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2218e-110">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="2218e-110">Performance Counter</span></span></th>
<th><span data-ttu-id="2218e-111">Soglie di base</span><span class="sxs-lookup"><span data-stu-id="2218e-111">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2218e-112">Transazioni/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="2218e-112">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2218e-113">Transazioni/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="2218e-113">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2218e-114">Transazioni/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="2218e-114">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2218e-115">Vampate di log/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="2218e-115">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2218e-116">Vampate di log/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="2218e-116">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2218e-117">Vampate di log/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="2218e-117">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2218e-118">Trasferimenti su disco/sec (lettura + scrittura)-RTC DB</span><span class="sxs-lookup"><span data-stu-id="2218e-118">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2218e-119">Trasferimenti disco/sec-RTC log</span><span class="sxs-lookup"><span data-stu-id="2218e-119">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2218e-120">Trasferimenti su disco/sec-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="2218e-120">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2218e-121">Trasferimenti su disco/sec-RTCDyn log</span><span class="sxs-lookup"><span data-stu-id="2218e-121">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

