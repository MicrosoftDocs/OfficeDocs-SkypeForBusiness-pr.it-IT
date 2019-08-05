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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194653"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="f6443-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="f6443-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="f6443-104">tblScopePrincipal contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="f6443-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="f6443-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f6443-105">**Columns**</span></span>

|<span data-ttu-id="f6443-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f6443-106">**Column**</span></span>|<span data-ttu-id="f6443-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f6443-107">**Type**</span></span>|<span data-ttu-id="f6443-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f6443-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6443-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f6443-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f6443-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f6443-110">int, not null</span></span>  <br/> |<span data-ttu-id="f6443-111">ID nodo a cui si applica l'ambito.</span><span class="sxs-lookup"><span data-stu-id="f6443-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="f6443-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f6443-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="f6443-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f6443-113">int, not null</span></span>  <br/> |<span data-ttu-id="f6443-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="f6443-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f6443-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="f6443-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="f6443-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f6443-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f6443-117">True se il tipo di ambito è Deny; False se Consenti.</span><span class="sxs-lookup"><span data-stu-id="f6443-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="f6443-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f6443-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="f6443-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="f6443-119">int, not null</span></span>  <br/> |<span data-ttu-id="f6443-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="f6443-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f6443-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="f6443-121">**Keys**</span></span>

|<span data-ttu-id="f6443-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f6443-122">**Column**</span></span>|<span data-ttu-id="f6443-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f6443-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6443-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="f6443-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="f6443-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f6443-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f6443-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f6443-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f6443-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="f6443-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f6443-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f6443-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="f6443-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="f6443-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

