---
title: Tabella AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta una sola origine.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194643"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="6367d-104">Tabella AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="6367d-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="6367d-105">La tabella AppliedBandwidthSource è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="6367d-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="6367d-106">Ogni record rappresenta una sola origine.</span><span class="sxs-lookup"><span data-stu-id="6367d-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="6367d-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6367d-107">**Column**</span></span>|<span data-ttu-id="6367d-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="6367d-108">**Data Type**</span></span>|<span data-ttu-id="6367d-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="6367d-109">**Key/Index**</span></span>|<span data-ttu-id="6367d-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="6367d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6367d-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="6367d-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="6367d-112">int</span><span class="sxs-lookup"><span data-stu-id="6367d-112">int</span></span>  <br/> |<span data-ttu-id="6367d-113">Principale</span><span class="sxs-lookup"><span data-stu-id="6367d-113">Primary</span></span>  <br/> |<span data-ttu-id="6367d-114">Numero univoco che identifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="6367d-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="6367d-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="6367d-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="6367d-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="6367d-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="6367d-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="6367d-117">Unique</span></span>  <br/> |<span data-ttu-id="6367d-118">Questa è l'origine del limite di larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="6367d-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="6367d-119">Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".</span><span class="sxs-lookup"><span data-stu-id="6367d-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

