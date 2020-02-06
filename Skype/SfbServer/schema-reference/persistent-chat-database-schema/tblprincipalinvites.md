---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814184"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="3d925-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="3d925-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="3d925-104">tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.</span><span class="sxs-lookup"><span data-stu-id="3d925-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="3d925-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3d925-105">**Columns**</span></span>

|<span data-ttu-id="3d925-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3d925-106">**Column**</span></span>|<span data-ttu-id="3d925-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d925-107">**Type**</span></span>|<span data-ttu-id="3d925-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3d925-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d925-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3d925-109">prinID</span></span>  <br/> |<span data-ttu-id="3d925-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="3d925-110">int, not null</span></span>  <br/> |<span data-ttu-id="3d925-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="3d925-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3d925-112">invID</span><span class="sxs-lookup"><span data-stu-id="3d925-112">invID</span></span>  <br/> |<span data-ttu-id="3d925-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="3d925-113">int, not null</span></span>  <br/> |<span data-ttu-id="3d925-114">Numero sequenziale univoco (per ID entità) generato dalla tabella tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="3d925-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="3d925-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="3d925-115">nodeID</span></span>  <br/> |<span data-ttu-id="3d925-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="3d925-116">int, not null</span></span>  <br/> |<span data-ttu-id="3d925-117">ID nodo (solo chat room).</span><span class="sxs-lookup"><span data-stu-id="3d925-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="3d925-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="3d925-118">createdOn</span></span>  <br/> |<span data-ttu-id="3d925-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="3d925-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="3d925-120">Ora della creazione.</span><span class="sxs-lookup"><span data-stu-id="3d925-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="3d925-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="3d925-121">**Keys**</span></span>

|<span data-ttu-id="3d925-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3d925-122">**Column**</span></span>|<span data-ttu-id="3d925-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3d925-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d925-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="3d925-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="3d925-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="3d925-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3d925-126">prinID</span><span class="sxs-lookup"><span data-stu-id="3d925-126">prinID</span></span>  <br/> |<span data-ttu-id="3d925-127">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="3d925-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="3d925-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="3d925-128">nodeID</span></span>  <br/> |<span data-ttu-id="3d925-129">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="3d925-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

