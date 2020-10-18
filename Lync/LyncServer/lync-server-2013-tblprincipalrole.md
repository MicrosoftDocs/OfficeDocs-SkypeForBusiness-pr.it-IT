---
title: 'Lync Server 2013: tblPrincipalRole'
description: 'Lync Server 2013: tblPrincipalRole.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573632"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="5b9a0-103">tblPrincipalRole in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9a0-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9a0-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5b9a0-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5b9a0-105">tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5b9a0-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="5b9a0-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b9a0-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="5b9a0-107">Column</span></span></th>
<th><span data-ttu-id="5b9a0-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="5b9a0-108">Type</span></span></th>
<th><span data-ttu-id="5b9a0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b9a0-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b9a0-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="5b9a0-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-112">ID del nodo a cui si applica il ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9a0-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="5b9a0-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-115">ID entità.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9a0-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="5b9a0-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-118">ID del tipo di ruolo (da tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="5b9a0-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9a0-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5b9a0-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="5b9a0-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-121">ID dell'ultima entità che ha aggiornato questa voce.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5b9a0-122">Chiavi</span><span class="sxs-lookup"><span data-stu-id="5b9a0-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b9a0-123">Colonna</span><span class="sxs-lookup"><span data-stu-id="5b9a0-123">Column</span></span></th>
<th><span data-ttu-id="5b9a0-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b9a0-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b9a0-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="5b9a0-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-126">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9a0-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-128">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9a0-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-130">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9a0-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5b9a0-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="5b9a0-132">Chiave esterna con ricerca nella tabella tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="5b9a0-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

