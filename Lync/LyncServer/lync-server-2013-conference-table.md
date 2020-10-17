---
title: 'Lync Server 2013: tabella conferenze'
description: 'Lync Server 2013: tabella conferenze.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550662"
---
# <a name="conference-table-in-lync-server-2013"></a><span data-ttu-id="14c28-103">Tabella conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14c28-103">Conference table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14c28-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="14c28-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="14c28-p101">La tabella Conference è una tabella di supporto. Ogni record rappresenta una sessione di conferenza o peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="14c28-p101">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14c28-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="14c28-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="14c28-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="14c28-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14c28-111"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-111"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="14c28-112">int</span><span class="sxs-lookup"><span data-stu-id="14c28-112">int</span></span></p></td>
<td><p><span data-ttu-id="14c28-113">Principale</span><span class="sxs-lookup"><span data-stu-id="14c28-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="14c28-114">Numero univoco che identifica il record della conferenza.</span><span class="sxs-lookup"><span data-stu-id="14c28-114">Unique number identifying this conference record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c28-115"><strong>ConfURI</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-115"><strong>ConfURI</strong></span></span></p></td>
<td><p><span data-ttu-id="14c28-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="14c28-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="14c28-117">univoco</span><span class="sxs-lookup"><span data-stu-id="14c28-117">unique</span></span></p></td>
<td><p><span data-ttu-id="14c28-118">URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="14c28-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14c28-119"><strong>Checksum</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-119"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="14c28-120">int</span><span class="sxs-lookup"><span data-stu-id="14c28-120">int</span></span></p></td>
<td><p><span data-ttu-id="14c28-121">Indice</span><span class="sxs-lookup"><span data-stu-id="14c28-121">index</span></span></p></td>
<td><p><span data-ttu-id="14c28-p102">Checksum dell'URI conferenza. Per uso interno.</span><span class="sxs-lookup"><span data-stu-id="14c28-p102">Checksum of the conference URI. This is used internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14c28-124"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="14c28-124"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="14c28-125">datetime</span><span class="sxs-lookup"><span data-stu-id="14c28-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14c28-126">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="14c28-126">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

