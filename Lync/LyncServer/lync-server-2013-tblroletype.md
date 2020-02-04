---
title: 'Lync Server 2013: tblRoleType'
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
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="18fe7-102">tblRoleType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18fe7-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18fe7-103">_**Argomento Ultima modifica:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="18fe7-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="18fe7-104">tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="18fe7-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="18fe7-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="18fe7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18fe7-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="18fe7-106">Column</span></span></th>
<th><span data-ttu-id="18fe7-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="18fe7-107">Type</span></span></th>
<th><span data-ttu-id="18fe7-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18fe7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18fe7-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="18fe7-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="18fe7-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="18fe7-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="18fe7-111">ID tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="18fe7-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fe7-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="18fe7-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="18fe7-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="18fe7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="18fe7-114">Descrizione del tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="18fe7-114">Role type description.</span></span> <span data-ttu-id="18fe7-115">Esistono quattro ruoli disponibili:</span><span class="sxs-lookup"><span data-stu-id="18fe7-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="18fe7-116">Membro: membro della chat room</span><span class="sxs-lookup"><span data-stu-id="18fe7-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="18fe7-117">Manager: gestione chat room</span><span class="sxs-lookup"><span data-stu-id="18fe7-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="18fe7-118">Voiced: relatore per una chat room dell'Auditorium</span><span class="sxs-lookup"><span data-stu-id="18fe7-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="18fe7-119">Creatore: può creare chat room</span><span class="sxs-lookup"><span data-stu-id="18fe7-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fe7-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="18fe7-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="18fe7-121">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="18fe7-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="18fe7-122">Set di autorizzazioni per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="18fe7-122">Permission set for the role.</span></span> <span data-ttu-id="18fe7-123">I bit usati sono:</span><span class="sxs-lookup"><span data-stu-id="18fe7-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18fe7-124">2: true se il ruolo può gestire i nodi.</span><span class="sxs-lookup"><span data-stu-id="18fe7-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="18fe7-125">4: true se il ruolo può creare nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="18fe7-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="18fe7-126">7: vero se il ruolo può partecipare a una chat room (o chat room per bambini di una categoria).</span><span class="sxs-lookup"><span data-stu-id="18fe7-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="18fe7-127">8: true se il ruolo può essere chattato in una chat room o in chat per bambini di una categoria.</span><span class="sxs-lookup"><span data-stu-id="18fe7-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="18fe7-128">10: true se il ruolo può leggere la cronologia chat anche quando non è stato aggiunto a una chat room.</span><span class="sxs-lookup"><span data-stu-id="18fe7-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="18fe7-129">11: vero se il ruolo può vedere la chat room.</span><span class="sxs-lookup"><span data-stu-id="18fe7-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="18fe7-130">(Questa operazione viene ulteriormente affinata da fattori come l'ambito e la visibilità).</span><span class="sxs-lookup"><span data-stu-id="18fe7-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="18fe7-131">12: vero se il ruolo può chattare in una chat room di un auditorium.</span><span class="sxs-lookup"><span data-stu-id="18fe7-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="18fe7-132">13: true se il ruolo può ignorare le regole di visibilità durante la visualizzazione dei nodi.</span><span class="sxs-lookup"><span data-stu-id="18fe7-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="18fe7-133">Chiave</span><span class="sxs-lookup"><span data-stu-id="18fe7-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18fe7-134">Colonna</span><span class="sxs-lookup"><span data-stu-id="18fe7-134">Column</span></span></th>
<th><span data-ttu-id="18fe7-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18fe7-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18fe7-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="18fe7-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="18fe7-137">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="18fe7-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

