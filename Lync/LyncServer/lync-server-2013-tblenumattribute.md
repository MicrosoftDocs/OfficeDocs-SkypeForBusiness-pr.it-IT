---
title: 'Lync Server 2013: tblEnumAttribute'
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
ms.openlocfilehash: 8d7078c36763fb5c582f62c5b4ff7ddedf9cd100
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="7d262-102">tblEnumAttribute in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d262-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d262-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7d262-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7d262-104">tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="7d262-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="7d262-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="7d262-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d262-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="7d262-106">Column</span></span></th>
<th><span data-ttu-id="7d262-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="7d262-107">Type</span></span></th>
<th><span data-ttu-id="7d262-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d262-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d262-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="7d262-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7d262-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="7d262-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7d262-111">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="7d262-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d262-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="7d262-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="7d262-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="7d262-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7d262-114">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="7d262-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="7d262-115">Chiave</span><span class="sxs-lookup"><span data-stu-id="7d262-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d262-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="7d262-116">Column</span></span></th>
<th><span data-ttu-id="7d262-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d262-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d262-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="7d262-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="7d262-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7d262-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="7d262-120">Valori tabella</span><span class="sxs-lookup"><span data-stu-id="7d262-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d262-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="7d262-121">attributeID</span></span></th>
<th><span data-ttu-id="7d262-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="7d262-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d262-123">1 </span><span class="sxs-lookup"><span data-stu-id="7d262-123">1</span></span></p></td>
<td><p><span data-ttu-id="7d262-124">Visibilità.</span><span class="sxs-lookup"><span data-stu-id="7d262-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d262-125">2 </span><span class="sxs-lookup"><span data-stu-id="7d262-125">2</span></span></p></td>
<td><p><span data-ttu-id="7d262-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="7d262-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7d262-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d262-127">See Also</span></span>


[<span data-ttu-id="7d262-128">tblNode in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d262-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

