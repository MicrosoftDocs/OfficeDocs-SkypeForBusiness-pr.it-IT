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
ms.localizationpriority: medium
description: I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire Skype for Business Server comunicazioni unificate. Dopo aver eseguito la migrazione di una distribuzione Skype for Business Server 2019, è inoltre necessario eseguire la migrazione degli oggetti contatto associati all'area comune legacy Telefono. Utilizzando Skype for Business Server Management Shell, verranno innanzitutto recuperati tutti gli oggetti contatto associati ai telefoni di area comune legacy e quindi spostati nel pool di Skype for Business Server 2019.
ms.openlocfilehash: dabb91925b2d5271ba2760f62dd962ed7fa7a24c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579530"
---
# <a name="migrate-common-area-phones"></a>Migrare i telefoni delle aree comuni

I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire Skype for Business Server comunicazioni unificate. Dopo aver eseguito la migrazione di una distribuzione Skype for Business Server 2019, è inoltre necessario eseguire la migrazione degli oggetti contatto associati all'area comune legacy Telefono. Utilizzando Skype for Business Server Management Shell, verranno innanzitutto recuperati tutti gli oggetti contatto associati ai telefoni dell'area comune legacy e quindi spostati nel pool di Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrare i telefoni delle aree comuni

1. Dal front-end Skype for Business Server 2019 aprire Skype for Business Server Management Shell.
    
2. Dalla riga di comando digitare quanto segue:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Per verificare che tutti gli oggetti contatto siano stati spostati nel pool Skype for Business Server 2019, da Skype for Business Server Management Shell digitare quanto segue:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verificare che tutti gli oggetti contatto siano ora associati al pool Skype for Business Server 2019.
    

