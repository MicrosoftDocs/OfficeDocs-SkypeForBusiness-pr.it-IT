---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene gli ambiti assegnati ai nodi.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831516"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b4dba-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b4dba-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b4dba-104">tblScopePrincipal contiene gli ambiti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="b4dba-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b4dba-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b4dba-105">**Columns**</span></span>

|<span data-ttu-id="b4dba-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b4dba-106">**Column**</span></span>|<span data-ttu-id="b4dba-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4dba-107">**Type**</span></span>|<span data-ttu-id="b4dba-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b4dba-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4dba-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b4dba-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b4dba-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4dba-110">int, not null</span></span>  <br/> |<span data-ttu-id="b4dba-111">ID di nodo a cui si applica l'ambito.</span><span class="sxs-lookup"><span data-stu-id="b4dba-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b4dba-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b4dba-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b4dba-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4dba-113">int, not null</span></span>  <br/> |<span data-ttu-id="b4dba-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="b4dba-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b4dba-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b4dba-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b4dba-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="b4dba-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b4dba-117">True se il tipo di ambito è Deny; False se è Allow.</span><span class="sxs-lookup"><span data-stu-id="b4dba-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b4dba-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b4dba-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b4dba-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4dba-119">int, not null</span></span>  <br/> |<span data-ttu-id="b4dba-120">ID dell'ultima entità che ha aggiornato questa voce.</span><span class="sxs-lookup"><span data-stu-id="b4dba-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b4dba-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="b4dba-121">**Keys**</span></span>

|<span data-ttu-id="b4dba-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b4dba-122">**Column**</span></span>|<span data-ttu-id="b4dba-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b4dba-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="b4dba-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b4dba-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b4dba-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b4dba-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b4dba-126">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="b4dba-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b4dba-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b4dba-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="b4dba-128">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="b4dba-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

