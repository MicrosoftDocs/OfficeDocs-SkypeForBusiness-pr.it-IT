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
ms.openlocfilehash: 47531c91ec7fed7e758bd73285f4e995afa65941
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509333"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="9656f-102">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9656f-102">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9656f-103">_**Ultimo argomento modificato:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9656f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9656f-104">In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="9656f-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="9656f-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="9656f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9656f-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="9656f-106">Column</span></span></th>
<th><span data-ttu-id="9656f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9656f-107">Type</span></span></th>
<th><span data-ttu-id="9656f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9656f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9656f-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="9656f-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="9656f-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="9656f-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="9656f-111">Token univoco (un GUID).</span><span class="sxs-lookup"><span data-stu-id="9656f-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9656f-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="9656f-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="9656f-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="9656f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9656f-114">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="9656f-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9656f-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="9656f-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="9656f-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="9656f-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9656f-117">GUID del nodo della chat.</span><span class="sxs-lookup"><span data-stu-id="9656f-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9656f-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="9656f-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="9656f-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="9656f-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="9656f-p101">Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="9656f-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9656f-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="9656f-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="9656f-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9656f-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9656f-124">URL del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="9656f-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9656f-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="9656f-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="9656f-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9656f-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9656f-127">URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="9656f-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9656f-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="9656f-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="9656f-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="9656f-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="9656f-130">Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="9656f-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9656f-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="9656f-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="9656f-132">po'</span><span class="sxs-lookup"><span data-stu-id="9656f-132">bit</span></span></p></td>
<td><p><span data-ttu-id="9656f-133">True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="9656f-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9656f-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="9656f-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="9656f-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9656f-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9656f-p102">True se il token è bloccato. Usato per mantenere il token nella tabella finché il servizio Conformità non ha l'opportunità di recuperare i campi pertinenti dal token stesso.</span><span class="sxs-lookup"><span data-stu-id="9656f-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9656f-138">Chiavi</span><span class="sxs-lookup"><span data-stu-id="9656f-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9656f-139">Colonna</span><span class="sxs-lookup"><span data-stu-id="9656f-139">Column</span></span></th>
<th><span data-ttu-id="9656f-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9656f-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9656f-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="9656f-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="9656f-142">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9656f-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9656f-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="9656f-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="9656f-144">Chiave esterna con ricerca nella tabella tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="9656f-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

