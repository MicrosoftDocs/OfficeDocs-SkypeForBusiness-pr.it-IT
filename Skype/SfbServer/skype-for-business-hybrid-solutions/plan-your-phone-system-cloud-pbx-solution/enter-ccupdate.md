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
description: Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento attivando la modalità di manutenzione. L'applicazione arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802176"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="e9232-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9232-104">Enter-CcUpdate</span></span>

<span data-ttu-id="e9232-105">Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento attivando la modalità di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e9232-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="e9232-106">L'applicazione arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.</span><span class="sxs-lookup"><span data-stu-id="e9232-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="e9232-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9232-107">Parameters</span></span>

<span data-ttu-id="e9232-108">None</span><span class="sxs-lookup"><span data-stu-id="e9232-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e9232-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="e9232-109">Examples</span></span>
<span data-ttu-id="e9232-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e9232-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="e9232-111">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="e9232-111">Example 1</span></span>

<span data-ttu-id="e9232-112">Nell'esempio seguente viene preparato l'applicazione per il processo di aggiornamento attivando la modalità di manutenzione:</span><span class="sxs-lookup"><span data-stu-id="e9232-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="e9232-113">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="e9232-113">Detailed Description</span></span>
<span data-ttu-id="e9232-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e9232-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="e9232-115">Il cmdlet Enter-CcUpdate arresta immediatamente tutti i servizi che terminano le chiamate in corso e l'applicazione rifiuterà le nuove chiamate, trasferite ad altre appliance di produzione.</span><span class="sxs-lookup"><span data-stu-id="e9232-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="e9232-116">È necessario verificare che gli appliance di produzione rimanenti siano in grado di gestire le chiamate dall'appliance che si sta preparando per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e9232-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="e9232-117">La modalità manutenzione è utile, ad esempio, se l'applicazione dispone dell'aggiornamento automatico abilitato e Microsoft rilascia un hotfix critico.</span><span class="sxs-lookup"><span data-stu-id="e9232-117">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix.</span></span> <span data-ttu-id="e9232-118">La modalità manutenzione è utile anche se decidi di disattivare gli aggiornamenti automatici, ma esegui gli aggiornamenti manuali su base coerente.</span><span class="sxs-lookup"><span data-stu-id="e9232-118">Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="e9232-119">Dopo aver installato gli aggiornamenti, il dispositivo può essere riportato in modalità di produzione eseguendo il cmdlet Exit-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="e9232-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9232-120">Se si decide di aggiornare manualmente un'applicazione Cloud Connector, è necessario aggiornarla entro 60 giorni dal rilascio della versione successiva da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e9232-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="e9232-121">Microsoft supporta la versione rilasciata in precedenza di Cloud Connector per 60 giorni dopo il rilascio della nuova versione</span><span class="sxs-lookup"><span data-stu-id="e9232-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="e9232-122">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="e9232-122">Input Types</span></span>
<span data-ttu-id="e9232-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9232-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="e9232-124">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="e9232-124">None.</span></span> <span data-ttu-id="e9232-125">Il cmdlet Enter-CCUpdate non accetta input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="e9232-125">The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e9232-126">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="e9232-126">Return Types</span></span>
<span data-ttu-id="e9232-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9232-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="e9232-128">None</span><span class="sxs-lookup"><span data-stu-id="e9232-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e9232-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9232-129">See also</span></span>
<span data-ttu-id="e9232-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e9232-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="e9232-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="e9232-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

