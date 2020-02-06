---
title: Eseguire la migrazione dei telefoni di aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Skype for Business Server Management Shell si recupereranno prima tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposteremo questi oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813564"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="2f9ee-106">Eseguire la migrazione dei telefoni di aree comuni</span><span class="sxs-lookup"><span data-stu-id="2f9ee-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="2f9ee-107">I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="2f9ee-108">I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="2f9ee-109">Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="2f9ee-110">Usando Skype for Business Server Management Shell, in primo luogo recupererà tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposterà questi oggetti nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="2f9ee-111">Eseguire la migrazione dei telefoni di aree comuni</span><span class="sxs-lookup"><span data-stu-id="2f9ee-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="2f9ee-112">In Skype for Business Server 2019 front end server aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="2f9ee-113">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2f9ee-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="2f9ee-114">Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019, digitare quanto segue in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="2f9ee-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="2f9ee-115">Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2f9ee-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

