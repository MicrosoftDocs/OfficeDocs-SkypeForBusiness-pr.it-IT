---
title: 'Lync Server 2013: tabella AppSharingMetricsThreshold'
description: 'Lync Server 2013: tabella AppSharingMetricsThreshold.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546812"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="7f52d-103">Tabella AppSharingMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f52d-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f52d-104">_**Ultimo argomento modificato:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="7f52d-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="7f52d-p101">La tabella AppSharingMetricsThreshold contiene i valori ottimali e accettabili delle metriche QoE utilizzate con la condivisione delle applicazioni. Questi valori soglia sono utilizzati per determinare se l'esperienza di condivisione deve essere classificata come insufficiente.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="7f52d-107">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f52d-108"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7f52d-109"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7f52d-110"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7f52d-111"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-113">int</span><span class="sxs-lookup"><span data-stu-id="7f52d-113">int</span></span></p></td>
<td><p><span data-ttu-id="7f52d-114">Principale</span><span class="sxs-lookup"><span data-stu-id="7f52d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="7f52d-115">Tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="7f52d-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-117">int</span><span class="sxs-lookup"><span data-stu-id="7f52d-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p102">Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1000000.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-121">int</span><span class="sxs-lookup"><span data-stu-id="7f52d-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p103">Limitazione accettabile della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 500000.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-125">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7f52d-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p104">Tasso percentuale ottimale delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 11 percento.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-131">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7f52d-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p105">Tasso percentuale accettabile delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 36 percento.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-137">int</span><span class="sxs-lookup"><span data-stu-id="7f52d-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-138">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-140">int</span><span class="sxs-lookup"><span data-stu-id="7f52d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-141">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-143">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-144">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-146">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-147">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-149">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-150">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-152">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-153">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-155">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p106">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="7f52d-159">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-161">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-p107">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,75 secondi.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="7f52d-165">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f52d-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-167">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-168">Latenza ottimale di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f52d-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7f52d-169">Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="7f52d-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7f52d-p109">Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7f52d-173">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f52d-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7f52d-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7f52d-175">galleggiante</span><span class="sxs-lookup"><span data-stu-id="7f52d-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7f52d-176">Latenza accettabile di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="7f52d-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="7f52d-177">Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="7f52d-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="7f52d-p111">Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</span><span class="sxs-lookup"><span data-stu-id="7f52d-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="7f52d-181">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f52d-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

