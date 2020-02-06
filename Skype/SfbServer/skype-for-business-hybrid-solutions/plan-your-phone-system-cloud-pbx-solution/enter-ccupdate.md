---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Il cmdlet Enter-CcUpdate prepara il server host di Skype for Business Cloud Connector Edition per il processo di aggiornamento inserendolo in modalità di manutenzione. L'appliance arresta immediatamente tutti i servizi, terminando qualsiasi chiamata in corso e rifiutando le nuove chiamate.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802176"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="d99a4-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="d99a4-104">Enter-CcUpdate</span></span>

<span data-ttu-id="d99a4-105">Il cmdlet Enter-CcUpdate prepara il server host di Skype for Business Cloud Connector Edition per il processo di aggiornamento inserendolo in modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="d99a4-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="d99a4-106">L'appliance arresta immediatamente tutti i servizi, terminando qualsiasi chiamata in corso e rifiutando le nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="d99a4-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="d99a4-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="d99a4-107">Parameters</span></span>

<span data-ttu-id="d99a4-108">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d99a4-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d99a4-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="d99a4-109">Examples</span></span>
<span data-ttu-id="d99a4-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d99a4-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d99a4-111">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="d99a4-111">Example 1</span></span>

<span data-ttu-id="d99a4-112">L'esempio seguente prepara l'appliance per il processo di aggiornamento immettendo la modalità di manutenzione:</span><span class="sxs-lookup"><span data-stu-id="d99a4-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="d99a4-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="d99a4-113">Detailed Description</span></span>
<span data-ttu-id="d99a4-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d99a4-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d99a4-115">Il cmdlet Enter-CcUpdate arresta immediatamente tutti i servizi che terminano le chiamate in corso e l'appliance respinge le nuove chiamate, che vengono trasferite ad altri apparecchi di produzione.</span><span class="sxs-lookup"><span data-stu-id="d99a4-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="d99a4-116">È necessario assicurarsi che gli apparecchi di produzione rimanenti abbiano una capacità sufficiente per gestire le chiamate dall'appliance che si sta preparando per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d99a4-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="d99a4-117">La modalità di manutenzione è utile se l'accessorio è abilitato per l'aggiornamento automatico, ad esempio, e Microsoft rilascia un hotfix critico.</span><span class="sxs-lookup"><span data-stu-id="d99a4-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="d99a4-118">La modalità di manutenzione è utile anche se si decide di disattivare gli aggiornamenti automatici, ma si eseguono aggiornamenti manuali su base coerente.</span><span class="sxs-lookup"><span data-stu-id="d99a4-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="d99a4-119">Dopo l'installazione degli aggiornamenti, l'appliance può essere riportata in modalità di produzione eseguendo il cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="d99a4-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d99a4-120">Se si decide di aggiornare manualmente un dispositivo Cloud Connector, è necessario aggiornarlo entro 60 giorni dopo che Microsoft rilascia la versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d99a4-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="d99a4-121">Microsoft supporta la versione rilasciata in precedenza di Cloud Connector per 60 giorni dopo il rilascio della nuova versione</span><span class="sxs-lookup"><span data-stu-id="d99a4-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="d99a4-122">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="d99a4-122">Input Types</span></span>
<span data-ttu-id="d99a4-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d99a4-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d99a4-124">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d99a4-124">None.</span></span> <span data-ttu-id="d99a4-125">Il cmdlet Enter-CCUpdate non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="d99a4-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d99a4-126">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="d99a4-126">Return Types</span></span>
<span data-ttu-id="d99a4-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d99a4-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d99a4-128">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d99a4-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d99a4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d99a4-129">See also</span></span>
<span data-ttu-id="d99a4-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d99a4-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d99a4-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="d99a4-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

