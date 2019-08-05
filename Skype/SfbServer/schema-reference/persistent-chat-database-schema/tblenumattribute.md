---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194685"
---
# <a name="tblenumattribute"></a><span data-ttu-id="0eeb9-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="0eeb9-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="0eeb9-104">tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="0eeb9-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-105">**Columns**</span></span>

|<span data-ttu-id="0eeb9-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-106">**Column**</span></span>|<span data-ttu-id="0eeb9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-107">**Type**</span></span>|<span data-ttu-id="0eeb9-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eeb9-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="0eeb9-109">attributeID</span></span>  <br/> |<span data-ttu-id="0eeb9-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="0eeb9-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="0eeb9-111">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="0eeb9-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="0eeb9-112">attributeName</span></span>  <br/> |<span data-ttu-id="0eeb9-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="0eeb9-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0eeb9-114">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="0eeb9-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-115">**Key**</span></span>

|<span data-ttu-id="0eeb9-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-116">**Column**</span></span>|<span data-ttu-id="0eeb9-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0eeb9-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="0eeb9-118">attributeID</span></span>  <br/> |<span data-ttu-id="0eeb9-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="0eeb9-120">**Valori tabella**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-120">**Table Values**</span></span>

|<span data-ttu-id="0eeb9-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-121">**attributeID**</span></span>|<span data-ttu-id="0eeb9-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="0eeb9-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0eeb9-123">1</span><span class="sxs-lookup"><span data-stu-id="0eeb9-123">1</span></span>  <br/> |<span data-ttu-id="0eeb9-124">Visibilità.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="0eeb9-125">2</span><span class="sxs-lookup"><span data-stu-id="0eeb9-125">2</span></span>  <br/> |<span data-ttu-id="0eeb9-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="0eeb9-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0eeb9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eeb9-127">See also</span></span>

[<span data-ttu-id="0eeb9-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="0eeb9-128">tblNode</span></span>](tblnode.md)
