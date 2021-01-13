---
title: Tabella AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831406"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="47b2d-104">Tabella AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="47b2d-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="47b2d-p102">La tabella AppliedBandwidthSource è una tabella di supporto. Ogni record rappresenta un'origine.</span><span class="sxs-lookup"><span data-stu-id="47b2d-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="47b2d-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="47b2d-107">**Column**</span></span>|<span data-ttu-id="47b2d-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="47b2d-108">**Data Type**</span></span>|<span data-ttu-id="47b2d-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="47b2d-109">**Key/Index**</span></span>|<span data-ttu-id="47b2d-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="47b2d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47b2d-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="47b2d-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="47b2d-112">int</span><span class="sxs-lookup"><span data-stu-id="47b2d-112">int</span></span>  <br/> |<span data-ttu-id="47b2d-113">Principale</span><span class="sxs-lookup"><span data-stu-id="47b2d-113">Primary</span></span>  <br/> |<span data-ttu-id="47b2d-114">Numero univoco che identifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="47b2d-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="47b2d-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="47b2d-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="47b2d-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="47b2d-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="47b2d-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="47b2d-117">Unique</span></span>  <br/> |<span data-ttu-id="47b2d-118">Origine del limite della larghezza di banda imposto.</span><span class="sxs-lookup"><span data-stu-id="47b2d-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="47b2d-119">In questo articolo viene descritto il percorso del limite di larghezza di banda, ad esempio "server criteri", "Attiva server" o "modalità".</span><span class="sxs-lookup"><span data-stu-id="47b2d-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

