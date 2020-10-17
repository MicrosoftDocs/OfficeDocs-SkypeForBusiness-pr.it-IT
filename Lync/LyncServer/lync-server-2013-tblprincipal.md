---
title: 'Lync Server 2013: tabella tblPrincipal'
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
ms.openlocfilehash: 5e4b0c8154429fa68bc05e757130e0b92a47e65c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523763"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="7d65b-102">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d65b-102">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d65b-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7d65b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7d65b-104">La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="7d65b-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="7d65b-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="7d65b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d65b-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="7d65b-106">Column</span></span></th>
<th><span data-ttu-id="7d65b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="7d65b-107">Type</span></span></th>
<th><span data-ttu-id="7d65b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d65b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7d65b-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="7d65b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="7d65b-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7d65b-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="7d65b-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="7d65b-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-114">GUID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="7d65b-114">Principal GUID.</span></span> <span data-ttu-id="7d65b-115">Questa operazione viene ampiamente utilizzata come chiave primaria alternativa, in quanto il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d65b-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="7d65b-116">Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7d65b-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="7d65b-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="7d65b-118">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="7d65b-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p102">URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-121">prinname</span><span class="sxs-lookup"><span data-stu-id="7d65b-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="7d65b-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d65b-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p103">Nome comune. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="7d65b-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="7d65b-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d65b-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p104">Nome visualizzato. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="7d65b-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="7d65b-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d65b-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p105">Nome della società. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="7d65b-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="7d65b-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d65b-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p106">Posta elettronica. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="7d65b-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="7d65b-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="7d65b-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p107">Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7d65b-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="7d65b-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7d65b-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="7d65b-p108">Nome dell'entità dell'utente. Valore utilizzato solo dai tipi utente normali.</span><span class="sxs-lookup"><span data-stu-id="7d65b-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="7d65b-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="7d65b-146">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="7d65b-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7d65b-147">0: Principale attivo.</span><span class="sxs-lookup"><span data-stu-id="7d65b-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="7d65b-148">1: Principale è disabilitato poiché le funzionalità SIP dell'utente sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="7d65b-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="7d65b-149">2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="7d65b-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="7d65b-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-151">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="7d65b-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-152">Tipo di entità (dalla tabella PrincipalType).</span><span class="sxs-lookup"><span data-stu-id="7d65b-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="7d65b-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="7d65b-154">Int</span></span></p></td>
<td><p><span data-ttu-id="7d65b-155">Assegnazione del pool Lync per l'entità.</span><span class="sxs-lookup"><span data-stu-id="7d65b-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="7d65b-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-157">Soglia</span><span class="sxs-lookup"><span data-stu-id="7d65b-157">Int</span></span></p></td>
<td><p><span data-ttu-id="7d65b-158">Valore dei criteri del server Chat persistente per l'utente, se è presente il criterio tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="7d65b-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="7d65b-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="7d65b-160">int</span><span class="sxs-lookup"><span data-stu-id="7d65b-160">int</span></span></p></td>
<td><p><span data-ttu-id="7d65b-161">ID entità del creatore.</span><span class="sxs-lookup"><span data-stu-id="7d65b-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="7d65b-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="7d65b-163">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="7d65b-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-164">Indicatore di data e ora per il momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="7d65b-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="7d65b-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="7d65b-166">int</span><span class="sxs-lookup"><span data-stu-id="7d65b-166">int</span></span></p></td>
<td><p><span data-ttu-id="7d65b-167">ID dell'entità che ha eseguito l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7d65b-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="7d65b-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="7d65b-169">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="7d65b-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-170">Indicatore di data e ora per l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7d65b-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="7d65b-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="7d65b-172">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="7d65b-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="7d65b-173">Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.</span><span class="sxs-lookup"><span data-stu-id="7d65b-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7d65b-174">Chiavi</span><span class="sxs-lookup"><span data-stu-id="7d65b-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d65b-175">Colonna</span><span class="sxs-lookup"><span data-stu-id="7d65b-175">Column</span></span></th>
<th><span data-ttu-id="7d65b-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d65b-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d65b-177">prinID</span><span class="sxs-lookup"><span data-stu-id="7d65b-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-178">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="7d65b-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d65b-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="7d65b-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="7d65b-180">Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="7d65b-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

