---
title: Tabella SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabella SessionCorrelation è una tabella di supporto. Ogni record rappresenta un correlationID utilizzato per correlare più sessioni.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802656"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="2ff37-104">Tabella SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="2ff37-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="2ff37-105">La tabella SessionCorrelation è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="2ff37-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="2ff37-106">Ogni record rappresenta un correlationID utilizzato per correlare più sessioni.</span><span class="sxs-lookup"><span data-stu-id="2ff37-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="2ff37-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2ff37-107">**Column**</span></span>|<span data-ttu-id="2ff37-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2ff37-108">**Data Type**</span></span>|<span data-ttu-id="2ff37-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2ff37-109">**Key/Index**</span></span>|<span data-ttu-id="2ff37-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2ff37-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ff37-111">**Checksum**</span><span class="sxs-lookup"><span data-stu-id="2ff37-111">**Checksum**</span></span> <br/> |<span data-ttu-id="2ff37-112">int</span><span class="sxs-lookup"><span data-stu-id="2ff37-112">int</span></span>  <br/> |||
|<span data-ttu-id="2ff37-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="2ff37-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="2ff37-114">int</span><span class="sxs-lookup"><span data-stu-id="2ff37-114">int</span></span>  <br/> |<span data-ttu-id="2ff37-115">Principale</span><span class="sxs-lookup"><span data-stu-id="2ff37-115">Primary</span></span>  <br/> |<span data-ttu-id="2ff37-116">Numero univoco che identifica questo A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="2ff37-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="2ff37-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="2ff37-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="2ff37-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ff37-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2ff37-119">Univoco</span><span class="sxs-lookup"><span data-stu-id="2ff37-119">Unique</span></span>  <br/> |<span data-ttu-id="2ff37-120">Le sessioni correlate avranno lo stesso ID correlazione.</span><span class="sxs-lookup"><span data-stu-id="2ff37-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="2ff37-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2ff37-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2ff37-122">datetime</span><span class="sxs-lookup"><span data-stu-id="2ff37-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="2ff37-123">Solo per uso interno.</span><span class="sxs-lookup"><span data-stu-id="2ff37-123">For internal use only.</span></span>  <br/> |
   

