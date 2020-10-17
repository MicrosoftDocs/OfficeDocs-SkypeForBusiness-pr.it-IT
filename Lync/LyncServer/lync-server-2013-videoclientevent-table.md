---
title: 'Lync Server 2013: Tabella VideoClientEvent'
description: 'Lync Server 2013: Tabella VideoClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568492"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="d6310-103">Tabella VideoClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6310-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6310-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="d6310-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="d6310-105">Ogni record contiene l'evento client per un endpoint in una chiamata video.</span><span class="sxs-lookup"><span data-stu-id="d6310-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d6310-106">In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d6310-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6310-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d6310-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d6310-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d6310-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6310-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d6310-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d6310-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="d6310-113">Principale</span><span class="sxs-lookup"><span data-stu-id="d6310-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6310-114">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6310-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6310-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d6310-116">int</span><span class="sxs-lookup"><span data-stu-id="d6310-116">int</span></span></p></td>
<td><p><span data-ttu-id="d6310-117">Principale</span><span class="sxs-lookup"><span data-stu-id="d6310-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6310-118">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6310-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6310-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d6310-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d6310-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d6310-121">Principale</span><span class="sxs-lookup"><span data-stu-id="d6310-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6310-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d6310-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6310-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="d6310-124">po'</span><span class="sxs-lookup"><span data-stu-id="d6310-124">bit</span></span></p></td>
<td><p><span data-ttu-id="d6310-125">Principale</span><span class="sxs-lookup"><span data-stu-id="d6310-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="d6310-126">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="d6310-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="d6310-127">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="d6310-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6310-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6310-129">Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="d6310-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="d6310-130">La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="d6310-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6310-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="d6310-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="d6310-132">Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="d6310-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="d6310-133">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="d6310-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

