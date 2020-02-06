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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807404"
---
# <a name="pool-table"></a><span data-ttu-id="7a1bd-104">Tabella Pool</span><span class="sxs-lookup"><span data-stu-id="7a1bd-104">Pool table</span></span>
 
<span data-ttu-id="7a1bd-105">La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="7a1bd-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="7a1bd-106">Ogni record nella tabella rappresenta un pool.</span><span class="sxs-lookup"><span data-stu-id="7a1bd-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="7a1bd-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-107">**Column**</span></span>|<span data-ttu-id="7a1bd-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-108">**Data Type**</span></span>|<span data-ttu-id="7a1bd-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-109">**Key/Index**</span></span>|<span data-ttu-id="7a1bd-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a1bd-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="7a1bd-112">int</span><span class="sxs-lookup"><span data-stu-id="7a1bd-112">int</span></span>  <br/> |<span data-ttu-id="7a1bd-113">Principale</span><span class="sxs-lookup"><span data-stu-id="7a1bd-113">Primary</span></span>  <br/> |<span data-ttu-id="7a1bd-114">Numero univoco che identifica questo pool.</span><span class="sxs-lookup"><span data-stu-id="7a1bd-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="7a1bd-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7a1bd-115">**PoolName**</span></span> <br/> |<span data-ttu-id="7a1bd-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7a1bd-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7a1bd-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="7a1bd-117">Unique</span></span>  <br/> |<span data-ttu-id="7a1bd-118">FQDN del pool.</span><span class="sxs-lookup"><span data-stu-id="7a1bd-118">Pool FQDN.</span></span>  <br/> |
   

