---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5db403431c182e3f5bb8e7a3fabaa04cd2a94d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="f53bd-102">tblPrincipalMemberDifference in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f53bd-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f53bd-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f53bd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f53bd-104">tblPrincipalMemberDifference contiene le modifiche dell'appartenenza ai gruppi (membri aggiunti e rimossi) che non sono ancora state elaborate dai passaggi successivi di sincronizzazione dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f53bd-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="f53bd-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="f53bd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f53bd-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="f53bd-106">Column</span></span></th>
<th><span data-ttu-id="f53bd-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f53bd-107">Type</span></span></th>
<th><span data-ttu-id="f53bd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f53bd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f53bd-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f53bd-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f53bd-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="f53bd-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f53bd-111">GUID principale del gruppo modificato.</span><span class="sxs-lookup"><span data-stu-id="f53bd-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f53bd-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="f53bd-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="f53bd-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f53bd-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f53bd-114">Nome distinto del membro.</span><span class="sxs-lookup"><span data-stu-id="f53bd-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f53bd-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="f53bd-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="f53bd-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f53bd-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f53bd-117">False se il membro è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f53bd-117">False if the member was added.</span></span> <span data-ttu-id="f53bd-118">True se il membro è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="f53bd-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f53bd-119">Chiave</span><span class="sxs-lookup"><span data-stu-id="f53bd-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f53bd-120">Colonna</span><span class="sxs-lookup"><span data-stu-id="f53bd-120">Column</span></span></th>
<th><span data-ttu-id="f53bd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f53bd-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f53bd-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="f53bd-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="f53bd-123">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f53bd-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

