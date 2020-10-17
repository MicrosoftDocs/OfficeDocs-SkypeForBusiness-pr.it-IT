---
title: 'Lync Server 2013: tblRoleType'
description: 'Lync Server 2013: tblRoleType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568542"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="ce0e6-103">tblRoleType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e6-103">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0e6-104">_**Ultimo argomento modificato:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="ce0e6-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="ce0e6-105">tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-105">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="ce0e6-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="ce0e6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce0e6-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="ce0e6-107">Column</span></span></th>
<th><span data-ttu-id="ce0e6-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce0e6-108">Type</span></span></th>
<th><span data-ttu-id="ce0e6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce0e6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce0e6-110">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ce0e6-110">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="ce0e6-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-112">ID del tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-112">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce0e6-113">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="ce0e6-113">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="ce0e6-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-p101">Descrizione del tipo di ruolo. Sono disponibili quattro ruoli:</span><span class="sxs-lookup"><span data-stu-id="ce0e6-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="ce0e6-117">Member: membro della chat.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-117">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-118">Manager: responsabile della chat.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-118">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-119">Voiced: relatore per una chat. auditorium</span><span class="sxs-lookup"><span data-stu-id="ce0e6-119">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-120">Creator: creazione di chat room</span><span class="sxs-lookup"><span data-stu-id="ce0e6-120">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce0e6-121">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="ce0e6-121">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-122">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="ce0e6-122">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-p102">Set di autorizzazioni per il ruolo. I bit utilizzati sono:</span><span class="sxs-lookup"><span data-stu-id="ce0e6-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ce0e6-125">2: true se il ruolo può gestire i nodi.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-125">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-126">4: true se il ruolo può creare nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-126">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-127">7: true se il ruolo può partecipare a una chat (o a chat figlio di una categoria).</span><span class="sxs-lookup"><span data-stu-id="ce0e6-127">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-128">8: true se il ruolo può eseguire chat in una chat (o in chat figlio di una categoria).</span><span class="sxs-lookup"><span data-stu-id="ce0e6-128">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-129">10: true se il ruolo può leggere la cronologia delle chat anche se non partecipa a una chat.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-129">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-p103">11: true se il ruolo può visualizzare la chat (ulteriormente definito da fattori come l'ambito e la visibilità).</span><span class="sxs-lookup"><span data-stu-id="ce0e6-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-132">12: true se il ruolo può eseguire chat in una chat auditorium.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-132">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="ce0e6-133">13: true se il ruolo può ignorare le regole di visibilità quando visualizza i nodi.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-133">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="ce0e6-134">Chiave</span><span class="sxs-lookup"><span data-stu-id="ce0e6-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce0e6-135">Colonna</span><span class="sxs-lookup"><span data-stu-id="ce0e6-135">Column</span></span></th>
<th><span data-ttu-id="ce0e6-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce0e6-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce0e6-137">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ce0e6-137">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="ce0e6-138">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ce0e6-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

