---
title: 'Lync Server 2013: Tabella VideoMetricsThreshold'
description: 'Lync Server 2013: Tabella VideoMetricsThreshold.'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568002"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="4e040-103">Tabella VideoMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e040-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e040-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4e040-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4e040-105">Nella tabella VideoMetricsThreshold sono contenuti valori ottimali e accettabili per le metriche Quality of Experience usate con le chiamate video.</span><span class="sxs-lookup"><span data-stu-id="4e040-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e040-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4e040-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4e040-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4e040-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e040-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-111">int</span><span class="sxs-lookup"><span data-stu-id="4e040-111">int</span></span></p></td>
<td><p><span data-ttu-id="4e040-112">Principale</span><span class="sxs-lookup"><span data-stu-id="4e040-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e040-113">Tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="4e040-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-115">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-116">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="4e040-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-118">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-119">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="4e040-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-121">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-122">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="4e040-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-124">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-125">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="4e040-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-127">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4e040-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-128">Il valore predefinito è 12.0000.</span><span class="sxs-lookup"><span data-stu-id="4e040-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-130">decimale (9, 4)</span><span class="sxs-lookup"><span data-stu-id="4e040-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-131">Il valore predefinito è 7.0000.</span><span class="sxs-lookup"><span data-stu-id="4e040-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-133">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-134">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="4e040-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-136">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-137">Il valore predefinito è 10.0/</span><span class="sxs-lookup"><span data-stu-id="4e040-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-139">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-140">Il valore predefinito è 5.0.</span><span class="sxs-lookup"><span data-stu-id="4e040-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-142">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-143">Il valore predefinito è 10.0.</span><span class="sxs-lookup"><span data-stu-id="4e040-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-145">foat</span><span class="sxs-lookup"><span data-stu-id="4e040-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-146">Il valore predefinito è 0.05.</span><span class="sxs-lookup"><span data-stu-id="4e040-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-148">galleggiante</span><span class="sxs-lookup"><span data-stu-id="4e040-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-149">Il valore predefinito è 0.10.</span><span class="sxs-lookup"><span data-stu-id="4e040-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-151">galleggiante</span><span class="sxs-lookup"><span data-stu-id="4e040-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-152">Il valore predefinito è 12.</span><span class="sxs-lookup"><span data-stu-id="4e040-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-154">galleggiante</span><span class="sxs-lookup"><span data-stu-id="4e040-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-155">Il valore predefinito è 7.</span><span class="sxs-lookup"><span data-stu-id="4e040-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e040-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-157">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-158">Il valore predefinito è 5.00.</span><span class="sxs-lookup"><span data-stu-id="4e040-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e040-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="4e040-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="4e040-160">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="4e040-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e040-161">Il valore predefinito è 10.00.</span><span class="sxs-lookup"><span data-stu-id="4e040-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

