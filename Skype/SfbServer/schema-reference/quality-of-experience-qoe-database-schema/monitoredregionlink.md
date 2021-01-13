---
title: Tabella MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806346"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="887c1-104">Tabella MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="887c1-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="887c1-p102">La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi.</span><span class="sxs-lookup"><span data-stu-id="887c1-p102">The MonitoredRegionLink table is a supporting table. Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="887c1-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="887c1-107">**Column**</span></span>|<span data-ttu-id="887c1-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="887c1-108">**Data Type**</span></span>|<span data-ttu-id="887c1-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="887c1-109">**Key/Index**</span></span>|<span data-ttu-id="887c1-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="887c1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="887c1-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="887c1-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="887c1-112">int</span><span class="sxs-lookup"><span data-stu-id="887c1-112">int</span></span>  <br/> |<span data-ttu-id="887c1-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="887c1-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="887c1-114">A cui viene fatto riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="887c1-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="887c1-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="887c1-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="887c1-116">int</span><span class="sxs-lookup"><span data-stu-id="887c1-116">int</span></span>  <br/> |<span data-ttu-id="887c1-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="887c1-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="887c1-118">A cui viene fatto riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="887c1-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

