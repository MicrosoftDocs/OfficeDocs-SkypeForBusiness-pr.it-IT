---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190829"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="09393-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="09393-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="09393-104">Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="09393-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="09393-105">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="09393-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="09393-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="09393-106">Parameters</span></span>

<span data-ttu-id="09393-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="09393-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="09393-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="09393-108">Examples</span></span>
<span data-ttu-id="09393-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="09393-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="09393-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="09393-110">Example 1</span></span>

<span data-ttu-id="09393-111">Il comando seguente inserisce l'appliance in cui viene eseguito di nuovo in modalità di produzione:</span><span class="sxs-lookup"><span data-stu-id="09393-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="09393-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="09393-112">Detailed Description</span></span>
<span data-ttu-id="09393-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="09393-113"></span></span>

<span data-ttu-id="09393-114">Se si dispone di appliance inserite in modalità di manutenzione specificando il cmdlet Enter-CcUpdate, il cmdlet Exit-CcUpdate li riporterà in modalità di produzione.</span><span class="sxs-lookup"><span data-stu-id="09393-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="09393-115">Per altre informazioni su come inserire gli apparecchi in modalità di manutenzione, vedere Invio-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="09393-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="09393-116">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="09393-116">Input Types</span></span>
<span data-ttu-id="09393-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="09393-117"></span></span>

<span data-ttu-id="09393-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="09393-118">None.</span></span> <span data-ttu-id="09393-119">Il cmdlet Exit-CcUpdate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="09393-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="09393-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="09393-120">Return Types</span></span>
<span data-ttu-id="09393-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="09393-121"></span></span>

<span data-ttu-id="09393-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="09393-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="09393-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09393-123">See also</span></span>
<span data-ttu-id="09393-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="09393-124"></span></span>

[<span data-ttu-id="09393-125">Invio-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="09393-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

