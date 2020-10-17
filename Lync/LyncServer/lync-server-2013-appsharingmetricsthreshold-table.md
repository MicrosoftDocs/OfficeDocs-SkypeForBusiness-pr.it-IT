---
title: 'Lync Server 2013: tabella AppSharingMetricsThreshold'
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
ms.openlocfilehash: 6e7a2d73f09a3cb48b1d50f06aa530c91d779b28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529553"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="a18aa-102">Tabella AppSharingMetricsThreshold in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a18aa-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a18aa-103">_**Ultimo argomento modificato:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="a18aa-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="a18aa-p101">La tabella AppSharingMetricsThreshold contiene i valori ottimali e accettabili delle metriche QoE utilizzate con la condivisione delle applicazioni. Questi valori soglia sono utilizzati per determinare se l'esperienza di condivisione deve essere classificata come insufficiente.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="a18aa-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a18aa-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a18aa-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a18aa-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a18aa-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-112">int</span><span class="sxs-lookup"><span data-stu-id="a18aa-112">int</span></span></p></td>
<td><p><span data-ttu-id="a18aa-113">Principale</span><span class="sxs-lookup"><span data-stu-id="a18aa-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a18aa-114">Tipo di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="a18aa-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-116">int</span><span class="sxs-lookup"><span data-stu-id="a18aa-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p102">Limitazione ottimale della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 1000000.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-120">int</span><span class="sxs-lookup"><span data-stu-id="a18aa-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p103">Limitazione accettabile della larghezza di banda per la condivisione delle applicazioni. Il valore predefinito è 500000.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-124">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a18aa-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p104">Tasso percentuale ottimale delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 11 percento.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-130">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a18aa-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p105">Tasso percentuale accettabile delle sezioni “danneggiate” per la classificazione della qualità di una condivisione delle applicazioni. Questo valore rappresenta la percentuale di contenuto del condivisore che non ha raggiunto il visualizzatore. Il contenuto potrebbe essere scartato (o danneggiato) rispettivamente quando il condivisore scarta le sezioni dall'origine grafica o ASMCU scarica le sezioni dal condivisore. Il valore predefinito è 36 percento.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-136">int</span><span class="sxs-lookup"><span data-stu-id="a18aa-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-137">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-139">int</span><span class="sxs-lookup"><span data-stu-id="a18aa-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-140">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-142">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-143">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-145">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-146">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-148">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-149">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-151">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-152">Questa colonna non viene utilizzata in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-154">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p106">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,0 secondi.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="a18aa-158">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-160">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-p107">Valore ottimale per il ritardo unidirezionale relativo tra i due endpoint multimediali coinvolti nella condivisione delle applicazioni. È una misura della latenza a hop singolo. Il valore predefinito è 1,75 secondi.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="a18aa-164">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a18aa-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-166">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-167">Latenza ottimale di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="a18aa-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="a18aa-168">Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="a18aa-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="a18aa-p109">Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="a18aa-172">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a18aa-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="a18aa-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="a18aa-174">galleggiante</span><span class="sxs-lookup"><span data-stu-id="a18aa-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a18aa-175">Latenza accettabile di elaborazione delle sezioni RDP nel server per conferenze di Condivisione applicazioni per tutta la durata della sessione di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="a18aa-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="a18aa-176">Latenza è la differenza di tempo tra quando la cornice iniziale è codificata sul server (condivisore o MCU a seconda dello scenario) e lo stesso frame iniziale viene decodificato nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="a18aa-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="a18aa-p111">Una media elevata è sintomo di un ritardo superiore nell'esperienza di visualizzazione. In un server per conferenze sovraccarico possono verificarsi ritardi medi superiori. Il valore predefinito è 200 ms.</span><span class="sxs-lookup"><span data-stu-id="a18aa-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="a18aa-180">La colonna è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a18aa-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

