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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194700"
---
# <a name="tbladupdates"></a><span data-ttu-id="88982-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="88982-103">tblADUpdates</span></span>
 
<span data-ttu-id="88982-104">tblADUpdates contiene le modifiche dei servizi di dominio Active Directory che non sono state ancora elaborate dalla procedura di sincronizzazione di Active Directory successiva.</span><span class="sxs-lookup"><span data-stu-id="88982-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="88982-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="88982-105">**Columns**</span></span>

|<span data-ttu-id="88982-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="88982-106">**Column**</span></span>|<span data-ttu-id="88982-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="88982-107">**Type**</span></span>|<span data-ttu-id="88982-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="88982-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88982-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="88982-109">prinGuid</span></span>  <br/> |<span data-ttu-id="88982-110">GUID, non null</span><span class="sxs-lookup"><span data-stu-id="88982-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="88982-111">GUID principale dell'oggetto modificato.</span><span class="sxs-lookup"><span data-stu-id="88982-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="88982-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="88982-112">prinADPath</span></span>  <br/> |<span data-ttu-id="88982-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="88982-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="88982-114">Nome distinto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="88982-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="88982-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="88982-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="88982-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="88982-116">bit, not null</span></span>  <br/> |<span data-ttu-id="88982-117">True se almeno un attributo dell'oggetto è cambiato.</span><span class="sxs-lookup"><span data-stu-id="88982-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="88982-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="88982-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="88982-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="88982-119">bit, not null</span></span>  <br/> |<span data-ttu-id="88982-120">True se l'appartenenza è cambiata.</span><span class="sxs-lookup"><span data-stu-id="88982-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="88982-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="88982-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="88982-122">bit, not null</span><span class="sxs-lookup"><span data-stu-id="88982-122">bit, not null</span></span>  <br/> |<span data-ttu-id="88982-123">Non usato.</span><span class="sxs-lookup"><span data-stu-id="88982-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="88982-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="88982-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="88982-125">bit, not null</span><span class="sxs-lookup"><span data-stu-id="88982-125">bit, not null</span></span>  <br/> |<span data-ttu-id="88982-126">True se l'oggetto è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="88982-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="88982-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="88982-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="88982-128">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="88982-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="88982-129">Indicatore di data e ora di quando è stata inserita la riga.</span><span class="sxs-lookup"><span data-stu-id="88982-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

