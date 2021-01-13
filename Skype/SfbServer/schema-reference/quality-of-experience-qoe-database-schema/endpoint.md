---
title: Tabella endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823066"
---
# <a name="endpoint-table"></a><span data-ttu-id="92097-104">Tabella endpoint</span><span class="sxs-lookup"><span data-stu-id="92097-104">Endpoint table</span></span>
 
<span data-ttu-id="92097-105">La tabella endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="92097-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="92097-106">Ogni record nella tabella rappresenta un endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="92097-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="92097-107">**Column**</span></span>|<span data-ttu-id="92097-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="92097-108">**Data Type**</span></span>|<span data-ttu-id="92097-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="92097-109">**Key/Index**</span></span>|<span data-ttu-id="92097-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="92097-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92097-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="92097-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="92097-112">int</span><span class="sxs-lookup"><span data-stu-id="92097-112">int</span></span>  <br/> |<span data-ttu-id="92097-113">Principale</span><span class="sxs-lookup"><span data-stu-id="92097-113">Primary</span></span>  <br/> |<span data-ttu-id="92097-114">Numero univoco che identifica l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="92097-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="92097-115">**Name**</span></span> <br/> |<span data-ttu-id="92097-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="92097-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="92097-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="92097-117">Unique</span></span>  <br/> |<span data-ttu-id="92097-118">Nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="92097-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="92097-119">**OS**</span></span> <br/> |<span data-ttu-id="92097-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="92097-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="92097-121">Sistema operativo (OS) dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="92097-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="92097-122">**CPUName**</span></span> <br/> |<span data-ttu-id="92097-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="92097-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="92097-124">Nome della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="92097-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="92097-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="92097-126">smallint</span><span class="sxs-lookup"><span data-stu-id="92097-126">smallint</span></span>  <br/> ||<span data-ttu-id="92097-127">Numero di core della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="92097-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="92097-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="92097-129">int</span><span class="sxs-lookup"><span data-stu-id="92097-129">int</span></span>  <br/> ||<span data-ttu-id="92097-130">Velocità del processore della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="92097-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="92097-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="92097-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="92097-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="92097-132">tinyint</span></span>  <br/> || <span data-ttu-id="92097-133">Flag di bit che indica se il sistema è in esecuzione in un ambiente virtualizzato:</span><span class="sxs-lookup"><span data-stu-id="92097-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="92097-134">0x0000-None</span><span class="sxs-lookup"><span data-stu-id="92097-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="92097-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="92097-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="92097-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="92097-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="92097-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="92097-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="92097-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="92097-138">0x0008 - Xen PC</span></span> <br/> |
   

