---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Il cmdlet Start-CcLogging genera il registro chiamate in ingresso e in uscita per un dispositivo Skype for Business Cloud Connector Edition.
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824170"
---
# <a name="start-cclogging"></a><span data-ttu-id="d3e2c-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="d3e2c-103">Start-CcLogging</span></span>
 
<span data-ttu-id="d3e2c-104">Il cmdlet Start-CcLogging genera il registro chiamate in ingresso e in uscita per un dispositivo Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="d3e2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3e2c-105">Parameters</span></span>

<span data-ttu-id="d3e2c-106">None</span><span class="sxs-lookup"><span data-stu-id="d3e2c-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d3e2c-107">Esempi</span><span class="sxs-lookup"><span data-stu-id="d3e2c-107">Examples</span></span>
<span data-ttu-id="d3e2c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d3e2c-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d3e2c-109">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d3e2c-109">Example 1</span></span>

<span data-ttu-id="d3e2c-110">Nell'esempio seguente viene generato il registro chiamate in ingresso e in uscita:</span><span class="sxs-lookup"><span data-stu-id="d3e2c-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="d3e2c-111">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="d3e2c-111">Detailed Description</span></span>
<span data-ttu-id="d3e2c-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d3e2c-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d3e2c-113">Il cmdlet Start-CcLogging consente agli amministratori di iniziare a registrare le chiamate in arrivo e in uscita su un dispositivo Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="d3e2c-114">Per impostazione predefinita, la registrazione viene interrotta automaticamente dopo quattro ore.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d3e2c-115">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="d3e2c-115">Input Types</span></span>
<span data-ttu-id="d3e2c-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d3e2c-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d3e2c-117">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-117">None.</span></span> <span data-ttu-id="d3e2c-118">Il cmdlet Start-CcLogging non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d3e2c-119">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="d3e2c-119">Return Types</span></span>
<span data-ttu-id="d3e2c-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d3e2c-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d3e2c-121">None</span><span class="sxs-lookup"><span data-stu-id="d3e2c-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3e2c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e2c-122">See also</span></span>
<span data-ttu-id="d3e2c-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d3e2c-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d3e2c-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="d3e2c-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="d3e2c-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="d3e2c-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

