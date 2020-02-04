---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="20a9f-102">tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20a9f-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20a9f-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="20a9f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="20a9f-104">tblPrincipal contiene tutte le entità, inclusi utenti, cartelle e gruppi.</span><span class="sxs-lookup"><span data-stu-id="20a9f-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="20a9f-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="20a9f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20a9f-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="20a9f-106">Column</span></span></th>
<th><span data-ttu-id="20a9f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="20a9f-107">Type</span></span></th>
<th><span data-ttu-id="20a9f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20a9f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="20a9f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="20a9f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="20a9f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="20a9f-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="20a9f-113">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="20a9f-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-114">GUID principale.</span><span class="sxs-lookup"><span data-stu-id="20a9f-114">Principal GUID.</span></span> <span data-ttu-id="20a9f-115">Questa operazione viene ampiamente usata come chiave primaria alternativa perché il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20a9f-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="20a9f-116">Il GUID di un'entità memorizzata nella cache è uguale al GUID dell'oggetto Active Directory corrispondente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="20a9f-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="20a9f-118">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="20a9f-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-119">URI principale.</span><span class="sxs-lookup"><span data-stu-id="20a9f-119">Principal URI.</span></span> <span data-ttu-id="20a9f-120">Lo schema SIP viene usato per gli utenti e ma-GRP viene usato per quasi tutto il resto.</span><span class="sxs-lookup"><span data-stu-id="20a9f-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-121">prinname</span><span class="sxs-lookup"><span data-stu-id="20a9f-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="20a9f-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20a9f-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-123">Nome comune.</span><span class="sxs-lookup"><span data-stu-id="20a9f-123">Common name.</span></span> <span data-ttu-id="20a9f-124">Usato solo dai tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="20a9f-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="20a9f-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20a9f-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-127">Nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="20a9f-127">Display name.</span></span> <span data-ttu-id="20a9f-128">Usato solo dai tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="20a9f-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="20a9f-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20a9f-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-131">Nome società.</span><span class="sxs-lookup"><span data-stu-id="20a9f-131">Company name.</span></span> <span data-ttu-id="20a9f-132">Usato solo dai tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="20a9f-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="20a9f-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20a9f-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-135">Posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="20a9f-135">Email.</span></span> <span data-ttu-id="20a9f-136">Usato solo dai tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="20a9f-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="20a9f-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="20a9f-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-139">Nome di dominio dell'oggetto Active Directory in cui l'entità è una versione memorizzata nella cache.</span><span class="sxs-lookup"><span data-stu-id="20a9f-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="20a9f-140">Può essere null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="20a9f-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="20a9f-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="20a9f-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20a9f-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="20a9f-143">Nome dell'entità utente (UPN) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="20a9f-144">Usato solo dai normali tipi di utente.</span><span class="sxs-lookup"><span data-stu-id="20a9f-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="20a9f-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="20a9f-146">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="20a9f-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="20a9f-147">0: Principal è attivo.</span><span class="sxs-lookup"><span data-stu-id="20a9f-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="20a9f-148">1: Principal è disabilitato perché le funzionalità SIP dell'utente sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="20a9f-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="20a9f-149">2: Principal viene eliminato perché l'oggetto Active Directory associato è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="20a9f-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="20a9f-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-151">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="20a9f-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-152">Tipo di entità (dalla tabella tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="20a9f-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="20a9f-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-154">Int</span><span class="sxs-lookup"><span data-stu-id="20a9f-154">Int</span></span></p></td>
<td><p><span data-ttu-id="20a9f-155">Assegnazione Lync pool per l'entità.</span><span class="sxs-lookup"><span data-stu-id="20a9f-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="20a9f-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-157">Int</span><span class="sxs-lookup"><span data-stu-id="20a9f-157">Int</span></span></p></td>
<td><p><span data-ttu-id="20a9f-158">Valore dei criteri del server di chat persistente per l'utente, se è presente il criterio tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="20a9f-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="20a9f-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="20a9f-160">int</span><span class="sxs-lookup"><span data-stu-id="20a9f-160">int</span></span></p></td>
<td><p><span data-ttu-id="20a9f-161">ID principale del creatore.</span><span class="sxs-lookup"><span data-stu-id="20a9f-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="20a9f-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="20a9f-163">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="20a9f-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-164">Indicatore di data e ora per la creazione.</span><span class="sxs-lookup"><span data-stu-id="20a9f-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="20a9f-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="20a9f-166">int</span><span class="sxs-lookup"><span data-stu-id="20a9f-166">int</span></span></p></td>
<td><p><span data-ttu-id="20a9f-167">ID dell'oggetto Principal che ha aggiornato l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="20a9f-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="20a9f-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="20a9f-169">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="20a9f-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-170">Indicatore di data e ora per l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="20a9f-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="20a9f-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="20a9f-172">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="20a9f-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="20a9f-173">Data e ora dell'ultimo aggiornamento della sincronizzazione di Active Directory per l'entità.</span><span class="sxs-lookup"><span data-stu-id="20a9f-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="20a9f-174">Tasti</span><span class="sxs-lookup"><span data-stu-id="20a9f-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20a9f-175">Colonna</span><span class="sxs-lookup"><span data-stu-id="20a9f-175">Column</span></span></th>
<th><span data-ttu-id="20a9f-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20a9f-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20a9f-177">prinID</span><span class="sxs-lookup"><span data-stu-id="20a9f-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-178">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="20a9f-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20a9f-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="20a9f-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="20a9f-180">Chiave esterna con ricerca nella tabella tblPrincipalType. ptypeID.</span><span class="sxs-lookup"><span data-stu-id="20a9f-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

