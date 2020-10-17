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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509323"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="3e28c-102">Nella in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e28c-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e28c-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="3e28c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="3e28c-104">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="3e28c-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="3e28c-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="3e28c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e28c-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="3e28c-106">Column</span></span></th>
<th><span data-ttu-id="3e28c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e28c-107">Type</span></span></th>
<th><span data-ttu-id="3e28c-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e28c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-109">valueID</span><span class="sxs-lookup"><span data-stu-id="3e28c-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="3e28c-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="3e28c-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="3e28c-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="3e28c-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e28c-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="3e28c-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="3e28c-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="3e28c-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="3e28c-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3e28c-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="3e28c-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="3e28c-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="3e28c-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="3e28c-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="3e28c-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3e28c-118">Chiavi</span><span class="sxs-lookup"><span data-stu-id="3e28c-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e28c-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="3e28c-119">Column</span></span></th>
<th><span data-ttu-id="3e28c-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e28c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-121">valueID</span><span class="sxs-lookup"><span data-stu-id="3e28c-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="3e28c-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3e28c-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e28c-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="3e28c-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="3e28c-124">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="3e28c-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="3e28c-125">Valori della tabella</span><span class="sxs-lookup"><span data-stu-id="3e28c-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e28c-126">valueID</span><span class="sxs-lookup"><span data-stu-id="3e28c-126">valueID</span></span></th>
<th><span data-ttu-id="3e28c-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="3e28c-127">attributeID</span></span></th>
<th><span data-ttu-id="3e28c-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="3e28c-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-129">2</span><span class="sxs-lookup"><span data-stu-id="3e28c-129">2</span></span></p></td>
<td><p><span data-ttu-id="3e28c-130">1 </span><span class="sxs-lookup"><span data-stu-id="3e28c-130">1</span></span></p></td>
<td><p><span data-ttu-id="3e28c-131">privata</span><span class="sxs-lookup"><span data-stu-id="3e28c-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e28c-132">3</span><span class="sxs-lookup"><span data-stu-id="3e28c-132">3</span></span></p></td>
<td><p><span data-ttu-id="3e28c-133">1 </span><span class="sxs-lookup"><span data-stu-id="3e28c-133">1</span></span></p></td>
<td><p><span data-ttu-id="3e28c-134">ambito</span><span class="sxs-lookup"><span data-stu-id="3e28c-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-135">4 </span><span class="sxs-lookup"><span data-stu-id="3e28c-135">4</span></span></p></td>
<td><p><span data-ttu-id="3e28c-136">2</span><span class="sxs-lookup"><span data-stu-id="3e28c-136">2</span></span></p></td>
<td><p><span data-ttu-id="3e28c-137">normale</span><span class="sxs-lookup"><span data-stu-id="3e28c-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e28c-138">5 </span><span class="sxs-lookup"><span data-stu-id="3e28c-138">5</span></span></p></td>
<td><p><span data-ttu-id="3e28c-139">2</span><span class="sxs-lookup"><span data-stu-id="3e28c-139">2</span></span></p></td>
<td><p><span data-ttu-id="3e28c-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="3e28c-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e28c-141">6 </span><span class="sxs-lookup"><span data-stu-id="3e28c-141">6</span></span></p></td>
<td><p><span data-ttu-id="3e28c-142">1 </span><span class="sxs-lookup"><span data-stu-id="3e28c-142">1</span></span></p></td>
<td><p><span data-ttu-id="3e28c-143">aprire</span><span class="sxs-lookup"><span data-stu-id="3e28c-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="3e28c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e28c-144">See Also</span></span>


[<span data-ttu-id="3e28c-145">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e28c-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

