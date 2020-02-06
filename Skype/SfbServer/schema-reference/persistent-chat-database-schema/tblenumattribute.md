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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814614"
---
# <a name="tblenumattribute"></a><span data-ttu-id="10f74-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="10f74-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="10f74-104">tblEnumAttribute è una tabella hardcoded che contiene gli attributi Visibility e Behavior usati nella tabella Node.</span><span class="sxs-lookup"><span data-stu-id="10f74-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="10f74-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="10f74-105">**Columns**</span></span>

|<span data-ttu-id="10f74-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="10f74-106">**Column**</span></span>|<span data-ttu-id="10f74-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10f74-107">**Type**</span></span>|<span data-ttu-id="10f74-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="10f74-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10f74-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="10f74-109">attributeID</span></span>  <br/> |<span data-ttu-id="10f74-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="10f74-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="10f74-111">ID dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="10f74-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="10f74-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="10f74-112">attributeName</span></span>  <br/> |<span data-ttu-id="10f74-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="10f74-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="10f74-114">Nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="10f74-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="10f74-115">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="10f74-115">**Key**</span></span>

|<span data-ttu-id="10f74-116">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="10f74-116">**Column**</span></span>|<span data-ttu-id="10f74-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="10f74-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10f74-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="10f74-118">attributeID</span></span>  <br/> |<span data-ttu-id="10f74-119">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="10f74-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="10f74-120">**Valori tabella**</span><span class="sxs-lookup"><span data-stu-id="10f74-120">**Table Values**</span></span>

|<span data-ttu-id="10f74-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="10f74-121">**attributeID**</span></span>|<span data-ttu-id="10f74-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="10f74-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10f74-123">1</span><span class="sxs-lookup"><span data-stu-id="10f74-123">1</span></span>  <br/> |<span data-ttu-id="10f74-124">Visibilità.</span><span class="sxs-lookup"><span data-stu-id="10f74-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="10f74-125">2</span><span class="sxs-lookup"><span data-stu-id="10f74-125">2</span></span>  <br/> |<span data-ttu-id="10f74-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="10f74-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="10f74-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10f74-127">See also</span></span>

[<span data-ttu-id="10f74-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="10f74-128">tblNode</span></span>](tblnode.md)
