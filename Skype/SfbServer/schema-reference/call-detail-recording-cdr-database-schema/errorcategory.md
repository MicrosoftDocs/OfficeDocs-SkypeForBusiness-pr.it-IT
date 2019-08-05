---
title: Tabella ErrorCategory in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015. Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194811"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b9355-104">Tabella ErrorCategory in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9355-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9355-105">La tabella ErrorCategory contiene il nome descrittivo per ogni classificazione di diagnostica di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9355-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="b9355-106">Per impostazione predefinita, Skype for Business Server 2015 USA le classificazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9355-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="b9355-107">0--successo</span><span class="sxs-lookup"><span data-stu-id="b9355-107">0 -- Success</span></span>
    
- <span data-ttu-id="b9355-108">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="b9355-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="b9355-109">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="b9355-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="b9355-110">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9355-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b9355-111">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="b9355-111">**Column**</span></span>|<span data-ttu-id="b9355-112">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b9355-112">**Data Type**</span></span>|<span data-ttu-id="b9355-113">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="b9355-113">**Key/Index**</span></span>|<span data-ttu-id="b9355-114">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="b9355-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9355-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="b9355-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="b9355-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="b9355-116">tinyint</span></span>  <br/> |<span data-ttu-id="b9355-117">Principale</span><span class="sxs-lookup"><span data-stu-id="b9355-117">Primary</span></span>  <br/> |<span data-ttu-id="b9355-118">Identificatore univoco per la classificazione.</span><span class="sxs-lookup"><span data-stu-id="b9355-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="b9355-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b9355-119">**Name**</span></span> <br/> |<span data-ttu-id="b9355-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9355-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b9355-121">Valore e nome descrittivo assegnato alla classificazione.</span><span class="sxs-lookup"><span data-stu-id="b9355-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="b9355-122">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="b9355-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="b9355-123">0--successo</span><span class="sxs-lookup"><span data-stu-id="b9355-123">0 -- Success</span></span> <br/>  <span data-ttu-id="b9355-124">1-errore previsto</span><span class="sxs-lookup"><span data-stu-id="b9355-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="b9355-125">2-errore imprevisto</span><span class="sxs-lookup"><span data-stu-id="b9355-125">2 - Unexpected failure</span></span> <br/> |
   

