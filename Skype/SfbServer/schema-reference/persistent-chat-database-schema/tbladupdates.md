---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814684"
---
# <a name="tbladupdates"></a><span data-ttu-id="30fd6-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="30fd6-103">tblADUpdates</span></span>
 
<span data-ttu-id="30fd6-104">tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.</span><span class="sxs-lookup"><span data-stu-id="30fd6-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="30fd6-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="30fd6-105">**Columns**</span></span>

|<span data-ttu-id="30fd6-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="30fd6-106">**Column**</span></span>|<span data-ttu-id="30fd6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="30fd6-107">**Type**</span></span>|<span data-ttu-id="30fd6-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="30fd6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30fd6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="30fd6-109">prinGuid</span></span>  <br/> |<span data-ttu-id="30fd6-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="30fd6-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="30fd6-111">GUID principale dell'oggetto modificato.</span><span class="sxs-lookup"><span data-stu-id="30fd6-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="30fd6-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="30fd6-112">prinADPath</span></span>  <br/> |<span data-ttu-id="30fd6-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="30fd6-114">Nome distinto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="30fd6-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="30fd6-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="30fd6-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="30fd6-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-116">bit, not null</span></span>  <br/> |<span data-ttu-id="30fd6-117">True se almeno un attributo dell'oggetto è cambiato.</span><span class="sxs-lookup"><span data-stu-id="30fd6-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="30fd6-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="30fd6-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="30fd6-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-119">bit, not null</span></span>  <br/> |<span data-ttu-id="30fd6-120">True se l'appartenenza è cambiata.</span><span class="sxs-lookup"><span data-stu-id="30fd6-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="30fd6-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="30fd6-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="30fd6-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-122">bit, not null</span></span>  <br/> |<span data-ttu-id="30fd6-123">Non usato.</span><span class="sxs-lookup"><span data-stu-id="30fd6-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="30fd6-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="30fd6-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="30fd6-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-125">bit, not null</span></span>  <br/> |<span data-ttu-id="30fd6-126">True se l'oggetto è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="30fd6-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="30fd6-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="30fd6-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="30fd6-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="30fd6-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="30fd6-129">Indicatore di data e ora di quando è stata inserita la riga.</span><span class="sxs-lookup"><span data-stu-id="30fd6-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

