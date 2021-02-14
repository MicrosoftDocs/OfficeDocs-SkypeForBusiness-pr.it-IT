---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816016"
---
# <a name="tblfiletoken"></a><span data-ttu-id="4282e-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="4282e-103">tblFileToken</span></span>
 
<span data-ttu-id="4282e-104">In tblFileToken sono inclusi i token temporanei ai fini del trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="4282e-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="4282e-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4282e-105">**Columns**</span></span>

|<span data-ttu-id="4282e-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4282e-106">**Column**</span></span>|<span data-ttu-id="4282e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4282e-107">**Type**</span></span>|<span data-ttu-id="4282e-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4282e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4282e-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="4282e-109">fileToken</span></span>  <br/> |<span data-ttu-id="4282e-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="4282e-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="4282e-111">Token univoco (un GUID).</span><span class="sxs-lookup"><span data-stu-id="4282e-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="4282e-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="4282e-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="4282e-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="4282e-113">int, not null</span></span>  <br/> |<span data-ttu-id="4282e-114">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="4282e-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="4282e-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="4282e-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="4282e-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="4282e-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="4282e-117">GUID del nodo della chat.</span><span class="sxs-lookup"><span data-stu-id="4282e-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="4282e-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="4282e-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="4282e-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="4282e-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="4282e-p101">Ora di scadenza. I token scadono dopo 30 minuti, se non sono stati bloccati (vedere le descrizioni che seguono in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="4282e-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="4282e-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="4282e-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="4282e-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4282e-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4282e-124">URL del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4282e-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4282e-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="4282e-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="4282e-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4282e-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4282e-127">URL dell'anteprima del file trasferito (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4282e-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4282e-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="4282e-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="4282e-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="4282e-129">datetime2</span></span>  <br/> |<span data-ttu-id="4282e-130">Timestamp dell'effettiva operazione di trasferimento del file (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4282e-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4282e-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="4282e-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="4282e-132">bit</span><span class="sxs-lookup"><span data-stu-id="4282e-132">bit</span></span>  <br/> |<span data-ttu-id="4282e-133">True se si tratta di un caricamento, False se si tratta di un download (per l'uso con il servizio Conformità).</span><span class="sxs-lookup"><span data-stu-id="4282e-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="4282e-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="4282e-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="4282e-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="4282e-135">bit, not null</span></span>  <br/> |<span data-ttu-id="4282e-136">True se il token è bloccato.</span><span class="sxs-lookup"><span data-stu-id="4282e-136">True if token is pinned.</span></span> <span data-ttu-id="4282e-137">Viene usato per mantenere il token nella tabella fino a quando il servizio di conformità non ha la possibilità di recuperare i campi rilevanti da essa.</span><span class="sxs-lookup"><span data-stu-id="4282e-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="4282e-138">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="4282e-138">**Keys**</span></span>

|<span data-ttu-id="4282e-139">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4282e-139">**Column**</span></span>|<span data-ttu-id="4282e-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4282e-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4282e-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="4282e-141">fileToken</span></span>  <br/> |<span data-ttu-id="4282e-142">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="4282e-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4282e-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="4282e-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="4282e-144">Chiave esterna con ricerca nella tabella tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="4282e-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

