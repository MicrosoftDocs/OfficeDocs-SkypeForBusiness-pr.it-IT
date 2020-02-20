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
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="57cfb-102">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57cfb-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57cfb-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="57cfb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="57cfb-104">La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="57cfb-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="57cfb-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="57cfb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57cfb-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="57cfb-106">Column</span></span></th>
<th><span data-ttu-id="57cfb-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="57cfb-107">Type</span></span></th>
<th><span data-ttu-id="57cfb-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57cfb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="57cfb-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="57cfb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="57cfb-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="57cfb-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="57cfb-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="57cfb-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-114">GUID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="57cfb-114">Principal GUID.</span></span> <span data-ttu-id="57cfb-115">Questa operazione viene ampiamente utilizzata come chiave primaria alternativa, in quanto il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57cfb-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="57cfb-116">Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.</span><span class="sxs-lookup"><span data-stu-id="57cfb-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="57cfb-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="57cfb-118">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="57cfb-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p102">URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-121">prinname</span><span class="sxs-lookup"><span data-stu-id="57cfb-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="57cfb-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57cfb-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p103">Nome comune. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="57cfb-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="57cfb-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57cfb-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p104">Nome visualizzato. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="57cfb-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="57cfb-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57cfb-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p105">Nome della società. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="57cfb-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="57cfb-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57cfb-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p106">Posta elettronica. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="57cfb-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="57cfb-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="57cfb-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p107">Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="57cfb-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="57cfb-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="57cfb-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="57cfb-p108">Nome dell'entità dell'utente. Valore utilizzato solo dai tipi utente normali.</span><span class="sxs-lookup"><span data-stu-id="57cfb-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="57cfb-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="57cfb-146">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="57cfb-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="57cfb-147">0: Principale attivo.</span><span class="sxs-lookup"><span data-stu-id="57cfb-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="57cfb-148">1: Principale è disabilitato poiché le funzionalità SIP dell'utente sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="57cfb-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="57cfb-149">2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="57cfb-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="57cfb-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-151">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="57cfb-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-152">Tipo di entità (dalla tabella PrincipalType).</span><span class="sxs-lookup"><span data-stu-id="57cfb-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="57cfb-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="57cfb-154">Int</span></span></p></td>
<td><p><span data-ttu-id="57cfb-155">Assegnazione del pool Lync per l'entità.</span><span class="sxs-lookup"><span data-stu-id="57cfb-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="57cfb-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-157">Soglia</span><span class="sxs-lookup"><span data-stu-id="57cfb-157">Int</span></span></p></td>
<td><p><span data-ttu-id="57cfb-158">Valore dei criteri del server Chat persistente per l'utente, se è presente il criterio tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="57cfb-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="57cfb-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="57cfb-160">int</span><span class="sxs-lookup"><span data-stu-id="57cfb-160">int</span></span></p></td>
<td><p><span data-ttu-id="57cfb-161">ID entità del creatore.</span><span class="sxs-lookup"><span data-stu-id="57cfb-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="57cfb-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="57cfb-163">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="57cfb-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-164">Indicatore di data e ora per il momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="57cfb-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="57cfb-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="57cfb-166">int</span><span class="sxs-lookup"><span data-stu-id="57cfb-166">int</span></span></p></td>
<td><p><span data-ttu-id="57cfb-167">ID dell'entità che ha eseguito l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="57cfb-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="57cfb-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="57cfb-169">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="57cfb-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-170">Indicatore di data e ora per l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="57cfb-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="57cfb-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="57cfb-172">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="57cfb-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="57cfb-173">Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.</span><span class="sxs-lookup"><span data-stu-id="57cfb-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="57cfb-174">Chiavi</span><span class="sxs-lookup"><span data-stu-id="57cfb-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57cfb-175">Colonna</span><span class="sxs-lookup"><span data-stu-id="57cfb-175">Column</span></span></th>
<th><span data-ttu-id="57cfb-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57cfb-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57cfb-177">prinID</span><span class="sxs-lookup"><span data-stu-id="57cfb-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-178">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="57cfb-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57cfb-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="57cfb-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="57cfb-180">Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="57cfb-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

