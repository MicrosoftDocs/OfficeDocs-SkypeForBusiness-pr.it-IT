---
title: Tabella User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un solo utente.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805094"
---
# <a name="user-table"></a><span data-ttu-id="32c64-104">Tabella User</span><span class="sxs-lookup"><span data-stu-id="32c64-104">User table</span></span>
 
<span data-ttu-id="32c64-105">La tabella utente è una tabella di supporto in cui è archiviato un elenco dei vari utenti che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="32c64-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="32c64-106">Ogni record nella tabella rappresenta un solo utente.</span><span class="sxs-lookup"><span data-stu-id="32c64-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="32c64-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="32c64-107">**Column**</span></span>|<span data-ttu-id="32c64-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="32c64-108">**Data Type**</span></span>|<span data-ttu-id="32c64-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="32c64-109">**Key/Index**</span></span>|<span data-ttu-id="32c64-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="32c64-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32c64-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="32c64-111">**UserKey**</span></span> <br/> |<span data-ttu-id="32c64-112">int</span><span class="sxs-lookup"><span data-stu-id="32c64-112">int</span></span>  <br/> |<span data-ttu-id="32c64-113">Principale</span><span class="sxs-lookup"><span data-stu-id="32c64-113">Primary</span></span>  <br/> |<span data-ttu-id="32c64-114">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="32c64-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="32c64-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="32c64-115">**URI**</span></span> <br/> |<span data-ttu-id="32c64-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="32c64-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="32c64-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="32c64-117">Unique</span></span>  <br/> |<span data-ttu-id="32c64-118">Stringa URI.</span><span class="sxs-lookup"><span data-stu-id="32c64-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="32c64-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="32c64-119">**URIType**</span></span> <br/> |<span data-ttu-id="32c64-120">int</span><span class="sxs-lookup"><span data-stu-id="32c64-120">int</span></span>  <br/> ||<span data-ttu-id="32c64-121">1 è un tipo URI sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="32c64-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="32c64-122">2 è l'URI dell'utente.</span><span class="sxs-lookup"><span data-stu-id="32c64-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="32c64-123">4 è l'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="32c64-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="32c64-124">8 è l'URI del telefono.</span><span class="sxs-lookup"><span data-stu-id="32c64-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="32c64-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="32c64-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="32c64-126">int</span><span class="sxs-lookup"><span data-stu-id="32c64-126">int</span></span>  <br/> |<span data-ttu-id="32c64-127">Esterna</span><span class="sxs-lookup"><span data-stu-id="32c64-127">Foreign</span></span>  <br/> |<span data-ttu-id="32c64-128">Tenant dell'utente, a cui si fa riferimento dalla tabella tenant.</span><span class="sxs-lookup"><span data-stu-id="32c64-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="32c64-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="32c64-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="32c64-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="32c64-130">datetime</span></span>  <br/> ||<span data-ttu-id="32c64-131">Indicatore di data e ora più recente quando l'utente ha ricevuto una chiamata audio scadente.</span><span class="sxs-lookup"><span data-stu-id="32c64-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="32c64-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="32c64-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="32c64-133">DateTime</span><span class="sxs-lookup"><span data-stu-id="32c64-133">datetime</span></span>  <br/> ||<span data-ttu-id="32c64-134">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="32c64-134">For internal use only.</span></span>  <br/> |
   

