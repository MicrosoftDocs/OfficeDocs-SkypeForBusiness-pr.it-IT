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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190616"
---
# <a name="stop-cclogging"></a><span data-ttu-id="1efa7-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1efa7-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="1efa7-104">Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1efa7-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="1efa7-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="1efa7-105">Examples</span></span>
<span data-ttu-id="1efa7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1efa7-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="1efa7-107">Example 1</span></span>

<span data-ttu-id="1efa7-108">L'esempio seguente interrompe la generazione del log delle chiamate in entrata e in uscita:</span><span class="sxs-lookup"><span data-stu-id="1efa7-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="1efa7-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="1efa7-109">Example 2</span></span>

<span data-ttu-id="1efa7-110">L'esempio seguente smette di generare il log delle chiamate in entrata e in uscita e pulisce i file della cache:</span><span class="sxs-lookup"><span data-stu-id="1efa7-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="1efa7-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="1efa7-111">Detailed Description</span></span>
<span data-ttu-id="1efa7-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-112"></span></span>

<span data-ttu-id="1efa7-113">Il cmdlet Stop-CcLogging interrompe la registrazione delle chiamate in entrata e in uscita in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1efa7-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="1efa7-114">Per impostazione predefinita, la registrazione si arresta automaticamente dopo quattro ore.</span><span class="sxs-lookup"><span data-stu-id="1efa7-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1efa7-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="1efa7-115">Parameters</span></span>
<span data-ttu-id="1efa7-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-116"></span></span>

|<span data-ttu-id="1efa7-117">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="1efa7-117">**Parameter**</span></span>|<span data-ttu-id="1efa7-118">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="1efa7-118">**Required**</span></span>|<span data-ttu-id="1efa7-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1efa7-119">**Type**</span></span>|<span data-ttu-id="1efa7-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1efa7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1efa7-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="1efa7-121">RemoveCache</span></span> <br/> | <span data-ttu-id="1efa7-122">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="1efa7-122">Optional</span></span> <br/> | <span data-ttu-id="1efa7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1efa7-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="1efa7-124">Rimuove i file della cache di registrazione.</span><span class="sxs-lookup"><span data-stu-id="1efa7-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1efa7-125">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="1efa7-125">Input Types</span></span>
<span data-ttu-id="1efa7-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-126"></span></span>

<span data-ttu-id="1efa7-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1efa7-127">None.</span></span> <span data-ttu-id="1efa7-128">Il cmdlet Stop-CcLogging non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="1efa7-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1efa7-129">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="1efa7-129">Return Types</span></span>
<span data-ttu-id="1efa7-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-130"></span></span>

<span data-ttu-id="1efa7-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1efa7-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1efa7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1efa7-132">See also</span></span>
<span data-ttu-id="1efa7-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1efa7-133"></span></span>

[<span data-ttu-id="1efa7-134">Ricerca-CcLog</span><span class="sxs-lookup"><span data-stu-id="1efa7-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="1efa7-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1efa7-135">Start-CcLogging</span></span>](start-cclogging.md)
  

