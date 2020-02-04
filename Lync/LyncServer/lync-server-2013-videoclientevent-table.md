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
ms.openlocfilehash: 8ff9e19288aaaa09b8c72f857f3cfcf4e5331dd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="a27e3-102">Tabella VideoClientEvent in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a27e3-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a27e3-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a27e3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a27e3-104">Ogni record contiene l'evento client per un endpoint in una videochiamata.</span><span class="sxs-lookup"><span data-stu-id="a27e3-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="a27e3-105">In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="a27e3-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a27e3-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a27e3-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a27e3-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a27e3-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a27e3-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a27e3-111">DateTime</span><span class="sxs-lookup"><span data-stu-id="a27e3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a27e3-112">Principale</span><span class="sxs-lookup"><span data-stu-id="a27e3-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a27e3-113">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a27e3-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a27e3-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a27e3-115">int</span><span class="sxs-lookup"><span data-stu-id="a27e3-115">int</span></span></p></td>
<td><p><span data-ttu-id="a27e3-116">Principale</span><span class="sxs-lookup"><span data-stu-id="a27e3-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a27e3-117">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a27e3-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a27e3-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a27e3-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a27e3-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a27e3-120">Principale</span><span class="sxs-lookup"><span data-stu-id="a27e3-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a27e3-121">A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a27e3-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a27e3-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a27e3-123">po'</span><span class="sxs-lookup"><span data-stu-id="a27e3-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a27e3-124">Principale</span><span class="sxs-lookup"><span data-stu-id="a27e3-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a27e3-125">0: dati del destinatario</span><span class="sxs-lookup"><span data-stu-id="a27e3-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a27e3-126">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="a27e3-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a27e3-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a27e3-128">Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="a27e3-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="a27e3-129">La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="a27e3-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a27e3-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a27e3-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a27e3-131">Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="a27e3-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="a27e3-132">La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="a27e3-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

