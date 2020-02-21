---
title: 'Lync Server 2013: tabella UserSite'
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
ms.openlocfilehash: 39119f423f1bc06b6f51f9f18cbbf39d670c7270
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a><span data-ttu-id="75de8-102">Tabella UserSite in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75de8-102">UserSite table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75de8-103">_**Ultimo argomento modificato:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="75de8-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="75de8-p101">La tabella UserSite è una tabella di supporto. Ogni record rappresenta un sito utente definito nell'impostazione di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="75de8-p101">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75de8-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="75de8-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="75de8-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="75de8-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75de8-110"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-110"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="75de8-111">int</span><span class="sxs-lookup"><span data-stu-id="75de8-111">int</span></span></p></td>
<td><p><span data-ttu-id="75de8-112">Principale</span><span class="sxs-lookup"><span data-stu-id="75de8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="75de8-113">Numero univoco che identifica il sito utente.</span><span class="sxs-lookup"><span data-stu-id="75de8-113">Unique number identifying the user site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75de8-114"><strong>UserSiteName</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-114"><strong>UserSiteName</strong></span></span></p></td>
<td><p><span data-ttu-id="75de8-115">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="75de8-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="75de8-116">Univoco</span><span class="sxs-lookup"><span data-stu-id="75de8-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="75de8-117">Nome del sito utente.</span><span class="sxs-lookup"><span data-stu-id="75de8-117">User site’s name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75de8-118"><strong>RegionKey</strong></span><span class="sxs-lookup"><span data-stu-id="75de8-118"><strong>RegionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="75de8-119">int</span><span class="sxs-lookup"><span data-stu-id="75de8-119">int</span></span></p></td>
<td><p><span data-ttu-id="75de8-120">Stranieri</span><span class="sxs-lookup"><span data-stu-id="75de8-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="75de8-121">A cui viene fatto riferimento dalla <a href="lync-server-2013-region-table.md">tabella Region in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="75de8-121">Referenced from <a href="lync-server-2013-region-table.md">Region table in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

