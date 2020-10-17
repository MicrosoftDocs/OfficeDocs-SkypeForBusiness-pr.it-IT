---
title: 'Lync Server 2013: tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a49682d5c154b154ddda6c5fd411905f5850722d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523793"
---
# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="f4ac0-102">tblLastInviteId in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ac0-102">tblLastInviteId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4ac0-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f4ac0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f4ac0-104">tblLastInviteId contiene l'ultimo ID invito generato per ogni utente e utilizzato nella tabella tblPrincipalInvites.</span><span class="sxs-lookup"><span data-stu-id="f4ac0-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="f4ac0-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="f4ac0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4ac0-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="f4ac0-106">Column</span></span></th>
<th><span data-ttu-id="f4ac0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4ac0-107">Type</span></span></th>
<th><span data-ttu-id="f4ac0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4ac0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4ac0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f4ac0-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f4ac0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="f4ac0-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4ac0-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="f4ac0-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f4ac0-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-114">Ultimo ID invito utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f4ac0-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f4ac0-115">Chiavi</span><span class="sxs-lookup"><span data-stu-id="f4ac0-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4ac0-116">Colonna</span><span class="sxs-lookup"><span data-stu-id="f4ac0-116">Column</span></span></th>
<th><span data-ttu-id="f4ac0-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f4ac0-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4ac0-118">prinID</span><span class="sxs-lookup"><span data-stu-id="f4ac0-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f4ac0-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4ac0-120">prinID</span><span class="sxs-lookup"><span data-stu-id="f4ac0-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="f4ac0-121">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f4ac0-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f4ac0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4ac0-122">See Also</span></span>


[<span data-ttu-id="f4ac0-123">tblPrincipalInvites in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ac0-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

