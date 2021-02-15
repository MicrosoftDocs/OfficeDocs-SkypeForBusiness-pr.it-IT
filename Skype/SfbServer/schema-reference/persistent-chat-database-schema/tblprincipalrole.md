---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831556"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="bc610-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="bc610-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="bc610-104">tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="bc610-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="bc610-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="bc610-105">**Columns**</span></span>

|<span data-ttu-id="bc610-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="bc610-106">**Column**</span></span>|<span data-ttu-id="bc610-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bc610-107">**Type**</span></span>|<span data-ttu-id="bc610-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bc610-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc610-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bc610-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="bc610-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="bc610-110">int, not null</span></span>  <br/> |<span data-ttu-id="bc610-111">ID nodo a cui si applica il ruolo.</span><span class="sxs-lookup"><span data-stu-id="bc610-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="bc610-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bc610-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="bc610-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="bc610-113">int, not null</span></span>  <br/> |<span data-ttu-id="bc610-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="bc610-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="bc610-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bc610-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="bc610-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="bc610-116">int, not null</span></span>  <br/> |<span data-ttu-id="bc610-117">ID del tipo di ruolo (da tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="bc610-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="bc610-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="bc610-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="bc610-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="bc610-119">int, not null</span></span>  <br/> |<span data-ttu-id="bc610-120">ID dell'ultima entità che ha aggiornato questa voce.</span><span class="sxs-lookup"><span data-stu-id="bc610-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="bc610-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="bc610-121">**Keys**</span></span>

|<span data-ttu-id="bc610-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="bc610-122">**Column**</span></span>|<span data-ttu-id="bc610-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="bc610-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="bc610-124">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="bc610-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="bc610-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="bc610-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="bc610-126">Chiave esterna con ricerca nella tabella tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="bc610-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="bc610-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="bc610-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="bc610-128">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="bc610-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="bc610-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="bc610-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="bc610-130">Chiave esterna con ricerca nella tabella tblRoleType.rtypeID.</span><span class="sxs-lookup"><span data-stu-id="bc610-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

