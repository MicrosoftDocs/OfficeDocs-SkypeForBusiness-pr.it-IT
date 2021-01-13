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
# <a name="tblenumvalue"></a><span data-ttu-id="14c19-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="14c19-103">tblEnumValue</span></span>
 
<span data-ttu-id="14c19-104">tblEnumValue è una tabella hardcoded contenente i valori Visibility e Behavior degli attributi utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="14c19-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="14c19-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="14c19-105">**Columns**</span></span>

|<span data-ttu-id="14c19-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="14c19-106">**Column**</span></span>|<span data-ttu-id="14c19-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="14c19-107">**Type**</span></span>|<span data-ttu-id="14c19-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14c19-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14c19-109">valueID</span><span class="sxs-lookup"><span data-stu-id="14c19-109">valueID</span></span>  <br/> |<span data-ttu-id="14c19-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="14c19-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="14c19-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="14c19-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="14c19-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="14c19-112">attributeID</span></span>  <br/> |<span data-ttu-id="14c19-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="14c19-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="14c19-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="14c19-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="14c19-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="14c19-115">attributeValue</span></span>  <br/> |<span data-ttu-id="14c19-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="14c19-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="14c19-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="14c19-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="14c19-118">**Chiavi**</span><span class="sxs-lookup"><span data-stu-id="14c19-118">**Keys**</span></span>

|<span data-ttu-id="14c19-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="14c19-119">**Column**</span></span>|<span data-ttu-id="14c19-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="14c19-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14c19-121">valueID</span><span class="sxs-lookup"><span data-stu-id="14c19-121">valueID</span></span>  <br/> |<span data-ttu-id="14c19-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="14c19-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="14c19-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="14c19-123">attributeID</span></span>  <br/> |<span data-ttu-id="14c19-124">Chiave esterna con ricerca nella tabella tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="14c19-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="14c19-125">**Valori della tabella**</span><span class="sxs-lookup"><span data-stu-id="14c19-125">**Table Values**</span></span>

|<span data-ttu-id="14c19-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="14c19-126">**valueID**</span></span>|<span data-ttu-id="14c19-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="14c19-127">**attributeID**</span></span>|<span data-ttu-id="14c19-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="14c19-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14c19-129">2 </span><span class="sxs-lookup"><span data-stu-id="14c19-129">2</span></span>  <br/> |<span data-ttu-id="14c19-130">1 </span><span class="sxs-lookup"><span data-stu-id="14c19-130">1</span></span>  <br/> |<span data-ttu-id="14c19-131">privata</span><span class="sxs-lookup"><span data-stu-id="14c19-131">private</span></span>  <br/> |
|<span data-ttu-id="14c19-132">3 </span><span class="sxs-lookup"><span data-stu-id="14c19-132">3</span></span>  <br/> |<span data-ttu-id="14c19-133">1 </span><span class="sxs-lookup"><span data-stu-id="14c19-133">1</span></span>  <br/> |<span data-ttu-id="14c19-134">ambito</span><span class="sxs-lookup"><span data-stu-id="14c19-134">scope</span></span>  <br/> |
|<span data-ttu-id="14c19-135">4 </span><span class="sxs-lookup"><span data-stu-id="14c19-135">4</span></span>  <br/> |<span data-ttu-id="14c19-136">2 </span><span class="sxs-lookup"><span data-stu-id="14c19-136">2</span></span>  <br/> |<span data-ttu-id="14c19-137">normale</span><span class="sxs-lookup"><span data-stu-id="14c19-137">normal</span></span>  <br/> |
|<span data-ttu-id="14c19-138">5 </span><span class="sxs-lookup"><span data-stu-id="14c19-138">5</span></span>  <br/> |<span data-ttu-id="14c19-139">2 </span><span class="sxs-lookup"><span data-stu-id="14c19-139">2</span></span>  <br/> |<span data-ttu-id="14c19-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="14c19-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="14c19-141">6 </span><span class="sxs-lookup"><span data-stu-id="14c19-141">6</span></span>  <br/> |<span data-ttu-id="14c19-142">1 </span><span class="sxs-lookup"><span data-stu-id="14c19-142">1</span></span>  <br/> |<span data-ttu-id="14c19-143">aprire</span><span class="sxs-lookup"><span data-stu-id="14c19-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="14c19-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14c19-144">See also</span></span>

[<span data-ttu-id="14c19-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="14c19-145">tblNode</span></span>](tblnode.md)
