---
title: Tabella MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi/aree geografiche.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807814"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="0bbe1-104">Tabella MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="0bbe1-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="0bbe1-105">La tabella MonitoredRegionLink è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="0bbe1-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="0bbe1-106">Ogni record rappresenta un collegamento tra due paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="0bbe1-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="0bbe1-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-107">**Column**</span></span>|<span data-ttu-id="0bbe1-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-108">**Data Type**</span></span>|<span data-ttu-id="0bbe1-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-109">**Key/Index**</span></span>|<span data-ttu-id="0bbe1-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0bbe1-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="0bbe1-112">int</span><span class="sxs-lookup"><span data-stu-id="0bbe1-112">int</span></span>  <br/> |<span data-ttu-id="0bbe1-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="0bbe1-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0bbe1-114">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="0bbe1-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="0bbe1-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="0bbe1-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="0bbe1-116">int</span><span class="sxs-lookup"><span data-stu-id="0bbe1-116">int</span></span>  <br/> |<span data-ttu-id="0bbe1-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="0bbe1-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0bbe1-118">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="0bbe1-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

