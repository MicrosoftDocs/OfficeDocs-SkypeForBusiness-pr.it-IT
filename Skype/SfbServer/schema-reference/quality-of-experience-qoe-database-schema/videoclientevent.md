---
title: Tabella VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Ogni record contiene l'evento client per un endpoint in una chiamata video. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821396"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="d66a6-104">Tabella VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="d66a6-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="d66a6-105">Ogni record contiene l'evento client per un endpoint in una chiamata video.</span><span class="sxs-lookup"><span data-stu-id="d66a6-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d66a6-106">In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d66a6-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="d66a6-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="d66a6-107">**Column**</span></span>|<span data-ttu-id="d66a6-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="d66a6-108">**Data Type**</span></span>|<span data-ttu-id="d66a6-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="d66a6-109">**Key/Index**</span></span>|<span data-ttu-id="d66a6-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="d66a6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d66a6-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d66a6-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d66a6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d66a6-112">datetime</span></span>  <br/> |<span data-ttu-id="d66a6-113">Principale</span><span class="sxs-lookup"><span data-stu-id="d66a6-113">Primary</span></span>  <br/> |<span data-ttu-id="d66a6-114">Riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d66a6-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d66a6-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d66a6-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d66a6-116">int</span><span class="sxs-lookup"><span data-stu-id="d66a6-116">int</span></span>  <br/> |<span data-ttu-id="d66a6-117">Principale</span><span class="sxs-lookup"><span data-stu-id="d66a6-117">Primary</span></span>  <br/> |<span data-ttu-id="d66a6-118">Riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d66a6-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d66a6-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d66a6-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d66a6-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d66a6-120">tinyint</span></span>  <br/> |<span data-ttu-id="d66a6-121">Principale</span><span class="sxs-lookup"><span data-stu-id="d66a6-121">Primary</span></span>  <br/> |<span data-ttu-id="d66a6-122">Riferimento dalla [Tabella MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="d66a6-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d66a6-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d66a6-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="d66a6-124">po'</span><span class="sxs-lookup"><span data-stu-id="d66a6-124">bit</span></span>  <br/> |<span data-ttu-id="d66a6-125">Principale</span><span class="sxs-lookup"><span data-stu-id="d66a6-125">Primary</span></span>  <br/> |<span data-ttu-id="d66a6-126">0: dati del destinatario della chiamata</span><span class="sxs-lookup"><span data-stu-id="d66a6-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="d66a6-127">1: dati del chiamante</span><span class="sxs-lookup"><span data-stu-id="d66a6-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="d66a6-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d66a6-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d66a6-129">Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="d66a6-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="d66a6-130">La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.</span><span class="sxs-lookup"><span data-stu-id="d66a6-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="d66a6-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d66a6-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d66a6-132">Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="d66a6-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="d66a6-133">La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="d66a6-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

