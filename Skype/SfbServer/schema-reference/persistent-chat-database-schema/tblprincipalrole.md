---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813364"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="84e67-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="84e67-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="84e67-104">tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="84e67-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="84e67-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="84e67-105">**Columns**</span></span>

|<span data-ttu-id="84e67-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="84e67-106">**Column**</span></span>|<span data-ttu-id="84e67-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="84e67-107">**Type**</span></span>|<span data-ttu-id="84e67-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="84e67-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84e67-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="84e67-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="84e67-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="84e67-110">int, not null</span></span>  <br/> |<span data-ttu-id="84e67-111">ID nodo a cui si applica il ruolo.</span><span class="sxs-lookup"><span data-stu-id="84e67-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="84e67-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="84e67-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="84e67-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="84e67-113">int, not null</span></span>  <br/> |<span data-ttu-id="84e67-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="84e67-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="84e67-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="84e67-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="84e67-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="84e67-116">int, not null</span></span>  <br/> |<span data-ttu-id="84e67-117">ID tipo di ruolo (da tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="84e67-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="84e67-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="84e67-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="84e67-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="84e67-119">int, not null</span></span>  <br/> |<span data-ttu-id="84e67-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="84e67-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="84e67-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="84e67-121">**Keys**</span></span>

|<span data-ttu-id="84e67-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="84e67-122">**Column**</span></span>|<span data-ttu-id="84e67-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="84e67-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84e67-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="84e67-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="84e67-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="84e67-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="84e67-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="84e67-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="84e67-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="84e67-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="84e67-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="84e67-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="84e67-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="84e67-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="84e67-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="84e67-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="84e67-131">Chiave esterna con ricerca nella tabella tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="84e67-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

