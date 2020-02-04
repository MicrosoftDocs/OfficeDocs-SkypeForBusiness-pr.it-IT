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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="12ca9-102">Tabella VideoMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12ca9-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12ca9-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="12ca9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="12ca9-104">La tabella VideoMetricsThreshold contiene valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con le videochiamate.</span><span class="sxs-lookup"><span data-stu-id="12ca9-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12ca9-105"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="12ca9-106"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="12ca9-107"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="12ca9-108"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-110">int</span><span class="sxs-lookup"><span data-stu-id="12ca9-110">int</span></span></p></td>
<td><p><span data-ttu-id="12ca9-111">Principale</span><span class="sxs-lookup"><span data-stu-id="12ca9-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="12ca9-112">Tipo di chiamata inserita.</span><span class="sxs-lookup"><span data-stu-id="12ca9-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-114">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-115">Il valore predefinito è 0,05.</span><span class="sxs-lookup"><span data-stu-id="12ca9-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-117">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-118">Il valore predefinito è 0,10.</span><span class="sxs-lookup"><span data-stu-id="12ca9-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-120">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-121">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="12ca9-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-123">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-124">Il valore predefinito è 10,0.</span><span class="sxs-lookup"><span data-stu-id="12ca9-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-126">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="12ca9-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-127">Il valore predefinito è 12,0000.</span><span class="sxs-lookup"><span data-stu-id="12ca9-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-129">decimale (9; 4)</span><span class="sxs-lookup"><span data-stu-id="12ca9-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-130">Il valore predefinito è 7,0000.</span><span class="sxs-lookup"><span data-stu-id="12ca9-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-132">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-133">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="12ca9-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-135">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-136">Il valore predefinito è 10.0/</span><span class="sxs-lookup"><span data-stu-id="12ca9-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-138">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-139">Il valore predefinito è 5,0.</span><span class="sxs-lookup"><span data-stu-id="12ca9-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-141">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-142">Il valore predefinito è 10,0.</span><span class="sxs-lookup"><span data-stu-id="12ca9-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-144">foat</span><span class="sxs-lookup"><span data-stu-id="12ca9-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-145">Il valore predefinito è 0,05.</span><span class="sxs-lookup"><span data-stu-id="12ca9-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-147">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12ca9-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-148">Il valore predefinito è 0,10.</span><span class="sxs-lookup"><span data-stu-id="12ca9-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-150">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12ca9-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-151">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="12ca9-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-153">galleggiante</span><span class="sxs-lookup"><span data-stu-id="12ca9-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-154">Il valore predefinito è 7.</span><span class="sxs-lookup"><span data-stu-id="12ca9-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ca9-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-156">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-157">Il valore predefinito è 5,00.</span><span class="sxs-lookup"><span data-stu-id="12ca9-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ca9-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="12ca9-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="12ca9-159">decimale (5; 2)</span><span class="sxs-lookup"><span data-stu-id="12ca9-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="12ca9-160">Il valore predefinito è 10,00.</span><span class="sxs-lookup"><span data-stu-id="12ca9-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

