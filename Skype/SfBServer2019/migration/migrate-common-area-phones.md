---
title: Migrare i telefoni delle aree comuni
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità di comunicazioni unificate di Skype for Business Server. Dopo aver eseguito la migrazione di una distribuzione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono dell'area comune legacy. Utilizzando Skype for Business Server Management Shell, verranno prima recuperati tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi spostati nel pool di Skype for Business Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752708"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="9ed1a-106">Migrare i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="9ed1a-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="9ed1a-107">I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="9ed1a-108">Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità di comunicazioni unificate di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="9ed1a-109">Dopo aver eseguito la migrazione di una distribuzione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono dell'area comune legacy.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="9ed1a-110">Utilizzando Skype for Business Server Management Shell, si recuperano prima tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi si spostano tali oggetti nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="9ed1a-111">Migrare i telefoni delle aree comuni</span><span class="sxs-lookup"><span data-stu-id="9ed1a-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="9ed1a-112">Da Skype for Business Server 2019 Front End Server, aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="9ed1a-113">Dalla riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ed1a-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="9ed1a-114">Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019, da Skype for Business Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ed1a-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="9ed1a-115">Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9ed1a-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

