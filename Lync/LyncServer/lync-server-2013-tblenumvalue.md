---
title: 'Lync Server 2013: nella'
description: 'Lync Server 2013: nella.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571372"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="9d266-103">Nella in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d266-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d266-104">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="9d266-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="9d266-105">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="9d266-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="9d266-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="9d266-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d266-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="9d266-107">Column</span></span></th>
<th><span data-ttu-id="9d266-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="9d266-108">Type</span></span></th>
<th><span data-ttu-id="9d266-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d266-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d266-110">valueID</span><span class="sxs-lookup"><span data-stu-id="9d266-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="9d266-111">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="9d266-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9d266-112">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="9d266-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d266-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="9d266-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9d266-114">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="9d266-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9d266-115">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="9d266-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d266-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9d266-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="9d266-117">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="9d266-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9d266-118">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="9d266-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9d266-119">Chiavi</span><span class="sxs-lookup"><span data-stu-id="9d266-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d266-120">Colonna</span><span class="sxs-lookup"><span data-stu-id="9d266-120">Column</span></span></th>
<th><span data-ttu-id="9d266-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d266-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d266-122">valueID</span><span class="sxs-lookup"><span data-stu-id="9d266-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="9d266-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9d266-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d266-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="9d266-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9d266-125">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="9d266-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="9d266-126">Valori della tabella</span><span class="sxs-lookup"><span data-stu-id="9d266-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9d266-127">valueID</span><span class="sxs-lookup"><span data-stu-id="9d266-127">valueID</span></span></th>
<th><span data-ttu-id="9d266-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="9d266-128">attributeID</span></span></th>
<th><span data-ttu-id="9d266-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9d266-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9d266-130">2</span><span class="sxs-lookup"><span data-stu-id="9d266-130">2</span></span></p></td>
<td><p><span data-ttu-id="9d266-131">1 </span><span class="sxs-lookup"><span data-stu-id="9d266-131">1</span></span></p></td>
<td><p><span data-ttu-id="9d266-132">privata</span><span class="sxs-lookup"><span data-stu-id="9d266-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d266-133">3</span><span class="sxs-lookup"><span data-stu-id="9d266-133">3</span></span></p></td>
<td><p><span data-ttu-id="9d266-134">1 </span><span class="sxs-lookup"><span data-stu-id="9d266-134">1</span></span></p></td>
<td><p><span data-ttu-id="9d266-135">ambito</span><span class="sxs-lookup"><span data-stu-id="9d266-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d266-136">4 </span><span class="sxs-lookup"><span data-stu-id="9d266-136">4</span></span></p></td>
<td><p><span data-ttu-id="9d266-137">2</span><span class="sxs-lookup"><span data-stu-id="9d266-137">2</span></span></p></td>
<td><p><span data-ttu-id="9d266-138">normale</span><span class="sxs-lookup"><span data-stu-id="9d266-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9d266-139">5 </span><span class="sxs-lookup"><span data-stu-id="9d266-139">5</span></span></p></td>
<td><p><span data-ttu-id="9d266-140">2</span><span class="sxs-lookup"><span data-stu-id="9d266-140">2</span></span></p></td>
<td><p><span data-ttu-id="9d266-141">Auditorium</span><span class="sxs-lookup"><span data-stu-id="9d266-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9d266-142">6 </span><span class="sxs-lookup"><span data-stu-id="9d266-142">6</span></span></p></td>
<td><p><span data-ttu-id="9d266-143">1 </span><span class="sxs-lookup"><span data-stu-id="9d266-143">1</span></span></p></td>
<td><p><span data-ttu-id="9d266-144">aprire</span><span class="sxs-lookup"><span data-stu-id="9d266-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9d266-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d266-145">See Also</span></span>


[<span data-ttu-id="9d266-146">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d266-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

