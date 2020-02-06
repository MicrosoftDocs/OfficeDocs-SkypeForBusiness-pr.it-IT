---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812904"
---
# <a name="tblroletype"></a><span data-ttu-id="ce6df-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="ce6df-103">tblRoleType</span></span>
 
<span data-ttu-id="ce6df-104">tblRoleType è una tabella di ricerca statica con i tipi di ruolo e i set di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="ce6df-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="ce6df-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ce6df-105">**Columns**</span></span>

|<span data-ttu-id="ce6df-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ce6df-106">**Column**</span></span>|<span data-ttu-id="ce6df-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce6df-107">**Type**</span></span>|<span data-ttu-id="ce6df-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ce6df-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce6df-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ce6df-109">rtypeID</span></span>  <br/> |<span data-ttu-id="ce6df-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="ce6df-110">int, not null</span></span>  <br/> |<span data-ttu-id="ce6df-111">ID tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ce6df-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="ce6df-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="ce6df-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="ce6df-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="ce6df-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="ce6df-114">Descrizione del tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="ce6df-114">Role type description.</span></span> <span data-ttu-id="ce6df-115">Esistono quattro ruoli disponibili:</span><span class="sxs-lookup"><span data-stu-id="ce6df-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="ce6df-116">Membro: membro della chat room</span><span class="sxs-lookup"><span data-stu-id="ce6df-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="ce6df-117">Manager: gestione chat room</span><span class="sxs-lookup"><span data-stu-id="ce6df-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="ce6df-118">Voiced: relatore per una chat room dell'Auditorium</span><span class="sxs-lookup"><span data-stu-id="ce6df-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="ce6df-119">Creatore: può creare chat room</span><span class="sxs-lookup"><span data-stu-id="ce6df-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="ce6df-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="ce6df-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="ce6df-121">bigint e non null</span><span class="sxs-lookup"><span data-stu-id="ce6df-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="ce6df-122">Set di autorizzazioni per il ruolo.</span><span class="sxs-lookup"><span data-stu-id="ce6df-122">Permission set for the role.</span></span> <span data-ttu-id="ce6df-123">I bit usati sono:</span><span class="sxs-lookup"><span data-stu-id="ce6df-123">The used bits are:</span></span> <br/>  <span data-ttu-id="ce6df-124">2: true se il ruolo può gestire i nodi.</span><span class="sxs-lookup"><span data-stu-id="ce6df-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="ce6df-125">4: true se il ruolo può creare nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="ce6df-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="ce6df-126">7: vero se il ruolo può partecipare a una chat room (o chat room per bambini di una categoria).</span><span class="sxs-lookup"><span data-stu-id="ce6df-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="ce6df-127">8: true se il ruolo può essere chattato in una chat room o in chat per bambini di una categoria.</span><span class="sxs-lookup"><span data-stu-id="ce6df-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="ce6df-128">10: true se il ruolo può leggere la cronologia chat anche quando non è stato aggiunto a una chat room.</span><span class="sxs-lookup"><span data-stu-id="ce6df-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="ce6df-129">11: vero se il ruolo può vedere la chat room.</span><span class="sxs-lookup"><span data-stu-id="ce6df-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="ce6df-130">(Questa operazione viene ulteriormente affinata da fattori come l'ambito e la visibilità).</span><span class="sxs-lookup"><span data-stu-id="ce6df-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="ce6df-131">12: vero se il ruolo può chattare in una chat room di un auditorium.</span><span class="sxs-lookup"><span data-stu-id="ce6df-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="ce6df-132">13: true se il ruolo può ignorare le regole di visibilità durante la visualizzazione dei nodi.</span><span class="sxs-lookup"><span data-stu-id="ce6df-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="ce6df-133">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="ce6df-133">**Key**</span></span>

|<span data-ttu-id="ce6df-134">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ce6df-134">**Column**</span></span>|<span data-ttu-id="ce6df-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ce6df-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce6df-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ce6df-136">rtypeID</span></span>  <br/> |<span data-ttu-id="ce6df-137">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ce6df-137">Primary key.</span></span>  <br/> |
   

