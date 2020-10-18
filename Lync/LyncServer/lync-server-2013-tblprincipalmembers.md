---
title: 'Lync Server 2013: tblPrincipalMembers'
description: 'Lync Server 2013: tblPrincipalMembers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bbb8be0b83d09b1bd54ea98655558581e6df834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573182"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="130fc-103">tblPrincipalMembers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="130fc-103">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="130fc-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="130fc-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="130fc-105">Nella tabella tblPrincipalMembers sono contenute le appartenenze principali.</span><span class="sxs-lookup"><span data-stu-id="130fc-105">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="130fc-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="130fc-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="130fc-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="130fc-107">Column</span></span></th>
<th><span data-ttu-id="130fc-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="130fc-108">Type</span></span></th>
<th><span data-ttu-id="130fc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="130fc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="130fc-110">prinID</span><span class="sxs-lookup"><span data-stu-id="130fc-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="130fc-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="130fc-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="130fc-112">ID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="130fc-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="130fc-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="130fc-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="130fc-114">nvarchar (384), non null</span><span class="sxs-lookup"><span data-stu-id="130fc-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="130fc-p101">Nome distinto di un membro. Non è necessario che un membro sia un'entità (nella tabella tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="130fc-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="130fc-117">Chiavi</span><span class="sxs-lookup"><span data-stu-id="130fc-117">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="130fc-118">Colonna</span><span class="sxs-lookup"><span data-stu-id="130fc-118">Column</span></span></th>
<th><span data-ttu-id="130fc-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="130fc-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="130fc-120">&lt;prinID, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="130fc-120">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="130fc-121">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="130fc-121">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="130fc-122">prinID</span><span class="sxs-lookup"><span data-stu-id="130fc-122">prinID</span></span></p></td>
<td><p><span data-ttu-id="130fc-123">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="130fc-123">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

