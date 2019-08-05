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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194669"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="1ff79-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="1ff79-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="1ff79-104">tblPrincipalInvites contiene gli inviti per tutti gli utenti con provisioning per tutti i nodi con l'invito automatico attivato.</span><span class="sxs-lookup"><span data-stu-id="1ff79-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="1ff79-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1ff79-105">**Columns**</span></span>

|<span data-ttu-id="1ff79-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1ff79-106">**Column**</span></span>|<span data-ttu-id="1ff79-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1ff79-107">**Type**</span></span>|<span data-ttu-id="1ff79-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1ff79-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ff79-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1ff79-109">prinID</span></span>  <br/> |<span data-ttu-id="1ff79-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="1ff79-110">int, not null</span></span>  <br/> |<span data-ttu-id="1ff79-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="1ff79-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1ff79-112">invID</span><span class="sxs-lookup"><span data-stu-id="1ff79-112">invID</span></span>  <br/> |<span data-ttu-id="1ff79-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="1ff79-113">int, not null</span></span>  <br/> |<span data-ttu-id="1ff79-114">Numero sequenziale univoco (per ID entità) generato dalla tabella tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="1ff79-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="1ff79-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="1ff79-115">nodeID</span></span>  <br/> |<span data-ttu-id="1ff79-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="1ff79-116">int, not null</span></span>  <br/> |<span data-ttu-id="1ff79-117">ID nodo (solo chat room).</span><span class="sxs-lookup"><span data-stu-id="1ff79-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="1ff79-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="1ff79-118">createdOn</span></span>  <br/> |<span data-ttu-id="1ff79-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="1ff79-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="1ff79-120">Ora della creazione.</span><span class="sxs-lookup"><span data-stu-id="1ff79-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="1ff79-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="1ff79-121">**Keys**</span></span>

|<span data-ttu-id="1ff79-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1ff79-122">**Column**</span></span>|<span data-ttu-id="1ff79-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1ff79-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ff79-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="1ff79-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="1ff79-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="1ff79-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1ff79-126">prinID</span><span class="sxs-lookup"><span data-stu-id="1ff79-126">prinID</span></span>  <br/> |<span data-ttu-id="1ff79-127">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="1ff79-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="1ff79-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="1ff79-128">nodeID</span></span>  <br/> |<span data-ttu-id="1ff79-129">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="1ff79-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

