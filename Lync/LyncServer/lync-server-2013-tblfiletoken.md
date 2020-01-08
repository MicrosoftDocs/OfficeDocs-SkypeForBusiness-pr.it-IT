---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="15715-102">tblFileToken in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15715-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15715-103">_**Argomento Ultima modifica:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="15715-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="15715-104">tblFileToken contiene token temporanei per scopi di trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="15715-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="15715-105">Colonne</span><span class="sxs-lookup"><span data-stu-id="15715-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15715-106">Colonna</span><span class="sxs-lookup"><span data-stu-id="15715-106">Column</span></span></th>
<th><span data-ttu-id="15715-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="15715-107">Type</span></span></th>
<th><span data-ttu-id="15715-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15715-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15715-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="15715-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="15715-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="15715-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="15715-111">Token univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="15715-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15715-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="15715-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="15715-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="15715-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="15715-114">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="15715-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15715-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="15715-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="15715-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="15715-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="15715-117">GUID del nodo della chat room.</span><span class="sxs-lookup"><span data-stu-id="15715-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15715-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="15715-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="15715-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="15715-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="15715-120">Data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="15715-120">Expiration time.</span></span> <span data-ttu-id="15715-121">I token scadono dopo 30 minuti, a meno che non siano stati aggiunti (Vedi le descrizioni seguenti in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="15715-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15715-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="15715-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="15715-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15715-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15715-124">URL del file trasferito (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="15715-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15715-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="15715-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="15715-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="15715-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="15715-127">URL dell'anteprima del file trasferito (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="15715-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15715-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="15715-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="15715-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="15715-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="15715-130">Timestamp per l'effettiva operazione di trasferimento file (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="15715-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15715-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="15715-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="15715-132">po'</span><span class="sxs-lookup"><span data-stu-id="15715-132">bit</span></span></p></td>
<td><p><span data-ttu-id="15715-133">True se upload; False se il download (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="15715-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15715-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="15715-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="15715-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="15715-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="15715-136">True se il token è bloccato.</span><span class="sxs-lookup"><span data-stu-id="15715-136">True if token is pinned.</span></span> <span data-ttu-id="15715-137">Viene usato per conservare il token nella tabella finché il servizio di conformità non ha la possibilità di recuperare i campi rilevanti.</span><span class="sxs-lookup"><span data-stu-id="15715-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="15715-138">Tasti</span><span class="sxs-lookup"><span data-stu-id="15715-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15715-139">Colonna</span><span class="sxs-lookup"><span data-stu-id="15715-139">Column</span></span></th>
<th><span data-ttu-id="15715-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15715-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15715-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="15715-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="15715-142">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="15715-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15715-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="15715-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="15715-144">Chiave esterna con ricerca nella tabella tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="15715-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

