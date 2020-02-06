---
title: Tabella Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809554"
---
# <a name="endpoint-table"></a><span data-ttu-id="1f56e-104">Tabella Endpoint</span><span class="sxs-lookup"><span data-stu-id="1f56e-104">Endpoint table</span></span>
 
<span data-ttu-id="1f56e-105">La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="1f56e-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1f56e-106">Ogni record nella tabella rappresenta un endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="1f56e-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1f56e-107">**Column**</span></span>|<span data-ttu-id="1f56e-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="1f56e-108">**Data Type**</span></span>|<span data-ttu-id="1f56e-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="1f56e-109">**Key/Index**</span></span>|<span data-ttu-id="1f56e-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1f56e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f56e-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="1f56e-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="1f56e-112">int</span><span class="sxs-lookup"><span data-stu-id="1f56e-112">int</span></span>  <br/> |<span data-ttu-id="1f56e-113">Principale</span><span class="sxs-lookup"><span data-stu-id="1f56e-113">Primary</span></span>  <br/> |<span data-ttu-id="1f56e-114">Numero univoco che identifica questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="1f56e-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1f56e-115">**Name**</span></span> <br/> |<span data-ttu-id="1f56e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1f56e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1f56e-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="1f56e-117">Unique</span></span>  <br/> |<span data-ttu-id="1f56e-118">Nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="1f56e-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="1f56e-119">**OS**</span></span> <br/> |<span data-ttu-id="1f56e-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="1f56e-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="1f56e-121">Sistema operativo (OS) dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1f56e-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="1f56e-122">**CPUName**</span></span> <br/> |<span data-ttu-id="1f56e-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="1f56e-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="1f56e-124">Nome della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1f56e-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="1f56e-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="1f56e-126">smallint</span><span class="sxs-lookup"><span data-stu-id="1f56e-126">smallint</span></span>  <br/> ||<span data-ttu-id="1f56e-127">Numero di core della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1f56e-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="1f56e-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="1f56e-129">int</span><span class="sxs-lookup"><span data-stu-id="1f56e-129">int</span></span>  <br/> ||<span data-ttu-id="1f56e-130">Velocità del processore della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1f56e-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="1f56e-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="1f56e-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="1f56e-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="1f56e-132">tinyint</span></span>  <br/> || <span data-ttu-id="1f56e-133">Flag di bit che indica se il sistema è in uso in un ambiente virtualizzato:</span><span class="sxs-lookup"><span data-stu-id="1f56e-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="1f56e-134">0x0000-None</span><span class="sxs-lookup"><span data-stu-id="1f56e-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="1f56e-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="1f56e-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="1f56e-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="1f56e-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="1f56e-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="1f56e-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="1f56e-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="1f56e-138">0x0008 - Xen PC</span></span> <br/> |
   

