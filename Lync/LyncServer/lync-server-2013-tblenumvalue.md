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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="b8080-102">Nella in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8080-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8080-103">_**Ultimo argomento modificato:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="b8080-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="b8080-104">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="b8080-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="b8080-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8080-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8080-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="b8080-106">Column</span></span></th>
<th><span data-ttu-id="b8080-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="b8080-107">Type</span></span></th>
<th><span data-ttu-id="b8080-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8080-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8080-109">valueID</span><span class="sxs-lookup"><span data-stu-id="b8080-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="b8080-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b8080-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b8080-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="b8080-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8080-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8080-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b8080-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b8080-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b8080-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="b8080-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8080-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="b8080-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="b8080-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b8080-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b8080-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="b8080-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b8080-118">Chiavi</span><span class="sxs-lookup"><span data-stu-id="b8080-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8080-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="b8080-119">Column</span></span></th>
<th><span data-ttu-id="b8080-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8080-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8080-121">valueID</span><span class="sxs-lookup"><span data-stu-id="b8080-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="b8080-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b8080-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8080-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8080-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="b8080-124">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="b8080-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="b8080-125">Valori della tabella</span><span class="sxs-lookup"><span data-stu-id="b8080-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8080-126">valueID</span><span class="sxs-lookup"><span data-stu-id="b8080-126">valueID</span></span></th>
<th><span data-ttu-id="b8080-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8080-127">attributeID</span></span></th>
<th><span data-ttu-id="b8080-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="b8080-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b8080-129">2</span><span class="sxs-lookup"><span data-stu-id="b8080-129">2</span></span></p></td>
<td><p><span data-ttu-id="b8080-130">1</span><span class="sxs-lookup"><span data-stu-id="b8080-130">1</span></span></p></td>
<td><p><span data-ttu-id="b8080-131">privata</span><span class="sxs-lookup"><span data-stu-id="b8080-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8080-132">3</span><span class="sxs-lookup"><span data-stu-id="b8080-132">3</span></span></p></td>
<td><p><span data-ttu-id="b8080-133">1</span><span class="sxs-lookup"><span data-stu-id="b8080-133">1</span></span></p></td>
<td><p><span data-ttu-id="b8080-134">ambito</span><span class="sxs-lookup"><span data-stu-id="b8080-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8080-135">4</span><span class="sxs-lookup"><span data-stu-id="b8080-135">4</span></span></p></td>
<td><p><span data-ttu-id="b8080-136">2</span><span class="sxs-lookup"><span data-stu-id="b8080-136">2</span></span></p></td>
<td><p><span data-ttu-id="b8080-137">normale</span><span class="sxs-lookup"><span data-stu-id="b8080-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b8080-138">5</span><span class="sxs-lookup"><span data-stu-id="b8080-138">5</span></span></p></td>
<td><p><span data-ttu-id="b8080-139">2</span><span class="sxs-lookup"><span data-stu-id="b8080-139">2</span></span></p></td>
<td><p><span data-ttu-id="b8080-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="b8080-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b8080-141">6 </span><span class="sxs-lookup"><span data-stu-id="b8080-141">6</span></span></p></td>
<td><p><span data-ttu-id="b8080-142">1</span><span class="sxs-lookup"><span data-stu-id="b8080-142">1</span></span></p></td>
<td><p><span data-ttu-id="b8080-143">aprire</span><span class="sxs-lookup"><span data-stu-id="b8080-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b8080-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8080-144">See Also</span></span>


[<span data-ttu-id="b8080-145">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8080-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

