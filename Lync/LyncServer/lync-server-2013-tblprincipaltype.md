---
title: 'Lync Server 2013: PrincipalType'
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
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="691bf-102">PrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="691bf-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="691bf-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="691bf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="691bf-104">Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="691bf-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="691bf-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="691bf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="691bf-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="691bf-106">Column</span></span></th>
<th><span data-ttu-id="691bf-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="691bf-107">Type</span></span></th>
<th><span data-ttu-id="691bf-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="691bf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="691bf-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="691bf-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="691bf-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="691bf-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="691bf-111">ID del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="691bf-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="691bf-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="691bf-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="691bf-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="691bf-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="691bf-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="691bf-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="691bf-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="691bf-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="691bf-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="691bf-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="691bf-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="691bf-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="691bf-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="691bf-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="691bf-120">True se il tipo è un tipo utente.</span><span class="sxs-lookup"><span data-stu-id="691bf-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="691bf-121">Chiave</span><span class="sxs-lookup"><span data-stu-id="691bf-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="691bf-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="691bf-122">Column</span></span></th>
<th><span data-ttu-id="691bf-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="691bf-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="691bf-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="691bf-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="691bf-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="691bf-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="691bf-126">Valori principali</span><span class="sxs-lookup"><span data-stu-id="691bf-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="691bf-127">ID</span><span class="sxs-lookup"><span data-stu-id="691bf-127">ID</span></span></th>
<th><span data-ttu-id="691bf-128">Ruolo</span><span class="sxs-lookup"><span data-stu-id="691bf-128">Role</span></span></th>
<th><span data-ttu-id="691bf-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="691bf-129">Description</span></span></th>
<th><span data-ttu-id="691bf-130">Utente</span><span class="sxs-lookup"><span data-stu-id="691bf-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="691bf-131">1</span><span class="sxs-lookup"><span data-stu-id="691bf-131">1</span></span></p></td>
<td><p><span data-ttu-id="691bf-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="691bf-132">Any</span></span></p></td>
<td><p><span data-ttu-id="691bf-p101">Entità generica senza tipo conosciuto. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="691bf-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-135">2</span><span class="sxs-lookup"><span data-stu-id="691bf-135">2</span></span></p></td>
<td><p><span data-ttu-id="691bf-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="691bf-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="691bf-p102">Entità generica di tipo utente. Non usate nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="691bf-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="691bf-139">Sì</span><span class="sxs-lookup"><span data-stu-id="691bf-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="691bf-140">3</span><span class="sxs-lookup"><span data-stu-id="691bf-140">3</span></span></p></td>
<td><p><span data-ttu-id="691bf-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="691bf-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="691bf-p103">Entità generica con semantica di gruppo. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="691bf-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-144">4</span><span class="sxs-lookup"><span data-stu-id="691bf-144">4</span></span></p></td>
<td><p><span data-ttu-id="691bf-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="691bf-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="691bf-146">Entità utilizzata internamente dal server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="691bf-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="691bf-147">5</span><span class="sxs-lookup"><span data-stu-id="691bf-147">5</span></span></p></td>
<td><p><span data-ttu-id="691bf-148">Utente</span><span class="sxs-lookup"><span data-stu-id="691bf-148">User</span></span></p></td>
<td><p><span data-ttu-id="691bf-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="691bf-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="691bf-150">Sì</span><span class="sxs-lookup"><span data-stu-id="691bf-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-151">8 </span><span class="sxs-lookup"><span data-stu-id="691bf-151">8</span></span></p></td>
<td><p><span data-ttu-id="691bf-152">DC</span><span class="sxs-lookup"><span data-stu-id="691bf-152">DC</span></span></p></td>
<td><p><span data-ttu-id="691bf-153">Controller di dominio di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="691bf-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="691bf-154">9 </span><span class="sxs-lookup"><span data-stu-id="691bf-154">9</span></span></p></td>
<td><p><span data-ttu-id="691bf-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="691bf-155">Group</span></span></p></td>
<td><p><span data-ttu-id="691bf-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="691bf-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="691bf-157">10 </span><span class="sxs-lookup"><span data-stu-id="691bf-157">10</span></span></p></td>
<td><p><span data-ttu-id="691bf-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="691bf-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="691bf-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="691bf-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="691bf-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="691bf-160">See Also</span></span>


[<span data-ttu-id="691bf-161">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="691bf-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

