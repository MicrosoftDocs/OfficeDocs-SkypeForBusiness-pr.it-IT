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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database. Ogni record nella tabella rappresenta un endpoint.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194621"
---
# <a name="endpoint-table"></a><span data-ttu-id="06a65-104">Tabella Endpoint</span><span class="sxs-lookup"><span data-stu-id="06a65-104">Endpoint table</span></span>
 
<span data-ttu-id="06a65-105">La tabella di endpoint è una tabella di supporto in cui vengono archiviate informazioni sugli endpoint che hanno partecipato a sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="06a65-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="06a65-106">Ogni record nella tabella rappresenta un endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="06a65-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="06a65-107">**Column**</span></span>|<span data-ttu-id="06a65-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="06a65-108">**Data Type**</span></span>|<span data-ttu-id="06a65-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="06a65-109">**Key/Index**</span></span>|<span data-ttu-id="06a65-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="06a65-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06a65-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="06a65-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="06a65-112">int</span><span class="sxs-lookup"><span data-stu-id="06a65-112">int</span></span>  <br/> |<span data-ttu-id="06a65-113">Principale</span><span class="sxs-lookup"><span data-stu-id="06a65-113">Primary</span></span>  <br/> |<span data-ttu-id="06a65-114">Numero univoco che identifica questo endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="06a65-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="06a65-115">**Name**</span></span> <br/> |<span data-ttu-id="06a65-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="06a65-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="06a65-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="06a65-117">Unique</span></span>  <br/> |<span data-ttu-id="06a65-118">Nome dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="06a65-119">**OS**</span><span class="sxs-lookup"><span data-stu-id="06a65-119">**OS**</span></span> <br/> |<span data-ttu-id="06a65-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="06a65-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="06a65-121">Sistema operativo (OS) dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="06a65-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="06a65-122">**CPUName**</span></span> <br/> |<span data-ttu-id="06a65-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="06a65-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="06a65-124">Nome della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="06a65-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="06a65-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="06a65-126">smallint</span><span class="sxs-lookup"><span data-stu-id="06a65-126">smallint</span></span>  <br/> ||<span data-ttu-id="06a65-127">Numero di core della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="06a65-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="06a65-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="06a65-129">int</span><span class="sxs-lookup"><span data-stu-id="06a65-129">int</span></span>  <br/> ||<span data-ttu-id="06a65-130">Velocità del processore della CPU dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="06a65-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="06a65-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="06a65-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="06a65-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="06a65-132">tinyint</span></span>  <br/> || <span data-ttu-id="06a65-133">Flag di bit che indica se il sistema è in uso in un ambiente virtualizzato:</span><span class="sxs-lookup"><span data-stu-id="06a65-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="06a65-134">0x0000-None</span><span class="sxs-lookup"><span data-stu-id="06a65-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="06a65-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="06a65-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="06a65-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="06a65-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="06a65-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="06a65-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="06a65-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="06a65-138">0x0008 - Xen PC</span></span> <br/> |
   

