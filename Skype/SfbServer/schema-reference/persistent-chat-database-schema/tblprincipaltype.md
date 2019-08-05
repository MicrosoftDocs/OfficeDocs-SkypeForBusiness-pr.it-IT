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
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194659"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="d9bdd-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="d9bdd-103">tblPrincipalType</span></span>
 
<span data-ttu-id="d9bdd-104">tblPrincipalType contiene i tipi Principal per categorizzare il contenuto della tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="d9bdd-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-105">**Columns**</span></span>

|<span data-ttu-id="d9bdd-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-106">**Column**</span></span>|<span data-ttu-id="d9bdd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-107">**Type**</span></span>|<span data-ttu-id="d9bdd-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9bdd-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="d9bdd-109">ptypeID</span></span>  <br/> |<span data-ttu-id="d9bdd-110">smallint e non null</span><span class="sxs-lookup"><span data-stu-id="d9bdd-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="d9bdd-111">ID tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="d9bdd-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="d9bdd-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="d9bdd-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="d9bdd-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d9bdd-114">Descrizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="d9bdd-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="d9bdd-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="d9bdd-116">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d9bdd-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d9bdd-117">True se il tipo corrisponde alle entità usate per scopi interni.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="d9bdd-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="d9bdd-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="d9bdd-119">bit, not null</span><span class="sxs-lookup"><span data-stu-id="d9bdd-119">bit, not null</span></span>  <br/> |<span data-ttu-id="d9bdd-120">True se il tipo è un tipo di utente.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="d9bdd-121">**Chiave**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-121">**Key**</span></span>

|<span data-ttu-id="d9bdd-122">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-122">**Column**</span></span>|<span data-ttu-id="d9bdd-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9bdd-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="d9bdd-124">ptypeID</span></span>  <br/> |<span data-ttu-id="d9bdd-125">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="d9bdd-126">**Valori principali**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-126">**Principal Values**</span></span>

|<span data-ttu-id="d9bdd-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-127">**ID**</span></span>|<span data-ttu-id="d9bdd-128">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-128">**Role**</span></span>|<span data-ttu-id="d9bdd-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-129">**Description**</span></span>|<span data-ttu-id="d9bdd-130">**Utente**</span><span class="sxs-lookup"><span data-stu-id="d9bdd-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9bdd-131">1</span><span class="sxs-lookup"><span data-stu-id="d9bdd-131">1</span></span>  <br/> |<span data-ttu-id="d9bdd-132">Qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d9bdd-132">Any</span></span>  <br/> |<span data-ttu-id="d9bdd-133">Entità generica con nessun tipo noto.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-133">Generic principal with no known type.</span></span> <span data-ttu-id="d9bdd-134">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="d9bdd-135">2</span><span class="sxs-lookup"><span data-stu-id="d9bdd-135">2</span></span>  <br/> |<span data-ttu-id="d9bdd-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="d9bdd-136">AnyUser</span></span>  <br/> |<span data-ttu-id="d9bdd-137">Oggetto Principal generico di tipo utente.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-137">Generic principal of user type.</span></span> <span data-ttu-id="d9bdd-138">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="d9bdd-139">Sì</span><span class="sxs-lookup"><span data-stu-id="d9bdd-139">Yes</span></span>  <br/> |
|<span data-ttu-id="d9bdd-140">3</span><span class="sxs-lookup"><span data-stu-id="d9bdd-140">3</span></span>  <br/> |<span data-ttu-id="d9bdd-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="d9bdd-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="d9bdd-142">Entità generica con semantica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-142">Generic principal with group semantic.</span></span> <span data-ttu-id="d9bdd-143">Non usato nella tabella tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="d9bdd-144">4</span><span class="sxs-lookup"><span data-stu-id="d9bdd-144">4</span></span>  <br/> |<span data-ttu-id="d9bdd-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="d9bdd-145">SystemUser</span></span>  <br/> |<span data-ttu-id="d9bdd-146">Principal usato internamente dal server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="d9bdd-147">5</span><span class="sxs-lookup"><span data-stu-id="d9bdd-147">5</span></span>  <br/> |<span data-ttu-id="d9bdd-148">Utente</span><span class="sxs-lookup"><span data-stu-id="d9bdd-148">User</span></span>  <br/> |<span data-ttu-id="d9bdd-149">Utente normale.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-149">Regular user.</span></span>  <br/> |<span data-ttu-id="d9bdd-150">Sì</span><span class="sxs-lookup"><span data-stu-id="d9bdd-150">Yes</span></span>  <br/> |
|<span data-ttu-id="d9bdd-151">8</span><span class="sxs-lookup"><span data-stu-id="d9bdd-151">8</span></span>  <br/> |<span data-ttu-id="d9bdd-152">DC</span><span class="sxs-lookup"><span data-stu-id="d9bdd-152">DC</span></span>  <br/> |<span data-ttu-id="d9bdd-153">Controller di dominio Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="d9bdd-154">9</span><span class="sxs-lookup"><span data-stu-id="d9bdd-154">9</span></span>  <br/> |<span data-ttu-id="d9bdd-155">Gruppo</span><span class="sxs-lookup"><span data-stu-id="d9bdd-155">Group</span></span>  <br/> |<span data-ttu-id="d9bdd-156">Gruppo di sicurezza di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="d9bdd-157">10</span><span class="sxs-lookup"><span data-stu-id="d9bdd-157">10</span></span>  <br/> |<span data-ttu-id="d9bdd-158">Cartella</span><span class="sxs-lookup"><span data-stu-id="d9bdd-158">Folder</span></span>  <br/> |<span data-ttu-id="d9bdd-159">Contenitore o unità organizzativa di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d9bdd-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="d9bdd-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9bdd-160">See also</span></span>

[<span data-ttu-id="d9bdd-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="d9bdd-161">tblPrincipal</span></span>](tblprincipal.md)
