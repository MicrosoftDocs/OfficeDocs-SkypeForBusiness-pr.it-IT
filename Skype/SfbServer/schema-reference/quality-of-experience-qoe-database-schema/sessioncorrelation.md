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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un CorrelationID usato per correlare più sessioni.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194576"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="1df42-104">Tabella SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="1df42-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="1df42-105">La tabella SessionCorrelation è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="1df42-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="1df42-106">Ogni record rappresenta un CorrelationID usato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="1df42-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="1df42-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1df42-107">**Column**</span></span>|<span data-ttu-id="1df42-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="1df42-108">**Data Type**</span></span>|<span data-ttu-id="1df42-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="1df42-109">**Key/Index**</span></span>|<span data-ttu-id="1df42-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1df42-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1df42-111">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="1df42-111">**Checksum**</span></span> <br/> |<span data-ttu-id="1df42-112">int</span><span class="sxs-lookup"><span data-stu-id="1df42-112">int</span></span>  <br/> |||
|<span data-ttu-id="1df42-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="1df42-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="1df42-114">int</span><span class="sxs-lookup"><span data-stu-id="1df42-114">int</span></span>  <br/> |<span data-ttu-id="1df42-115">Principale</span><span class="sxs-lookup"><span data-stu-id="1df42-115">Primary</span></span>  <br/> |<span data-ttu-id="1df42-116">Numero univoco che identifica questo server di conferenza A/V.</span><span class="sxs-lookup"><span data-stu-id="1df42-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="1df42-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="1df42-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="1df42-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1df42-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1df42-119">Univoci</span><span class="sxs-lookup"><span data-stu-id="1df42-119">Unique</span></span>  <br/> |<span data-ttu-id="1df42-120">Le sessioni correlate avranno lo stesso ID di correlazione.</span><span class="sxs-lookup"><span data-stu-id="1df42-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="1df42-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1df42-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1df42-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="1df42-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="1df42-123">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="1df42-123">For internal use only.</span></span>  <br/> |
   

