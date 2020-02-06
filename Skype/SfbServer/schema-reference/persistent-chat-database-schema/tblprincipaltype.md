---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812934"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="f130d-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="f130d-103">tblPrincipalType</span></span>
 
<span data-ttu-id="f130d-104">tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f130d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="f130d-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f130d-105">**Columns**</span></span>

|<span data-ttu-id="f130d-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f130d-106">**Column**</span></span>|<span data-ttu-id="f130d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f130d-107">**Type**</span></span>|<span data-ttu-id="f130d-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f130d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f130d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f130d-109">ptypeID</span></span>  <br/> |<span data-ttu-id="f130d-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="f130d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f130d-111">ID tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="f130d-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="f130d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="f130d-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="f130d-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="f130d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f130d-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="f130d-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="f130d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="f130d-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="f130d-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f130d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f130d-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="f130d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="f130d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="f130d-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="f130d-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="f130d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f130d-120">True se il tipo è un tipo di utente.</span><span class="sxs-lookup"><span data-stu-id="f130d-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="f130d-121">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="f130d-121">**Key**</span></span>

|<span data-ttu-id="f130d-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="f130d-122">**Column**</span></span>|<span data-ttu-id="f130d-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f130d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f130d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f130d-124">ptypeID</span></span>  <br/> |<span data-ttu-id="f130d-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="f130d-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f130d-126">**Valori principali**</span><span class="sxs-lookup"><span data-stu-id="f130d-126">**Principal Values**</span></span>

|<span data-ttu-id="f130d-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="f130d-127">**ID**</span></span>|<span data-ttu-id="f130d-128">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="f130d-128">**Role**</span></span>|<span data-ttu-id="f130d-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f130d-129">**Description**</span></span>|<span data-ttu-id="f130d-130">**Utente**</span><span class="sxs-lookup"><span data-stu-id="f130d-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f130d-131">1</span><span class="sxs-lookup"><span data-stu-id="f130d-131">1</span></span>  <br/> |<span data-ttu-id="f130d-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="f130d-132">Any</span></span>  <br/> |<span data-ttu-id="f130d-133">Entità generica con nessun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="f130d-133">Generic principal with no known type.</span></span> <span data-ttu-id="f130d-134">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f130d-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f130d-135">2</span><span class="sxs-lookup"><span data-stu-id="f130d-135">2</span></span>  <br/> |<span data-ttu-id="f130d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="f130d-136">AnyUser</span></span>  <br/> |<span data-ttu-id="f130d-137">Oggetto Principal generico di tipo utente.</span><span class="sxs-lookup"><span data-stu-id="f130d-137">Generic principal of user type.</span></span> <span data-ttu-id="f130d-138">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f130d-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="f130d-139">Sì</span><span class="sxs-lookup"><span data-stu-id="f130d-139">Yes</span></span>  <br/> |
|<span data-ttu-id="f130d-140">3</span><span class="sxs-lookup"><span data-stu-id="f130d-140">3</span></span>  <br/> |<span data-ttu-id="f130d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="f130d-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="f130d-142">Entità generica con semantica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f130d-142">Generic principal with group semantic.</span></span> <span data-ttu-id="f130d-143">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="f130d-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f130d-144">4</span><span class="sxs-lookup"><span data-stu-id="f130d-144">4</span></span>  <br/> |<span data-ttu-id="f130d-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="f130d-145">SystemUser</span></span>  <br/> |<span data-ttu-id="f130d-146">Principal usato internamente dal server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="f130d-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="f130d-147">5</span><span class="sxs-lookup"><span data-stu-id="f130d-147">5</span></span>  <br/> |<span data-ttu-id="f130d-148">Utente</span><span class="sxs-lookup"><span data-stu-id="f130d-148">User</span></span>  <br/> |<span data-ttu-id="f130d-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="f130d-149">Regular user.</span></span>  <br/> |<span data-ttu-id="f130d-150">Sì</span><span class="sxs-lookup"><span data-stu-id="f130d-150">Yes</span></span>  <br/> |
|<span data-ttu-id="f130d-151">8</span><span class="sxs-lookup"><span data-stu-id="f130d-151">8</span></span>  <br/> |<span data-ttu-id="f130d-152">DC</span><span class="sxs-lookup"><span data-stu-id="f130d-152">DC</span></span>  <br/> |<span data-ttu-id="f130d-153">Controller di dominio Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="f130d-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="f130d-154">9</span><span class="sxs-lookup"><span data-stu-id="f130d-154">9</span></span>  <br/> |<span data-ttu-id="f130d-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="f130d-155">Group</span></span>  <br/> |<span data-ttu-id="f130d-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f130d-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="f130d-157">10</span><span class="sxs-lookup"><span data-stu-id="f130d-157">10</span></span>  <br/> |<span data-ttu-id="f130d-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="f130d-158">Folder</span></span>  <br/> |<span data-ttu-id="f130d-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f130d-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="f130d-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f130d-160">See also</span></span>

[<span data-ttu-id="f130d-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="f130d-161">tblPrincipal</span></span>](tblprincipal.md)
