---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831536"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="6e60f-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="6e60f-103">tblPrincipalType</span></span>
 
<span data-ttu-id="6e60f-104">Nella tabella tblPrincipalType sono inclusi i tipi di entità per classificare gli elementi contenuti nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6e60f-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="6e60f-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6e60f-105">**Columns**</span></span>

|<span data-ttu-id="6e60f-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e60f-106">**Column**</span></span>|<span data-ttu-id="6e60f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6e60f-107">**Type**</span></span>|<span data-ttu-id="6e60f-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6e60f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e60f-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6e60f-109">ptypeID</span></span>  <br/> |<span data-ttu-id="6e60f-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="6e60f-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="6e60f-111">ID del tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="6e60f-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="6e60f-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="6e60f-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="6e60f-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="6e60f-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6e60f-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="6e60f-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="6e60f-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="6e60f-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="6e60f-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="6e60f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6e60f-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="6e60f-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="6e60f-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="6e60f-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="6e60f-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="6e60f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6e60f-120">True se il tipo è un tipo utente.</span><span class="sxs-lookup"><span data-stu-id="6e60f-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="6e60f-121">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="6e60f-121">**Key**</span></span>

|<span data-ttu-id="6e60f-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e60f-122">**Column**</span></span>|<span data-ttu-id="6e60f-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6e60f-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6e60f-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="6e60f-124">ptypeID</span></span>  <br/> |<span data-ttu-id="6e60f-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="6e60f-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="6e60f-126">**Valori principali**</span><span class="sxs-lookup"><span data-stu-id="6e60f-126">**Principal Values**</span></span>

|<span data-ttu-id="6e60f-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="6e60f-127">**ID**</span></span>|<span data-ttu-id="6e60f-128">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="6e60f-128">**Role**</span></span>|<span data-ttu-id="6e60f-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6e60f-129">**Description**</span></span>|<span data-ttu-id="6e60f-130">**Utente**</span><span class="sxs-lookup"><span data-stu-id="6e60f-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e60f-131">1 </span><span class="sxs-lookup"><span data-stu-id="6e60f-131">1</span></span>  <br/> |<span data-ttu-id="6e60f-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="6e60f-132">Any</span></span>  <br/> |<span data-ttu-id="6e60f-p101">Entità generica senza tipo conosciuto. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6e60f-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6e60f-135">2 </span><span class="sxs-lookup"><span data-stu-id="6e60f-135">2</span></span>  <br/> |<span data-ttu-id="6e60f-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="6e60f-136">AnyUser</span></span>  <br/> |<span data-ttu-id="6e60f-p102">Entità generica di tipo utente. Non usate nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6e60f-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="6e60f-139">Sì</span><span class="sxs-lookup"><span data-stu-id="6e60f-139">Yes</span></span>  <br/> |
|<span data-ttu-id="6e60f-140">3 </span><span class="sxs-lookup"><span data-stu-id="6e60f-140">3</span></span>  <br/> |<span data-ttu-id="6e60f-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="6e60f-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="6e60f-p103">Entità generica con semantica di gruppo. Non usata nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="6e60f-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="6e60f-144">4 </span><span class="sxs-lookup"><span data-stu-id="6e60f-144">4</span></span>  <br/> |<span data-ttu-id="6e60f-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="6e60f-145">SystemUser</span></span>  <br/> |<span data-ttu-id="6e60f-146">Entità utilizzata internamente dal server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="6e60f-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="6e60f-147">5 </span><span class="sxs-lookup"><span data-stu-id="6e60f-147">5</span></span>  <br/> |<span data-ttu-id="6e60f-148">Utente</span><span class="sxs-lookup"><span data-stu-id="6e60f-148">User</span></span>  <br/> |<span data-ttu-id="6e60f-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="6e60f-149">Regular user.</span></span>  <br/> |<span data-ttu-id="6e60f-150">Sì</span><span class="sxs-lookup"><span data-stu-id="6e60f-150">Yes</span></span>  <br/> |
|<span data-ttu-id="6e60f-151">8 </span><span class="sxs-lookup"><span data-stu-id="6e60f-151">8</span></span>  <br/> |<span data-ttu-id="6e60f-152">DC</span><span class="sxs-lookup"><span data-stu-id="6e60f-152">DC</span></span>  <br/> |<span data-ttu-id="6e60f-153">Controller di dominio di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e60f-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="6e60f-154">9 </span><span class="sxs-lookup"><span data-stu-id="6e60f-154">9</span></span>  <br/> |<span data-ttu-id="6e60f-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="6e60f-155">Group</span></span>  <br/> |<span data-ttu-id="6e60f-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e60f-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="6e60f-157">10 </span><span class="sxs-lookup"><span data-stu-id="6e60f-157">10</span></span>  <br/> |<span data-ttu-id="6e60f-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="6e60f-158">Folder</span></span>  <br/> |<span data-ttu-id="6e60f-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6e60f-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="6e60f-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e60f-160">See also</span></span>

[<span data-ttu-id="6e60f-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="6e60f-161">tblPrincipal</span></span>](tblprincipal.md)
