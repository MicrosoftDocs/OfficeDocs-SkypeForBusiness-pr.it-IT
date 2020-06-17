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
description: I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo aver eseguito la migrazione di una distribuzione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono di area comune legacy. Usando Skype for Business Server Management Shell, per prima cosa è necessario recuperare tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752708"
---
# <a name="migrate-common-area-phones"></a>Migrare i telefoni delle aree comuni

I telefoni delle aree comuni sono telefoni IP che molto spesso risiedono in un'area di lavoro condivisa o area comune, ad esempio una sala di attesa, una cucina o un reparto produzione. Non è necessario che i telefoni delle aree comuni siano connessi a un computer per fornire la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo aver eseguito la migrazione di una distribuzione a Skype for Business Server 2019, è necessario eseguire la migrazione anche degli oggetti contatto associati al telefono di area comune legacy. Usando Skype for Business Server Management Shell, per prima cosa è necessario recuperare tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrare i telefoni delle aree comuni

1. Da Skype for Business Server 2019 front end server, aprire Skype for Business Server Management Shell.
    
2. Dalla riga di comando digitare quanto segue:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019, in Skype for Business Server Management Shell digitare quanto segue:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verificare che tutti gli oggetti contatto siano ora associati al pool Skype for Business Server 2019.
    

