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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801766"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="ed190-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="ed190-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="ed190-104">Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="ed190-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="ed190-105">Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ed190-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="ed190-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed190-106">Parameters</span></span>

<span data-ttu-id="ed190-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ed190-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ed190-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="ed190-108">Examples</span></span>
<span data-ttu-id="ed190-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed190-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ed190-110">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ed190-110">Example 1</span></span>

<span data-ttu-id="ed190-111">Il comando seguente inserisce l'appliance in cui viene eseguito di nuovo in modalità di produzione:</span><span class="sxs-lookup"><span data-stu-id="ed190-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="ed190-112">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="ed190-112">Detailed Description</span></span>
<span data-ttu-id="ed190-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ed190-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ed190-114">Se si dispone di appliance inserite in modalità di manutenzione specificando il cmdlet Enter-CcUpdate, il cmdlet Exit-CcUpdate li riporterà in modalità di produzione.</span><span class="sxs-lookup"><span data-stu-id="ed190-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="ed190-115">Per altre informazioni su come inserire gli apparecchi in modalità di manutenzione, vedere Invio-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="ed190-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="ed190-116">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="ed190-116">Input Types</span></span>
<span data-ttu-id="ed190-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed190-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ed190-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="ed190-118">None.</span></span> <span data-ttu-id="ed190-119">Il cmdlet Exit-CcUpdate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="ed190-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ed190-120">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="ed190-120">Return Types</span></span>
<span data-ttu-id="ed190-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed190-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ed190-122">Nessuno</span><span class="sxs-lookup"><span data-stu-id="ed190-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed190-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed190-123">See also</span></span>
<span data-ttu-id="ed190-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed190-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="ed190-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="ed190-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

