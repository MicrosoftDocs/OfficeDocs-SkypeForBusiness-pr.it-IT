---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809716"
---
# <a name="tblenumattribute"></a><span data-ttu-id="be37c-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="be37c-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="be37c-104">tblEnumAttribute è una tabella hardcoded in cui sono inclusi gli attributi Visibility e Behavior utilizzati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="be37c-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="be37c-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="be37c-105">**Columns**</span></span>

|<span data-ttu-id="be37c-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="be37c-106">**Column**</span></span>|<span data-ttu-id="be37c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="be37c-107">**Type**</span></span>|<span data-ttu-id="be37c-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="be37c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="be37c-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="be37c-109">attributeID</span></span>  <br/> |<span data-ttu-id="be37c-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="be37c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="be37c-111">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be37c-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="be37c-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="be37c-112">attributeName</span></span>  <br/> |<span data-ttu-id="be37c-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="be37c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="be37c-114">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="be37c-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="be37c-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="be37c-115">**Key**</span></span>

|<span data-ttu-id="be37c-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="be37c-116">**Column**</span></span>|<span data-ttu-id="be37c-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="be37c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be37c-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="be37c-118">attributeID</span></span>  <br/> |<span data-ttu-id="be37c-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="be37c-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="be37c-120">**Valori tabella**</span><span class="sxs-lookup"><span data-stu-id="be37c-120">**Table Values**</span></span>

|<span data-ttu-id="be37c-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="be37c-121">**attributeID**</span></span>|<span data-ttu-id="be37c-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="be37c-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be37c-123">1 </span><span class="sxs-lookup"><span data-stu-id="be37c-123">1</span></span>  <br/> |<span data-ttu-id="be37c-124">Visibilità.</span><span class="sxs-lookup"><span data-stu-id="be37c-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="be37c-125">2 </span><span class="sxs-lookup"><span data-stu-id="be37c-125">2</span></span>  <br/> |<span data-ttu-id="be37c-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="be37c-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="be37c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be37c-127">See also</span></span>

[<span data-ttu-id="be37c-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="be37c-128">tblNode</span></span>](tblnode.md)
