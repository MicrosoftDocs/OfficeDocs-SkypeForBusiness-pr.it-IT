---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547632"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="4920c-103">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4920c-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4920c-104">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4920c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4920c-105">In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="4920c-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="4920c-106">Colonne</span><span class="sxs-lookup"><span data-stu-id="4920c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4920c-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="4920c-107">Column</span></span></th>
<th><span data-ttu-id="4920c-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="4920c-108">Type</span></span></th>
<th><span data-ttu-id="4920c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4920c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4920c-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="4920c-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="4920c-111">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="4920c-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="4920c-112">Token univoco (un GUID).</span><span class="sxs-lookup"><span data-stu-id="4920c-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4920c-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="4920c-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="4920c-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="4920c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4920c-115">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="4920c-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4920c-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="4920c-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="4920c-117">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="4920c-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="4920c-118">GUID del nodo della chat.</span><span class="sxs-lookup"><span data-stu-id="4920c-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4920c-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="4920c-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="4920c-120">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="4920c-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4920c-p101">Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="4920c-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4920c-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="4920c-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="4920c-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4920c-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4920c-125">URL del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4920c-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4920c-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="4920c-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="4920c-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4920c-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4920c-128">URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4920c-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4920c-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="4920c-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="4920c-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="4920c-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="4920c-131">Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4920c-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4920c-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="4920c-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="4920c-133">po'</span><span class="sxs-lookup"><span data-stu-id="4920c-133">bit</span></span></p></td>
<td><p><span data-ttu-id="4920c-134">True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4920c-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4920c-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="4920c-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="4920c-136">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4920c-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4920c-p102">True se il token è bloccato. Usato per mantenere il token nella tabella finché il servizio Conformità non ha l'opportunità di recuperare i campi pertinenti dal token stesso.</span><span class="sxs-lookup"><span data-stu-id="4920c-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4920c-139">Chiavi</span><span class="sxs-lookup"><span data-stu-id="4920c-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4920c-140">Colonna</span><span class="sxs-lookup"><span data-stu-id="4920c-140">Column</span></span></th>
<th><span data-ttu-id="4920c-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4920c-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4920c-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="4920c-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="4920c-143">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="4920c-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4920c-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="4920c-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="4920c-145">Chiave esterna con ricerca nella tabella tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="4920c-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

