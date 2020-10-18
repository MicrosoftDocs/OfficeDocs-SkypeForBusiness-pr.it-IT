---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573222"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="58928-103">tblPrincipalMemberDifference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58928-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58928-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="58928-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="58928-105">tblPrincipalMemberDifference contiene le modifiche apportate all'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono state ancora elaborate dai successivi passaggi di sincronizzazione dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58928-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="58928-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="58928-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58928-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="58928-107">Column</span></span></th>
<th><span data-ttu-id="58928-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="58928-108">Type</span></span></th>
<th><span data-ttu-id="58928-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58928-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58928-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="58928-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="58928-111">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="58928-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="58928-112">GUID entità del gruppo modificato.</span><span class="sxs-lookup"><span data-stu-id="58928-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58928-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="58928-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="58928-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="58928-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="58928-115">Nome distinto del membro.</span><span class="sxs-lookup"><span data-stu-id="58928-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58928-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="58928-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="58928-117">bit, not null</span><span class="sxs-lookup"><span data-stu-id="58928-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="58928-p101">False se il membro è stato aggiunto. True se il membro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="58928-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="58928-120">Chiave</span><span class="sxs-lookup"><span data-stu-id="58928-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58928-121">Colonna</span><span class="sxs-lookup"><span data-stu-id="58928-121">Column</span></span></th>
<th><span data-ttu-id="58928-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58928-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58928-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="58928-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="58928-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="58928-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

