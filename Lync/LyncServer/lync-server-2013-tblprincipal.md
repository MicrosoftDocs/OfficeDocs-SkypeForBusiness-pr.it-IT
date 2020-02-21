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
ms.openlocfilehash: bcf2defebaf557230118bf557800d06a862ed39d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="1d7e6-102">Tabella tblPrincipal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d7e6-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d7e6-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1d7e6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1d7e6-104">La tabella Principal contiene tutte le entità, inclusi gli utenti, le cartelle e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="1d7e6-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="1d7e6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7e6-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="1d7e6-106">Column</span></span></th>
<th><span data-ttu-id="1d7e6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d7e6-107">Type</span></span></th>
<th><span data-ttu-id="1d7e6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d7e6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="1d7e6-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-113">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-114">GUID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-114">Principal GUID.</span></span> <span data-ttu-id="1d7e6-115">Questa operazione viene ampiamente utilizzata come chiave primaria alternativa, in quanto il relativo significato viene attraversato nello spazio dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="1d7e6-116">Il GUID per un'entità memorizzata nella cache equivale al GUID oggetto Active Directory corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="1d7e6-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-118">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p102">URI dell'entità. Lo schema SIP viene utilizzato per gli utenti, mentre ma-grp viene utilizzato per quasi tutte le altre entità.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-121">prinname</span><span class="sxs-lookup"><span data-stu-id="1d7e6-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p103">Nome comune. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="1d7e6-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p104">Nome visualizzato. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="1d7e6-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p105">Nome della società. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="1d7e6-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p106">Posta elettronica. Valore utilizzato solo dai tipi utente.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="1d7e6-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p107">Nome di dominio dell'oggetto Active Directory di cui l'entità è una versione memorizzata nella cache. Può essere Null per i tipi che non sono oggetti Active Directory, ad esempio gli utenti di sistema.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="1d7e6-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1d7e6-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-p108">Nome dell'entità dell'utente. Valore utilizzato solo dai tipi utente normali.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="1d7e6-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-146">smallint, non null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="1d7e6-147">0: Principale attivo.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="1d7e6-148">1: Principale è disabilitato poiché le funzionalità SIP dell'utente sono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="1d7e6-149">2: Principale è eliminato poiché l'oggetto AD associato è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-151">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-152">Tipo di entità (dalla tabella PrincipalType).</span><span class="sxs-lookup"><span data-stu-id="1d7e6-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-154">Soglia</span><span class="sxs-lookup"><span data-stu-id="1d7e6-154">Int</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-155">Assegnazione del pool Lync per l'entità.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-157">Soglia</span><span class="sxs-lookup"><span data-stu-id="1d7e6-157">Int</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-158">Valore dei criteri del server Chat persistente per l'utente, se è presente il criterio tipo di tag.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="1d7e6-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-160">int</span><span class="sxs-lookup"><span data-stu-id="1d7e6-160">int</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-161">ID entità del creatore.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="1d7e6-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-163">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-164">Indicatore di data e ora per il momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1d7e6-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-166">int</span><span class="sxs-lookup"><span data-stu-id="1d7e6-166">int</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-167">ID dell'entità che ha eseguito l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="1d7e6-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-169">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-170">Indicatore di data e ora per l'ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="1d7e6-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-172">datetime, non null</span><span class="sxs-lookup"><span data-stu-id="1d7e6-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-173">Data e ora dell'ultimo aggiornamento di Sincronizzazione Active Directory per l'entità.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="1d7e6-174">Chiavi</span><span class="sxs-lookup"><span data-stu-id="1d7e6-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7e6-175">Colonna</span><span class="sxs-lookup"><span data-stu-id="1d7e6-175">Column</span></span></th>
<th><span data-ttu-id="1d7e6-176">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d7e6-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7e6-177">prinID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-178">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7e6-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="1d7e6-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="1d7e6-180">Chiave esterna con ricerca nella tabella PrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="1d7e6-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

