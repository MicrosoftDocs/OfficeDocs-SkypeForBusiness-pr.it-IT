---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 23240588fae3895c7d4aa5b0ecbf642bd2db51a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="fd63d-102">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd63d-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd63d-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fd63d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fd63d-104">In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="fd63d-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="fd63d-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="fd63d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd63d-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="fd63d-106">Column</span></span></th>
<th><span data-ttu-id="fd63d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="fd63d-107">Type</span></span></th>
<th><span data-ttu-id="fd63d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd63d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="fd63d-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="fd63d-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="fd63d-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="fd63d-111">Token univoco (un GUID).</span><span class="sxs-lookup"><span data-stu-id="fd63d-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd63d-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="fd63d-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="fd63d-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="fd63d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd63d-114">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="fd63d-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fd63d-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="fd63d-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="fd63d-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="fd63d-117">GUID del nodo della chat.</span><span class="sxs-lookup"><span data-stu-id="fd63d-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd63d-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="fd63d-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="fd63d-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="fd63d-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fd63d-p101">Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="fd63d-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="fd63d-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="fd63d-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd63d-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd63d-124">URL del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="fd63d-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd63d-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="fd63d-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="fd63d-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fd63d-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fd63d-127">URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="fd63d-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="fd63d-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="fd63d-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="fd63d-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="fd63d-130">Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="fd63d-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd63d-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="fd63d-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="fd63d-132">po'</span><span class="sxs-lookup"><span data-stu-id="fd63d-132">bit</span></span></p></td>
<td><p><span data-ttu-id="fd63d-133">True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="fd63d-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="fd63d-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="fd63d-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="fd63d-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="fd63d-p102">True se il token è bloccato. Usato per mantenere il token nella tabella finché il servizio Conformità non ha l'opportunità di recuperare i campi pertinenti dal token stesso.</span><span class="sxs-lookup"><span data-stu-id="fd63d-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fd63d-138">Chiavi</span><span class="sxs-lookup"><span data-stu-id="fd63d-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd63d-139">Colonna</span><span class="sxs-lookup"><span data-stu-id="fd63d-139">Column</span></span></th>
<th><span data-ttu-id="fd63d-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd63d-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd63d-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="fd63d-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="fd63d-142">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="fd63d-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd63d-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="fd63d-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="fd63d-144">Chiave esterna con ricerca nella tabella tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="fd63d-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

