---
title: 'Lync Server 2013: tblPrincipalType'
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
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="dba51-102">tblPrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dba51-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dba51-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dba51-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dba51-104">tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="dba51-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="dba51-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="dba51-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dba51-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="dba51-106">Column</span></span></th>
<th><span data-ttu-id="dba51-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="dba51-107">Type</span></span></th>
<th><span data-ttu-id="dba51-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dba51-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dba51-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="dba51-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="dba51-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="dba51-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="dba51-111">ID tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="dba51-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="dba51-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="dba51-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="dba51-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dba51-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="dba51-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dba51-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="dba51-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="dba51-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="dba51-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="dba51-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="dba51-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="dba51-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="dba51-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="dba51-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="dba51-120">True se il tipo è un tipo di utente.</span><span class="sxs-lookup"><span data-stu-id="dba51-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dba51-121">Chiave</span><span class="sxs-lookup"><span data-stu-id="dba51-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dba51-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="dba51-122">Column</span></span></th>
<th><span data-ttu-id="dba51-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dba51-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dba51-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="dba51-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="dba51-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="dba51-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="dba51-126">Valori principali</span><span class="sxs-lookup"><span data-stu-id="dba51-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dba51-127">ID</span><span class="sxs-lookup"><span data-stu-id="dba51-127">ID</span></span></th>
<th><span data-ttu-id="dba51-128">Ruolo</span><span class="sxs-lookup"><span data-stu-id="dba51-128">Role</span></span></th>
<th><span data-ttu-id="dba51-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dba51-129">Description</span></span></th>
<th><span data-ttu-id="dba51-130">Utente</span><span class="sxs-lookup"><span data-stu-id="dba51-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dba51-131">1</span><span class="sxs-lookup"><span data-stu-id="dba51-131">1</span></span></p></td>
<td><p><span data-ttu-id="dba51-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dba51-132">Any</span></span></p></td>
<td><p><span data-ttu-id="dba51-133">Entità generica con nessun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="dba51-133">Generic principal with no known type.</span></span> <span data-ttu-id="dba51-134">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="dba51-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-135">2</span><span class="sxs-lookup"><span data-stu-id="dba51-135">2</span></span></p></td>
<td><p><span data-ttu-id="dba51-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="dba51-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="dba51-137">Oggetto Principal generico di tipo utente.</span><span class="sxs-lookup"><span data-stu-id="dba51-137">Generic principal of user type.</span></span> <span data-ttu-id="dba51-138">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="dba51-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="dba51-139">Sì</span><span class="sxs-lookup"><span data-stu-id="dba51-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dba51-140">3</span><span class="sxs-lookup"><span data-stu-id="dba51-140">3</span></span></p></td>
<td><p><span data-ttu-id="dba51-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="dba51-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="dba51-142">Entità generica con semantica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="dba51-142">Generic principal with group semantic.</span></span> <span data-ttu-id="dba51-143">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="dba51-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-144">4</span><span class="sxs-lookup"><span data-stu-id="dba51-144">4</span></span></p></td>
<td><p><span data-ttu-id="dba51-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="dba51-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="dba51-146">Principal usato internamente dal server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dba51-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dba51-147">5</span><span class="sxs-lookup"><span data-stu-id="dba51-147">5</span></span></p></td>
<td><p><span data-ttu-id="dba51-148">Utente</span><span class="sxs-lookup"><span data-stu-id="dba51-148">User</span></span></p></td>
<td><p><span data-ttu-id="dba51-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="dba51-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="dba51-150">Sì</span><span class="sxs-lookup"><span data-stu-id="dba51-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-151">8</span><span class="sxs-lookup"><span data-stu-id="dba51-151">8</span></span></p></td>
<td><p><span data-ttu-id="dba51-152">DC</span><span class="sxs-lookup"><span data-stu-id="dba51-152">DC</span></span></p></td>
<td><p><span data-ttu-id="dba51-153">Controller di dominio Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="dba51-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dba51-154">9</span><span class="sxs-lookup"><span data-stu-id="dba51-154">9</span></span></p></td>
<td><p><span data-ttu-id="dba51-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="dba51-155">Group</span></span></p></td>
<td><p><span data-ttu-id="dba51-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dba51-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dba51-157">10</span><span class="sxs-lookup"><span data-stu-id="dba51-157">10</span></span></p></td>
<td><p><span data-ttu-id="dba51-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="dba51-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="dba51-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dba51-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="dba51-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dba51-160">See Also</span></span>


[<span data-ttu-id="dba51-161">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dba51-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

