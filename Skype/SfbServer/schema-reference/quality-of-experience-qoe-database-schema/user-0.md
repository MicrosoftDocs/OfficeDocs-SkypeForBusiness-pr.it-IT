---
title: Tabella user
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800076"
---
# <a name="user-table"></a><span data-ttu-id="ac27f-104">Tabella user</span><span class="sxs-lookup"><span data-stu-id="ac27f-104">User table</span></span>
 
<span data-ttu-id="ac27f-p102">La tabella User è una tabella di supporto in cui è archiviato un elenco dei diversi utenti che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta un utente.</span><span class="sxs-lookup"><span data-stu-id="ac27f-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="ac27f-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ac27f-107">**Column**</span></span>|<span data-ttu-id="ac27f-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ac27f-108">**Data Type**</span></span>|<span data-ttu-id="ac27f-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="ac27f-109">**Key/Index**</span></span>|<span data-ttu-id="ac27f-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ac27f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac27f-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="ac27f-111">**UserKey**</span></span> <br/> |<span data-ttu-id="ac27f-112">int</span><span class="sxs-lookup"><span data-stu-id="ac27f-112">int</span></span>  <br/> |<span data-ttu-id="ac27f-113">Principale</span><span class="sxs-lookup"><span data-stu-id="ac27f-113">Primary</span></span>  <br/> |<span data-ttu-id="ac27f-114">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="ac27f-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ac27f-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="ac27f-115">**URI**</span></span> <br/> |<span data-ttu-id="ac27f-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ac27f-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ac27f-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="ac27f-117">Unique</span></span>  <br/> |<span data-ttu-id="ac27f-118">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="ac27f-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="ac27f-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="ac27f-119">**URIType**</span></span> <br/> |<span data-ttu-id="ac27f-120">int</span><span class="sxs-lookup"><span data-stu-id="ac27f-120">int</span></span>  <br/> ||<span data-ttu-id="ac27f-121">1 è un tipo di URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac27f-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="ac27f-122">2 è un URI utente.</span><span class="sxs-lookup"><span data-stu-id="ac27f-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="ac27f-123">4 è un URI conferenza.</span><span class="sxs-lookup"><span data-stu-id="ac27f-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="ac27f-124">8 è un URI telefono.</span><span class="sxs-lookup"><span data-stu-id="ac27f-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="ac27f-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="ac27f-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="ac27f-126">int</span><span class="sxs-lookup"><span data-stu-id="ac27f-126">int</span></span>  <br/> |<span data-ttu-id="ac27f-127">Stranieri</span><span class="sxs-lookup"><span data-stu-id="ac27f-127">Foreign</span></span>  <br/> |<span data-ttu-id="ac27f-128">Tenant dell'utente, cui viene fatto riferimento dalla tabella Tenant.</span><span class="sxs-lookup"><span data-stu-id="ac27f-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="ac27f-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="ac27f-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="ac27f-130">datetime</span><span class="sxs-lookup"><span data-stu-id="ac27f-130">datetime</span></span>  <br/> ||<span data-ttu-id="ac27f-131">Ultimo indicatore di data e ora in cui si è verificata una chiamata audio di qualità scadente per l'utente.</span><span class="sxs-lookup"><span data-stu-id="ac27f-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="ac27f-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="ac27f-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="ac27f-133">datetime</span><span class="sxs-lookup"><span data-stu-id="ac27f-133">datetime</span></span>  <br/> ||<span data-ttu-id="ac27f-134">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="ac27f-134">For internal use only.</span></span>  <br/> |
   

