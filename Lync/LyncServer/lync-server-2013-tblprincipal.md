---
title: 'Lync Server 2013: tabella tblPrincipal'
description: 'Lync Server 2013: tabella tblPrincipal.'
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
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547492"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="f5c26-103">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5c26-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c26-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f5c26-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f5c26-105">La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="f5c26-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="f5c26-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="f5c26-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5c26-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="f5c26-107">Column</span></span></th>
<th><span data-ttu-id="f5c26-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="f5c26-108">Type</span></span></th>
<th><span data-ttu-id="f5c26-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5c26-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-110">prinID</span><span class="sxs-lookup"><span data-stu-id="f5c26-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="f5c26-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-112">ID entità.</span><span class="sxs-lookup"><span data-stu-id="f5c26-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f5c26-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f5c26-114">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="f5c26-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-115">GUID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="f5c26-115">Principal GUID.</span></span> <span data-ttu-id="f5c26-116">Questa operazione viene ampiamente utilizzata come chiave primaria alternativa, in quanto il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f5c26-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="f5c26-117">Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f5c26-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="f5c26-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="f5c26-119">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="f5c26-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p102">URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-122">prinname</span><span class="sxs-lookup"><span data-stu-id="f5c26-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="f5c26-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5c26-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p103">Nome comune. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="f5c26-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="f5c26-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5c26-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p104">Nome visualizzato. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="f5c26-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="f5c26-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5c26-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p105">Nome della società. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="f5c26-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="f5c26-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5c26-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p106">Posta elettronica. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f5c26-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="f5c26-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="f5c26-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p107">Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f5c26-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="f5c26-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f5c26-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="f5c26-p108">Nome dell'entità dell'utente. Valore utilizzato solo dai tipi utente normali.</span><span class="sxs-lookup"><span data-stu-id="f5c26-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="f5c26-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="f5c26-147">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="f5c26-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f5c26-148">0: Principale attivo.</span><span class="sxs-lookup"><span data-stu-id="f5c26-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="f5c26-149">1: Principale è disabilitato poiché le funzionalità SIP dell'utente sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="f5c26-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="f5c26-150">2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="f5c26-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f5c26-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-152">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="f5c26-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-153">Tipo di entità (dalla tabella PrincipalType).</span><span class="sxs-lookup"><span data-stu-id="f5c26-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="f5c26-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-155">Soglia</span><span class="sxs-lookup"><span data-stu-id="f5c26-155">Int</span></span></p></td>
<td><p><span data-ttu-id="f5c26-156">Assegnazione del pool Lync per l'entità.</span><span class="sxs-lookup"><span data-stu-id="f5c26-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="f5c26-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-158">Soglia</span><span class="sxs-lookup"><span data-stu-id="f5c26-158">Int</span></span></p></td>
<td><p><span data-ttu-id="f5c26-159">Valore dei criteri del server Chat persistente per l'utente, se è presente il criterio tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="f5c26-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="f5c26-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="f5c26-161">int</span><span class="sxs-lookup"><span data-stu-id="f5c26-161">int</span></span></p></td>
<td><p><span data-ttu-id="f5c26-162">ID entità del creatore.</span><span class="sxs-lookup"><span data-stu-id="f5c26-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="f5c26-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="f5c26-164">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f5c26-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-165">Indicatore di data e ora per il momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="f5c26-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f5c26-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f5c26-167">int</span><span class="sxs-lookup"><span data-stu-id="f5c26-167">int</span></span></p></td>
<td><p><span data-ttu-id="f5c26-168">ID dell'entità che ha eseguito l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f5c26-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="f5c26-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="f5c26-170">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f5c26-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-171">Indicatore di data e ora per l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f5c26-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="f5c26-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="f5c26-173">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="f5c26-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f5c26-174">Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.</span><span class="sxs-lookup"><span data-stu-id="f5c26-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f5c26-175">Chiavi</span><span class="sxs-lookup"><span data-stu-id="f5c26-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5c26-176">Colonna</span><span class="sxs-lookup"><span data-stu-id="f5c26-176">Column</span></span></th>
<th><span data-ttu-id="f5c26-177">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f5c26-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5c26-178">prinID</span><span class="sxs-lookup"><span data-stu-id="f5c26-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-179">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f5c26-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5c26-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="f5c26-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="f5c26-181">Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="f5c26-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

