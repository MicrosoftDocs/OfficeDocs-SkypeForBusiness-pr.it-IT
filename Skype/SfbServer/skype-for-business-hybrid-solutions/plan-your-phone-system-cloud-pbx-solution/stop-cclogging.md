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
description: Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824160"
---
# <a name="stop-cclogging"></a><span data-ttu-id="9a36a-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="9a36a-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="9a36a-104">Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="9a36a-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="9a36a-105">Esempi</span><span class="sxs-lookup"><span data-stu-id="9a36a-105">Examples</span></span>
<span data-ttu-id="9a36a-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="9a36a-107">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="9a36a-107">Example 1</span></span>

<span data-ttu-id="9a36a-108">L'esempio seguente interrompe la generazione del log delle chiamate in entrata e in uscita:</span><span class="sxs-lookup"><span data-stu-id="9a36a-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="9a36a-109">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="9a36a-109">Example 2</span></span>

<span data-ttu-id="9a36a-110">L'esempio seguente smette di generare il log delle chiamate in entrata e in uscita e pulisce i file della cache:</span><span class="sxs-lookup"><span data-stu-id="9a36a-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="9a36a-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="9a36a-111">Detailed Description</span></span>
<span data-ttu-id="9a36a-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="9a36a-113">Il cmdlet Stop-CcLogging interrompe la registrazione delle chiamate in entrata e in uscita in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9a36a-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="9a36a-114">Per impostazione predefinita, la registrazione si arresta automaticamente dopo quattro ore.</span><span class="sxs-lookup"><span data-stu-id="9a36a-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="9a36a-115">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a36a-115">Parameters</span></span>
<span data-ttu-id="9a36a-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="9a36a-117">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="9a36a-117">**Parameter**</span></span>|<span data-ttu-id="9a36a-118">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="9a36a-118">**Required**</span></span>|<span data-ttu-id="9a36a-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9a36a-119">**Type**</span></span>|<span data-ttu-id="9a36a-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9a36a-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="9a36a-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="9a36a-121">RemoveCache</span></span> <br/> | <span data-ttu-id="9a36a-122">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="9a36a-122">Optional</span></span> <br/> | <span data-ttu-id="9a36a-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="9a36a-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="9a36a-124">Rimuove i file della cache di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9a36a-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="9a36a-125">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="9a36a-125">Input Types</span></span>
<span data-ttu-id="9a36a-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="9a36a-127">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="9a36a-127">None.</span></span> <span data-ttu-id="9a36a-128">Il cmdlet Stop-CcLogging non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="9a36a-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="9a36a-129">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="9a36a-129">Return Types</span></span>
<span data-ttu-id="9a36a-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="9a36a-131">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9a36a-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a36a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a36a-132">See also</span></span>
<span data-ttu-id="9a36a-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="9a36a-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="9a36a-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="9a36a-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="9a36a-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="9a36a-135">Start-CcLogging</span></span>](start-cclogging.md)
  

