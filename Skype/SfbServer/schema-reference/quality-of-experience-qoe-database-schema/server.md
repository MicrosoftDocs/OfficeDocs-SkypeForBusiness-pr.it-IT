---
title: Tabella Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabella server è una tabella di supporto. Ogni record rappresenta un server.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806134"
---
# <a name="server-table"></a><span data-ttu-id="112ff-104">Tabella Server</span><span class="sxs-lookup"><span data-stu-id="112ff-104">Server table</span></span>
 
<span data-ttu-id="112ff-105">La tabella server è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="112ff-105">The Server table is a supporting table.</span></span> <span data-ttu-id="112ff-106">Ogni record rappresenta un server.</span><span class="sxs-lookup"><span data-stu-id="112ff-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="112ff-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="112ff-107">**Column**</span></span>|<span data-ttu-id="112ff-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="112ff-108">**Data Type**</span></span>|<span data-ttu-id="112ff-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="112ff-109">**Key/Index**</span></span>|<span data-ttu-id="112ff-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="112ff-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="112ff-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="112ff-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="112ff-112">int</span><span class="sxs-lookup"><span data-stu-id="112ff-112">int</span></span>  <br/> |<span data-ttu-id="112ff-113">Principale</span><span class="sxs-lookup"><span data-stu-id="112ff-113">Primary</span></span>  <br/> |<span data-ttu-id="112ff-114">Numero univoco che identifica il server.</span><span class="sxs-lookup"><span data-stu-id="112ff-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="112ff-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="112ff-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="112ff-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="112ff-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="112ff-117">Indice</span><span class="sxs-lookup"><span data-stu-id="112ff-117">index</span></span>  <br/> |<span data-ttu-id="112ff-118">Stringa dell'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="112ff-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="112ff-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="112ff-119">**ServerType**</span></span> <br/> |<span data-ttu-id="112ff-120">int</span><span class="sxs-lookup"><span data-stu-id="112ff-120">int</span></span>  <br/> |<span data-ttu-id="112ff-121">Esterna</span><span class="sxs-lookup"><span data-stu-id="112ff-121">Foreign</span></span>  <br/> |<span data-ttu-id="112ff-122">1: Mediation Server</span><span class="sxs-lookup"><span data-stu-id="112ff-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="112ff-123">2: a/V Conferencing Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="112ff-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="112ff-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="112ff-124">**PoolName**</span></span> <br/> |<span data-ttu-id="112ff-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="112ff-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="112ff-126">Pool a cui appartiene il server.</span><span class="sxs-lookup"><span data-stu-id="112ff-126">Pool the server belongs to.</span></span> <span data-ttu-id="112ff-127">Applicabile solo per l'A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="112ff-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="112ff-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="112ff-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="112ff-129">DateTime</span><span class="sxs-lookup"><span data-stu-id="112ff-129">datetime</span></span>  <br/> ||<span data-ttu-id="112ff-130">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="112ff-130">For internal use only.</span></span>  <br/> |
   

