---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="d7178-102">tblPrincipalType in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7178-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7178-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d7178-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d7178-104">tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d7178-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="d7178-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="d7178-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7178-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="d7178-106">Column</span></span></th>
<th><span data-ttu-id="d7178-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d7178-107">Type</span></span></th>
<th><span data-ttu-id="d7178-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7178-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7178-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="d7178-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="d7178-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="d7178-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="d7178-111">ID tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="d7178-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="d7178-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="d7178-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="d7178-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="d7178-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="d7178-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7178-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="d7178-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="d7178-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d7178-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d7178-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="d7178-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="d7178-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="d7178-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d7178-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d7178-120">True se il tipo è un tipo di utente.</span><span class="sxs-lookup"><span data-stu-id="d7178-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="d7178-121">Chiave</span><span class="sxs-lookup"><span data-stu-id="d7178-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7178-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="d7178-122">Column</span></span></th>
<th><span data-ttu-id="d7178-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7178-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7178-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="d7178-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="d7178-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="d7178-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="d7178-126">Valori principali</span><span class="sxs-lookup"><span data-stu-id="d7178-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7178-127">ID</span><span class="sxs-lookup"><span data-stu-id="d7178-127">ID</span></span></th>
<th><span data-ttu-id="d7178-128">Ruolo</span><span class="sxs-lookup"><span data-stu-id="d7178-128">Role</span></span></th>
<th><span data-ttu-id="d7178-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7178-129">Description</span></span></th>
<th><span data-ttu-id="d7178-130">Utente</span><span class="sxs-lookup"><span data-stu-id="d7178-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7178-131">1</span><span class="sxs-lookup"><span data-stu-id="d7178-131">1</span></span></p></td>
<td><p><span data-ttu-id="d7178-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d7178-132">Any</span></span></p></td>
<td><p><span data-ttu-id="d7178-133">Entità generica con nessun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="d7178-133">Generic principal with no known type.</span></span> <span data-ttu-id="d7178-134">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d7178-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-135">2</span><span class="sxs-lookup"><span data-stu-id="d7178-135">2</span></span></p></td>
<td><p><span data-ttu-id="d7178-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="d7178-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="d7178-137">Oggetto Principal generico di tipo utente.</span><span class="sxs-lookup"><span data-stu-id="d7178-137">Generic principal of user type.</span></span> <span data-ttu-id="d7178-138">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d7178-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="d7178-139">Sì</span><span class="sxs-lookup"><span data-stu-id="d7178-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7178-140">3</span><span class="sxs-lookup"><span data-stu-id="d7178-140">3</span></span></p></td>
<td><p><span data-ttu-id="d7178-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="d7178-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="d7178-142">Entità generica con semantica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d7178-142">Generic principal with group semantic.</span></span> <span data-ttu-id="d7178-143">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d7178-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-144">4</span><span class="sxs-lookup"><span data-stu-id="d7178-144">4</span></span></p></td>
<td><p><span data-ttu-id="d7178-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="d7178-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="d7178-146">Principal usato internamente dal server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d7178-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7178-147">5</span><span class="sxs-lookup"><span data-stu-id="d7178-147">5</span></span></p></td>
<td><p><span data-ttu-id="d7178-148">Utente</span><span class="sxs-lookup"><span data-stu-id="d7178-148">User</span></span></p></td>
<td><p><span data-ttu-id="d7178-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="d7178-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="d7178-150">Sì</span><span class="sxs-lookup"><span data-stu-id="d7178-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-151">8</span><span class="sxs-lookup"><span data-stu-id="d7178-151">8</span></span></p></td>
<td><p><span data-ttu-id="d7178-152">DC</span><span class="sxs-lookup"><span data-stu-id="d7178-152">DC</span></span></p></td>
<td><p><span data-ttu-id="d7178-153">Controller di dominio Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="d7178-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7178-154">9</span><span class="sxs-lookup"><span data-stu-id="d7178-154">9</span></span></p></td>
<td><p><span data-ttu-id="d7178-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="d7178-155">Group</span></span></p></td>
<td><p><span data-ttu-id="d7178-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d7178-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7178-157">10</span><span class="sxs-lookup"><span data-stu-id="d7178-157">10</span></span></p></td>
<td><p><span data-ttu-id="d7178-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="d7178-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="d7178-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d7178-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d7178-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7178-160">See Also</span></span>


[<span data-ttu-id="d7178-161">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7178-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

