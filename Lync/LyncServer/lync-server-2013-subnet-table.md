---
title: 'Lync Server 2013: tabella subnet'
description: 'Lync Server 2013: tabella subnet.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30c04ddf897e0a62551709b30211ba724a75cbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546312"
---
# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="84dd9-103">Tabella subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84dd9-103">Subnet table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84dd9-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="84dd9-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="84dd9-p101">La tabella Subnet è una tabella di supporto. Ogni record rappresenta una subnet definita nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="84dd9-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84dd9-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="84dd9-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="84dd9-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="84dd9-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84dd9-111"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-111"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="84dd9-112">int</span><span class="sxs-lookup"><span data-stu-id="84dd9-112">int</span></span></p></td>
<td><p><span data-ttu-id="84dd9-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="84dd9-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="84dd9-114">Rappresentazione in forma di numero intero dell'IP della subnet.</span><span class="sxs-lookup"><span data-stu-id="84dd9-114">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84dd9-115"><strong>SubnetMask</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-115"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="84dd9-116">int</span><span class="sxs-lookup"><span data-stu-id="84dd9-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84dd9-117">Subnet mask.</span><span class="sxs-lookup"><span data-stu-id="84dd9-117">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84dd9-118"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-118"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="84dd9-119">int</span><span class="sxs-lookup"><span data-stu-id="84dd9-119">int</span></span></p></td>
<td><p><span data-ttu-id="84dd9-120">Stranieri</span><span class="sxs-lookup"><span data-stu-id="84dd9-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84dd9-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-usersite-table.md">tabella UserSite in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="84dd9-121">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84dd9-122"><strong>SubnetDescription</strong></span><span class="sxs-lookup"><span data-stu-id="84dd9-122"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="84dd9-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="84dd9-123">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84dd9-124">Descrizione della subnet.</span><span class="sxs-lookup"><span data-stu-id="84dd9-124">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

