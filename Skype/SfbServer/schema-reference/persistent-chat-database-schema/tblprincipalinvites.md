---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: In tblPrincipalInvites sono inclusi gli inviti per tutti gli utenti di cui è stato eseguito il provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815856"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="ac7f3-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="ac7f3-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="ac7f3-104">In tblPrincipalInvites sono inclusi gli inviti per tutti gli utenti di cui è stato eseguito il provisioning per tutti i nodi con l'invito automatico attivato.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="ac7f3-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-105">**Columns**</span></span>

|<span data-ttu-id="ac7f3-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-106">**Column**</span></span>|<span data-ttu-id="ac7f3-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-107">**Type**</span></span>|<span data-ttu-id="ac7f3-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac7f3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ac7f3-109">prinID</span></span>  <br/> |<span data-ttu-id="ac7f3-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="ac7f3-110">int, not null</span></span>  <br/> |<span data-ttu-id="ac7f3-111">ID dell'entità.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ac7f3-112">invID</span><span class="sxs-lookup"><span data-stu-id="ac7f3-112">invID</span></span>  <br/> |<span data-ttu-id="ac7f3-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="ac7f3-113">int, not null</span></span>  <br/> |<span data-ttu-id="ac7f3-114">Numero sequenziale univoco (per ID dell'entità) generato da tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="ac7f3-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="ac7f3-115">nodeID</span></span>  <br/> |<span data-ttu-id="ac7f3-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="ac7f3-116">int, not null</span></span>  <br/> |<span data-ttu-id="ac7f3-117">ID del nodo (solo chat).</span><span class="sxs-lookup"><span data-stu-id="ac7f3-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="ac7f3-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="ac7f3-118">createdOn</span></span>  <br/> |<span data-ttu-id="ac7f3-119">datetime, not null</span><span class="sxs-lookup"><span data-stu-id="ac7f3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="ac7f3-120">Data e ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="ac7f3-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-121">**Keys**</span></span>

|<span data-ttu-id="ac7f3-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-122">**Column**</span></span>|<span data-ttu-id="ac7f3-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ac7f3-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="ac7f3-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ac7f3-125">prinID</span><span class="sxs-lookup"><span data-stu-id="ac7f3-125">prinID</span></span>  <br/> |<span data-ttu-id="ac7f3-126">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="ac7f3-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="ac7f3-127">nodeID</span></span>  <br/> |<span data-ttu-id="ac7f3-128">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="ac7f3-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

