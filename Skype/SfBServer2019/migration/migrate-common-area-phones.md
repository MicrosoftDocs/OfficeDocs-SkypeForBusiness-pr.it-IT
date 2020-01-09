---
title: Eseguire la migrazione dei telefoni di aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Skype for Business Server Management Shell si recupereranno prima tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposteremo questi oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: f268c22f1d1132b3b5b8c1c1676e5b3a0182cf3f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991151"
---
# <a name="migrate-common-area-phones"></a>Eseguire la migrazione dei telefoni di aree comuni

I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Skype for Business Server Management Shell, in primo luogo recupererà tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposterà questi oggetti nel pool di Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Eseguire la migrazione dei telefoni di aree comuni

1. In Skype for Business Server 2019 front end server aprire Skype for Business Server Management Shell.
    
2. Nella riga di comando digitare quanto segue:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019, digitare quanto segue in Skype for Business Server Management Shell:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.
    

