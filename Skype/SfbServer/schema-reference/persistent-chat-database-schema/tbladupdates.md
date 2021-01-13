---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821386"
---
# <a name="tbladupdates"></a><span data-ttu-id="21b20-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="21b20-103">tblADUpdates</span></span>
 
<span data-ttu-id="21b20-104">tblADUpdates contiene le modifiche ai servizi di dominio Active Directory che non sono state ancora elaborate dai successivi passaggi di sincronizzazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="21b20-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="21b20-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="21b20-105">**Columns**</span></span>

|<span data-ttu-id="21b20-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="21b20-106">**Column**</span></span>|<span data-ttu-id="21b20-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="21b20-107">**Type**</span></span>|<span data-ttu-id="21b20-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="21b20-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="21b20-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="21b20-109">prinGuid</span></span>  <br/> |<span data-ttu-id="21b20-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="21b20-111">GUID di entità dell'oggetto modificato.</span><span class="sxs-lookup"><span data-stu-id="21b20-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="21b20-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="21b20-112">prinADPath</span></span>  <br/> |<span data-ttu-id="21b20-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="21b20-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="21b20-114">Nome distinto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="21b20-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="21b20-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="21b20-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="21b20-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-116">bit, not null</span></span>  <br/> |<span data-ttu-id="21b20-117">True se viene modificato almeno un attributo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="21b20-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="21b20-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="21b20-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="21b20-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-119">bit, not null</span></span>  <br/> |<span data-ttu-id="21b20-120">True se l'appartenenza è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="21b20-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="21b20-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="21b20-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="21b20-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-122">bit, not null</span></span>  <br/> |<span data-ttu-id="21b20-123">Non utilizzata.</span><span class="sxs-lookup"><span data-stu-id="21b20-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="21b20-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="21b20-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="21b20-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-125">bit, not null</span></span>  <br/> |<span data-ttu-id="21b20-126">True se l'oggetto è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="21b20-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="21b20-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="21b20-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="21b20-128">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="21b20-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="21b20-129">Timestamp dell'inserimento della riga.</span><span class="sxs-lookup"><span data-stu-id="21b20-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

