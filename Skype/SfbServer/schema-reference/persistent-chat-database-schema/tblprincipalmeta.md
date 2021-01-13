---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831546"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="70b61-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="70b61-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="70b61-104">tblPrincipalMeta contiene le entità che devono essere aggiornate da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70b61-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="70b61-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="70b61-105">**Columns**</span></span>

|<span data-ttu-id="70b61-106">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="70b61-106">**Column**</span></span>|<span data-ttu-id="70b61-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="70b61-107">**Type**</span></span>|<span data-ttu-id="70b61-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="70b61-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70b61-109">prinID</span><span class="sxs-lookup"><span data-stu-id="70b61-109">prinID</span></span>  <br/> |<span data-ttu-id="70b61-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="70b61-110">int, not null</span></span>  <br/> |<span data-ttu-id="70b61-111">ID entità.</span><span class="sxs-lookup"><span data-stu-id="70b61-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="70b61-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="70b61-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="70b61-113">bit, non null</span><span class="sxs-lookup"><span data-stu-id="70b61-113">bit, not null</span></span>  <br/> |<span data-ttu-id="70b61-114">True se le affiliazioni delle entità devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="70b61-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="70b61-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="70b61-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="70b61-116">bit, non null</span><span class="sxs-lookup"><span data-stu-id="70b61-116">bit, not null</span></span>  <br/> |<span data-ttu-id="70b61-117">True se gli attributi delle entità devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="70b61-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="70b61-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="70b61-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="70b61-119">bit, non null</span><span class="sxs-lookup"><span data-stu-id="70b61-119">bit, not null</span></span>  <br/> |<span data-ttu-id="70b61-120">True se l'entità è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="70b61-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="70b61-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="70b61-121">tryCount</span></span>  <br/> |<span data-ttu-id="70b61-122">int</span><span class="sxs-lookup"><span data-stu-id="70b61-122">int</span></span>  <br/> |<span data-ttu-id="70b61-123">Numero di tentativi di aggiornamento dell'entità eseguiti fino a questo momento da Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70b61-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="70b61-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="70b61-124">lastTry</span></span>  <br/> |<span data-ttu-id="70b61-125">datetime</span><span class="sxs-lookup"><span data-stu-id="70b61-125">datetime</span></span>  <br/> |<span data-ttu-id="70b61-p101">Indicatore di data e ora del tentativo più recente di aggiornamento dell'entità. Può essere Null se non è ancora stato eseguito alcun tentativo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="70b61-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="70b61-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="70b61-128">nextTry</span></span>  <br/> |<span data-ttu-id="70b61-129">datetime</span><span class="sxs-lookup"><span data-stu-id="70b61-129">datetime</span></span>  <br/> |<span data-ttu-id="70b61-p102">Indicatore di data e ora del successivo aggiornamento pianificato. Può essere Null se non sono stati pianificati ulteriori aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="70b61-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="70b61-132">**Chiavi**</span><span class="sxs-lookup"><span data-stu-id="70b61-132">**Keys**</span></span>

|<span data-ttu-id="70b61-133">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="70b61-133">**Column**</span></span>|<span data-ttu-id="70b61-134">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="70b61-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70b61-135">prinID</span><span class="sxs-lookup"><span data-stu-id="70b61-135">prinID</span></span>  <br/> |<span data-ttu-id="70b61-136">Chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="70b61-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="70b61-137">prinID</span><span class="sxs-lookup"><span data-stu-id="70b61-137">prinID</span></span>  <br/> |<span data-ttu-id="70b61-138">Chiave esterna con ricerca nella tabella tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="70b61-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

