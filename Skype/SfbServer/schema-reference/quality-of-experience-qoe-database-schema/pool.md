---
title: Tabella Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194595"
---
# <a name="pool-table"></a><span data-ttu-id="e44da-104">Tabella Pool</span><span class="sxs-lookup"><span data-stu-id="e44da-104">Pool table</span></span>
 
<span data-ttu-id="e44da-105">La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="e44da-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="e44da-106">Ogni record nella tabella rappresenta un pool.</span><span class="sxs-lookup"><span data-stu-id="e44da-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="e44da-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e44da-107">**Column**</span></span>|<span data-ttu-id="e44da-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e44da-108">**Data Type**</span></span>|<span data-ttu-id="e44da-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e44da-109">**Key/Index**</span></span>|<span data-ttu-id="e44da-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e44da-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e44da-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="e44da-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="e44da-112">int</span><span class="sxs-lookup"><span data-stu-id="e44da-112">int</span></span>  <br/> |<span data-ttu-id="e44da-113">Principale</span><span class="sxs-lookup"><span data-stu-id="e44da-113">Primary</span></span>  <br/> |<span data-ttu-id="e44da-114">Numero univoco che identifica questo pool.</span><span class="sxs-lookup"><span data-stu-id="e44da-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="e44da-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="e44da-115">**PoolName**</span></span> <br/> |<span data-ttu-id="e44da-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e44da-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e44da-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="e44da-117">Unique</span></span>  <br/> |<span data-ttu-id="e44da-118">FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="e44da-118">Pool FQDN.</span></span>  <br/> |
   

