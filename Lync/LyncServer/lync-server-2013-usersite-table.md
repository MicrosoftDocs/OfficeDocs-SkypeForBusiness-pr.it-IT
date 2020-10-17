---
title: 'Lync Server 2013: tabella UserSite'
description: 'Lync Server 2013: tabella UserSite.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e0fb3149b9378bbfd3f14da8176eed226e4f57f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548622"
---
# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="e3995-103">Tabella UserSite in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3995-103">UserSite table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3995-104">_**Ultimo argomento modificato:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="e3995-104">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="e3995-p101">La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="e3995-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3995-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e3995-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e3995-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e3995-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3995-111"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-111"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e3995-112">int</span><span class="sxs-lookup"><span data-stu-id="e3995-112">int</span></span></p></td>
<td><p><span data-ttu-id="e3995-113">Principale</span><span class="sxs-lookup"><span data-stu-id="e3995-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e3995-114">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="e3995-114">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3995-115"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-115"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="e3995-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="e3995-116">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e3995-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="e3995-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="e3995-118">Nome del sito utente.</span><span class="sxs-lookup"><span data-stu-id="e3995-118">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3995-119"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="e3995-119"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e3995-120">int</span><span class="sxs-lookup"><span data-stu-id="e3995-120">int</span></span></p></td>
<td><p><span data-ttu-id="e3995-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="e3995-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e3995-122">A cui viene fatto riferimento dalla <a href="lync-server-2013-region-table.md">tabella Region in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e3995-122">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

