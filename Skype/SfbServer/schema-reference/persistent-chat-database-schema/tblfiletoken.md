---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contiene token temporanei per scopi di trasferimento di file.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814594"
---
# <a name="tblfiletoken"></a><span data-ttu-id="6cece-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="6cece-103">tblFileToken</span></span>
 
<span data-ttu-id="6cece-104">tblFileToken contiene token temporanei per scopi di trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="6cece-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="6cece-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6cece-105">**Columns**</span></span>

|<span data-ttu-id="6cece-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6cece-106">**Column**</span></span>|<span data-ttu-id="6cece-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6cece-107">**Type**</span></span>|<span data-ttu-id="6cece-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6cece-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6cece-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="6cece-109">fileToken</span></span>  <br/> |<span data-ttu-id="6cece-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="6cece-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="6cece-111">Token univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="6cece-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="6cece-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="6cece-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="6cece-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="6cece-113">int, not null</span></span>  <br/> |<span data-ttu-id="6cece-114">ID dell'entità che sta trasferendo il file.</span><span class="sxs-lookup"><span data-stu-id="6cece-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="6cece-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="6cece-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="6cece-116">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="6cece-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="6cece-117">GUID del nodo della chat room.</span><span class="sxs-lookup"><span data-stu-id="6cece-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="6cece-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="6cece-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="6cece-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="6cece-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="6cece-120">Data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="6cece-120">Expiration time.</span></span> <span data-ttu-id="6cece-121">I token scadono dopo 30 minuti, a meno che non siano stati aggiunti (Vedi le descrizioni seguenti in questa colonna).</span><span class="sxs-lookup"><span data-stu-id="6cece-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="6cece-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="6cece-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="6cece-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6cece-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6cece-124">URL del file trasferito (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="6cece-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="6cece-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="6cece-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="6cece-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6cece-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6cece-127">URL dell'anteprima del file trasferito (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="6cece-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="6cece-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="6cece-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="6cece-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="6cece-129">datetime2</span></span>  <br/> |<span data-ttu-id="6cece-130">Timestamp per l'effettiva operazione di trasferimento file (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="6cece-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="6cece-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="6cece-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="6cece-132">po'</span><span class="sxs-lookup"><span data-stu-id="6cece-132">bit</span></span>  <br/> |<span data-ttu-id="6cece-133">True se upload; False se il download (per l'uso del servizio di conformità).</span><span class="sxs-lookup"><span data-stu-id="6cece-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="6cece-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="6cece-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="6cece-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="6cece-135">bit, not null</span></span>  <br/> |<span data-ttu-id="6cece-136">True se il token è bloccato.</span><span class="sxs-lookup"><span data-stu-id="6cece-136">True if token is pinned.</span></span> <span data-ttu-id="6cece-137">Viene usato per conservare il token nella tabella finché il servizio di conformità non ha la possibilità di recuperare i campi rilevanti.</span><span class="sxs-lookup"><span data-stu-id="6cece-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="6cece-138">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="6cece-138">**Keys**</span></span>

|<span data-ttu-id="6cece-139">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6cece-139">**Column**</span></span>|<span data-ttu-id="6cece-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6cece-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6cece-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="6cece-141">fileToken</span></span>  <br/> |<span data-ttu-id="6cece-142">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="6cece-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6cece-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="6cece-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="6cece-144">Chiave esterna con ricerca nella tabella tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="6cece-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

