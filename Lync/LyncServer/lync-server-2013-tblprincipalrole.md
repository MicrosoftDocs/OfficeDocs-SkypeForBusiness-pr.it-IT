---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="e0446-102">tblPrincipalRole in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0446-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0446-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e0446-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e0446-104">tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="e0446-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="e0446-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="e0446-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0446-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="e0446-106">Column</span></span></th>
<th><span data-ttu-id="e0446-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e0446-107">Type</span></span></th>
<th><span data-ttu-id="e0446-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0446-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0446-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e0446-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="e0446-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e0446-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0446-111">ID nodo a cui si applica il ruolo.</span><span class="sxs-lookup"><span data-stu-id="e0446-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0446-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e0446-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="e0446-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="e0446-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0446-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="e0446-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0446-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e0446-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="e0446-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="e0446-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0446-117">ID tipo di ruolo (da tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="e0446-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0446-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e0446-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="e0446-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="e0446-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e0446-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="e0446-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e0446-121">Tasti</span><span class="sxs-lookup"><span data-stu-id="e0446-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0446-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="e0446-122">Column</span></span></th>
<th><span data-ttu-id="e0446-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0446-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0446-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="e0446-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e0446-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="e0446-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0446-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e0446-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="e0446-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="e0446-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0446-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e0446-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="e0446-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="e0446-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0446-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e0446-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="e0446-131">Chiave esterna con ricerca nella tabella tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="e0446-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

