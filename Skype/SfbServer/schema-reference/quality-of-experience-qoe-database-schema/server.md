---
title: Tabella server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabella server è una tabella di supporto. Ogni record rappresenta un server.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802706"
---
# <a name="server-table"></a><span data-ttu-id="3eb29-104">Tabella server</span><span class="sxs-lookup"><span data-stu-id="3eb29-104">Server table</span></span>
 
<span data-ttu-id="3eb29-105">La tabella server è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="3eb29-105">The Server table is a supporting table.</span></span> <span data-ttu-id="3eb29-106">Ogni record rappresenta un server.</span><span class="sxs-lookup"><span data-stu-id="3eb29-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="3eb29-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="3eb29-107">**Column**</span></span>|<span data-ttu-id="3eb29-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="3eb29-108">**Data Type**</span></span>|<span data-ttu-id="3eb29-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="3eb29-109">**Key/Index**</span></span>|<span data-ttu-id="3eb29-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3eb29-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3eb29-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="3eb29-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="3eb29-112">int</span><span class="sxs-lookup"><span data-stu-id="3eb29-112">int</span></span>  <br/> |<span data-ttu-id="3eb29-113">Principale</span><span class="sxs-lookup"><span data-stu-id="3eb29-113">Primary</span></span>  <br/> |<span data-ttu-id="3eb29-114">Numero univoco che identifica il server.</span><span class="sxs-lookup"><span data-stu-id="3eb29-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="3eb29-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="3eb29-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="3eb29-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3eb29-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3eb29-117">Indice</span><span class="sxs-lookup"><span data-stu-id="3eb29-117">index</span></span>  <br/> |<span data-ttu-id="3eb29-118">Stringa dell'indirizzo MAC.</span><span class="sxs-lookup"><span data-stu-id="3eb29-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="3eb29-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="3eb29-119">**ServerType**</span></span> <br/> |<span data-ttu-id="3eb29-120">int</span><span class="sxs-lookup"><span data-stu-id="3eb29-120">int</span></span>  <br/> |<span data-ttu-id="3eb29-121">Stranieri</span><span class="sxs-lookup"><span data-stu-id="3eb29-121">Foreign</span></span>  <br/> |<span data-ttu-id="3eb29-122">1: Mediation Server</span><span class="sxs-lookup"><span data-stu-id="3eb29-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="3eb29-123">2: a/V Conferencing Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="3eb29-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="3eb29-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="3eb29-124">**PoolName**</span></span> <br/> |<span data-ttu-id="3eb29-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3eb29-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="3eb29-126">Pool a cui appartiene il server.</span><span class="sxs-lookup"><span data-stu-id="3eb29-126">Pool the server belongs to.</span></span> <span data-ttu-id="3eb29-127">Applicabile solo per l'A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="3eb29-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="3eb29-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3eb29-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3eb29-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3eb29-129">datetime</span></span>  <br/> ||<span data-ttu-id="3eb29-130">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="3eb29-130">For internal use only.</span></span>  <br/> |
   

