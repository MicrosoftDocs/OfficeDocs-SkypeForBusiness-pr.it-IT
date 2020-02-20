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
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="4c472-102">Monitoraggio delle prestazioni di archiviazione di back-end Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c472-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c472-103">_**Ultimo argomento modificato:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="4c472-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="4c472-104">I database back-end di Lync Server 2013 sono una parte molto importante della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c472-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="4c472-105">È consigliabile monitorare costantemente i database e i rispettivi registri delle transazioni per garantire che il back-end di Lync Server 2013 sia in grado di eseguire in modo ottimale.</span><span class="sxs-lookup"><span data-stu-id="4c472-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="4c472-106">Nella tabella seguente vengono identificati i contatori delle prestazioni che devono essere monitorati per ottenere informazioni sulle prestazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4c472-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="4c472-107">I valori di base per questi contatori devono essere determinati prima (quando il sistema è normale, il carico previsto) per comprendere le modifiche apportate alle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="4c472-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="4c472-108">Contatori delle prestazioni da monitorare</span><span class="sxs-lookup"><span data-stu-id="4c472-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c472-109">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="4c472-109">Performance Counter</span></span></th>
<th><span data-ttu-id="4c472-110">Soglie di base</span><span class="sxs-lookup"><span data-stu-id="4c472-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c472-111">Transazioni/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="4c472-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c472-112">Transazioni/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="4c472-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c472-113">Transazioni/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="4c472-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c472-114">Vampate di log/sec (RTC)</span><span class="sxs-lookup"><span data-stu-id="4c472-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c472-115">Vampate di log/sec (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="4c472-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c472-116">Vampate di log/sec (tempdb)</span><span class="sxs-lookup"><span data-stu-id="4c472-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c472-117">Trasferimenti su disco/sec (lettura + scrittura)-RTC DB</span><span class="sxs-lookup"><span data-stu-id="4c472-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c472-118">Trasferimenti disco/sec-RTC log</span><span class="sxs-lookup"><span data-stu-id="4c472-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c472-119">Trasferimenti su disco/sec-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="4c472-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c472-120">Trasferimenti su disco/sec-RTCDyn log</span><span class="sxs-lookup"><span data-stu-id="4c472-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

