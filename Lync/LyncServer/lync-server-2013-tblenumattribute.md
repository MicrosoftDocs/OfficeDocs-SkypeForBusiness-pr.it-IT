---
title: 'Lync Server 2013: tblEnumAttribute'
description: 'Lync Server 2013: tblEnumAttribute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571392"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="bccf6-103">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccf6-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bccf6-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bccf6-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bccf6-105">tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="bccf6-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="bccf6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="bccf6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bccf6-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="bccf6-107">Column</span></span></th>
<th><span data-ttu-id="bccf6-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="bccf6-108">Type</span></span></th>
<th><span data-ttu-id="bccf6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bccf6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bccf6-110">attributeID</span><span class="sxs-lookup"><span data-stu-id="bccf6-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="bccf6-111">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="bccf6-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bccf6-112">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="bccf6-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bccf6-113">attributeName</span><span class="sxs-lookup"><span data-stu-id="bccf6-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="bccf6-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="bccf6-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bccf6-115">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="bccf6-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bccf6-116">Chiave</span><span class="sxs-lookup"><span data-stu-id="bccf6-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bccf6-117">Colonna</span><span class="sxs-lookup"><span data-stu-id="bccf6-117">Column</span></span></th>
<th><span data-ttu-id="bccf6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bccf6-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bccf6-119">attributeID</span><span class="sxs-lookup"><span data-stu-id="bccf6-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="bccf6-120">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="bccf6-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="bccf6-121">Valori tabella</span><span class="sxs-lookup"><span data-stu-id="bccf6-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bccf6-122">attributeID</span><span class="sxs-lookup"><span data-stu-id="bccf6-122">attributeID</span></span></th>
<th><span data-ttu-id="bccf6-123">attributeName</span><span class="sxs-lookup"><span data-stu-id="bccf6-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bccf6-124">1 </span><span class="sxs-lookup"><span data-stu-id="bccf6-124">1</span></span></p></td>
<td><p><span data-ttu-id="bccf6-125">Visibilità.</span><span class="sxs-lookup"><span data-stu-id="bccf6-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bccf6-126">2</span><span class="sxs-lookup"><span data-stu-id="bccf6-126">2</span></span></p></td>
<td><p><span data-ttu-id="bccf6-127">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="bccf6-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="bccf6-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bccf6-128">See Also</span></span>


[<span data-ttu-id="bccf6-129">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccf6-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

