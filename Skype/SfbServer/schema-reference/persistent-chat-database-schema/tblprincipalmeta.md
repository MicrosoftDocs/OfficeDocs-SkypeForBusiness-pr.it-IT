---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813574"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="3a2d4-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="3a2d4-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="3a2d4-104">tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="3a2d4-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-105">**Columns**</span></span>

|<span data-ttu-id="3a2d4-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-106">**Column**</span></span>|<span data-ttu-id="3a2d4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-107">**Type**</span></span>|<span data-ttu-id="3a2d4-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a2d4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3a2d4-109">prinID</span></span>  <br/> |<span data-ttu-id="3a2d4-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="3a2d4-110">int, not null</span></span>  <br/> |<span data-ttu-id="3a2d4-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="3a2d4-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="3a2d4-113">bit, not null</span><span class="sxs-lookup"><span data-stu-id="3a2d4-113">bit, not null</span></span>  <br/> |<span data-ttu-id="3a2d4-114">True se le affiliazioni principali devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="3a2d4-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="3a2d4-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="3a2d4-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3a2d4-117">True se gli attributi Principal devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3a2d4-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="3a2d4-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="3a2d4-119">bit, not null</span></span>  <br/> |<span data-ttu-id="3a2d4-120">True se l'entità è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="3a2d4-121">tryCount</span></span>  <br/> |<span data-ttu-id="3a2d4-122">int</span><span class="sxs-lookup"><span data-stu-id="3a2d4-122">int</span></span>  <br/> |<span data-ttu-id="3a2d4-123">Numero di tentativi di aggiornare l'oggetto Principal da servizi di dominio Active Directory che si sono verificati finora.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="3a2d4-124">lastTry</span></span>  <br/> |<span data-ttu-id="3a2d4-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="3a2d4-125">datetime</span></span>  <br/> |<span data-ttu-id="3a2d4-126">Indicatore di data e ora dal tentativo più recente di aggiornare l'entità.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="3a2d4-127">Può essere null se non è ancora stato tentato l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="3a2d4-128">nextTry</span></span>  <br/> |<span data-ttu-id="3a2d4-129">DateTime</span><span class="sxs-lookup"><span data-stu-id="3a2d4-129">datetime</span></span>  <br/> |<span data-ttu-id="3a2d4-130">Indicatore di data e ora per il successivo aggiornamento programmato.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="3a2d4-131">Può essere null se non è stato programmato un ulteriore aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="3a2d4-132">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-132">**Keys**</span></span>

|<span data-ttu-id="3a2d4-133">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-133">**Column**</span></span>|<span data-ttu-id="3a2d4-134">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3a2d4-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a2d4-135">prinID</span><span class="sxs-lookup"><span data-stu-id="3a2d4-135">prinID</span></span>  <br/> |<span data-ttu-id="3a2d4-136">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3a2d4-137">prinID</span><span class="sxs-lookup"><span data-stu-id="3a2d4-137">prinID</span></span>  <br/> |<span data-ttu-id="3a2d4-138">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="3a2d4-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

