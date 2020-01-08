---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="3ffa0-102">tblEnumValue in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ffa0-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ffa0-103">_**Argomento Ultima modifica:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="3ffa0-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="3ffa0-104">tblEnumValue è una tabella hardcoded che contiene i valori di visibilità e comportamento degli attributi usati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="3ffa0-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="3ffa0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ffa0-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="3ffa0-106">Column</span></span></th>
<th><span data-ttu-id="3ffa0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="3ffa0-107">Type</span></span></th>
<th><span data-ttu-id="3ffa0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ffa0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-109">valueID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="3ffa0-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffa0-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-113">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="3ffa0-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="3ffa0-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="3ffa0-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="3ffa0-118">Tasti</span><span class="sxs-lookup"><span data-stu-id="3ffa0-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ffa0-119">Colonna</span><span class="sxs-lookup"><span data-stu-id="3ffa0-119">Column</span></span></th>
<th><span data-ttu-id="3ffa0-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ffa0-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-121">valueID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffa0-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-124">Chiave esterna con ricerca nella tabella tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="3ffa0-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="3ffa0-125">Valori tabella</span><span class="sxs-lookup"><span data-stu-id="3ffa0-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ffa0-126">valueID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-126">valueID</span></span></th>
<th><span data-ttu-id="3ffa0-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="3ffa0-127">attributeID</span></span></th>
<th><span data-ttu-id="3ffa0-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="3ffa0-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-129">2</span><span class="sxs-lookup"><span data-stu-id="3ffa0-129">2</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-130">1</span><span class="sxs-lookup"><span data-stu-id="3ffa0-130">1</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-131">privato</span><span class="sxs-lookup"><span data-stu-id="3ffa0-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffa0-132">3</span><span class="sxs-lookup"><span data-stu-id="3ffa0-132">3</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-133">1</span><span class="sxs-lookup"><span data-stu-id="3ffa0-133">1</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-134">ambito</span><span class="sxs-lookup"><span data-stu-id="3ffa0-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-135">4</span><span class="sxs-lookup"><span data-stu-id="3ffa0-135">4</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-136">2</span><span class="sxs-lookup"><span data-stu-id="3ffa0-136">2</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-137">normale</span><span class="sxs-lookup"><span data-stu-id="3ffa0-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffa0-138">5</span><span class="sxs-lookup"><span data-stu-id="3ffa0-138">5</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-139">2</span><span class="sxs-lookup"><span data-stu-id="3ffa0-139">2</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="3ffa0-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffa0-141">6</span><span class="sxs-lookup"><span data-stu-id="3ffa0-141">6</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-142">1</span><span class="sxs-lookup"><span data-stu-id="3ffa0-142">1</span></span></p></td>
<td><p><span data-ttu-id="3ffa0-143">aprire</span><span class="sxs-lookup"><span data-stu-id="3ffa0-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="3ffa0-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ffa0-144">See Also</span></span>


[<span data-ttu-id="3ffa0-145">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ffa0-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

