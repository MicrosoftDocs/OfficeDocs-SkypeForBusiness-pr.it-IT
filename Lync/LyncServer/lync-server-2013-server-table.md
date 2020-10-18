---
title: 'Lync Server 2013: tabella server'
description: 'Lync Server 2013: tabella server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576522"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="e90d0-103">Tabella server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e90d0-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e90d0-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e90d0-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e90d0-105">La tabella server è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="e90d0-105">The Server table is a supporting table.</span></span> <span data-ttu-id="e90d0-106">Ogni record rappresenta un server.</span><span class="sxs-lookup"><span data-stu-id="e90d0-106">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e90d0-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e90d0-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e90d0-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e90d0-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e90d0-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e90d0-112">int</span><span class="sxs-lookup"><span data-stu-id="e90d0-112">int</span></span></p></td>
<td><p><span data-ttu-id="e90d0-113">Principale</span><span class="sxs-lookup"><span data-stu-id="e90d0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e90d0-114">Numero univoco che identifica il server.</span><span class="sxs-lookup"><span data-stu-id="e90d0-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e90d0-115"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="e90d0-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e90d0-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e90d0-117">Indice</span><span class="sxs-lookup"><span data-stu-id="e90d0-117">index</span></span></p></td>
<td><p><span data-ttu-id="e90d0-118">Stringa dell'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="e90d0-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e90d0-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e90d0-120">int</span><span class="sxs-lookup"><span data-stu-id="e90d0-120">int</span></span></p></td>
<td><p><span data-ttu-id="e90d0-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="e90d0-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e90d0-122">1: Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e90d0-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="e90d0-123">2: a/V Conferencing Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="e90d0-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e90d0-124"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="e90d0-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e90d0-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e90d0-126">Pool a cui appartiene il server.</span><span class="sxs-lookup"><span data-stu-id="e90d0-126">Pool the server belongs to.</span></span> <span data-ttu-id="e90d0-127">Applicabile solo per l'A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="e90d0-127">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e90d0-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e90d0-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e90d0-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e90d0-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e90d0-130">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="e90d0-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

