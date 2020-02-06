---
title: Tabella Conference
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La tabella conferenze è una tabella di supporto. Ogni record rappresenta una conferenza o una sessione peer-to-peer.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810304"
---
# <a name="conference-table"></a><span data-ttu-id="4ba36-104">Tabella Conference</span><span class="sxs-lookup"><span data-stu-id="4ba36-104">Conference table</span></span>
 
<span data-ttu-id="4ba36-105">La tabella conferenze è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="4ba36-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="4ba36-106">Ogni record rappresenta una conferenza o una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="4ba36-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="4ba36-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4ba36-107">**Column**</span></span>|<span data-ttu-id="4ba36-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="4ba36-108">**Data Type**</span></span>|<span data-ttu-id="4ba36-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="4ba36-109">**Key/Index**</span></span>|<span data-ttu-id="4ba36-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="4ba36-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ba36-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="4ba36-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="4ba36-112">int</span><span class="sxs-lookup"><span data-stu-id="4ba36-112">int</span></span>  <br/> |<span data-ttu-id="4ba36-113">Principale</span><span class="sxs-lookup"><span data-stu-id="4ba36-113">Primary</span></span>  <br/> |<span data-ttu-id="4ba36-114">Numero univoco che identifica questo record della conferenza.</span><span class="sxs-lookup"><span data-stu-id="4ba36-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="4ba36-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="4ba36-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="4ba36-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4ba36-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4ba36-117">univoci</span><span class="sxs-lookup"><span data-stu-id="4ba36-117">unique</span></span>  <br/> |<span data-ttu-id="4ba36-118">URI conferenza se si tratta di una conferenza o di DialogID se si tratta di una sessione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="4ba36-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="4ba36-119">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="4ba36-119">**Checksum**</span></span> <br/> |<span data-ttu-id="4ba36-120">int</span><span class="sxs-lookup"><span data-stu-id="4ba36-120">int</span></span>  <br/> |<span data-ttu-id="4ba36-121">Indice</span><span class="sxs-lookup"><span data-stu-id="4ba36-121">index</span></span>  <br/> |<span data-ttu-id="4ba36-122">Checksum dell'URI della conferenza.</span><span class="sxs-lookup"><span data-stu-id="4ba36-122">Checksum of the conference URI.</span></span> <span data-ttu-id="4ba36-123">Viene usato internamente.</span><span class="sxs-lookup"><span data-stu-id="4ba36-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="4ba36-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4ba36-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4ba36-125">DateTime</span><span class="sxs-lookup"><span data-stu-id="4ba36-125">datetime</span></span>  <br/> ||<span data-ttu-id="4ba36-126">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="4ba36-126">For internal use only.</span></span>  <br/> |
   

