---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="798e8-102">tblScopePrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="798e8-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="798e8-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="798e8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="798e8-104">tblScopePrincipal contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="798e8-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="798e8-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="798e8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="798e8-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="798e8-106">Column</span></span></th>
<th><span data-ttu-id="798e8-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="798e8-107">Type</span></span></th>
<th><span data-ttu-id="798e8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="798e8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="798e8-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="798e8-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="798e8-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="798e8-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="798e8-111">ID nodo a cui si applica l'ambito.</span><span class="sxs-lookup"><span data-stu-id="798e8-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="798e8-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="798e8-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="798e8-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="798e8-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="798e8-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="798e8-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="798e8-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="798e8-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="798e8-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="798e8-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="798e8-117">True se il tipo di ambito è Deny; False se Consenti.</span><span class="sxs-lookup"><span data-stu-id="798e8-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="798e8-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="798e8-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="798e8-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="798e8-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="798e8-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="798e8-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="798e8-121">Tasti</span><span class="sxs-lookup"><span data-stu-id="798e8-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="798e8-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="798e8-122">Column</span></span></th>
<th><span data-ttu-id="798e8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="798e8-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="798e8-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="798e8-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="798e8-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="798e8-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="798e8-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="798e8-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="798e8-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="798e8-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="798e8-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="798e8-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="798e8-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="798e8-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

