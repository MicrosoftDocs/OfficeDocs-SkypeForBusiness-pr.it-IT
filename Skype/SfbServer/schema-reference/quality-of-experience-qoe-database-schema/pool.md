---
title: Tabella Pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815816"
---
# <a name="pool-table"></a><span data-ttu-id="ab5b3-104">Tabella Pool</span><span class="sxs-lookup"><span data-stu-id="ab5b3-104">Pool table</span></span>
 
<span data-ttu-id="ab5b3-p102">La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.</span><span class="sxs-lookup"><span data-stu-id="ab5b3-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="ab5b3-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-107">**Column**</span></span>|<span data-ttu-id="ab5b3-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-108">**Data Type**</span></span>|<span data-ttu-id="ab5b3-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-109">**Key/Index**</span></span>|<span data-ttu-id="ab5b3-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab5b3-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="ab5b3-112">int</span><span class="sxs-lookup"><span data-stu-id="ab5b3-112">int</span></span>  <br/> |<span data-ttu-id="ab5b3-113">Principale</span><span class="sxs-lookup"><span data-stu-id="ab5b3-113">Primary</span></span>  <br/> |<span data-ttu-id="ab5b3-114">Numero univoco che identifica il pool.</span><span class="sxs-lookup"><span data-stu-id="ab5b3-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="ab5b3-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="ab5b3-115">**PoolName**</span></span> <br/> |<span data-ttu-id="ab5b3-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ab5b3-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ab5b3-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="ab5b3-117">Unique</span></span>  <br/> |<span data-ttu-id="ab5b3-118">Nome di dominio completo del pool.</span><span class="sxs-lookup"><span data-stu-id="ab5b3-118">Pool FQDN.</span></span>  <br/> |
   

