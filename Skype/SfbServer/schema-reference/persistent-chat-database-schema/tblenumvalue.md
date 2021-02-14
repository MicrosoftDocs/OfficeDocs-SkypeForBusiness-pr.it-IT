---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816026"
---
# <a name="tblenumvalue"></a><span data-ttu-id="b9294-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="b9294-103">tblEnumValue</span></span>
 
<span data-ttu-id="b9294-104">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="b9294-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b9294-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b9294-105">**Columns**</span></span>

|<span data-ttu-id="b9294-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9294-106">**Column**</span></span>|<span data-ttu-id="b9294-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b9294-107">**Type**</span></span>|<span data-ttu-id="b9294-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b9294-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9294-109">valueID</span><span class="sxs-lookup"><span data-stu-id="b9294-109">valueID</span></span>  <br/> |<span data-ttu-id="b9294-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b9294-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b9294-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="b9294-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="b9294-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="b9294-112">attributeID</span></span>  <br/> |<span data-ttu-id="b9294-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b9294-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="b9294-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="b9294-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b9294-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="b9294-115">attributeValue</span></span>  <br/> |<span data-ttu-id="b9294-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b9294-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b9294-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="b9294-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="b9294-118">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="b9294-118">**Keys**</span></span>

|<span data-ttu-id="b9294-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9294-119">**Column**</span></span>|<span data-ttu-id="b9294-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b9294-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9294-121">valueID</span><span class="sxs-lookup"><span data-stu-id="b9294-121">valueID</span></span>  <br/> |<span data-ttu-id="b9294-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b9294-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b9294-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="b9294-123">attributeID</span></span>  <br/> |<span data-ttu-id="b9294-124">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="b9294-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="b9294-125">**Valori della tabella**</span><span class="sxs-lookup"><span data-stu-id="b9294-125">**Table Values**</span></span>

|<span data-ttu-id="b9294-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="b9294-126">**valueID**</span></span>|<span data-ttu-id="b9294-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b9294-127">**attributeID**</span></span>|<span data-ttu-id="b9294-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="b9294-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9294-129">2 </span><span class="sxs-lookup"><span data-stu-id="b9294-129">2</span></span>  <br/> |<span data-ttu-id="b9294-130">1 </span><span class="sxs-lookup"><span data-stu-id="b9294-130">1</span></span>  <br/> |<span data-ttu-id="b9294-131">private</span><span class="sxs-lookup"><span data-stu-id="b9294-131">private</span></span>  <br/> |
|<span data-ttu-id="b9294-132">3 </span><span class="sxs-lookup"><span data-stu-id="b9294-132">3</span></span>  <br/> |<span data-ttu-id="b9294-133">1 </span><span class="sxs-lookup"><span data-stu-id="b9294-133">1</span></span>  <br/> |<span data-ttu-id="b9294-134">ambito</span><span class="sxs-lookup"><span data-stu-id="b9294-134">scope</span></span>  <br/> |
|<span data-ttu-id="b9294-135">4 </span><span class="sxs-lookup"><span data-stu-id="b9294-135">4</span></span>  <br/> |<span data-ttu-id="b9294-136">2 </span><span class="sxs-lookup"><span data-stu-id="b9294-136">2</span></span>  <br/> |<span data-ttu-id="b9294-137">normal</span><span class="sxs-lookup"><span data-stu-id="b9294-137">normal</span></span>  <br/> |
|<span data-ttu-id="b9294-138">5 </span><span class="sxs-lookup"><span data-stu-id="b9294-138">5</span></span>  <br/> |<span data-ttu-id="b9294-139">2 </span><span class="sxs-lookup"><span data-stu-id="b9294-139">2</span></span>  <br/> |<span data-ttu-id="b9294-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="b9294-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="b9294-141">6 </span><span class="sxs-lookup"><span data-stu-id="b9294-141">6</span></span>  <br/> |<span data-ttu-id="b9294-142">1 </span><span class="sxs-lookup"><span data-stu-id="b9294-142">1</span></span>  <br/> |<span data-ttu-id="b9294-143">open</span><span class="sxs-lookup"><span data-stu-id="b9294-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b9294-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9294-144">See also</span></span>

[<span data-ttu-id="b9294-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="b9294-145">tblNode</span></span>](tblnode.md)
