---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831526"
---
# <a name="tblroletype"></a><span data-ttu-id="4c8bd-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="4c8bd-103">tblRoleType</span></span>
 
<span data-ttu-id="4c8bd-104">tblRoleType è una tabella di ricerca statica con i tipi di ruoli e i relativi set di autorizzazioni associati.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="4c8bd-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-105">**Columns**</span></span>

|<span data-ttu-id="4c8bd-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-106">**Column**</span></span>|<span data-ttu-id="4c8bd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-107">**Type**</span></span>|<span data-ttu-id="4c8bd-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c8bd-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4c8bd-109">rtypeID</span></span>  <br/> |<span data-ttu-id="4c8bd-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="4c8bd-110">int, not null</span></span>  <br/> |<span data-ttu-id="4c8bd-111">ID del tipo di ruolo.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="4c8bd-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="4c8bd-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="4c8bd-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="4c8bd-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="4c8bd-p101">Descrizione del tipo di ruolo. Sono disponibili quattro ruoli:</span><span class="sxs-lookup"><span data-stu-id="4c8bd-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="4c8bd-116">Member: membro della chat.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="4c8bd-117">Manager: responsabile della chat.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="4c8bd-118">Voiced: relatore per una chat. auditorium</span><span class="sxs-lookup"><span data-stu-id="4c8bd-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="4c8bd-119">Creator: creazione di chat room</span><span class="sxs-lookup"><span data-stu-id="4c8bd-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="4c8bd-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="4c8bd-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="4c8bd-121">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="4c8bd-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="4c8bd-p102">Set di autorizzazioni per il ruolo. I bit utilizzati sono:</span><span class="sxs-lookup"><span data-stu-id="4c8bd-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="4c8bd-124">2: true se il ruolo può gestire i nodi.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="4c8bd-125">4: true se il ruolo può creare nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="4c8bd-126">7: true se il ruolo può partecipare a una chat (o a chat figlio di una categoria).</span><span class="sxs-lookup"><span data-stu-id="4c8bd-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4c8bd-127">8: true se il ruolo può eseguire chat in una chat (o in chat figlio di una categoria).</span><span class="sxs-lookup"><span data-stu-id="4c8bd-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4c8bd-128">10: true se il ruolo può leggere la cronologia delle chat anche se non partecipa a una chat.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="4c8bd-p103">11: true se il ruolo può visualizzare la chat (ulteriormente definito da fattori come l'ambito e la visibilità).</span><span class="sxs-lookup"><span data-stu-id="4c8bd-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="4c8bd-131">12: true se il ruolo può eseguire chat in una chat auditorium.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="4c8bd-132">13: true se il ruolo può ignorare le regole di visibilità quando visualizza i nodi.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="4c8bd-133">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-133">**Key**</span></span>

|<span data-ttu-id="4c8bd-134">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-134">**Column**</span></span>|<span data-ttu-id="4c8bd-135">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4c8bd-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4c8bd-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4c8bd-136">rtypeID</span></span>  <br/> |<span data-ttu-id="4c8bd-137">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="4c8bd-137">Primary key.</span></span>  <br/> |
   

