---
title: 'Lync Server 2013: nella'
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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="59c3b-102">Nella in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c3b-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c3b-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="59c3b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="59c3b-104">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="59c3b-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="59c3b-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="59c3b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59c3b-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="59c3b-106">Column</span></span></th>
<th><span data-ttu-id="59c3b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="59c3b-107">Type</span></span></th>
<th><span data-ttu-id="59c3b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59c3b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-109">valueID</span><span class="sxs-lookup"><span data-stu-id="59c3b-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="59c3b-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="59c3b-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="59c3b-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="59c3b-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c3b-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="59c3b-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="59c3b-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="59c3b-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="59c3b-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="59c3b-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="59c3b-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="59c3b-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="59c3b-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="59c3b-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="59c3b-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="59c3b-118">Chiavi</span><span class="sxs-lookup"><span data-stu-id="59c3b-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59c3b-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="59c3b-119">Column</span></span></th>
<th><span data-ttu-id="59c3b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59c3b-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-121">valueID</span><span class="sxs-lookup"><span data-stu-id="59c3b-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="59c3b-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="59c3b-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c3b-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="59c3b-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="59c3b-124">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="59c3b-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="59c3b-125">Valori della tabella</span><span class="sxs-lookup"><span data-stu-id="59c3b-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59c3b-126">valueID</span><span class="sxs-lookup"><span data-stu-id="59c3b-126">valueID</span></span></th>
<th><span data-ttu-id="59c3b-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="59c3b-127">attributeID</span></span></th>
<th><span data-ttu-id="59c3b-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="59c3b-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-129">2</span><span class="sxs-lookup"><span data-stu-id="59c3b-129">2</span></span></p></td>
<td><p><span data-ttu-id="59c3b-130">1</span><span class="sxs-lookup"><span data-stu-id="59c3b-130">1</span></span></p></td>
<td><p><span data-ttu-id="59c3b-131">privata</span><span class="sxs-lookup"><span data-stu-id="59c3b-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c3b-132">3</span><span class="sxs-lookup"><span data-stu-id="59c3b-132">3</span></span></p></td>
<td><p><span data-ttu-id="59c3b-133">1</span><span class="sxs-lookup"><span data-stu-id="59c3b-133">1</span></span></p></td>
<td><p><span data-ttu-id="59c3b-134">ambito</span><span class="sxs-lookup"><span data-stu-id="59c3b-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-135">4</span><span class="sxs-lookup"><span data-stu-id="59c3b-135">4</span></span></p></td>
<td><p><span data-ttu-id="59c3b-136">2</span><span class="sxs-lookup"><span data-stu-id="59c3b-136">2</span></span></p></td>
<td><p><span data-ttu-id="59c3b-137">normale</span><span class="sxs-lookup"><span data-stu-id="59c3b-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59c3b-138">5</span><span class="sxs-lookup"><span data-stu-id="59c3b-138">5</span></span></p></td>
<td><p><span data-ttu-id="59c3b-139">2</span><span class="sxs-lookup"><span data-stu-id="59c3b-139">2</span></span></p></td>
<td><p><span data-ttu-id="59c3b-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="59c3b-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59c3b-141">6 </span><span class="sxs-lookup"><span data-stu-id="59c3b-141">6</span></span></p></td>
<td><p><span data-ttu-id="59c3b-142">1</span><span class="sxs-lookup"><span data-stu-id="59c3b-142">1</span></span></p></td>
<td><p><span data-ttu-id="59c3b-143">aprire</span><span class="sxs-lookup"><span data-stu-id="59c3b-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="59c3b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59c3b-144">See Also</span></span>


[<span data-ttu-id="59c3b-145">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c3b-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

