---
title: 'Lync Server 2013: Tabella VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58a054ba58ff7e1e839b0aeca88d0e61164e30b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="b1133-102">Tabella VideoMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1133-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1133-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b1133-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b1133-104">Nella tabella VideoMetricsThreshold sono contenuti valori ottimali e accettabili per le metriche Quality of Experience usate con le chiamate video.</span><span class="sxs-lookup"><span data-stu-id="b1133-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1133-105"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b1133-106"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b1133-107"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b1133-108"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1133-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-110">int</span><span class="sxs-lookup"><span data-stu-id="b1133-110">int</span></span></p></td>
<td><p><span data-ttu-id="b1133-111">Principale</span><span class="sxs-lookup"><span data-stu-id="b1133-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b1133-112">Tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="b1133-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-114">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-115">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="b1133-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-117">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-118">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="b1133-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-120">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-121">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="b1133-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-123">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-124">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="b1133-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-126">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b1133-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-127">Il valore predefinito è 12.0000.</span><span class="sxs-lookup"><span data-stu-id="b1133-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-129">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="b1133-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-130">Il valore predefinito è 7.0000.</span><span class="sxs-lookup"><span data-stu-id="b1133-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-132">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-133">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="b1133-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-135">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-136">Il valore predefinito è 10.0/</span><span class="sxs-lookup"><span data-stu-id="b1133-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-138">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-139">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="b1133-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-141">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-142">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="b1133-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-144">foat</span><span class="sxs-lookup"><span data-stu-id="b1133-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-145">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="b1133-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-147">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b1133-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-148">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="b1133-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-150">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b1133-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-151">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="b1133-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-153">galleggiante</span><span class="sxs-lookup"><span data-stu-id="b1133-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-154">Il valore predefinito è 7.</span><span class="sxs-lookup"><span data-stu-id="b1133-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1133-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-156">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-157">Il valore predefinito è 5.00.</span><span class="sxs-lookup"><span data-stu-id="b1133-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1133-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="b1133-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="b1133-159">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b1133-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b1133-160">Il valore predefinito è 10.00.</span><span class="sxs-lookup"><span data-stu-id="b1133-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

