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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabella MonitoredRegionLink è una tabella di supporto. Ogni record rappresenta un collegamento tra due paesi/aree geografiche.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194608"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="07d41-104">Tabella MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="07d41-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="07d41-105">La tabella MonitoredRegionLink è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="07d41-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="07d41-106">Ogni record rappresenta un collegamento tra due paesi/aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="07d41-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="07d41-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="07d41-107">**Column**</span></span>|<span data-ttu-id="07d41-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="07d41-108">**Data Type**</span></span>|<span data-ttu-id="07d41-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="07d41-109">**Key/Index**</span></span>|<span data-ttu-id="07d41-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="07d41-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07d41-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="07d41-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="07d41-112">int</span><span class="sxs-lookup"><span data-stu-id="07d41-112">int</span></span>  <br/> |<span data-ttu-id="07d41-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="07d41-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07d41-114">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="07d41-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="07d41-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="07d41-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="07d41-116">int</span><span class="sxs-lookup"><span data-stu-id="07d41-116">int</span></span>  <br/> |<span data-ttu-id="07d41-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="07d41-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07d41-118">A cui si fa riferimento dalla [tabella Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="07d41-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

