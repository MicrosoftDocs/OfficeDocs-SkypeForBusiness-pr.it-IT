---
title: Tabella SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un CorrelationID usato per correlare più sessioni.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805744"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="8c5f6-104">Tabella SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="8c5f6-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="8c5f6-105">La tabella SessionCorrelation è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="8c5f6-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="8c5f6-106">Ogni record rappresenta un CorrelationID usato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="8c5f6-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="8c5f6-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-107">**Column**</span></span>|<span data-ttu-id="8c5f6-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-108">**Data Type**</span></span>|<span data-ttu-id="8c5f6-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-109">**Key/Index**</span></span>|<span data-ttu-id="8c5f6-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c5f6-111">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-111">**Checksum**</span></span> <br/> |<span data-ttu-id="8c5f6-112">int</span><span class="sxs-lookup"><span data-stu-id="8c5f6-112">int</span></span>  <br/> |||
|<span data-ttu-id="8c5f6-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="8c5f6-114">int</span><span class="sxs-lookup"><span data-stu-id="8c5f6-114">int</span></span>  <br/> |<span data-ttu-id="8c5f6-115">Principale</span><span class="sxs-lookup"><span data-stu-id="8c5f6-115">Primary</span></span>  <br/> |<span data-ttu-id="8c5f6-116">Numero univoco che identifica questo server di conferenza A/V.</span><span class="sxs-lookup"><span data-stu-id="8c5f6-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="8c5f6-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="8c5f6-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8c5f6-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8c5f6-119">Univoci</span><span class="sxs-lookup"><span data-stu-id="8c5f6-119">Unique</span></span>  <br/> |<span data-ttu-id="8c5f6-120">Le sessioni correlate avranno lo stesso ID di correlazione.</span><span class="sxs-lookup"><span data-stu-id="8c5f6-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="8c5f6-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8c5f6-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8c5f6-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c5f6-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="8c5f6-123">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="8c5f6-123">For internal use only.</span></span>  <br/> |
   

