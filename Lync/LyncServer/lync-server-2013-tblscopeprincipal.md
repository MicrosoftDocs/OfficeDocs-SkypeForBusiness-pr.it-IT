---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8263369e9224c4a3aeb20bbb664392fbe3ba7c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536283"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="56ac1-102">tblScopePrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56ac1-102">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56ac1-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="56ac1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="56ac1-104">tblScopePrincipal contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="56ac1-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="56ac1-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="56ac1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56ac1-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="56ac1-106">Column</span></span></th>
<th><span data-ttu-id="56ac1-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="56ac1-107">Type</span></span></th>
<th><span data-ttu-id="56ac1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56ac1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ac1-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="56ac1-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="56ac1-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="56ac1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="56ac1-111">ID di nodo a cui si applica l'ambito.</span><span class="sxs-lookup"><span data-stu-id="56ac1-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ac1-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="56ac1-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="56ac1-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="56ac1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="56ac1-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="56ac1-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ac1-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="56ac1-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="56ac1-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="56ac1-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="56ac1-117">True se il tipo di ambito è Deny; False se è Allow.</span><span class="sxs-lookup"><span data-stu-id="56ac1-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ac1-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="56ac1-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="56ac1-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="56ac1-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="56ac1-120">ID dell'ultima entità che ha aggiornato questa voce.</span><span class="sxs-lookup"><span data-stu-id="56ac1-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="56ac1-121">Chiavi</span><span class="sxs-lookup"><span data-stu-id="56ac1-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56ac1-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="56ac1-122">Column</span></span></th>
<th><span data-ttu-id="56ac1-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="56ac1-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56ac1-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="56ac1-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="56ac1-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="56ac1-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56ac1-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="56ac1-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="56ac1-127">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="56ac1-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56ac1-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="56ac1-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="56ac1-129">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="56ac1-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

