---
title: 'Lync Server 2013: tabella server'
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
ms.openlocfilehash: d95ca6af9a3e762a39142fcaf754d810050d83d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="093d7-102">Tabella server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="093d7-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="093d7-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="093d7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="093d7-104">La tabella server è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="093d7-104">The Server table is a supporting table.</span></span> <span data-ttu-id="093d7-105">Ogni record rappresenta un server.</span><span class="sxs-lookup"><span data-stu-id="093d7-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="093d7-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="093d7-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="093d7-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="093d7-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="093d7-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="093d7-111">int</span><span class="sxs-lookup"><span data-stu-id="093d7-111">int</span></span></p></td>
<td><p><span data-ttu-id="093d7-112">Principale</span><span class="sxs-lookup"><span data-stu-id="093d7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="093d7-113">Numero univoco che identifica il server.</span><span class="sxs-lookup"><span data-stu-id="093d7-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="093d7-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="093d7-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="093d7-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="093d7-116">Indice</span><span class="sxs-lookup"><span data-stu-id="093d7-116">index</span></span></p></td>
<td><p><span data-ttu-id="093d7-117">Stringa dell'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="093d7-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="093d7-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="093d7-119">int</span><span class="sxs-lookup"><span data-stu-id="093d7-119">int</span></span></p></td>
<td><p><span data-ttu-id="093d7-120">Stranieri</span><span class="sxs-lookup"><span data-stu-id="093d7-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="093d7-121">1: Mediation Server</span><span class="sxs-lookup"><span data-stu-id="093d7-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="093d7-122">2: a/V Conferencing Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="093d7-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="093d7-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="093d7-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="093d7-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="093d7-125">Pool a cui appartiene il server.</span><span class="sxs-lookup"><span data-stu-id="093d7-125">Pool the server belongs to.</span></span> <span data-ttu-id="093d7-126">Applicabile solo per l'A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="093d7-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="093d7-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="093d7-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="093d7-128">datetime</span><span class="sxs-lookup"><span data-stu-id="093d7-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="093d7-129">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="093d7-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

