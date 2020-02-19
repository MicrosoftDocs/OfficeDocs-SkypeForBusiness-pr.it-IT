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
ms.openlocfilehash: 1a40e32b9c9730e37a339286ec152ed4ee0270b9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="3e7b4-102">Tabella VideoMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e7b4-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e7b4-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3e7b4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3e7b4-104">Nella tabella VideoMetricsThreshold sono contenuti valori ottimali e accettabili per le metriche Quality of Experience usate con le chiamate video.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e7b4-105"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3e7b4-106"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3e7b4-107"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3e7b4-108"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-110">int</span><span class="sxs-lookup"><span data-stu-id="3e7b4-110">int</span></span></p></td>
<td><p><span data-ttu-id="3e7b4-111">Principale</span><span class="sxs-lookup"><span data-stu-id="3e7b4-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="3e7b4-112">Tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-114">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-115">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-117">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-118">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-120">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-121">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-123">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-124">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-126">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-127">Il valore predefinito è 12.0000.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-129">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-130">Il valore predefinito è 7.0000.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-132">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-133">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-135">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-136">Il valore predefinito è 10.0/</span><span class="sxs-lookup"><span data-stu-id="3e7b4-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-138">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-139">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-141">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-142">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-144">foat</span><span class="sxs-lookup"><span data-stu-id="3e7b4-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-145">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-147">galleggiante</span><span class="sxs-lookup"><span data-stu-id="3e7b4-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-148">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-150">galleggiante</span><span class="sxs-lookup"><span data-stu-id="3e7b4-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-151">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-153">galleggiante</span><span class="sxs-lookup"><span data-stu-id="3e7b4-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-154">Il valore predefinito è 7.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e7b4-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-156">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-157">Il valore predefinito è 5.00.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e7b4-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="3e7b4-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="3e7b4-159">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="3e7b4-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3e7b4-160">Il valore predefinito è 10.00.</span><span class="sxs-lookup"><span data-stu-id="3e7b4-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

