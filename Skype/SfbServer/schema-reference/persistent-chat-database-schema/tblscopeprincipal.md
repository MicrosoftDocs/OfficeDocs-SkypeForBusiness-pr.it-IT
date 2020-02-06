---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812444"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b9f3b-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b9f3b-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b9f3b-104">tblScopePrincipal contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b9f3b-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-105">**Columns**</span></span>

|<span data-ttu-id="b9f3b-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-106">**Column**</span></span>|<span data-ttu-id="b9f3b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-107">**Type**</span></span>|<span data-ttu-id="b9f3b-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9f3b-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b9f3b-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b9f3b-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b9f3b-110">int, not null</span></span>  <br/> |<span data-ttu-id="b9f3b-111">ID nodo a cui si applica l'ambito.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b9f3b-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b9f3b-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b9f3b-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="b9f3b-113">int, not null</span></span>  <br/> |<span data-ttu-id="b9f3b-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b9f3b-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b9f3b-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b9f3b-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b9f3b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b9f3b-117">True se il tipo di ambito è Deny; False se Consenti.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b9f3b-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b9f3b-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b9f3b-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="b9f3b-119">int, not null</span></span>  <br/> |<span data-ttu-id="b9f3b-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b9f3b-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-121">**Keys**</span></span>

|<span data-ttu-id="b9f3b-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-122">**Column**</span></span>|<span data-ttu-id="b9f3b-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b9f3b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9f3b-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="b9f3b-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="b9f3b-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b9f3b-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b9f3b-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b9f3b-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b9f3b-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b9f3b-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="b9f3b-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="b9f3b-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

