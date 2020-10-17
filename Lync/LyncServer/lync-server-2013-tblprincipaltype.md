---
title: 'Lync Server 2013: PrincipalType'
description: 'Lync Server 2013: PrincipalType.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549862"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="0ee03-103">PrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ee03-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ee03-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0ee03-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0ee03-105">Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0ee03-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="0ee03-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="0ee03-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ee03-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="0ee03-107">Column</span></span></th>
<th><span data-ttu-id="0ee03-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="0ee03-108">Type</span></span></th>
<th><span data-ttu-id="0ee03-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee03-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="0ee03-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0ee03-111">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="0ee03-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0ee03-112">ID del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="0ee03-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="0ee03-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="0ee03-114">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="0ee03-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0ee03-115">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="0ee03-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="0ee03-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="0ee03-117">bit, not null</span><span class="sxs-lookup"><span data-stu-id="0ee03-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0ee03-118">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="0ee03-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="0ee03-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="0ee03-120">bit, not null</span><span class="sxs-lookup"><span data-stu-id="0ee03-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0ee03-121">True se il tipo è un tipo utente.</span><span class="sxs-lookup"><span data-stu-id="0ee03-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0ee03-122">Chiave</span><span class="sxs-lookup"><span data-stu-id="0ee03-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ee03-123">Colonna</span><span class="sxs-lookup"><span data-stu-id="0ee03-123">Column</span></span></th>
<th><span data-ttu-id="0ee03-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee03-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="0ee03-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0ee03-126">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="0ee03-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="0ee03-127">Valori principali</span><span class="sxs-lookup"><span data-stu-id="0ee03-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ee03-128">ID</span><span class="sxs-lookup"><span data-stu-id="0ee03-128">ID</span></span></th>
<th><span data-ttu-id="0ee03-129">Ruolo</span><span class="sxs-lookup"><span data-stu-id="0ee03-129">Role</span></span></th>
<th><span data-ttu-id="0ee03-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee03-130">Description</span></span></th>
<th><span data-ttu-id="0ee03-131">Utente</span><span class="sxs-lookup"><span data-stu-id="0ee03-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-132">1 </span><span class="sxs-lookup"><span data-stu-id="0ee03-132">1</span></span></p></td>
<td><p><span data-ttu-id="0ee03-133">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="0ee03-133">Any</span></span></p></td>
<td><p><span data-ttu-id="0ee03-p101">Entità generica senza tipo conosciuto. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0ee03-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-136">2</span><span class="sxs-lookup"><span data-stu-id="0ee03-136">2</span></span></p></td>
<td><p><span data-ttu-id="0ee03-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="0ee03-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="0ee03-p102">Entità generica di tipo utente. Non usate nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0ee03-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="0ee03-140">Sì</span><span class="sxs-lookup"><span data-stu-id="0ee03-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-141">3</span><span class="sxs-lookup"><span data-stu-id="0ee03-141">3</span></span></p></td>
<td><p><span data-ttu-id="0ee03-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="0ee03-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="0ee03-p103">Entità generica con semantica di gruppo. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0ee03-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-145">4 </span><span class="sxs-lookup"><span data-stu-id="0ee03-145">4</span></span></p></td>
<td><p><span data-ttu-id="0ee03-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="0ee03-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="0ee03-147">Entità utilizzata internamente dal server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ee03-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-148">5 </span><span class="sxs-lookup"><span data-stu-id="0ee03-148">5</span></span></p></td>
<td><p><span data-ttu-id="0ee03-149">Utente</span><span class="sxs-lookup"><span data-stu-id="0ee03-149">User</span></span></p></td>
<td><p><span data-ttu-id="0ee03-150">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="0ee03-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="0ee03-151">Sì</span><span class="sxs-lookup"><span data-stu-id="0ee03-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-152">8 </span><span class="sxs-lookup"><span data-stu-id="0ee03-152">8</span></span></p></td>
<td><p><span data-ttu-id="0ee03-153">DC</span><span class="sxs-lookup"><span data-stu-id="0ee03-153">DC</span></span></p></td>
<td><p><span data-ttu-id="0ee03-154">Controller di dominio di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ee03-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ee03-155">9 </span><span class="sxs-lookup"><span data-stu-id="0ee03-155">9</span></span></p></td>
<td><p><span data-ttu-id="0ee03-156">Gruppo</span><span class="sxs-lookup"><span data-stu-id="0ee03-156">Group</span></span></p></td>
<td><p><span data-ttu-id="0ee03-157">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ee03-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ee03-158">10  </span><span class="sxs-lookup"><span data-stu-id="0ee03-158">10</span></span></p></td>
<td><p><span data-ttu-id="0ee03-159">Cartella</span><span class="sxs-lookup"><span data-stu-id="0ee03-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="0ee03-160">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ee03-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0ee03-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee03-161">See Also</span></span>


[<span data-ttu-id="0ee03-162">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ee03-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

