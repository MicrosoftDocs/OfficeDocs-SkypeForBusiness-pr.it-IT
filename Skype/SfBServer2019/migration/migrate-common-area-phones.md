---
title: Eseguire la migrazione dei telefoni delle aree comuni
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Skype for Business Server Management Shell si recupereranno prima tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposteremo questi oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: 123f0a73da65e7d661541c6c4bec65481bf12f0c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238704"
---
# <a name="migrate-common-area-phones"></a>Eseguire la migrazione dei telefoni delle aree comuni

I telefoni per l'area comune sono i telefoni IP che più spesso si trovano in un'area di lavoro condivisa o in uno spazio comune, ad esempio una sala d'attesa, una cucina o una fabbrica. I telefoni per l'area comune non devono essere connessi a un computer per ottenere la funzionalità UC (Unified Communications) di Skype for Business Server. Dopo la migrazione di una distribuzione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati al telefono dell'area comune legacy. Usando Skype for Business Server Management Shell, in primo luogo recupererà tutti gli oggetti contatto associati ai telefoni delle aree comuni legacy e quindi sposterà questi oggetti nel pool di Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Eseguire la migrazione dei telefoni delle aree comuni

1. In Skype for Business Server 2019 front end server aprire Skype for Business Server Management Shell.
    
2. Nella riga di comando digitare quanto segue:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Per verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019, digitare quanto segue in Skype for Business Server Management Shell:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.
    

