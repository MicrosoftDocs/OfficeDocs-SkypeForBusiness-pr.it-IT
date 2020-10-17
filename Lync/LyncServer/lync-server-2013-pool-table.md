---
title: 'Lync Server 2013: tabella del pool'
description: 'Lync Server 2013: tabella del pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559244d37580070e7930a163eaddcc748eb2172c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563952"
---
# <a name="pool-table-in-lync-server-2013"></a><span data-ttu-id="c0c8a-103">Tabella del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0c8a-103">Pool table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0c8a-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c0c8a-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c0c8a-p101">La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.</span><span class="sxs-lookup"><span data-stu-id="c0c8a-p101">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0c8a-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c0c8a-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c0c8a-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c0c8a-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0c8a-111"><strong>PoolKey</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-111"><strong>PoolKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c0c8a-112">int</span><span class="sxs-lookup"><span data-stu-id="c0c8a-112">int</span></span></p></td>
<td><p><span data-ttu-id="c0c8a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c0c8a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0c8a-114">Numero univoco che identifica il pool.</span><span class="sxs-lookup"><span data-stu-id="c0c8a-114">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0c8a-115"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="c0c8a-115"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="c0c8a-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c0c8a-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c0c8a-117">Univoco </span><span class="sxs-lookup"><span data-stu-id="c0c8a-117">Unique </span></span></p></td>
<td><p><span data-ttu-id="c0c8a-118">Nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="c0c8a-118">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

