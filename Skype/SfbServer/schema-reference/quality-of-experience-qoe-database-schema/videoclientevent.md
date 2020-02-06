---
title: Tabella VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Ogni record contiene l'evento client per un endpoint in una videochiamata. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804994"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="6e2a8-104">Tabella VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="6e2a8-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="6e2a8-105">Ogni record contiene l'evento client per un endpoint in una videochiamata.</span><span class="sxs-lookup"><span data-stu-id="6e2a8-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="6e2a8-106">In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.</span><span class="sxs-lookup"><span data-stu-id="6e2a8-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="6e2a8-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-107">**Column**</span></span>|<span data-ttu-id="6e2a8-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-108">**Data Type**</span></span>|<span data-ttu-id="6e2a8-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-109">**Key/Index**</span></span>|<span data-ttu-id="6e2a8-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e2a8-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="6e2a8-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="6e2a8-112">datetime</span></span>  <br/> |<span data-ttu-id="6e2a8-113">Principale</span><span class="sxs-lookup"><span data-stu-id="6e2a8-113">Primary</span></span>  <br/> |<span data-ttu-id="6e2a8-114">A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="6e2a8-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6e2a8-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="6e2a8-116">int</span><span class="sxs-lookup"><span data-stu-id="6e2a8-116">int</span></span>  <br/> |<span data-ttu-id="6e2a8-117">Principale</span><span class="sxs-lookup"><span data-stu-id="6e2a8-117">Primary</span></span>  <br/> |<span data-ttu-id="6e2a8-118">A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="6e2a8-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6e2a8-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="6e2a8-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="6e2a8-120">tinyint</span></span>  <br/> |<span data-ttu-id="6e2a8-121">Principale</span><span class="sxs-lookup"><span data-stu-id="6e2a8-121">Primary</span></span>  <br/> |<span data-ttu-id="6e2a8-122">A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="6e2a8-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="6e2a8-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="6e2a8-124">po'</span><span class="sxs-lookup"><span data-stu-id="6e2a8-124">bit</span></span>  <br/> |<span data-ttu-id="6e2a8-125">Principale</span><span class="sxs-lookup"><span data-stu-id="6e2a8-125">Primary</span></span>  <br/> |<span data-ttu-id="6e2a8-126">0: dati del destinatario</span><span class="sxs-lookup"><span data-stu-id="6e2a8-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="6e2a8-127">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="6e2a8-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="6e2a8-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="6e2a8-129">Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="6e2a8-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="6e2a8-130">La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="6e2a8-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="6e2a8-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="6e2a8-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="6e2a8-132">Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".</span><span class="sxs-lookup"><span data-stu-id="6e2a8-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="6e2a8-133">La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="6e2a8-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

