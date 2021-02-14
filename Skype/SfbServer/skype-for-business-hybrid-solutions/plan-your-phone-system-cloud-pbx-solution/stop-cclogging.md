---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Il Stop-CcLogging cmdlet interrompe la generazione del registro chiamate in ingresso e in uscita per un'applicazione Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824160"
---
# <a name="stop-cclogging"></a><span data-ttu-id="3d0d9-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="3d0d9-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="3d0d9-104">Il Stop-CcLogging cmdlet interrompe la generazione del registro chiamate in ingresso e in uscita per un'applicazione Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="3d0d9-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="3d0d9-105">Examples</span></span>
<span data-ttu-id="3d0d9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="3d0d9-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3d0d9-107">Example 1</span></span>

<span data-ttu-id="3d0d9-108">Nell'esempio seguente viene interrotta la generazione del registro chiamate in ingresso e in uscita:</span><span class="sxs-lookup"><span data-stu-id="3d0d9-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="3d0d9-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="3d0d9-109">Example 2</span></span>

<span data-ttu-id="3d0d9-110">Nell'esempio seguente viene interrotta la generazione del registro chiamate in ingresso e in uscita e vengono puliti i file della cache:</span><span class="sxs-lookup"><span data-stu-id="3d0d9-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="3d0d9-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="3d0d9-111">Detailed Description</span></span>
<span data-ttu-id="3d0d9-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="3d0d9-113">Il Stop-CcLogging cmdlet interrompe la registrazione delle chiamate in ingresso e in uscita su un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="3d0d9-114">Per impostazione predefinita, la registrazione viene interrotta automaticamente dopo quattro ore.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3d0d9-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d0d9-115">Parameters</span></span>
<span data-ttu-id="3d0d9-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="3d0d9-117">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="3d0d9-117">**Parameter**</span></span>|<span data-ttu-id="3d0d9-118">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="3d0d9-118">**Required**</span></span>|<span data-ttu-id="3d0d9-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d0d9-119">**Type**</span></span>|<span data-ttu-id="3d0d9-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3d0d9-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3d0d9-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="3d0d9-121">RemoveCache</span></span> <br/> | <span data-ttu-id="3d0d9-122">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="3d0d9-122">Optional</span></span> <br/> | <span data-ttu-id="3d0d9-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3d0d9-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="3d0d9-124">Rimuove i file della cache di registrazione.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3d0d9-125">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="3d0d9-125">Input Types</span></span>
<span data-ttu-id="3d0d9-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="3d0d9-127">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-127">None.</span></span> <span data-ttu-id="3d0d9-128">Il cmdlet Stop-CcLogging non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="3d0d9-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3d0d9-129">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="3d0d9-129">Return Types</span></span>
<span data-ttu-id="3d0d9-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="3d0d9-131">None</span><span class="sxs-lookup"><span data-stu-id="3d0d9-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d0d9-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d0d9-132">See also</span></span>
<span data-ttu-id="3d0d9-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0d9-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="3d0d9-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="3d0d9-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="3d0d9-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="3d0d9-135">Start-CcLogging</span></span>](start-cclogging.md)
  

