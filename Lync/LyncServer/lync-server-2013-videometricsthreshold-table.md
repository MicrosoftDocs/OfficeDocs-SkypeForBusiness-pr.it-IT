---
title: 'Lync Server 2013: Tabella VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="5af09-102">Tabella VideoMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5af09-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af09-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5af09-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5af09-104">La tabella VideoMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con le videochiamate.</span><span class="sxs-lookup"><span data-stu-id="5af09-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5af09-105"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5af09-106"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5af09-107"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5af09-108"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af09-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-110">int</span><span class="sxs-lookup"><span data-stu-id="5af09-110">int</span></span></p></td>
<td><p><span data-ttu-id="5af09-111">Principale</span><span class="sxs-lookup"><span data-stu-id="5af09-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5af09-112">Tipo di chiamata inserita.</span><span class="sxs-lookup"><span data-stu-id="5af09-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-114">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-115">Il valore predefinito è 0,05.</span><span class="sxs-lookup"><span data-stu-id="5af09-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-117">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-118">Il valore predefinito è 0,10.</span><span class="sxs-lookup"><span data-stu-id="5af09-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-120">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-121">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="5af09-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-123">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-124">Il valore predefinito è 10,0.</span><span class="sxs-lookup"><span data-stu-id="5af09-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-126">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="5af09-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-127">Il valore predefinito è 12,0000.</span><span class="sxs-lookup"><span data-stu-id="5af09-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-129">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="5af09-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-130">Il valore predefinito è 7,0000.</span><span class="sxs-lookup"><span data-stu-id="5af09-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-132">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-133">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="5af09-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-135">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-136">Il valore predefinito è 10.0/</span><span class="sxs-lookup"><span data-stu-id="5af09-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-138">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-139">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="5af09-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-141">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-142">Il valore predefinito è 10,0.</span><span class="sxs-lookup"><span data-stu-id="5af09-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-144">foat</span><span class="sxs-lookup"><span data-stu-id="5af09-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-145">Il valore predefinito è 0,05.</span><span class="sxs-lookup"><span data-stu-id="5af09-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-147">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5af09-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-148">Il valore predefinito è 0,10.</span><span class="sxs-lookup"><span data-stu-id="5af09-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-150">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5af09-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-151">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="5af09-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-153">galleggiante</span><span class="sxs-lookup"><span data-stu-id="5af09-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-154">Il valore predefinito è 7.</span><span class="sxs-lookup"><span data-stu-id="5af09-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af09-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-156">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-157">Il valore predefinito è 5,00.</span><span class="sxs-lookup"><span data-stu-id="5af09-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af09-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5af09-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5af09-159">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="5af09-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5af09-160">Il valore predefinito è 10,00.</span><span class="sxs-lookup"><span data-stu-id="5af09-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

