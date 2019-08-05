---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue è una tabella hardcoded che contiene i valori di visibilità e comportamento degli attributi usati nella tabella Node.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194684"
---
# <a name="tblenumvalue"></a><span data-ttu-id="4600a-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="4600a-103">tblEnumValue</span></span>
 
<span data-ttu-id="4600a-104">tblEnumValue è una tabella hardcoded che contiene i valori di visibilità e comportamento degli attributi usati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="4600a-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="4600a-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4600a-105">**Columns**</span></span>

|<span data-ttu-id="4600a-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4600a-106">**Column**</span></span>|<span data-ttu-id="4600a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4600a-107">**Type**</span></span>|<span data-ttu-id="4600a-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4600a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4600a-109">valueID</span><span class="sxs-lookup"><span data-stu-id="4600a-109">valueID</span></span>  <br/> |<span data-ttu-id="4600a-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="4600a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="4600a-111">ID del valore.</span><span class="sxs-lookup"><span data-stu-id="4600a-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="4600a-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="4600a-112">attributeID</span></span>  <br/> |<span data-ttu-id="4600a-113">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="4600a-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="4600a-114">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4600a-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="4600a-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="4600a-115">attributeValue</span></span>  <br/> |<span data-ttu-id="4600a-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="4600a-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="4600a-117">Nome del valore.</span><span class="sxs-lookup"><span data-stu-id="4600a-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="4600a-118">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="4600a-118">**Keys**</span></span>

|<span data-ttu-id="4600a-119">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4600a-119">**Column**</span></span>|<span data-ttu-id="4600a-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4600a-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4600a-121">valueID</span><span class="sxs-lookup"><span data-stu-id="4600a-121">valueID</span></span>  <br/> |<span data-ttu-id="4600a-122">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="4600a-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4600a-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="4600a-123">attributeID</span></span>  <br/> |<span data-ttu-id="4600a-124">Chiave esterna con ricerca nella tabella tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="4600a-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="4600a-125">**Valori tabella**</span><span class="sxs-lookup"><span data-stu-id="4600a-125">**Table Values**</span></span>

|<span data-ttu-id="4600a-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="4600a-126">**valueID**</span></span>|<span data-ttu-id="4600a-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="4600a-127">**attributeID**</span></span>|<span data-ttu-id="4600a-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="4600a-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4600a-129">2</span><span class="sxs-lookup"><span data-stu-id="4600a-129">2</span></span>  <br/> |<span data-ttu-id="4600a-130">1</span><span class="sxs-lookup"><span data-stu-id="4600a-130">1</span></span>  <br/> |<span data-ttu-id="4600a-131">privato</span><span class="sxs-lookup"><span data-stu-id="4600a-131">private</span></span>  <br/> |
|<span data-ttu-id="4600a-132">3</span><span class="sxs-lookup"><span data-stu-id="4600a-132">3</span></span>  <br/> |<span data-ttu-id="4600a-133">1</span><span class="sxs-lookup"><span data-stu-id="4600a-133">1</span></span>  <br/> |<span data-ttu-id="4600a-134">ambito</span><span class="sxs-lookup"><span data-stu-id="4600a-134">scope</span></span>  <br/> |
|<span data-ttu-id="4600a-135">4</span><span class="sxs-lookup"><span data-stu-id="4600a-135">4</span></span>  <br/> |<span data-ttu-id="4600a-136">2</span><span class="sxs-lookup"><span data-stu-id="4600a-136">2</span></span>  <br/> |<span data-ttu-id="4600a-137">normale</span><span class="sxs-lookup"><span data-stu-id="4600a-137">normal</span></span>  <br/> |
|<span data-ttu-id="4600a-138">5</span><span class="sxs-lookup"><span data-stu-id="4600a-138">5</span></span>  <br/> |<span data-ttu-id="4600a-139">2</span><span class="sxs-lookup"><span data-stu-id="4600a-139">2</span></span>  <br/> |<span data-ttu-id="4600a-140">Auditorium</span><span class="sxs-lookup"><span data-stu-id="4600a-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="4600a-141">6</span><span class="sxs-lookup"><span data-stu-id="4600a-141">6</span></span>  <br/> |<span data-ttu-id="4600a-142">1</span><span class="sxs-lookup"><span data-stu-id="4600a-142">1</span></span>  <br/> |<span data-ttu-id="4600a-143">aprire</span><span class="sxs-lookup"><span data-stu-id="4600a-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4600a-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4600a-144">See also</span></span>

[<span data-ttu-id="4600a-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="4600a-145">tblNode</span></span>](tblnode.md)
