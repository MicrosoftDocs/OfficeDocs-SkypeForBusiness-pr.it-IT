---
title: 'Lync Server 2013: Tabella VideoClientEvent'
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
ms.openlocfilehash: 9282af929757a4703f40537cb94d50761b1ac422
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527583"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="10df8-102">Tabella VideoClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10df8-102">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10df8-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="10df8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="10df8-104">Ogni record contiene l'evento client per un endpoint in una chiamata video.</span><span class="sxs-lookup"><span data-stu-id="10df8-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="10df8-105">In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="10df8-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10df8-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="10df8-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="10df8-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="10df8-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10df8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="10df8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="10df8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="10df8-112">Principale</span><span class="sxs-lookup"><span data-stu-id="10df8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="10df8-113">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="10df8-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10df8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="10df8-115">int</span><span class="sxs-lookup"><span data-stu-id="10df8-115">int</span></span></p></td>
<td><p><span data-ttu-id="10df8-116">Principale</span><span class="sxs-lookup"><span data-stu-id="10df8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="10df8-117">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="10df8-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10df8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="10df8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="10df8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="10df8-120">Principale</span><span class="sxs-lookup"><span data-stu-id="10df8-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="10df8-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="10df8-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10df8-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="10df8-123">po'</span><span class="sxs-lookup"><span data-stu-id="10df8-123">bit</span></span></p></td>
<td><p><span data-ttu-id="10df8-124">Principale</span><span class="sxs-lookup"><span data-stu-id="10df8-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="10df8-125">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="10df8-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="10df8-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="10df8-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10df8-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="10df8-128">Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="10df8-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="10df8-129">La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="10df8-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10df8-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="10df8-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="10df8-131">Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="10df8-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="10df8-132">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="10df8-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

