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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194661"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="68ed9-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="68ed9-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="68ed9-104">tblPrincipalRole contiene ruoli espliciti assegnati ai nodi.</span><span class="sxs-lookup"><span data-stu-id="68ed9-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="68ed9-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="68ed9-105">**Columns**</span></span>

|<span data-ttu-id="68ed9-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="68ed9-106">**Column**</span></span>|<span data-ttu-id="68ed9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="68ed9-107">**Type**</span></span>|<span data-ttu-id="68ed9-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="68ed9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="68ed9-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="68ed9-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="68ed9-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="68ed9-110">int, not null</span></span>  <br/> |<span data-ttu-id="68ed9-111">ID nodo a cui si applica il ruolo.</span><span class="sxs-lookup"><span data-stu-id="68ed9-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="68ed9-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="68ed9-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="68ed9-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="68ed9-113">int, not null</span></span>  <br/> |<span data-ttu-id="68ed9-114">ID entità.</span><span class="sxs-lookup"><span data-stu-id="68ed9-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="68ed9-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="68ed9-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="68ed9-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="68ed9-116">int, not null</span></span>  <br/> |<span data-ttu-id="68ed9-117">ID tipo di ruolo (da tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="68ed9-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="68ed9-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="68ed9-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="68ed9-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="68ed9-119">int, not null</span></span>  <br/> |<span data-ttu-id="68ed9-120">ID dell'entità che ha aggiornato l'ultima voce.</span><span class="sxs-lookup"><span data-stu-id="68ed9-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="68ed9-121">**Tasti**</span><span class="sxs-lookup"><span data-stu-id="68ed9-121">**Keys**</span></span>

|<span data-ttu-id="68ed9-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="68ed9-122">**Column**</span></span>|<span data-ttu-id="68ed9-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="68ed9-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68ed9-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="68ed9-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="68ed9-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="68ed9-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="68ed9-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="68ed9-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="68ed9-127">Chiave esterna con ricerca nella tabella tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="68ed9-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="68ed9-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="68ed9-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="68ed9-129">Chiave esterna con ricerca nella tabella tblPrincipal. prinID.</span><span class="sxs-lookup"><span data-stu-id="68ed9-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="68ed9-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="68ed9-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="68ed9-131">Chiave esterna con ricerca nella tabella tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="68ed9-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

